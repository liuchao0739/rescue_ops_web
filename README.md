# rescue_ops_web

智能应急救援平台（Rescue Platform）**运营平台 Web** 仓库，包含后台管理系统与 **调度大屏**（`rescue_dispatch_screen`）视图。

| 属性 | 说明 |
|------|------|
| 平台 | [rescue_platform](https://github.com/liuchao0739) |
| 界面语言 | English (en-US) |
| 推荐技术栈 | React 18 + TypeScript + Ant Design Pro |

## 产品范围

本仓库承载两个 Web 形态（同一 codebase，不同路由）：

| 模块 | 命名 | 说明 |
|------|------|------|
| 运营平台 | `rescue_ops_web` | 仪表盘、SOS 中心、调度、设备、SIM、OTA、用户、权限 |
| 调度大屏 | `rescue_dispatch_screen` | 大屏投屏视图，如 `/dispatch-screen` |

## 规划目录结构

```
rescue_ops_web/
├── src/
│   ├── pages/
│   │   ├── dashboard/
│   │   ├── sos/              # SOS Center, List, Details
│   │   ├── dispatch/         # Dispatch Center, Order Board
│   │   ├── map/              # GIS Map + layers
│   │   ├── devices/
│   │   ├── sim/
│   │   ├── ota/
│   │   ├── users/
│   │   └── dispatch-screen/  # 调度大屏
│   ├── components/
│   ├── services/             # API + WebSocket client
│   └── locales/              # en-US (default), zh-CN P1
├── public/
└── docs/
    └── rescue_platform_mvp_plan.md
```

## P0 功能模块

- **工作台**：Dashboard、Live Alerts  
- **SOS**：SOS Center / List / Details、Risk Level L1-L5  
- **调度**：Dispatch Center、Order Board、Manual Dispatch、Rescue Resources、Dispatch Timeline  
- **地图**：GIS Map、SOS / Device / Rescue Resource 图层  
- **设备 & SIM**：Device Management、SIM Management、Activation Check  
- **OTA**：OTA Management、OTA Tasks  
- **系统**：RBAC、Operator Management、Operation Logs、System Health  

## 实时通信

- 通过 `rescue_ws_server` 订阅 SOS、设备、工单、告警事件  
- 地图刷新目标延迟 **< 1 秒**

## 本地开发（待初始化）

```bash
npm install
npm run dev
```

环境变量示例（待补充 `.env.example`）：

```
VITE_API_BASE_URL=https://api.rescue.example/v1
VITE_WS_URL=wss://ws.rescue.example
```

## 相关仓库

| 仓库 | 说明 |
|------|------|
| [rescue_platform_api](https://github.com/liuchao0739/rescue_platform_api) | 后端 API + WebSocket |
| [rescue_mobile_suite](https://github.com/liuchao0739/rescue_mobile_suite) | 用户端 / 救援人员 App |
| [rescue_platform_infra](https://github.com/liuchao0739/rescue_platform_infra) | 部署与域名 |

## 文档

- [MVP 产品规划与技术方案](docs/rescue_platform_mvp_plan.md)

## License

Proprietary — Rescue Platform MVP
