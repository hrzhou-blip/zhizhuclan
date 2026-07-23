
## 知烛 · ZhiZhu

**A Local-First Genealogy Management System for Chinese Clans**

ZhiZhu is a privacy-first, fully offline family tree and clan management tool built specifically for Chinese genealogy. Unlike Western family tree software, ZhiZhu natively handles complex Chinese kinship structures—dual lineage adoption (过继), dual heirship (兼祧), matrilocal marriage (招婿入赘), and full female member records—as first-class data structures, not footnotes.

**Why ZhiZhu?**

Most genealogy tools either can't model Chinese clan relationships or force you to upload sensitive family data to the cloud. ZhiZhu does neither.

- **100% Local Storage** — All data stays on your computer. No account, no cloud, no registration. Your clan data is your family's private asset.
- **Built for Chinese Genealogy** — Native support for adoption, dual heirship, matrilocal marriage, and complete female lineage records. Every woman has a full name, origin, and story recorded.
- **3D Stellar Map** — Powered by Three.js and ngraph force-directed engine. Visualize your entire clan as an interactive galaxy. Each person is a star. 100,000 nodes tested.
- **Smart Zibei Management** — Multi-generation naming tables with automatic character assignment. No more manually fixing inconsistent generation names across branch submissions.
- **Multi-Clan Project Management** — One database file per clan. Manage multiple clans, branches, and lineages independently.
- **Universal Data Import** — Accepts data exported from any genealogy software. Auto-recognizes column names in Chinese and English variants.
- **Traditional & Simplified Chinese** — Full UI language switching for users across different regions.

**Tech Stack**

Python · PySide6 · SQLite3 · Three.js · ngraph · D3.js · Inno Setup

**License & Contact**

This is closed-source software with compiled code protection.

For inquiries or feedback, reach out via Zhihu or Baidu Tieba.

## 知烛宗族管理系统

**知所从来，烛照其往。**

一款专为中国宗族文化设计的纯本地化族谱管理软件。从几百人的小家谱到数十万人的大宗族，均能适用。


### 为什么做知烛

市面上不缺修谱软件，但缺一个真正理解中国宗族的工具。

国外软件不懂过继和兼祧，国内平台大多要把数据传到云端。族谱是家族最私密的东西——谁是谁的后代、葬在哪里、各房怎么分布——这些信息不应该放在别人的服务器上。

知烛的出发点很简单：**让族谱数据真正属于修谱人自己。** 不上云、不注册、不联网。数据存在你自己的电脑上，备份就靠拷贝，一百年后用任何数据库工具都能打开。


### 核心亮点

**复杂宗法关系原生支持**

过继双线展示、兼祧两房配偶各自归属、招婿入赘自动对齐——是数据层面的正式结构，不靠备注凑合。

**女性成员完整记录**

贯彻"凡有姓名，皆可入谱"。女儿有全名有去向，媳妇有娘家有来处。底层关系模型不预设世系必从父姓，天然兼容母系族谱修撰需求。

**繁简中文切换**

支持繁体中文与简体中文界面一键切换，适配不同地区华人的使用习惯。

**3D星系图**

基于 Three.js + ngraph 力导向引擎。环形初始布局，支持聚拢排序、星座连线、直系连线高亮。十万节点压测通过。布局计算与渲染解耦，离线预处理 + WebGL 在线渲染。根据硬件性能最高能渲染40万个节点。

**关系图谱**

基于 D3.js + Canvas 2D 渲染。支持按人员或分支探索，双击节点弹出人物卡。

**字辈自动管理**

多字辈表并行。各房表格导入时，系统自动根据世代推算统一用字，无需人工逐条核对。

**13条数据校验**

自动排查世代倒挂、生卒矛盾、重复录入、孤立人员等常见错误。支持批量修复与回滚撤销。

**多族谱分库管理**

一个族谱一个独立数据库文件。同时管理多个祠堂、多个分支，各自独立备份与迁移。

**兼容任意来源数据导入**

可接入任何族谱软件导出的数据。列名不管写成"父亲""爸爸""爹"还是"father"，系统自动识别。

**PDF电子家谱一键导出**

封面自定义，序言跋文可自撰。电子家谱零成本复制，发家族群人手一份。


### 快速开始

1. 下载安装包，双击安装
2. 无需注册、无需联网，打开即用
3. 导入你的族谱数据（Excel / CSV / GEDCOM 均可）
4. 开始修谱


### 技术栈

Python · PySide6 · SQLite3 · HTML / CSS / JavaScript · Three.js · Inno Setup

**技术参考**

星系图的设计借鉴了开源社区在大规模图可视化领域的探索成果：

力导向布局引擎采用 ngraph.forcelayout，解决了大规模节点聚拢时的重叠问题

底层图数据结构参考了 ngraph.graph

"星系"隐喻和 WebGL 渲染思路受到 anvaka 开源项目的启发

技术架构采用"离线预处理（计算布局）+ 在线渲染（WebGL）"的分离管线

在此基础上，针对中国宗族的多房系、多代际、过继兼祧双线展示等特殊需求做了定制化改造。


### 许可与联系

本项目为闭源软件，源码已进行编译保护。

如需帮助或反馈问题，可通过知乎、贴吧等渠道联系开发者。

微信：zhizhuclan
邮箱：zhizhuManager@163.com
