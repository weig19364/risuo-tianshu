# 🪐 Riso-Tianshu-Hybrid（天枢混合全息引擎 · 公式美学版）

本项目属于天枢系统的混合全息核心，其根本任务在于将**刘教授公式美学**（高精历算矩阵）与天枢核心算法进行全息熔炼。通过对黄赤交角、均时差及定气对冲数据的毫秒级解算，最终产出具备完全独立算力的完全体系统 `index.html`，实现天象、法理与数字基础设施的大一统一体化网络。

## 🌐 线上边缘静态部署（GitHub Pages）

本项目已完全对齐现代前端静态托管标准，构建产物死锁根目录默认路由 `index.html`。

全球边缘网络节点消费入口（直接访问顶级域名即可秒级加载算力层）：
```text
[https://weig19364.github.io/Riso-Tianshu-Hybrid/](https://weig19364.github.io/Riso-Tianshu-Hybrid/)

🏛️ 核心算法理法：刘梭天文历法历表数学模型系统摒弃了传统术数粗糙的固定查表法，在底层构建了以下四个核心算力阶段：阶段一：时空基准锚定系统建立以当前流年 $y$ 为基准的绝对力学时与地球自转长期摩擦修正轴。年首绝对儒略日（JD）基准：$$jd_0 = \text{getJD}(y-1, 12, 31) - \frac{1}{3}$$长效自转摩擦修正（Meeus $\Delta T$）：以 $J2000.0$ 起算的儒略世纪数 $T$ 补偿自转减速引起的代差：$$T = \frac{jd_0 - 2451545 + 182.625}{36525}$$$$\Delta T = \Phi(T) \quad (\text{秒})$$解析时间长轴自变量 $L_s$：设第 $i$ 个节气的索引为 $i$（$0 \le i \le 23$），引入均值步长（每步 $15.2184$ 天）作为轨道位置的平黄经代理自变量：$$L_s = (y - 2000) + \frac{i + istart}{24.0}$$阶段二：轨道非线性解析算子（Analytical Engine）纯数学级数拟合，用于快速拟合出一条无限接近 JPL 真实轨道的非线性平滑曲线。多项式基础回归（岁差与长周期摄动）：$$offset = 2451545 - jd_0 - \frac{\Delta T}{86400}$$$$s_{\text{poly}} = g.\text{poly}[0] + offset + L_s \cdot \left(g.\text{poly}[1] + L_s \cdot \left(g.\text{poly}[2] + L_s \cdot g.\text{poly}[3]\right)\right)$$8项主要天体非线性引力场震荡修正：$$s_{\text{periodic}} = \sum_{j=0}^{7} g.\text{amp}[j] \cdot \sin\left( \left(w[j] \cdot L_s \pmod{2\pi}\right) + g.\text{ph}[j] \right)$$完整解析天数估值：$$s = s_{\text{poly}} + s_{\text{periodic}}$$阶段三：🎛️ 1441 隔离进制编码与残差融合刘教授的核心艺术——时空互换残差编码，将纯数理算不准的引力微调值与公式进行合流。解析分钟数与整天天数的分离编码：$$s_1 = \lfloor (s - \lfloor s \rfloor) \times 1440 + 0.5 \rfloor$$数学转换为带溢出隔离槽的整型 Moment：$$M_{\text{analytical}} = s_1 + 1441 \times \lfloor s \rfloor$$物理残差场注入（LUT 补正）：通过线性叠加从密文表中解密出的分钟微调残差 $\delta_i = solar\_comp[i]$（区间为 $[-158, 97]$），求出分秒不差对齐 JPL 真实引力场的绝对 Moment 真值 $M_{\text{true}}$：$$M_{\text{true}} = M_{\text{analytical}} + \delta_i - O_{\text{comp}}$$阶段四：🔓 绝对时间流无损了解码（decompress_time）利用高阶模运算（Modulo）进行无视跨年、跨月边界的强行分流解码，一枪还原相对浮点天数 $t_{\text{final}}$：$$\text{Days} = \lfloor \frac{M_{\text{true}}}{1441} \rfloor$$$$\text{Minutes} = M_{\text{true}} \pmod{1441}$$$$\text{Final Day Output:} \quad t_{\text{final}} = \text{Days} + \frac{\text{Minutes}}{1440}$$📝 刘教授的公式美学真谛一句话概括其历算精髓：$$\text{JPL 绝对真值位置} = f_{\text{解析级数曲线}}(L_s) + \Delta_{\text{高密矩阵残差}}(\delta_i)$$传统公式法（如原生 VSOP2013）使用无限长的三角级数硬算逼近真值，属于高频三角函数的算力黑洞；而刘教授只用 8 项级数算出基础曲线 $f(L_s)$，把算不准的长尾余数，打包压缩为离线字节矩阵 $\Delta(\delta_i)$。在运行时直接通过整型加减法回填，既消灭了浮点开销，又实现了精度上的绝对统治。⚙️ 本地核心生产指令在本地 Zorin OS 硬件加密隔离工作站中，进入项目目录后执行以下极简闭环生产线：1. 物理环境注入Bashnpm install
2. 历算逻辑与理法本地回测Bashnode index.js
3. 公式美学矩阵编译（生成完全体单页资产）Bashnode build.js
执行后，将重新缝合 src/ 与 template.html，本地生成最新版 Tianshu_Hybrid_Single.html。🔒 硬件加密级运维安全提醒由于本项目涉及高精天文残差矩阵解算，在 HDD（机械硬盘）寻址运行编译时，请务必保持主机的物理静止，防止机械磁头划伤，并定期冷备至安全 NAS 中。
