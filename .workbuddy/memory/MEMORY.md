# 项目记忆 - BD工作动态管理系统

## 技术栈
- 前端：React 19 + TypeScript + TailwindCSS + Vite 8 (PWA)
- 数据层：IndexedDB (12个表) + AES-GCM加密
- 安全：密码登录(PBKDF2) + QR码登录(HMAC) + 防暴力锁定
- 部署：GitHub Pages → jsDelivr CDN

## 关键路径
- 源码：E:\Dad's homework\WJQ\AI Claude\schedule-app\
- 仓库：github.com/cartervans200582-eng/JQ202601
- 国内访问：https://cdn.jsdelivr.net/gh/cartervans200582-eng/JQ202601@main/index.html

## 改造策略
- React前端源码不改；新index.html包裹层拦截fetch调用
- /api/* → IndexedDB CRUD；12个object stores对应原SQLite表
- AES-GCM加密：密钥由用户密码派生，所有IndexedDB数据加密存储
