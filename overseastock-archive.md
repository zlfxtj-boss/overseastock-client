# 海外仓掌柜 - 项目归档文档
生成时间: 2026-05-02 14:42:00

## 项目概述
海外仓掌柜是一套跨境电商海外仓管理系统，包含客户端采购平台和管理后台两个部分。

## 源代码仓库

### 客户端 (overseastock-client)
- **仓库**: https://github.com/zlfxtj-boss/overseastock-client
- **分支**: master
- **文件结构**:
  - `index.html` - 首页/商品列表（28个真实商品）
  - `product-detail.html` - 商品详情页
  - `cart.html` - 购物车/采购单
  - `checkout.html` - 结账页面
  - `orders.html` - 订单页面
  - `admin/` - 管理后台
  - `imgs/` - 29张商品图片 (image1~29)
  - `products-data-real.js` - 真实商品数据（28个美国仓商品）
  - `products-data.js` - 商品数据结构
  - `styles.css` - 样式表
  - `批量导入商品模板*.csv` - 批量导入模板
  - `美国仓自动导入.html` - 自动导入工具

### 后端API (overseastock-api)
- **仓库**: https://github.com/zlfxtj-boss/overseastock-api
- **分支**: master
- **文件结构**:
  - `server.js` - Express API服务器（含商品管理、订单、CSV导入）
  - `Dockerfile` - Docker部署配置
  - `railway.json` - Railway部署配置
  - `README.md` - 项目说明
  - `.github/workflows/` - GitHub Actions CI/CD

## 部署信息

### 客户端部署 (GitHub Pages)
- **URL**: https://zlfxtj-boss.github.io/overseastock-client/
- **部署方式**: GitHub Actions 自动构建推送
- **触发**: master分支push时自动部署

### 后端API部署 (Railway)
- **URL**: https://overseastock-production.up.railway.app
- **健康检查**: https://overseastock-production.up.railway.app/health
- **部署方式**: Railway + GitHub集成
- **数据库**: Railway PostgreSQL (需手动配置 DATABASE_URL)
- **初始化**: 访问 /api/init-demo 初始化示例数据
- **版本**: overseastock_v2.1 (v2.1.1)

## 管理员账号
- **用户名**: shayu0909
- **密码**: shayu0909
- **入口**: https://zlfxtj-boss.github.io/overseastock-client/ → 管理后台

## 商品数据 (美国仓28个商品)
包含家具、储物架、厨房用品等品类，含：
- 尺寸、重量、申报价格、木制品重量
- 1688采购链接
- 采购价(¥)和建议零售价($)

## 备份文件
- **最终备份**: overseastock-complete-backup-20260502-163823.tar.gz (8.9MB)
  - SHA256: 0d7e60bad9ad5a171f3e03a8eab590160a195d565fb8891a8ee1bfd5d1bba885
  - 包含: client + api + landing + archive.md
- **最终提交 (client)**: `9b46fb4` data: 添加29张商品图片和SKU映射文件
- **最终提交 (api)**: `cc26f19` fix: add railway.toml + improve deployment workflow with diagnostics

## Git提交历史

### 客户端提交:
```
9b46fb4 data: 添加29张商品图片和SKU映射文件
d3f5767 fix: window.products 挂载到全局，修复商品不显示问题
0e779f8 data: 更新真实商品数据文件
58fcc9e fix: 优化商品数据加载和展示逻辑
48cf8d0 fix: 移除英国仓和德国仓的虚拟数据，仅保留美国仓
```

### 后端API提交:
```
b27359c fix: update Railway deployment workflow
5dd174d chore: add PostgreSQL plugin config for Railway
118ecb2 feat: 更新美国仓28个商品数据，添加CSV导入接口
20390af feat: 添加数据初始化接口 /api/init-demo
69584f3 fix: update Railway deployment workflow
```

## 项目完成度
- [x] 客户端商品展示页面
- [x] 商品详情和采购单功能
- [x] 购物车和结算流程
- [x] 管理后台（管理员登录、商品管理、订单管理）
- [x] 后端REST API
- [x] GitHub Actions自动部署
- [x] Railway后端部署
- [x] 28个真实商品数据
- [x] CSV批量导入功能

---
归档完成时间: 2026-05-02 14:42:00