# 雨云MCSM面板服教程：手把手教你搭建Minecraft Forge 1.20.2服务器

## 雨云游戏云核心优势

雨云面板服支持一键开服的主流游戏包括：
- Minecraft Java版/基岩版
- 泰拉瑞亚
- 饥荒
- 纯Java/Linux环境（Docker）

> **重点说明**：当前Minecraft Java版支持Arclight、Mohist等主流服务端，但Forge需通过纯Java环境手动搭建，本教程将详细讲解Forge 1.20.2服务端的搭建流程。

👉 [【点击查看】2025年最新雨云优惠码及特价云服务器方案汇总](https://bit.ly/RainYun)

## 硬件性能对比

### 专业级游戏云配置
- **CPU**：13900K 5.8Ghz / 5900X 4.8Ghz
- **内存**：DDR4高频内存
- **存储**：NVME SSD固态硬盘
- **网络**：BGP多线接入

## 服务模式解析

### VPS云服务器
- 基于KVM虚拟化技术
- 支持Windows/Linux系统
- 15个开放端口
- 完整root权限

### MCSM面板服
- 网页可视化操作
- 按天计费（最低0.5元/天）
- 自动备份功能
- 适合新手快速搭建

## Forge服务端搭建全流程

### 准备工作
1. 注册雨云账号
2. 购买MCSM面板服（选择纯Java环境）
3. 准备Forge安装包

### 详细步骤
1. **上传服务端**  
   通过文件管理功能上传Forge安装包（推荐1.20.2-48.0.30版本）

2. **配置启动参数**  
   修改`启动脚本(可修改).sh`文件：
   bash
   java -Xms128M -XX:MaxRAMPercentage=95.0 -jar forge-1.20.2-48.0.30-installer.jar --installServer
   

3. **安装服务端**  
   启动实例完成自动安装，出现`The server installed successfully`提示即安装成功

4. **修改运行配置**  
   编辑`run.sh`文件添加优化参数：
   bash
   -Dfile.encoding=UTF-8 -Duser.language=zh
   

5. **同意EULA协议**  
   修改`eula.txt`中`eula=false`为`eula=true`

6. **端口配置**  
   在`server.properties`中修改：
   properties
   server-port=你的专属端口号
   online-mode=false
   

## 客户端连接指南
1. 获取服务器地址（控制台显示）
2. 客户端添加服务器地址
3. 首次连接需等待资源加载

## 常见问题解决方案
- **安装失败**：使用预装库文件压缩包
- **内存不足**：调整Xmx参数
- **连接超时**：检查端口映射

> **专业提示**：高版本服务器建议选择4核8G及以上配置，动态计费模式可显著降低成本。

## Minecraft 1.20版本特性
- 新增樱花生物群系
- 考古学系统（可疑的沙砾）
- 锻造模板系统
- 嗅探兽等新生物

通过本教程，您已掌握在雨云平台搭建Forge服务器的完整流程。如需更多模组支持，可参考官方文档进行扩展配置。