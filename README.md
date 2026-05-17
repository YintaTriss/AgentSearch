# Search Skill

多引擎搜索技能，支持 Tavily、Brave Search 等。

## 特性

- **多引擎支持**：Tavily、Brave Search、Exa、Perplexity
- **智能路由**：根据调用来源决定输出格式
- **结果去重**：按 URL 自动去重
- **缓存机制**：避免重复搜索

## 安装

```bash
pip install -e .
```

## 使用

```python
from search import SearchSkill, SearchConfig

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
search-skill/
├── skill.py          # 核心技能实现
├── SKILL.md          # OpenClaw 技能入口
└── __init__.py       # 导出
```

## License

MIT