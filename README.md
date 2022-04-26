# Embedded1-bare-machine-001-Openocd
Openocd Command
1. 暂停CPU
   halt
   只有先暂停CPU才能进行后续操作

2. 下载bin文件进入内存
   load_image xxx.bin：

============================================

3. help bp

4. 设置硬件断点
   bp address length hw：

5. 查看断点数：
   bp

6. 移除断点
   rbp addr

============================================

7. 连续运行
   resume [address] 恢复目标板的运行，如果指定了 address，则从 address 处开始运行
   resume 0：从0地址处运行

8. 单步运行
   step [address] 单步执行，如果指定了 address，则从 address 处开始执行一条指令
   step 0:从0地址处运行


9. 查看寄存器
   reg

============================================

10. 向addr地址处写入data
   mww addr data :
   mww 0 0x88888888

11. 读出addr地址处内容
   mdw addr:
   mdw 0

============================================

12. 设置软件断点
   bp address length
   bp 0x6c 4

13. 复位目标板
   reset 复位目标板

============================================
内存装载命令，注意:下载程序之前先使用“ halt” 命令暂停单板，才能下载代码；
如果使用“ poll” 命令发现单板的 MMU 或 D-cache 已经使能，则需要使用“ arm920t cp15 2 0” 、“ step”
两条命令禁止 MMU 和 D-cache
