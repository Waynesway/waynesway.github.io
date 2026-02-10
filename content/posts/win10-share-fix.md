title: "Win10 安装完之后不能访问共享的解决办法"
date: 2026-02-10T03:45:00+08:00
draft: false
tags: ["Windows", "Win10", "网络共享", "SMB"]
categories: ["技术折腾"]
cover:
    image: "/img/win10-share-fix.png"
    alt: "Windows 10 Network Sharing Fix"
    relative: false
---

这篇文章记录了 Windows 10 安装完成后无法访问网络共享的解决办法。

### 1. 打开 SMB 协议
在控制面板中启用 SMB 1.0/CIFS 文件共享支持。

路径：`控制面板\程序\程序和功能` -> `启用或关闭 Windows 功能` -> 勾选 `SMB 1.0/CIFS 文件共享支持`。

![SMB 设置](https://img.orzorg.eu.org/v2/RqWa1Fu.png)

### 2. 组策略中打开“启用不安全来宾登录”
如果对方共享没有设置密码，Win10 默认会拦截不安全的来宾登录。

**操作步骤：**
1. 按下 `Win + R`，输入 `gpedit.msc` 打开组策略编辑器。
2. 依次选择：`计算机配置` -> `管理模板` -> `网络` -> `Lanman 工作站`。
3. 在右侧找到 **“启用不安全的来宾登录”**，双击打开。
4. 选择 **“已启用”**，点击确定。

![组策略设置](https://lh3.googleusercontent.com/blogger_img_proxy/AEn0k_vLiyyCT9VIzSvbmhmYivZj3PMLMix60GrYzpzMQnjg5H3weicC4kEINT55v_PSbPq5FOahl5zWL8VzDaWlkJBT5dTleqByWXnL=s0-d)

---
*原文搬运自：风中散发 (fanguo.eu.org)*
