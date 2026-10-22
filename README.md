# RuoYi-Vue 管理系统（前后端分离）

基于开源项目 **RuoYi-Vue** 搭建的前后端分离管理系统示例，后端 Spring Boot 3 + Java 17，前端 Vue 3 + Vite + Element Plus。

## 技术栈

| 层 | 技术 |
| --- | --- |
| 后端 | Spring Boot 3.5、Spring Security、JWT、MyBatis、Redis、MySQL |
| 前端 | Vue 3、Vite、Element Plus、Pinia、Axios |
| 构建 | Maven（后端）、npm / node（前端） |

## 目录结构

```
ruoyi-vue-admin/
├─ backend/    后端（RuoYi-Vue springboot3 分支）
└─ frontend/   前端（RuoYi-Vue3）
```

- `backend/`：Maven 多模块工程，`ruoyi-admin` 为启动模块。
- `frontend/`：Vue 3 工程，`npm run dev` 启动开发服务器。

## 快速开始

### 1. 数据库

执行 `backend/sql/` 下的脚本（先建库，再导入 `ry_*.sql` 与 `quartz.sql`），并修改
`backend/ruoyi-admin/src/main/resources/application-druid.yml` 中的数据库连接。

### 2. 后端

```bash
cd backend
mvn clean package -DskipTests
java -jar ruoyi-admin/target/ruoyi-admin.jar
```

默认端口 `8080`，上下文路径 `/`（接口前缀 `/dev-api` 由前端代理配置决定）。

### 3. 前端

```bash
cd frontend
npm install
npm run dev
```

默认访问 `http://localhost:80`，代理到后端 `http://localhost:8080`。

> 依赖 Redis，请先启动 Redis 并在 `application.yml` 中配置。

## 上游与许可

- 后端：[RuoYi-Vue](https://gitee.com/y_project/RuoYi-Vue)（MIT）
- 前端：[RuoYi-Vue3](https://gitcode.com/yangzongzhuan/RuoYi-Vue3)（MIT）

本项目保留上游 `LICENSE` 与版权声明；如用于生产，请自行完成安全加固与配置管理。
