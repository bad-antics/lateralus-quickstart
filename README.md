# lateralus-quickstart

> The official starter template for Lateralus applications.

Fork this repo to bootstrap a new project — batteries included.

## Project Layout

```
lateralus-quickstart/
├── src/
│   ├── main.ltl          # entry point
│   ├── models.ltl         # data models
│   ├── utils.ltl          # shared helpers
│   ├── config.ltl         # Config struct + from_env / from_file
│   ├── logger.ltl         # structured logger (Level enum, ANSI colours)
│   ├── router.ltl         # HTTP router with :param pattern matching
│   ├── middleware.ltl     # logging / CORS / auth / rate-limit middleware
│   ├── db.ltl             # database abstraction (connect, migrate, CRUD)
│   ├── cache.ltl          # in-memory TTL cache with Arc<Mutex<>>
│   ├── events.ltl         # typed EventEmitter (on/off/once/emit)
│   ├── validator.ltl      # composable validators (email, range, combine)
│   ├── pagination.ltl     # offset + cursor pagination helpers
│   └── scheduler.ltl      # cron-style async task scheduler
├── tests/
│   ├── test_main.ltl      # main module tests
│   ├── test_config.ltl    # 3 config tests
│   ├── test_validator.ltl # 6 validator tests
│   ├── test_cache.ltl     # 5 cache tests
│   └── test_pagination.ltl# 4 pagination tests
└── examples/
    ├── hello.ltl          # minimal hello world
    ├── http_demo.ltl      # router + middleware chain demo
    └── db_demo.ltl        # SQLite CRUD demo
```

## Quick Start

```bash
# 1. Fork / clone
git clone https://github.com/YOUR_USERNAME/lateralus-quickstart my-app
cd my-app

# 2. Run
ltl run src/main.ltl

# 3. Test
ltl test tests/

# 4. Try an example
ltl run examples/http_demo.ltl
```

## Key Patterns

```lateralus
// Config from environment
let cfg = Config.from_env()

// Logger
let log = Logger.new(Level.Info)
log.info("server started on :${cfg.port}")

// Router
let router = Router.new()
    |> route("GET", "/users/:id", get_user)
    |> route("POST", "/users",    create_user)

// Middleware pipeline
let app = router |> with(logging_mw) |> with(cors_mw) |> with(auth_mw)

// Async scheduler
let sched = Scheduler.new()
sched.every_minutes(5, || flush_cache())
sched.run().await
```

## Language

This project uses [Lateralus](https://github.com/bad-antics/lateralus-lang) — a systems-level
language with first-class pipelines (`|>`), async/await, algebraic types, and a Rust-inspired
ownership model.

- Compiler: [lateralus-compiler](https://github.com/bad-antics/lateralus-compiler)
- Learn: [learn-lateralus](https://github.com/bad-antics/learn-lateralus)
- Examples: [lateralus-examples](https://github.com/bad-antics/lateralus-examples)
