# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A Hugo static site (PaperMod theme, Chinese locale `zh-cn`) that documents five open-source LLM infrastructure projects "from scratch": **vllm** (inference), **ms-swift** (training), **slime** (agentic RL), **harbor** (docker & agentic evaluation), and **Megatron-LM** (GPU-optimized training). Content is written in Chinese under `content/posts/`, and deployed to GitHub Pages at `https://xiyuanyang-code.github.io/LLMInfraDocs`.

## Commands

Requires Hugo CLI (`dpkg -i hugo_*.deb` per README; the workflow uses v0.146.0). The PaperMod theme is a git submodule:

```bash
git submodule update --init --recursive   # fetch the theme after cloning
hugo serve                                 # local dev server (repo root)
hugo new content content/posts/<name>.md  # new post (created as draft)
hugo                                       # build site into ./public (gitignored)
```

Deployment is push-driven: pushing to `main` triggers `.github/workflows/gh-pages.yaml`, which builds with `--buildDrafts` (so drafts are published) and deploys `./public` to GitHub Pages. There is no test suite, linter, or build config to run beyond `hugo`.

## Architecture

- `content/` — all site content. Posts use TOML frontmatter (`+++`); `content/posts/` holds articles, `content/about.md` and `content/search.md` are special pages. Set `draft = true` while writing.
- `hugo.yaml` — all site configuration (baseURL, menu, params, KaTeX math flag). `params.math: true` is set globally.
- `layouts/partials/extend_head.html` — injects KaTeX (CDN) for LaTeX math rendering, active when `math` is true in frontmatter or site params.
- `themes/PaperMod` — git submodule of `adityatelange/hugo-PaperMod`; the deploy workflow updates it to latest remote commit.
- `code/` — **gitignored**; not part of the built site. Contains standalone git clones of the five upstream projects (each has its own `.git`), used as source material for writing docs. If a post describes behavior of one of these projects, read its source (and its own `AGENTS.md`/`CLAUDE.md`, e.g. `code/vllm/CLAUDE.md`) under `code/<project>/`.
- `.github/workflows/gh-pages.yaml` — CI/CD to GitHub Pages.
- `public/` — gitignored Hugo build output.

## Gotchas

- `code/` and `public/` are gitignored — never commit them.
- The git remote is `xiyuanyang-code/LLMInfraDocs.git` even though the local directory is `LLMInfra`.
- KaTeX delimiters are `$$`/`\(`/`\[` for display math, `$`/`\(` for inline.
