README.md - Versão Inicial
markdown# Codex_DT Core

> Production-ready RAG pipeline with multi-tenant isolation and chaos resilience.

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Node](https://img.shields.io/badge/node-%3E%3D18.0.0-brightgreen)

## 🎯 What is Codex_DT Core?

A tier-zero RAG system designed for **single-player efficiency** and **production-grade reliability**. Built with the philosophy that infrastructure should be governed, not just orchestrated.

### Key Features

- ⚡ **970 TPS** @ 100 concurrent pipelines
- 🔒 **100% tenant isolation** verified at 12k scale
- 🛡️ **Zero cascade failures** in chaos engineering
- 💾 **12KB memory per pipeline** (144MB @ 12k batch)
- 🎯 **T0-T4 cognitive tiers** for structured execution

## 🏗️ Architecture
```
T0 → Dispatcher      Multi-tenant routing & retry logic
T1 → Context Builder Contextual data assembly
T2 → Retriever       Vector search & semantic matching
T3 → Generator       LLM integration & response generation
T4 → Refiner         Response optimization & validation
```

## 🚀 Quick Start

### Installation
```bash
npm install @codex-dt/core
```

### Basic Usage
```typescript
import { Codex } from '@codex-dt/core';

const pipeline = new Codex({
  supabaseUrl: process.env.SUPABASE_URL,
  supabaseKey: process.env.SUPABASE_KEY,
});

const result = await pipeline.execute({
  playerId: 'user-123',
  query: 'What is the capital of France?',
  context: { /* optional context */ }
});

console.log(result.response);
```

## 📊 Performance Benchmarks

| Concurrent Pipelines | TPS | Latency (p50) | Memory |
|---------------------|-----|---------------|--------|
| 100                 | 970 | 103ms         | 1.2MB  |
| 1,000               | 593 | 168ms         | 13.5MB |
| 10,000              | 99  | 1,010ms       | 144MB  |

**Test Environment:** Node v20, PostgreSQL v15, Mock LLM mode

See [BENCHMARKS.md](./docs/BENCHMARKS.md) for detailed methodology.

## 🔒 What's NOT Included

Core is execution-focused. Missing enterprise features:

- ❌ Hallucination detection (T5 - Pro tier)
- ❌ Encryption layer (T6 - Pro tier)  
- ❌ Advanced telemetry (T7 - Pro tier)
- ❌ Meta-governance (Ω Layer - Sovereign tier)

→ Interested in enterprise features? [Contact us](mailto:cristiano@codeark.com.br)

## 📚 Documentation

- [Architecture Deep Dive](./docs/ARCHITECTURE.md)
- [API Reference](./docs/API_REFERENCE.md)
- [Performance Benchmarks](./docs/BENCHMARKS.md)
- [Migration Guide](./docs/MIGRATION_GUIDE.md)

## 🛠️ Requirements

- Node.js ≥ 18.0.0
- PostgreSQL ≥ 14 (with pgvector extension)
- Supabase account (or self-hosted)

## 🤝 Contributing

Contributions are welcome! See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

## 📜 License

MIT - See [LICENSE](./LICENSE)

## 🌟 Roadmap

- [ ] Plugin system for custom tiers
- [ ] CLI tools for pipeline management
- [ ] Docker Compose setup
- [ ] Horizontal scaling guide
- [ ] Benchmark comparison with LangChain/LlamaIndex

## 🔗 Related Projects

- [Arqos Engine](https://github.com/Scatlyus/arqos-engine) - Governed orchestration framework
- [CodeArk](https://github.com/Scatlyus/codeark) - Multi-agent AI system

## 💬 Community & Support

- 🐛 [Report a bug](https://github.com/Scatlyus/Codex_DT_Core/issues)
- 💡 [Request a feature](https://github.com/Scatlyus/Codex_DT_Core/issues)
- 📧 Email: cristiano@codeark.com.br
- 🌐 Website: [codeark.com.br](https://codeark.com.br)

---

Built with ⚡ by [Cristiano](https://github.com/Scatlyus) | Powered by [Arqos Engine](https://github.com/Scatlyus/arqos-engine)
```
