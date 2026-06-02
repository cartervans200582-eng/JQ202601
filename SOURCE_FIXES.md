# BD系统源码修复补丁
# 在Claude Code中应用以下修改，然后运行 npm run build

## 修复1: App.tsx - 移动端底部菜单增加AI洞察和个人成长
## 文件: src/App.tsx 第15-20行
## 已修改 (我已完成): 在mobileNav数组中增加了 /report 和 /goals

## 修复2: MonthlyReportPage.tsx - 返回顶部滚动修复
## 文件: src/pages/MonthlyReportPage.tsx 第524-527行
## 将以下代码:
```tsx
<FAB color="bg-blue-500" emoji="↑" label="顶部" onClick={() => {
    const main = document.querySelector('main')
    if (main) main.scrollTo({ top: 0, behavior: 'smooth' })
    else window.scrollTo({ top: 0, behavior: 'smooth' })
  }} />
```
## 替换为:
```tsx
<FAB color="bg-blue-500" emoji="↑" label="顶部" onClick={() => {
    window.scrollTo({ top: 0, behavior: 'smooth' })
    const container = document.querySelector('.min-h-screen.bg-gray-50')
    if (container) container.scrollTo({ top: 0, behavior: 'smooth' })
  }} />
```

## 修复3: MonthlyReportPage.tsx - FAB按钮统一样式
## 文件: src/pages/MonthlyReportPage.tsx 第522行
## 将 FAB 按钮颜色统一 (所有三个按钮颜色一致):
```tsx
// 改为全部用同一个颜色:
<FAB color="bg-blue-600" emoji="📋" label="批量" onClick={...} />
<FAB color="bg-blue-600" emoji="➕" label="添加" onClick={...} />
<FAB color="bg-blue-600" emoji="↑" label="顶部" onClick={...} />
```

## 构建:
npm run build
# 将 dist/assets/ 下的新文件复制到部署目录
