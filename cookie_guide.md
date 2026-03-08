---
emoji: "🍪"
title: "小红书Cookie获取指南"
subtitle: "详细步骤，一看就会"
---

# 什么是小红书 Cookie？

Cookie 是网站存储在浏览器中的小型文本文件，包含了用户的登录状态和会话信息。在使用小红书自动发布工具时，需要配置 Cookie 来模拟登录状态。

## 为什么需要 Cookie？

- **自动发布**：使用脚本工具批量发布笔记
- **数据获取**：获取个人账号数据
- **自动化操作**：实现更多批量操作功能

# 📱 获取步骤（Chrome 浏览器）

## 第一步：登录小红书

1. 打开浏览器，访问 [小红书网页版](https://www.xiaohongshu.com)
2. 点击「登录」按钮
3. 使用手机小红书 APP 扫码登录
4. 确保登录成功并进入首页

## 第二步：打开开发者工具

- **Windows/Linux**：按 `F12` 键
- **Mac**：按 `Command + Option + I` 键
- 或者右键点击页面，选择「检查」

## 第三步：找到 Network 面板

1. 在开发者工具中，点击顶部的「Network」标签
2. 刷新页面（按 `F5` 或 `Command + R`）
3. 等待页面重新加载完成

## 第四步：复制 Cookie

1. 在 Network 面板中，找到任意一个请求（推荐选择第一个）
2. 点击该请求，展开详情
3. 在右侧面板中，找到「Request Headers」部分
4. 找到「Cookie」字段，点击旁边的「复制」按钮
5. 保存好复制的 Cookie 字符串

# 📝 配置 Cookie

## 创建 .env 文件

1. 复制示例文件：
   ```bash
   cp env.example.txt .env
   ```

2. 编辑 .env 文件：
   ```env
   XHS_COOKIE=你的Cookie字符串
   ```

## 验证配置

使用以下命令测试 Cookie 是否有效：
```bash
python scripts/publish_xhs.py --title "测试" --desc "测试发布" --images demos/auto-fit/cover.png --dry-run
```

# ⚠️ 注意事项

## 安全问题

- **不要分享**：Cookie 包含个人登录信息，不要分享给他人
- **不要上传**：不要将包含 Cookie 的文件上传到公开仓库
- **定期更新**：Cookie 有有效期，过期后需要重新获取

## 常见问题

### 1. Cookie 在哪里？
- 在 Network 面板的 Request Headers 中
- 是一长串文本，包含多个键值对

### 2. Cookie 过期了怎么办？
- 重新按照步骤获取新的 Cookie
- 更新 .env 文件中的 XHS_COOKIE 值

### 3. 获取 Cookie 会被封号吗？
- 正常获取和使用不会被封号
- 不要频繁使用同一 Cookie 进行大量操作

# 🔧 使用场景

## 自动发布笔记

```bash
python scripts/publish_xhs.py \
  --title "笔记标题" \
  --desc "笔记描述" \
  --images cover.png card_1.png
```

## 定时发布

```bash
python scripts/publish_xhs.py \
  --title "笔记标题" \
  --desc "笔记描述" \
  --images cover.png \
  --post-time "2026-03-01 19:00:00"
```

# 🎯 总结

获取小红书 Cookie 的步骤非常简单：

1. 登录小红书网页版
2. 打开开发者工具
3. 查看 Network 面板
4. 复制 Cookie 字符串
5. 配置到 .env 文件

有了 Cookie，你就可以使用自动化工具更高效地管理小红书内容了！

---

# 💡 小贴士

- **使用 Chrome 浏览器**：操作最简单
- **保存好 Cookie**：建议备份到安全的地方
- **定期更新**：每月更新一次 Cookie 以确保有效性
- **小心使用**：不要用于违规操作

# 🌟 相关工具

- **Auto-Redbook-Skills**：小红书自动发布工具
- **xhs**：小红书 API 客户端库
- **playwright**：浏览器自动化工具

---

# 📚 扩展阅读

- [小红书开发者文档](https://open.xiaohongshu.com)
- [浏览器 Cookie 知识](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Cookies)
- [网络请求分析教程](https://developer.chrome.com/docs/devtools/network/)

---

希望这篇指南对你有帮助！如果有任何问题，欢迎在评论区留言讨论。

# 标签

#小红书 #Cookie #自动化 #教程 #技术分享 #开发者工具 #网络技巧