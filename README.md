# 营销抽奖平台

这是一个面向抽奖营销场景的 Java 后端与 Next.js 前端项目，重点展示分层架构、抽奖策略、库存一致性、消息驱动和运营配置等实践。

## 项目结构

- `big-market-app`：Spring Boot 应用入口与配置
- `big-market-domain`：领域模型、抽奖策略、规则链和规则树
- `big-market-infrastructure`：MySQL、Redis、Elasticsearch、消息队列等基础设施适配
- `big-market-api`、`big-market-trigger`、`big-market-querys`、`big-market-types`：接口、触发器、查询和公共类型模块
- `big-market-front`：Next.js 抽奖运营界面
- `docs/dev-ops`：本地 Docker Compose、数据库初始化脚本和可观测性配置
- `docs/interview-materials`：项目面试准备资料

## 技术栈

Java 17、Spring Boot、MyBatis、Redis、MySQL、RabbitMQ、Dubbo、Nacos、Zookeeper、Elasticsearch、Prometheus、Grafana、Next.js、TypeScript。

## 本地运行

1. 启动基础设施：`docker compose -f docs/dev-ops/docker-compose-local.yml up -d`
2. 使用本地 profile 启动后端：`mvn spring-boot:run -pl big-market-app`
3. 启动前端：进入 `big-market-front` 后执行 `npm install` 和 `npm run dev`

仓库中的配置只提供本地示例值。请通过环境变量或本机未提交的配置覆盖数据库、消息队列、注册中心和任务调度凭据。

## 设计要点

- 领域驱动的模块划分与清晰的端口适配边界
- 抽奖策略、权重算法、规则链和规则树
- Redis 库存、数据库分片与消息队列协作
- 任务调度、服务注册和 Prometheus/Grafana 监控
- 前后端分离的抽奖与运营页面



