# DMIT VPS 使用全指南：从购买到流量管理的完整教程

DMIT 全新的管理后台 UI 设计让 VPS 管理变得更加便捷，无论是重装系统、设置 root 密码、上传密钥，还是查看流量计费、取消服务器续费都能轻松完成。本文将详细介绍购买后的各项管理操作。

## 一、DMIT 官网与账户管理
访问 DMIT 官网即可进入用户后台，所有 VPS 管理功能都集中在此处。

## 二、流量计费机制详解
DMIT 对 HKG.T1 和 SJC.T1 套餐实施了全新的流量计费策略，采用单向取最大值计算方式：

- 计量标准：仅统计 MAX(IN, OUT) 流量
- 数据转换：8/15 19:00 UTC 时取流量统计平均值
- 新统计方式：8/16 UTC 0 点后开始分别记录 IN/OUT 流量
- 显示更新：UI 界面将同步更新展示方式

**常见套餐计费方式对比：**
1. PVM.HKG.T1.STARTER：单向流量计费，超量降速
2. PVM.LAX.sPro.CREATOR：双向流量计费，超量暂停
3. pvm.hkg.pro：双向计费，超量暂停

👉 [【点击查看】2025年最新 DMIT 优惠码及特价云服务器方案汇总](https://bit.ly/dmit_coupon)

## 三、SSH 密钥登录与 Root 密码设置
### 密钥登录配置
参考官方文档获取详细指南。

### Root 密码设置方法
**重要提示：**
- 默认 Root 密码仅用于控制台访问
- 修改后需完成电源生命周期（关机→开机）才能生效
- 需修改 SSH 配置以允许 Root 密码登录

**Debian 11 系统设置教程：**
bash
passwd # 设置密码
sudo sed -i 's/^#\?PermitRootLogin.*/PermitRootLogin yes/g' /etc/ssh/sshd_config;
sudo sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication yes/g' /etc/ssh/sshd_config;
sudo service sshd restart
reboot # 重启服务器

**可视化修改方法：**
bash
sudo -i
passwd
nano /etc/ssh/sshd_config
# 修改以下参数：
PermitRootLogin yes
PasswordAuthentication yes
reboot

## 四、实用管理功能
### 1. 快照功能
DMIT 提供 1 个免费快照服务，可用于系统备份和恢复。

### 2. 系统重装
后台支持多种操作系统的一键重装，操作简单直观。

### 3. 账单续费
在账单管理页面可轻松完成续费操作，暂停的续费也可在此恢复。

## 五、洛杉矶 PVM.LAX.Pro 套餐优势
- **网络线路：**
  - 电信去程：GIA(AS4809)
  - 联通去程：直连 AS4837
  - 移动去程：香港移动(AS58453)
  - 三网回程：GIA(AS4809)