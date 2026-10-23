# 简易进销存管理系统（教学版）

本分支（`lite-admin`）用于**学习与教学**：用一个体量小、结构简单的进销存后台管理系统替换 `main` 分支上的 RuoYi 框架。`main` 分支保持原样，两套代码互不影响。

- 上游项目：[toesbieya/jxc-admin](https://github.com/toesbieya/jxc-admin)（MIT）
- 形态：前后端分离，单模块后端 + 单工程前端，没有微服务、没有多模块依赖

## 技术栈

| 层 | 技术 |
| --- | --- |
| 后端 | Spring Boot 2.2.7（JDK 8）、Spring Security、MyBatis、Redis、MySQL |
| 前端 | Vue 2、Element UI 2.15、vue-cli、vuex、vue-router |
| 实时 | socket.io（消息通知） |

## 目录结构

```
ruoyi-vue-admin/
├─ java/
│  ├─ local/        单体后端（pom.xml + src）
│  ├─ cloud/        Spring Cloud 版本（可选，教学对照用）
│  └─ db/my.rar     数据库脚本（解压后导入 MySQL）
├─ vue/
│  ├─ full/         完整前端工程
│  └─ template/     前端模板（可选）
├─ docs/            项目文档
└─ LICENSE          MIT
```

## 本地运行

### 1. 数据库

解压 `java/db/my.rar`，在 MySQL 中建库并导入 SQL；按需修改
`java/local/src/main/resources/application.yml` 里的数据库、Redis 连接。

### 2. 后端

```bash
cd java/local
mvn spring-boot:run
```

默认端口见 `application.yml`（通常 `8080` 或 `9090`）。

### 3. 前端

```bash
cd vue/full
npm install
npm run serve
```

前端开发服务器的代理目标在 `vue.config.js` 中配置，指向上面的后端端口。

## 许可

上游为 MIT 协议，本分支保留其 `LICENSE` 与版权声明。
