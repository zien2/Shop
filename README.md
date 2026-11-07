# 商超市场（vue-rabbit）

基于 Vue 3 的电商前端演示项目，包含首页、分类、商品详情、购物车、结算、支付和会员中心等页面。

> **项目范围：**本仓库提供前端，不包含电商后端。商品、账户和订单等操作依赖外部小兔鲜演示 API；该服务的可用性和测试账号由服务端决定。

## 技术栈

- Vue 3（Composition API）
- Vite 7
- Vue Router 4
- Pinia、pinia-plugin-persistedstate
- Element Plus、Sass
- Axios、@vueuse/core、dayjs

## 本地运行

需要安装 Node.js 和 npm。

```bash
npm ci
npm run dev
```

开发服务器默认地址为 `http://localhost:5173/`。生产构建和本地预览：

```bash
npm run build
npm run preview
```

## 页面与目录

```
src/
  apis/           # 按业务拆分的接口封装
  components/     # 通用业务组件
  composables/    # 可复用逻辑
  directives/     # 自定义指令
  router/         # 页面路由
  stores/         # Pinia 状态（用户、购物车、分类）
  styles/         # 主题变量和 Element Plus 样式
  utils/http.js   # Axios 请求封装
  views/          # 首页、详情、结算、支付等页面
```

## 接口说明

当前演示 API 地址在 `src/utils/http.js` 中配置，指向小兔鲜前端测试服务。演示服务可能变更或不可用；若要接入自己的后端，请调整请求基础地址及接口适配，并处理相应的跨域配置。

本项目没有自带后端，因此本地前端能启动不代表登录、支付或订单流程可以独立运行。

## 相关文档

[技术栈与面试题清单](TECH_STACK_AND_INTERVIEW.md)
