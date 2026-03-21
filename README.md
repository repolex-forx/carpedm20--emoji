# Repolex Knowledge Graph of carpedm20/emoji

RDF knowledge graph data for [carpedm20/emoji](https://github.com/carpedm20/emoji), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download carpedm20/emoji
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── blob
│   ├── 1ef1fadbace531581f71632d374b4bfee9011854.nq.gz
│   ├── 31295c5967d1cfaeaf84e4a9d9dd17fd3962ee32.nq.gz
│   ├── 379d4ae693de1db9d3e350e48f4849710ca41c54.nq.gz
│   ├── 4340aaa95adaf306ddf062657fab185eef7d79ef.nq.gz
│   ├── 464abcc522a6237054e9abf5c0c61ae72e51cd0f.nq.gz
│   ├── 5fd08e5889e32c495e8759515c4961aed339c73d.nq.gz
│   ├── 6460c5bcec9cc500df7b9a52a792180f502ae4d9.nq.gz
│   ├── 70b4e4ac69ef4247fbd6faa321bba12d6ab555c2.nq.gz
│   ├── 76f59c6dc2914132f7ed22594c24920106caf73e.nq.gz
│   ├── 7cc296b1d589d656e9acb09d8e03a147d162d2c6.nq.gz
│   ├── 83376853e7bd76db7f3cbe29663f348b4e905cdd.nq.gz
│   ├── 854fef17c52a6e4570a835156d84569d8d80156c.nq.gz
│   ├── 92b944ff18e84d9dd5ef9f292011d0773d579b9a.nq.gz
│   ├── 9bbeb77e0b88377a29b41e94f299e33532565315.nq.gz
│   ├── c1cebb5b61c20e129e58b0f5f8e9e8f5decb572a.nq.gz
│   ├── c26e9f641117b85727f2a18f238e287620aedf60.nq.gz
│   ├── c9fcc001aa705963e0e5f387b8ea798039fe0279.nq.gz
│   ├── d7c939c152f605ce9cbccd52c0f6cb2842eb5e0f.nq.gz
│   ├── eb4f4d084530dd790b3978a51095613f64d4bedd.nq.gz
│   └── f89c587382cfca46c51f64c55525c7bf292ee885.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b3b70368b86e269f1e53079862a708e1e377cfbb.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

8 directories, 26 files
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

## Source repository

[carpedm20/emoji](https://github.com/carpedm20/emoji)

---
*Parsed on 2026-03-21 by [repolex](https://repolex.ai)*
