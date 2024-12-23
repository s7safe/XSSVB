# XSSVB

写了个xss向量生成工具，可以根据用户投喂的XSS payloads 进行学习，并且，根据用户提交的JS代码片段进行上下文分析，从而生成相对应的payload辅助测试

该项目还没写好，最终不确定是以网页形式还是网页插件形式来进行XSS漏洞挖掘，如果是网页形式，那么还需要根据特征码来识别上下文注入点，如果插件形式，是否可以输入固定的特征码进行自动化分析，自动化输入，并确认漏洞
![d3b9772dd2388e7e61e428e23f12f30](https://github.com/user-attachments/assets/8d2fec9e-7368-42b7-a0f3-dba5c94ec01a)
根据投喂进行学习
![5581ca9c1c99b41831e3a8c04cc11d5](https://github.com/user-attachments/assets/5e31ed34-2f60-4542-834a-c93cd79b957e)


目前代码，实现的功能如下
## 主要特性

- **上下文感知**：(这里的上下文感知是根据程序生成了一个特定的特征码进行识别分析的)
  - HTML 标签内容
  - 属性值注入
  - JavaScript 代码
  - URL 参数

- **语义分析**：
  - WAF 检测与识别（指纹验证，从而选择某个绕过方式）
  - 上下文相关的绕过建议


- **学习能力**：
  - 记录成功的 payload
  - 追踪绕过技术的有效性
  - 基于历史数据优化生成策略

- **测试工具集**：
  - 多种编码变体
  - 自动测试用例生成
  - 一键复制功能
  - 实时验证（写了一半，目前还办不到）

## 技术栈

- **后端**：Python Flask
- **前端**：原生 JavaScript (ES6+)
- **数据库**：SQLite
- **安全特性**：
  - 输入验证
  - Payload 净化
  - 错误处理
  - 日志系统

## 使用方法

1. 选择注入上下文
2. 输入包含标识符的 JavaScript 代码
3. 生成 Payload
4. 查看分析结果和建议
5. 测试生成的 Payload
6. 复制并使用成功的变体

## 注意事项

本工具属于墨渊安全团队内部工具集，在测试完美后，会进行开源，该工具仅用于安全研究和授权测试目的。在任何系统上测试 XSS payload 之前，请确保获得适当授权。
