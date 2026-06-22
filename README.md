# hana-skills

> HanaAgent 高潜力 Skill 云端仓库  
> 经过质量门控验证的高可用 Skill 归档与分发中心

## 仓库定位

本仓库是 [HanaAgent](https://github.com/liliMozi/openhanako) 生态的官方 Skill 分发节点。收录的每一个 Skill 都经过了：

- **质量门控**：SKILL.md 完整性 + evals 覆盖率 + 自检机制
- **可用性验证**：至少一次端到端实战验证
- **去重审查**：与已有 Skill 的功能重叠度低于阈值

## 目录结构

```
hana-skills/
├── README.md              # 本文件
├── registry.json          # Skill 注册表（索引 + 元数据）
├── skills/                # Skill 归档目录
│   └── <skill-name>/      # 单个 Skill 目录
│       ├── SKILL.md       # 核心 Skill 定义（必需）
│       ├── evals/         # 评估用例（推荐）
│       └── assets/        # 附属资源（可选）
└── templates/             # Skill 模板与创建指南
```

## Skill 收录标准

| 维度 | 要求 |
|------|------|
| 命名规范 | 小写 + 连字符，语义明确，如 `feishu-bitable-setup` |
| SKILL.md | 包含触发条件、使用说明、参数约定、依赖声明 |
| 自检机制 | 至少一个 smoke test 或 sanity check |
| 安全审查 | 无硬编码凭证、无任意命令注入风险 |
| 功能边界 | 单一职责，不与已有 Skill 高度重叠 |

## 快速使用

在 HanaAgent 中安装 Skill：

```
install_skill from github: mjnn/hana-skills/skills/<skill-name>
```

## 贡献

欢迎提交 PR，但需附上：
1. Skill 的功能说明与使用场景
2. 至少一条 eval 用例
3. 与其他 Skill 的差异说明（如有重叠）

---

*维护者：马捷（mjnn）*  
*归档原则：宁缺毋滥，质量优先*