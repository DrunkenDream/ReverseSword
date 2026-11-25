# ReverseSword  逆向利刃  
# Q群：1137584564
ReverseSword（逆向利刃）​ 是一个面向安全研究与逆向分析的 Windows 内核级工具箱。它把所有常用操作收拢进一个可拖拽缩放、字号可调、可最小化到任务栏的 ImGui 透明覆盖层：进程、线程、窗口、模块全部以可调整列宽和行高的列表呈现，右键即可完成设目标、DUMP、保护 / 提权、隐藏 / 暂停 / 恢复、改父窗口与标题等操作；内存读写支持 MDL、CR3、附加、内核拷贝与 VM_隐藏多种通道，DUMP 按「进程名_dump.原后缀」自动命名；PDB 解析、文件保护 / 强删、机器信息（厂商 / 型号 / 虚拟化）一应俱全。

注入方面提供五种驱动级方式，并内置 Dumper-7，可直接将 1.6 MB 镜像按当前选中的方式内存注入目标进程，无需落盘、无需手动选择通讯方式——每次调用都现取当前最快可用通道。启动流程也经过打磨：先装驱动，再以 ImGui 模态窗显示使用协议（10 秒倒计时，拒绝即卸载驱动退出），协议期间窗口缩到弹窗大小、不露主界面背景；进入界面后只对自身进程和窗口施加一次驱动级保护。

提供将进程设置为调试器功能  完全重建Windows调试系统，可过绝大部分的反调试 

功能亮点\
界面：透明覆盖层、拖拽缩放与最小化、字号 / 风格可调、列宽与行高可调、面板默认折叠、标题栏实时时间、每次启动显示 ImGui 协议弹窗。
进程 / 线程 / 窗口 / 模块：八列进程表（进程名 / PID / 父PID / Peb / Cr3 / 架构 / 模块名 / 模块基址），可见行优先查询防卡顿；线程、窗口（含子窗口）、模块明细子表；右键覆盖设目标、复制、CR3、DUMP、保护 / 提权、调试器、改 PID、结束 / 隐藏 / 暂停 / 恢复、改父窗口与标题等。\
内存与文件：多通道内存读写、进程 / 模块内存 DUMP、内核内存、PDB 解析、文件保护与强删（需显式勾选允许）。\
注入：隐藏 / VMCALL / VMCALL劫持 / APC / RIP 五种方式，支持路径注入与内置 Dumper-7 内存注入，通讯方式随机择优。\
自保护与日志：界面首次出现时对自身进程 / 窗口执行一次驱动级保护；运行日志、记录表与驱动端保护 / 隐藏列表管理。\
机器信息：厂商 / 型号 / 虚拟化只在启动后查询一次，不重复通讯。\
声明：本项目仅供在合法授权范围内进行安全逆向技术交流，请勿用于任何非法行为。

# UI图如下：
# 进程列表  窗口|线程|模块信息展示 进程内存  内核内存  PDB解析  虚拟化级注入  加载驱动
<img width="1560" height="1348" alt="image" src="https://github.com/user-attachments/assets/5b79f259-3475-4cf6-927e-d3595cfadb6f" />
<img width="1567" height="1346" alt="image" src="https://github.com/user-attachments/assets/cbd6e587-ceab-410c-aca7-ae45e45edd30" />
<img width="1566" height="1351" alt="image" src="https://github.com/user-attachments/assets/c513447a-cb4f-441e-a945-29002b195565" />
<img width="1564" height="1351" alt="image" src="https://github.com/user-attachments/assets/996a6d90-ed02-4056-9b6e-6ea6e2425e44" />
<img width="1562" height="1349" alt="image" src="https://github.com/user-attachments/assets/8310ccb0-3dfb-49d4-b831-0fe176abd7b5" />

