# Bark 通知发送器

一个简洁优雅的 Web 应用，用于向 iOS 设备发送 Bark 推送通知。支持多种通知格式和自定义选项。

## 功能特点

- 📱 完美适配移动端和桌面端
- 🎨 现代化渐变设计，界面美观
- 🔔 支持多种铃声选择（30+ 种内置铃声）
- 🖼️ 支持自定义图标和图片
- 🔗 支持点击通知跳转链接
- 📋 支持自动复制到剪贴板
- 📂 支持通知分组管理
- 💾 自动保存 Token 到浏览器 Cookie
- ⚡ 纯静态页面，无需后端服务器

## 快速开始

### 本地运行

1. 克隆或下载项目文件
2. 在项目目录下运行：
   ```bash
   npx serve .
   ```
3. 在浏览器中打开 `http://localhost:3000`

### 部署到 Vercel

1. 安装 Vercel CLI：
   ```bash
   npm install -g vercel
   ```

2. 在项目目录下运行：
   ```bash
   vercel
   ```

3. 或者直接通过 Vercel 网站部署：
   - 访问 [vercel.com](https://vercel.com)
   - 导入 Git 仓库或拖拽文件夹
   - 点击部署即可

### 部署到 Netlify

1. 安装 Netlify CLI：
   ```bash
   npm install -g netlify-cli
   ```

2. 在项目目录下运行：
   ```bash
   netlify deploy --prod
   ```

3. 或者通过 Netlify 网站部署：
   - 访问 [netlify.com](https://netlify.com)
   - 拖拽项目文件夹到部署区域
   - 自动部署完成

## 使用说明

### 基本使用

1. **输入接收方 Token**
   - 在 Bark App 中获取您的设备 Token
   - 输入到"接收方 Token"字段

2. **勾选"记住此 Token"**
   - Token 会保存在浏览器 Cookie 中
   - 下次访问时自动填充

3. **填写标题和内容**
   - 标题：通知的主标题
   - 内容：通知的详细内容

4. **配置高级选项（可选）**
   - **分组**：将通知归类到特定组
   - **跳转链接**：点击通知后打开的 URL
   - **图标 URL**：自定义通知图标
   - **复制文本**：指定要复制的文本
   - **铃声**：从 30+ 种铃声中选择
   - **自动复制**：接收时自动复制到剪贴板
   - **保存到历史**：是否归档到 Bark 历史记录

5. **点击发送**
   - 点击"发送通知"按钮
   - 等待发送结果提示

### Bark 服务器配置

项目默认使用的 Bark 服务器地址为：
```
https://bark.bj.noway.top:10997
```

如需修改，请编辑 `index.html` 文件中的 `BARK_URL` 常量：

```javascript
const BARK_URL = 'https://your-bark-server.com';
```

## 支持的铃声列表

- alarm（警报）
- bell（铃铛）
- birdsong（鸟鸣）
- bloom（绽放）
- calypso（卡里普索）
- chime（钟声）
- choo（火车）
- descent（下降）
- electronic（电子）
- fanfare（号角）
- glass（玻璃）
- gotosleep（入睡）
- healthnotification（健康）
- horn（喇叭）
- ladder（阶梯）
- mailsent（邮件已发送）
- minuet（小步舞曲）
- multiwayinvitation（多方邀请）
- newmail（新邮件）
- newsflash（快讯）
- noir（黑色）
- paymentsuccess（支付成功）
- shake（摇动）
- sherwoodforest（舍伍德森林）
- silence（静音）
- spell（咒语）
- suspense（悬念）
- telegraph（电报）
- tiptoes（踮脚）
- typewriters（打字机）
- update（更新）

## 技术栈

- HTML5
- CSS3（Flexbox、Grid、渐变）
- Vanilla JavaScript（ES6+）
- Bark Push API

## 浏览器兼容性

支持所有现代浏览器：
- Chrome / Edge（推荐）
- Safari
- Firefox
- 移动端浏览器

## 安全说明

- Token 仅保存在本地浏览器 Cookie 中
- 所有请求直接发送到 Bark 服务器
- 不经过任何第三方服务器
- 建议仅在个人设备上勾选"记住 Token"

## 常见问题

### 1. 发送失败怎么办？
- 检查 Token 是否正确
- 确认 Bark 服务器地址可访问
- 查看浏览器控制台的错误信息

### 2. Token 保存在哪里？
- 保存在浏览器 Cookie 中
- 仅在本地存储，不上传到服务器
- 清除浏览器数据会同时清除保存的 Token

### 3. 可以修改服务器地址吗？
- 可以，编辑 `index.html` 中的 `BARK_URL` 常量
- 修改后需要重新部署

## 许可证

MIT License

## 贡献

欢迎提交 Issue 和 Pull Request！

## 相关链接

- [Bark GitHub](https://github.com/Finb/Bark)
- [Bark 官方文档](https://bark.day.app/)
