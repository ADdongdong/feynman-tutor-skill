# 费曼学习法 · 真懂教练

> 确保你真正学懂一个概念，而不是假装学懂。

## 这是什么

一个 [WorkBuddy](https://workbuddy.com) Skill，用费曼学习法确保用户**真正理解**一个概念，而不是表面记住。

大多数学习是假学习：看完一段话，点头说"懂了"，但真让你解释却说不出来。这个 skill 根治这个问题：

**生活类比让你秒懂原理 → 追问让你用自己的话复述 → 诊断你到底卡在哪 → 对症补强 → 直到你能把它讲给别人听。**

## 核心特性

- **类比开场**：不用术语堆砌，用快递分拣、电影院找座位这种生活类比，30 秒产生"原来如此"
- **输出型验证**：不能只点"我懂了"，必须用自己的话讲出来、写出来
- **根因诊断**：答不好不等于"你不行"，先诊断是概念混淆、缺前置知识、还是表达问题，再对症下药
- **不通过不放行**：评估没过就补强，绝不让你带着一知半解进入下一概念
- **即时反馈**：你回答任何问题后，先告诉你哪些对了、哪些有问题，再继续讲

## 安装

### 方式一：手动安装

```bash
# 1. clone 本仓库
git clone https://github.com/ADdongdong/feynman-tutor-skill.git

# 2. 把 skill 目录复制到 WorkBuddy skills 目录
cp -r feynman-tutor-skill ~/.workbuddy/skills/feynman-tutor
```

### 方式二：使用安装脚本（Windows PowerShell）

```powershell
git clone https://github.com/ADdongdong/feynman-tutor-skill.git
.\feynman-tutor-skill\install.ps1
```

## 使用方法

在 WorkBuddy 对话中直接说：

- "我想学【多模态】，用费曼方法教我"
- "教我理解对齐"
- "帮我深入理解向量数据库"
- "费曼方法讲讲 RAG"

触发后 skill 会自动加载，按费曼学习法流程带你学。

## 目录结构

```
feynman-tutor-skill/
├── SKILL.md                          # Skill 主入口（frontmatter + 核心流程）
├── references/
│   ├── diagnosis_patterns.md         # 根因诊断表 + 补强话术 + 评估决策树
│   ├── response_envelope.md          # 结构化响应协议字段定义
│   └── kernel_spec.md               # 完整内核规范（状态机 + 落地说明）
├── install.ps1                       # Windows 安装脚本
├── .gitignore
└── README.md                         # 你正在看的这个文件
```

## 教学流程

```
学科选择 → 目标分级（能看懂/能用上/能设计）→ 模块计划
    ↓
类比开场 → 出题验证 → 评估
    ↓                          ↓ 不通过
  通过 → 归档              诊断根因 → 对症补强 → 回到验证
```

详细状态机见 `references/kernel_spec.md`。

## 版本管理

遵循 [语义化版本](https://semver.org/lang/zh-CN/)：

- **主版本号**：教学流程架构变更（如状态机重构）
- **次版本号**：新增功能（如新增复习队列、新增模态支持）
- **修订号**：修复 bug、优化话术、调整规则

## 技术栈

- 纯 Markdown，无依赖
- 兼容 WorkBuddy Skill 规范 v1
- 可同时作为 WorkBuddy Expert 使用（需转换格式）

## License

MIT
