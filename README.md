# skill-dfyx_code_security_review
东方隐侠团队出品，代码审计skill

# 代码安全审计专家

一个基于深度数据流分析和业务逻辑理解的专家级代码安全审计工具。专注于识别高危漏洞、逻辑缺陷及架构风险，通过模拟黑客攻击视角提供精准的修复方案。

## 核心特性

- **全面覆盖**：支持Java、Python、Go、PHP、Node.js等多种编程语言
- **五阶段审计**：标准化的审计流程，从侦察到报告的完整闭环
- **深度分析**：结合架构分析、数据流追踪和业务逻辑理解
- **丰富案例库**：涵盖注入、认证、授权、文件操作等7大类漏洞
- **自动化工具链**：集成静态分析、依赖扫描、动态测试等多种工具
- **可视化支持**：提供Mermaid架构图和数据流图
- **DevSecOps集成**：支持CI/CD管道和安全门禁

## 快速开始

### 基本使用

1. **准备审计环境**
   ```bash
   # 克隆项目
   git clone <repository_url>
   cd dfyx_code_security_review
   
   # 安装依赖
   pip install -r requirements.txt
   ```

2. **执行代码扫描**
   ```bash
   # Phase 1/2: 侦察与模式匹配
   python scripts/code_scan.py /path/to/project
   
   # Phase 3: 深度污点追踪
   python scripts/data_flow_analyzer.py /path/to/project
   
   # Phase 4: 漏洞验证
   python scripts/vulnerability_validator.py /path/to/project
   ```

3. **生成审计报告**
   ```bash
   python scripts/report_generator.py --input scan_results.json --output report.pdf
   ```

### Docker部署

```bash
# 构建镜像
docker build -t code-audit .

# 运行审计
docker run -v /path/to/project:/app/project code-audit
```

## 目录结构

```
dfyx_code_security_review/
├── SKILL.md                 # 完整的审计方法论和指南
├── README.md                # 项目介绍和快速入门（本文件）
├── scripts/                 # 自动化脚本
│   ├── code_scan.py         # 代码结构扫描
│   ├── pattern_scanner.py   # 模式匹配扫描
│   ├── data_flow_analyzer.py # 数据流分析
│   ├── vulnerability_validator.py # 漏洞验证
│   └── report_generator.py  # 报告生成
├── resources/               # 资源文件
│   ├── rules/              # 漏洞检测规则
│   ├── patterns/           # 代码模式库
│   ├── templates/          # 报告模板
│   └── checklists/         # 审计检查清单
├── examples/               # 示例和案例
│   ├── audit_examples/      # 审计示例
│   ├── vulnerability_cases/  # 漏洞案例
│   └── report_examples/    # 报告示例
└── tests/                 # 测试文件
    ├── unit/               # 单元测试
    ├── integration/        # 集成测试
    └── performance/        # 性能测试
```

## 审计流程

本工具采用五阶段标准化审计协议：

1. **侦察与绘图**：识别项目架构、技术栈、攻击面
2. **并行模式匹配**：使用规则库定位潜在漏洞
3. **深度污点追踪**：对高风险区域进行详细分析
4. **验证与攻击链构建**：验证漏洞真实性和影响
5. **结构化报告**：生成详细的审计报告和修复建议

详细方法论请参考 [SKILL.md](SKILL.md)

## 支持的漏洞类型

### 注入与代码执行类
- SQL注入
- 命令注入
- 表达式注入（SSTI/ELD）
- 反序列化漏洞

### 文件与网络安全类
- 文件读取与上传漏洞
- SSRF（服务端请求伪造）
- CSRF（跨站请求伪造）
- XXE（XML外部实体）

### 认证与授权类
- 认证绕过
- 会话管理缺陷
- 权限提升（IDOR）
- 管理界面暴露

### 业务逻辑类
- 逻辑漏洞
- 状态机缺陷
- 并发安全
- 资源管理

### 前端安全类
- XSS（跨站脚本）
- 前端逻辑漏洞
- 敏感信息暴露

### 云原生与容器安全
- Docker配置安全
- Kubernetes安全
- 云服务配置安全

### 技术栈特定漏洞
- Java特定漏洞
- Python特定漏洞
- Go特定漏洞
- PHP特定漏洞

详细的检测规则和修复建议请参考 [SKILL.md](SKILL.md#7-漏洞检测规则增强-案例库)

## 工具集成

### 静态分析工具
- SonarQube
- Fortify
- Checkmarx
- Bandit (Python)
- FindSecBugs (Java)
- Gosec (Go)

### 依赖扫描工具
- OWASP Dependency-Check
- Snyk
- WhiteSource
- NPM Audit
- Pip-audit

### 动态分析工具
- OWASP ZAP
- Burp Suite
- SQLmap
- Nikto

### 配置扫描工具
- Trufflehog
- GitLeaks
- YARA
- OSQuery

工具集成详细配置请参考 [SKILL.md](SKILL.md#6-工具集成与脚本联动)

## DevSecOps集成

本工具支持完整的DevSecOps流程集成：

- **代码提交阶段**：预提交钩子、静态分析、依赖扫描
- **构建阶段**：安全编译、容器扫描、软件组成分析
- **测试阶段**：动态分析、渗透测试、安全功能测试
- **部署阶段**：配置扫描、合规检查、运行时监控

详细的集成方案和配置示例请参考 [SKILL.md](SKILL.md#104-devsecops-集成)

## 报告输出

本工具生成标准化的安全审计报告，包含：

- 项目概述和技术栈分析
- 架构评估和可视化
- 漏洞详情列表（按严重程度分类）
- 攻击链分析
- 修复建议和代码对比
- 安全改进计划

报告模板和格式标准请参考 [SKILL.md](SKILL.md#101-报告结构标准)

## 常见问题

### Q1: 支持哪些编程语言？
A: 支持Java、Python、Go、PHP、Node.js等主流编程语言，并持续扩展中。

### Q2: 如何提高审计效率？
A: 可以通过以下方式提高效率：
- 使用自动化工具链进行初步扫描
- 优先审计高风险区域
- 并行执行多个扫描任务
- 使用缓存机制避免重复扫描

### Q3: 漏洞检测准确率如何？
A: 本工具结合了静态分析、动态测试和人工审计，通过多维度验证提高准确率。建议结合多种工具交叉验证。

### Q4: 如何集成到CI/CD流程？
A: 可以通过以下方式集成：
- 在CI/CD管道中添加安全扫描阶段
- 设置安全门禁，阻止高风险代码部署
- 使用Docker容器化部署审计环境
- 配置自动化报告生成和通知

### Q5: 如何处理误报？
A: 建议采取以下措施：
- 使用多种工具交叉验证
- 进行人工代码审查
- 建立误报过滤机制
- 定期更新检测规则

## 贡献指南

欢迎贡献代码、报告漏洞或提出改进建议：

1. Fork本项目
2. 创建特性分支
3. 提交更改
4. 推送到分支
5. 创建Pull Request

## 许可证

本项目采用MIT许可证，详见LICENSE文件。

## 联系方式

如有问题或建议，请通过以下方式联系：

- 提交Issue
- 发送邮件至：[easternsman@163.com]
- 加入社区讨论：[https://discord.gg/cKKjp35hFH]

## 致谢

感谢所有贡献者和开源社区的支持！
