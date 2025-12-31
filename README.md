### 快速开始

#### 安装运行dtm

参考[dtm安装运行](https://dtm.pub/guide/install.html)

#### 运行示例

准备数据库
- 安装 [src/main/resources/application.yml]() 中的spring/datasource准备数据库实例
- 创建库表
  - 库 `create schema dtm_busi collate utf8mb3_bin;`
  - 屏障表 `sql/barrier.sql`
  - TCC业务表 `sql/busi.mysql.sql`

运行服务

```
mvn package && java -jar target/dtmcli-java-sample-0.0.1-SNAPSHOT.jar
```

触发成功的TCC事务
```
curl localhost:8081/api/tccBarrier
```

触发回滚的TCC事务
```
curl localhost:8081/api/tccBarrierError
```
