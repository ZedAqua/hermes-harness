# hermes-harness

可复用的 Hermes 训练与评测环境仓库，负责把 Hermes、MCP 工具、mock/snapshot 环境和训练网关组合成可启动、可验证的整套运行环境。

## 职责

- 固定 Hermes 兼容版本、chat template、tool-call parser 和上下文处理配置。
- 维护训练所需的 MCP 工具 schema、适配器、mock 和 snapshot 环境。
- 提供本地或容器化的一键启动、健康检查和最小冒烟测试。
- 对接训练网关和评测 runner，保留原始消息、工具调用和必要的轨迹元数据。
- 记录环境版本、依赖镜像和兼容性测试结果。

## 不负责

- 不实现 AReaL/verl 等训练框架的核心逻辑。
- 不维护评测题库、gold 或训练数据处理流水线。
- 不替代 Hermes 生产仓库；这里只维护训练/评测所需的可复用环境封装。

## 计划目录

```text
docker/        镜像和 Compose 配置
hermes/        Hermes 接入层与兼容性配置
mcp/           工具 schema、适配器和 mock/snapshot 环境
gateway/       训练网关连接配置
configs/       chat template、解析器和运行参数
smoke-tests/   启动、健康检查和端到端冒烟测试
docs/          环境复现说明
```
