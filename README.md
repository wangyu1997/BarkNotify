# Bark 通知发送器

一个功能完整的 Web 应用，用于向 iOS 设备发送 Bark 推送通知。支持 Bark 官方的所有通知格式和参数。

## 功能特点

### 核心功能
- 📱 完美适配移动端和桌面端响应式设计
- 🎨 现代化渐变 UI，界面美观易用
- 🔄 支持 GET 和 POST 两种请求方式
- 📝 支持三种通知格式（简单/带标题/完整）
- 💾 自动保存 Key 到浏览器本地存储

### 通知格式
1. **简单通知** - `/:key/:body`
   - 仅包含通知内容

2. **带标题通知** - `/:key/:title/:body`
   - 包含标题和内容（推荐）

3. **完整格式** - `/:key/:title/:subtitle/:body`
   - 包含标题、副标题和内容

### 功能参数
- **url** - 点击推送跳转的链接
- **group** - 推送消息分组
- **icon** - 自定义图标（仅 iOS 15+）
- **copy** - 自动复制到剪贴板的内容
- **ciphertext** - 推送加密密文
- **sound** - 30+ 种内置铃声可选
- **call** - 重复播放铃声 30 秒
- **level** - 时效性通知级别
  - `active` - 立即亮屏显示（默认）
  - `timeSensitive` - 时效性通知（专注模式可显示）
  - `passive` - 仅添加到通知列表
  - `critical` - 重要警告（忽略静音和勿扰）

## 快速开始

### 本地运行

1. 克隆或下载项目文件
2. 在项目目录下运行：
   ```bash
   npx serve .
   ```
3. 在浏览器中打开 `http://localhost:3000`

### 部署到 Vercel

#### 方法一：命令行部署
1. 安装 Vercel CLI：
   ```bash
   npm install -g vercel
   ```

2. 在项目目录下运行：
   ```bash
   vercel
   ```

#### 方法二：网站部署
1. 访问 [vercel.com](https://vercel.com)
2. 导入 Git 仓库或拖拽文件夹
3. 点击部署即可

### 部署到 Netlify

#### 方法一：命令行部署
1. 安装 Netlify CLI：
   ```bash
   npm install -g netlify-cli
   ```

2. 在项目目录下运行：
   ```bash
   netlify deploy --prod
   ```

#### 方法二：拖拽部署
1. 访问 [netlify.com](https://netlify.com)
2. 拖拽项目文件夹到部署区域
3. 自动部署完成

## 使用说明

### 基础配置

1. **输入设备 Key**
   - 在 Bark App 中查看你的设备 Key
   - 输入到"设备 Key (Token)"字段
   - 勾选"记住此 Key"可保存在本地

2. **选择请求方式**
   - GET：通过 URL 参数发送（默认）
   - POST：通过请求体发送（推荐用于长内容）

### 通知格式

根据需要选择合适的格式：

- **简单通知**：仅需要内容，无标题
- **带标题**：标题 + 内容（最常用）
- **完整格式**：标题 + 副标题 + 内容

每种格式会动态显示对应的输入框。

### 功能选项

所有功能参数都是可选的，根据需要填写：

- **跳转链接**：点击通知后打开的 URL
- **分组**：将通知归类到指定分组
- **图标**：自定义通知图标（iOS 15+）
- **自动复制**：收到通知时自动复制内容
- **加密密文**：发送加密的推送内容

### 铃声和提醒

- **铃声选择**：从 30+ 种内置铃声中选择
- **重复播放**：勾选后铃声会重复播放 30 秒
- **时效性通知**：设置通知的优先级
  - 时效性通知可在专注模式下显示
  - 重要警告会忽略静音和勿扰模式

### 发送通知

填写完成后，点击"发送通知"按钮：
- 发送成功会弹窗提示
- 发送失败会显示错误信息
- 立即可在 iOS 设备上收到推送

## Bark 服务器配置

项目默认使用的 Bark 服务器地址为：
```
https://bark.bj.noway.top:10997
```

### 修改服务器地址

如需使用其他 Bark 服务器，编辑 `index.html` 第 546 行：

```javascript
const BARK_URL = 'https://your-bark-server.com';
```

修改后重新部署即可。

## 支持的铃声列表

| 铃声名称 | 说明 | 铃声名称 | 说明 |
|---------|------|---------|------|
| alarm | 警报 | bell | 铃铛 |
| birdsong | 鸟鸣 | bloom | 绽放 |
| calypso | 卡里普索 | chime | 钟声 |
| choo | 火车 | descent | 下降 |
| electronic | 电子 | fanfare | 号角 |
| glass | 玻璃 | gotosleep | 入睡 |
| healthnotification | 健康 | horn | 喇叭 |
| ladder | 阶梯 | mailsent | 邮件已发 |
| minuet | 小步舞曲 | multiwayinvitation | 多方邀请 |
| newmail | 新邮件 | newsflash | 快讯 |
| noir | 黑色 | paymentsuccess | 支付成功 |
| shake | 摇动 | sherwoodforest | 森林 |
| silence | 静音 | spell | 咒语 |
| suspense | 悬念 | telegraph | 电报 |
| tiptoes | 踮脚 | typewriters | 打字机 |
| update | 更新 | - | - |

## 技术栈

- **前端**：HTML5 + CSS3 + Vanilla JavaScript
- **样式**：Flexbox + Grid + 渐变设计
- **请求**：Fetch API（支持 GET/POST）
- **存储**：浏览器 Cookie
- **API**：Bark Push API

## 浏览器兼容性

支持所有现代浏览器：
- ✅ Chrome / Edge（推荐）
- ✅ Safari（iOS 和 macOS）
- ✅ Firefox
- ✅ 移动端浏览器

## 安全说明

- Key 仅保存在本地浏览器 Cookie 中
- 所有请求直接发送到 Bark 服务器
- 不经过任何第三方服务器
- 建议仅在个人设备上勾选"记住 Key"
- 清除浏览器数据会同时清除保存的 Key

## 常见问题

### 1. 发送失败怎么办？

**可能原因：**
- Key 输入错误
- Bark 服务器地址不可访问
- 网络连接问题

**解决方法：**
- 检查 Key 是否正确（在 Bark App 中确认）
- 测试服务器地址是否可以访问
- 检查浏览器控制台的错误信息
- 尝试切换 GET/POST 请求方式

### 2. Key 保存在哪里？

- 保存在浏览器 Cookie 中
- 有效期为 365 天
- 仅在本地存储，不上传到服务器
- 清除浏览器数据会同时清除保存的 Key

### 3. 可以修改服务器地址吗？

可以！编辑 `index.html` 中的 `BARK_URL` 常量：

```javascript
const BARK_URL = 'https://your-bark-server.com';
```

修改后需要重新部署。

### 4. GET 和 POST 有什么区别？

- **GET**：参数在 URL 中，适合简短内容
- **POST**：参数在请求体中，适合长内容和特殊字符

推荐使用 POST 方式发送包含特殊字符或较长的内容。

### 5. 时效性通知有什么用？

- **active**：默认方式，立即亮屏提醒
- **timeSensitive**：在专注模式下也能显示
- **passive**：不亮屏，仅添加到通知中心
- **critical**：重要警告，忽略所有静音设置

## 项目结构

```
bark/
├── index.html          # 主页面（包含 HTML/CSS/JS）
├── vercel.json         # Vercel 部署配置
├── netlify.toml        # Netlify 部署配置
├── package.json        # 项目配置
├── README.md           # 项目文档
└── .gitignore          # Git 忽略文件
```

## 更新日志

### v2.0.0 (最新)
- ✨ 新增通知格式选择（简单/带标题/完整）
- ✨ 支持 GET 和 POST 请求方式
- ✨ 添加所有 Bark 官方参数支持
- ✨ 新增时效性通知（level）
- ✨ 新增重复播放铃声（call）
- ✨ 新增加密密文（ciphertext）
- 🎨 重新设计 UI，分区域展示
- 🎨 优化结果弹窗显示
- 📱 改进移动端适配

### v1.0.0
- 🎉 初始版本发布
- 📝 基础通知功能
- 🔔 铃声选择
- 💾 Cookie 存储

## 贡献

欢迎提交 Issue 和 Pull Request！

### 开发指南
1. Fork 本仓库
2. 创建新分支 `git checkout -b feature/your-feature`
3. 提交更改 `git commit -m 'Add some feature'`
4. 推送到分支 `git push origin feature/your-feature`
5. 创建 Pull Request

## 许可证

MIT License

## 相关链接

- [Bark GitHub](https://github.com/Finb/Bark)
- [Bark 官方文档](https://bark.day.app/)
- [Bark API 文档](https://github.com/Finb/Bark/blob/master/docs/API_V2.md)
- [Vercel 文档](https://vercel.com/docs)
- [Netlify 文档](https://docs.netlify.com/)

## 致谢

感谢 [Bark](https://github.com/Finb/Bark) 项目提供的优秀 iOS 推送服务。
