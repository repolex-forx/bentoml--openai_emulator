# Repolex Knowledge Graph of bentoml/openai_emulator

RDF knowledge graph data for [bentoml/openai_emulator](https://github.com/bentoml/openai_emulator), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download bentoml/openai_emulator
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ee306ddfdc7b01f8e2ec3d1bd79661009be67df6
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ee306ddfdc7b01f8e2ec3d1bd79661009be67df6
│           └── chunk-001.nq.gz
├── blob
│   ├── 09d04a52980c07b528bb695e619a3f6984fd9f78.nq.gz
│   ├── 180899bca26bf9d922a61355809818076dee60e6.nq.gz
│   ├── 1bddb6e95e101f18b59befba7c0ddf0da6c70131.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2bd31fdd2a3d290b651cd0f5dbdb52946aa061dd.nq.gz
│   ├── 2cb624b139e74257d9e20ddd4396e03aa4161e34.nq.gz
│   ├── 306d6b7ceb356bd785e1edac04c19a30527267cb.nq.gz
│   ├── b081263ea397487f44789fd4aa4ab2ab8ccec1ff.nq.gz
│   ├── c2510c57723a58154446703b6d64646eb5fdc389.nq.gz
│   ├── d23f66d528f9b47435b70c1510b04b275db659c0.nq.gz
│   ├── e4a4f3f2a27389a457c0c1b6bec3077cb8a1a3f2.nq.gz
│   ├── e70a32c7876f55e3c4c44ff0a17ef0ac6c6b14fa.nq.gz
│   └── f4e455d1cb8376ab64d9f888f6932fb073283640.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ee306ddfdc7b01f8e2ec3d1bd79661009be67df6.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 20 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[bentoml/openai_emulator](https://github.com/bentoml/openai_emulator)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
