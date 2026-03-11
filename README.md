# survey-taste-engineer

口味工程师经验采集工作台

## 项目简介

本项目用于系统梳理口味工程师在客户需求理解、菜品可交付性判断、目标出品识别、设备执行映射、试菜调优方法等方面的经验与判断逻辑，为 AI 菜谱生态建设提供知识底座。

## 版本演进关系

| 版本 | 状态 | 说明 |
|------|------|------|
| v1.0 | 锁定基线 | 初始稳定版本，用于备份和对比 |
| v1.1 | 能力基线 | 新增自动保存与底部动作区优化 |
| v1.2 | 正式版本 | 问卷内容优化（14 模块，79 题） |
| v1.2.1 | 最新修复 | 漏填定位 + 顶部防闪动修复 |

## 线上访问链接

- **主入口（v1.2）**：https://survey-taste-engineer.vercel.app
- **v1.0**：https://survey-taste-engineer.vercel.app/v1.0
- **v1.1**：https://survey-taste-engineer.vercel.app/v1.1
- **v1.2**：https://survey-taste-engineer.vercel.app/v1.2
- **v1.2.1**：https://survey-taste-engineer.vercel.app/v1.2.1

## 本地打开方式

```bash
# 直接用浏览器打开任意版本
open index-survey-collect-v1.2.1.html
```

或在浏览器地址栏输入：
```
file:///path/to/survey-taste-engineer/index-survey-collect-v1.2.1.html
```

## Vercel 路由说明

| 路由 | 目标文件 |
|------|---------|
| `/` | index-survey-collect-v1.2.html |
| `/v1.0` | index-survey-collect-v1.0.html |
| `/v1.1` | index-survey-collect-v1.1.html |
| `/v1.2` | index-survey-collect-v1.2.html |
| `/v1.2.1` | index-survey-collect-v1.2.1.html |

## 文件结构

```
survey-taste-engineer/
├── index-survey-collect-v1.0.html   # v1.0 锁定基线
├── index-survey-collect-v1.1.html   # v1.1 能力基线（自动保存与底部动作区）
├── index-survey-collect-v1.2.html   # v1.2 问卷内容优化版本
├── index-survey-collect-v1.2.1.html # v1.2.1 交互修复版本
├── vercel.json                      # Vercel 路由配置
├── README.md                        # 项目说明
├── .gitignore                       # Git 忽略规则
└── docs/                            # 文档目录
    ├── versions.md                  # 版本演进与变更记录
    ├── v1.2-question-list.md        # v1.2 题目维度与选项清单
    └── v1.2.1-changelog.md          # v1.2.1 变更记录
```

## 版本说明

### v1.0（锁定基线）
- 初始版本，97 题，15 模块
- 基础问卷功能
- 手动保存进度

### v1.1（能力基线）
- 新增自动保存机制（每次答题后自动保存）
- 新增底部动作区优化（完成填写并导出）
- 自动保存状态长期可见
- 刷新后可恢复已填内容

### v1.2（问卷内容优化）
- 模块数量：15 → 14（删除 M14 自评模块）
- 题目总数：97 → 79
- q1_3 拆分为 q1_3a 和 q1_3b
- q2_2 与 q2_5 合并
- 删除 q1_7、q2_4、q2_5、q7_7
- 所有「其他」选项增加强制补充输入框
- 题干口语化改写 19 题
- 选项优化 10 题

### v1.2.1（交互修复）
- 漏填时自动滚动到第一个未填题目并高亮
- 「其他」补充输入框未填时自动展开并定位
- 顶部 header 滚动收起/展开防闪动优化（滞回区间）
- 用户开始填写后错误高亮自动消失

## 后续维护规则

1. **版本保护**
   - 不覆盖旧版本文件
   - 每个版本保留独立访问链接
   - 主入口切换需经确认后修改 vercel.json

2. **新版本开发**
   - 基于最新稳定版本独立复制开发
   - 新文件独立命名（如 v1.3、v1.3.1 等）
   - 独立部署测试链接

3. **文档维护**
   - 每个版本需在 docs/versions.md 中记录变更
   - 重大版本需单独创建 changelog 文件

## 部署说明

本项目部署在 Vercel，通过 vercel.json 配置路由规则。

```bash
# 本地部署测试
vercel --yes

# 生产部署
vercel --prod
```

## 技术栈

- 纯 HTML/CSS/JavaScript（无框架依赖）
- LocalStorage 本地存储
- Vercel 静态托管

---

**仓库地址**：https://github.com/gaogoying-sudo/survey-taste-engineer
