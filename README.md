# Swift Craft Launcher News API

基于 GitHub Pages + GitHub Actions 的静态公告 API。

## 使用方法

### 添加公告

在 `news/` 目录下创建 JSON 文件，文件名使用版本号格式：`[version].json`

例如：`0.3.1-beta.json`、`1.0.0.json`

JSON 格式（支持22种语言）：
```json
{
  "en": {
    "title": "Important Notice",
    "content": "Content",
    "author": "Swift Craft Launcher Team"
  },
  "zh-Hans": {
    "title": "重要通知",
    "content": "内容",
    "author": "Swift Craft Launcher 团队"
  },
  "es": {
    "title": "Aviso importante",
    "content": "Contenido",
    "author": "Equipo Swift Craft Launcher"
  }
}
```

### API 端点

`/api/announcements/[version]/[lang].json`

示例：
- `/api/announcements/0.3.1-beta/en.json`
- `/api/announcements/0.3.1-beta/zh-Hans.json`

### 使用函数

```javascript
const { getAnnouncement } = require('./scripts/generate-api.js');
const result = getAnnouncement('0.3.1-beta', 'en');
```

### 生成静态文件

```bash
node scripts/generate-api.js
```

## 支持的22种语言

ar, da, de, en, es, fi, fr, hi, it, ja, ko, nb, nl, pl, pt, ru, sv, th, tr, vi, zh-Hans, zh-Hant

