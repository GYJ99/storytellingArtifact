# AI故事生成器

一个基于Gemini AI的胎教故事生成器，支持多种故事类型，界面美观，适合在GitHub Pages上部署。

## 功能特点

- 🌟 多种故事类型：自然小夜曲、智慧寓言、想象翅膀、爱的旋律、成语故事、寓言故事、名人成才故事、卡通故事等
- 📱 响应式设计，支持移动端
- 💾 故事历史记录功能
- ⭐ 故事评分系统
- 🔒 安全的API密钥管理
- 🎨 现代化UI设计

## GitHub Pages 部署指南

### 使用GitHub Secrets（推荐）

1. **Fork 或上传此项目到你的GitHub仓库**

2. **配置Repository Secrets：**
   - 进入仓库的 `Settings` > `Secrets and variables` > `Actions`
   - 添加以下Repository Secrets：
     - Name: `GEMINI_API_KEY`
       Value: 你的Gemini API密钥
     - Name: `GEMINI_BASE_URL` (可选)
       Value: 自定义的Gemini API基础URL (默认: https://generativelanguage.googleapis.com)

3. **启用GitHub Pages：**
   - 进入仓库的 `Settings` > `Pages`
   - Source 选择 `GitHub Actions`
   - 项目已包含 `.github/workflows/deploy.yml` 工作流文件

4. **部署：**
   - 推送代码到main分支，GitHub Actions会自动部署
   - 部署完成后，访问 `https://你的用户名.github.io/仓库名` 即可使用

### 工作原理

GitHub Actions工作流会：
1. 读取你设置的Secrets中的API密钥
2. 自动生成包含API密钥的 `config.js` 文件
3. 将文件部署到GitHub Pages

这样既保证了API密钥的安全性，又能让应用正常工作。

## 本地开发

如果你想在本地测试应用：

1. **修改 `config.js` 文件：**
   ```javascript
   window.GEMINI_API_KEY = '你的真实API密钥';
   window.GEMINI_BASE_URL = 'https://generativelanguage.googleapis.com';
   ```

2. **使用本地服务器运行：**
   ```bash
   # 使用Python
   python -m http.server 8000
   
   # 或使用Node.js
   npx serve .
   ```

3. **访问 `http://localhost:8000` 进行测试**

**重要提醒：** 
- 项目已包含 `.gitignore` 文件来忽略 `config.js`，防止意外提交真实API密钥
- 如果你修改了 `config.js` 用于本地测试，Git会自动忽略这些更改
- GitHub Actions部署时会自动生成新的 `config.js` 文件，使用Secrets中的API密钥

## 获取Gemini API密钥

1. 访问 [Google AI Studio](https://makersuite.google.com/app/apikey)
2. 登录你的Google账户
3. 创建新的API密钥
4. 复制密钥用于配置

## 本地开发

1. 克隆仓库到本地
2. 在浏览器中直接打开 `故事生成器.html`
3. 在浏览器控制台中设置环境变量：
   ```javascript
   window.GEMINI_API_KEY = 'your-api-key-here';
   window.GEMINI_BASE_URL = 'https://generativelanguage.googleapis.com'; // 可选，使用默认值
   ```
4. 刷新页面即可使用

## 故事类型说明

- 🌿 **自然的小夜曲**：以大自然为主题的温馨故事
- 🦉 **智慧的寓言**：富含哲理的教育故事
- 🦋 **想象的翅膀**：激发创造力的奇幻故事
- 💕 **爱的旋律**：关于爱与温情的故事
- 📚 **成语故事**：中华传统成语典故
- 🐰 **寓言故事**：经典寓言改编
- ⭐ **名人成才故事**：励志的名人成长故事
- 🎨 **卡通故事**：轻松有趣的卡通风格故事
- 🔬 **科学启蒙**：科普知识故事
- 🎵 **音乐故事**：与音乐相关的故事

## 技术栈

- HTML5
- CSS3 (使用CSS变量和现代布局)
- Vanilla JavaScript
- Google Gemini AI API

## 许可证

MIT License

## 贡献

欢迎提交Issue和Pull Request来改进这个项目！