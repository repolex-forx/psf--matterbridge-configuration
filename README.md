# Repolex Knowledge Graph of psf/matterbridge-configuration

RDF knowledge graph data for [psf/matterbridge-configuration](https://github.com/psf/matterbridge-configuration), parsed by [repolex](https://repolex.ai).

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
rlex download psf/matterbridge-configuration
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 099868bb00499b593c325dc1d170d849bb91cd2b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 099868bb00499b593c325dc1d170d849bb91cd2b
│           └── chunk-001.nq.gz
├── blob
│   ├── 01baad5e18e6e9d3c03175b0805ef45fc2ab07d9.nq.gz
│   ├── 06d55b878118bf512a7aedd4d5986f8281c9cf74.nq.gz
│   ├── 0aacdea9305720317900c1e06b1e204de77a20c9.nq.gz
│   ├── 0dab66fcdcb494ea60248241514b96a9f394d405.nq.gz
│   ├── 630636127cb1d19cbd20e869686b185028fb5e91.nq.gz
│   ├── 644431f1b7a1f1b9fb12877768ae528905573792.nq.gz
│   ├── 7668f1041c743083bc4f1d7ab290203b20dda292.nq.gz
│   ├── a0e803991575831e603f9452b73bdd9797951a69.nq.gz
│   ├── b39182aa2c8c7ffef682495545468ed3dfaedf7e.nq.gz
│   ├── d6f216745c22a62ff962ffd193363662cbee1fb9.nq.gz
│   └── da10f7446789c1951883bcdbce91c6f0f21d3564.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 099868bb00499b593c325dc1d170d849bb91cd2b.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 18 files
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

[psf/matterbridge-configuration](https://github.com/psf/matterbridge-configuration)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
