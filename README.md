# AgentSearch

多引擎搜索技能，为 Agent 提供智能信息检索能力。

## 特性

- **多引擎支持**：Tavily、Brave Search、Exa、Perplexity
- **结果路由**：根据调用来源决定输出格式
- **智能去重**：按 URL 自动去重
- **缓存机制**：避免重复搜索

## 安装

```bash
git clone https://github.com/YintaTriss/AgentSearch.git
cd AgentSearch
pip install -e .
```

## 使用

```python
from agent_search import SearchSkill, SearchConfig

# 创建实例
config = SearchConfig(
    tavily_api_key="tvly-xxx",
    brave_api_key="BSAxxx"
)
search = SearchSkill(config)

# 执行搜索
result = search.execute("search", {
    "query": "OpenClaw skills documentation",
    "engines": ["tavily", "brave"],
    "max_results": 10
})
```

## 架构

```
AgentSearch/
├── agent_search/      # 主模块
│   ├── __init__.py
│   └── skill.py        # 核心技能实现
├── SKILL.md           # OpenClaw 技能入口
└── README.md          # 本文件
```

## 作为 AgentSymphony 的一部分

AgentSearch 是 [AgentSymphony](https://github.com/YintaTriss/AgentSymphony) 技能交响乐的子技能。

## License

MIT