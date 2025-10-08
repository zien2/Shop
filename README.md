## 商超市场（vue-rabbit）

一个基于 Vue 3 + Vite 的电商前端项目，包含首页、分类、详情、购物车、结算、支付、会员中心等模块。

### 技术栈
- Vue 3（Composition API）
- Vite 4
- Vue Router 4
- Pinia + pinia-plugin-persistedstate
- Element Plus（按需引入，Sass 主题覆盖）
- Axios、@vueuse/core、dayjs

### 快速开始
```bash
# 安装依赖（推荐 ci 保持锁定）
npm ci

# 本地启动（默认 http://localhost:5173/）
npm run dev

# 构建产物
npm run build

# 本地预览构建产物
npm run preview
```

### 目录结构
```
src/
  apis/           # 后端接口封装（按业务拆分）
  components/     # 通用业务组件（如 XtxSku、ImageView）
  composables/    # 可复用逻辑（useCountDown 等）
  directives/     # 自定义指令
  router/         # 路由配置
  stores/         # Pinia 状态（user/cart/category）
  styles/         # 主题变量与 Element 样式覆盖
  utils/http.js   # Axios 二次封装（拦截器、鉴权、错误提示）
  views/          # 页面模块（Home/Detail/Checkout/Pay/...）
```

### 环境变量
- 默认接口地址在 `src/utils/http.js` 中配置：
  - `http://pcapi-xiaotuxian-front-devtest.itheima.net`
- 如需切换环境，请修改 `baseURL` 或在封装处按需读取 `import.meta.env`。

### 常见问题（FAQ）
- 无法登录 / 400 Bad Request：
  - 确认测试账号是否有效；
  - 检查是否存在首尾空格；
  - 确认 `baseURL` 与协议（http/https）是否与服务端一致。
- 跨域/代理：
  - 本项目直接使用完整域名；如需本地代理，可在 `vite.config.js` 中配置 `server.proxy`。

### 开发建议
- 统一通过 `src/apis/*` 调用后端，避免在视图内直接写 `axios`。
- 组件拆分颗粒度以“可复用且职责单一”为准；业务状态统一放在 Pinia。
- 使用 `styles/var.scss` 调整主题色，`styles/element/index.scss` 定制组件样式。

### 相关文档
- 技术栈与面试题清单见：`TECH_STACK_AND_INTERVIEW.md`
