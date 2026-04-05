# 🚀 Lateralus Quickstart

> Hit **"Use this template"** above to create your own Lateralus project in seconds.

[![Lateralus](https://img.shields.io/badge/language-Lateralus-7c5cfc?style=flat-square)](https://github.com/bad-antics/lateralus-lang)
[![VS Code](https://img.shields.io/badge/editor-VS%20Code-007ACC?style=flat-square&logo=visualstudiocode)](https://marketplace.visualstudio.com/items?itemName=lateralus.lateralus-lang)
[![PyPI](https://img.shields.io/badge/pip-lateralus--lang-34d399?style=flat-square&logo=pypi)](https://pypi.org/project/lateralus-lang/)

---

## What's Inside

```
your-project/
├── src/
│   ├── main.ltl          # Entry point
│   ├── utils.ltl         # Helper functions
│   └── models.ltl        # Data models
├── tests/
│   └── test_main.ltl     # Example tests
├── lateralus.toml        # Project config
├── .github/workflows/
│   └── ci.yml            # CI pipeline (ready to go)
└── README.md             # You are here
```

## Quick Start

### 1. Install Lateralus

```bash
pip install lateralus-lang
```

### 2. Run the project

```bash
lateralus run src/main.ltl
```

### 3. Run tests

```bash
lateralus test
```

You should see:

```
✓ greet returns formatted string
✓ pipeline transforms data correctly
✓ User model validates fields

3 passed, 0 failed
```

## VS Code Support

Install the [Lateralus extension](https://marketplace.visualstudio.com/items?itemName=lateralus.lateralus-lang) for:

- 🎨 Syntax highlighting
- 📝 Snippets (`ltlfn`, `ltlpipe`, `ltlstruct`, etc.)
- 🔍 Bracket matching & auto-indent

```bash
code --install-extension lateralus.lateralus-lang
```

## What is Lateralus?

Lateralus is a modern programming language built around **pipelines**, **pattern matching**, and **expressive syntax**.

```lateralus
// Pipeline-driven data transformation
let result = data
    |> filter(x => x.score > 80)
    |> map(x => { ...x, grade: calculate_grade(x.score) })
    |> sort_by(.grade)
    |> take(10)

// Pattern matching
match response {
    { status: 200, body } => process(body),
    { status: 404 }       => log("not found"),
    { status }             => error("unexpected: ${status}")
}
```

## Learn More

| Resource | Link |
|---|---|
| 📖 Learn Lateralus | [Tutorial](https://github.com/bad-antics/learn-lateralus) |
| 📚 Language Repo | [lateralus-lang](https://github.com/bad-antics/lateralus-lang) |
| 🎮 Playground | [Try Online](https://bad-antics.github.io/lateralus/playground.html) |
| 💡 Examples | [lateralus-examples](https://github.com/bad-antics/lateralus-examples) |
| 🌐 Website | [bad-antics.github.io/lateralus](https://bad-antics.github.io/lateralus/) |

## License

MIT — use this template for anything.
