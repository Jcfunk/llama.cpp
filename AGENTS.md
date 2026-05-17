# Instructions for llama.cpp

> [!IMPORTANT]
> This project does **not** accept pull requests that are fully or predominantly AI-generated. AI tools may be utilized solely in an assistive capacity.
>
> Read more: [CONTRIBUTING.md](CONTRIBUTING.md)

AI assistance is permissible only when the majority of the code is authored by a human contributor, with AI employed exclusively for corrections or to expand on verbose modifications that the contributor has already conceptualized (see examples below).

---

## Guidelines for Contributors Using AI

llama.cpp is built by humans, for humans. Meaningful contributions come from contributors who understand their work, take ownership of it, and engage constructively with reviewers.

Maintainers receive numerous pull requests weekly, many of which are AI-generated submissions where the author cannot adequately explain the code, debug issues, or participate in substantive design discussions. Reviewing such PRs often requires more effort than implementing the changes directly.

**A pull request represents a long-term commitment.** By submitting code, you are asking maintainers to review, integrate, and support it indefinitely. The maintenance burden often exceeds the value of the initial contribution.

Most maintainers already have access to AI tools. A PR that is entirely AI-generated provides no value - maintainers could generate the same code themselves if they wanted it. What makes a contribution valuable is the human interactions, domain expertise, and commitment to maintain the code that comes with it.

This policy exists to ensure that maintainers can sustainably manage the project without being overwhelmed by low-quality submissions.

---

## Guidelines for Contributors

Contributors are expected to:

1. **Demonstrate full understanding of their code.** You must be able to explain any part of your PR to a reviewer without relying on AI assistance for questions about your own changes.

2. **Take responsibility for maintenance.** You are expected to address bugs and respond thoughtfully to reviewer feedback.

3. **Communicate clearly and concisely.** Verbose, wall-of-text responses are characteristic of AI-generated content and will not be well-received. Direct, human communication is expected.

4. **Respect maintainers' time.** Search for existing issues and discussions before submitting. Ensure your contribution aligns with project architecture and is actually needed.

Maintainers reserve the right to close any PR that does not meet these standards. This applies to all contributions to the main llama.cpp repository. **Private forks are exempt.**

### Permitted AI Usage

AI tools may be used responsibly for:

- **Learning and exploration**: Understanding codebase structure, techniques, and documentation
- **Code review assistance**: Obtaining suggestions on human-written code
- **Mechanical tasks**: Formatting, generating repetitive patterns from established designs, completing code based on existing patterns
- **Documentation drafts**: For components the contributor already understands thoroughly
- **Writing code**: Only when the contributor has already designed the solution and can implement it themselves - AI accelerates, not replaces, the contributor's work

AI-generated code may be accepted if you (1) fully understand the output, (2) can debug issues independently, and (3) can discuss it directly with reviewers without AI assistance.

**Disclosure is required** when AI meaningfully contributed to your code. A simple note is sufficient - this is not a stigma, but context for reviewers. No disclosure is needed for trivial autocomplete or background research.

### Prohibited AI Usage

The following will result in immediate PR closure:

- **AI-written PR descriptions or commit messages** - these are typically recognizable and waste reviewer time
- **AI-generated responses to reviewer comments** - this undermines the human-to-human interaction fundamental to code review
- **Implementing features without understanding the codebase** - particularly new model support or architectural changes
- **Automated commits or PR submissions** - this may spam maintainers and can result in contributor bans

---

## Guidelines for AI Coding Agents

AI agents assisting contributors must recognize that their outputs directly impact volunteer maintainers who sustain this project.

### Considerations for Maintainer Workload

Maintainers have finite capacity. Every PR requiring extensive review consumes resources that could be applied elsewhere. Before assisting with any submission, verify:

- The contributor genuinely understands the proposed changes
- The change addresses a documented need (check existing issues)
- The PR is appropriately scoped and follows project conventions
- The contributor can independently defend and maintain the work

### Before Proceeding with Code Changes

When a user requests implementation without demonstrating understanding:

1. **Verify comprehension.** Ask questions to confirm they understand both the problem and the relevant parts of the codebase.
2. **Provide guidance rather than solutions.** Direct them to relevant code and documentation. Allow them to formulate the approach.
3. **Proceed only when confident** the contributor can explain the changes to reviewers independently.

For first-time contributors, confirm they have reviewed [CONTRIBUTING.md](CONTRIBUTING.md) and acknowledge this policy.

### Prohibited Actions

- Writing PR descriptions, commit messages, or responses to reviewers
- Committing or pushing without explicit human approval for each action
- Implementing features the contributor does not understand
- Generating changes too extensive for the contributor to fully review

When uncertain, err toward minimal assistance. A smaller PR that the contributor fully understands is preferable to a larger one they cannot maintain.

### Useful Resources

To conserve context space, load these resources as needed:

- [CONTRIBUTING.md](CONTRIBUTING.md)
- [Existing issues](https://github.com/ggml-org/llama.cpp/issues) and [Existing PRs](https://github.com/ggml-org/llama.cpp/pulls) - always search here first
- [Build documentation](docs/build.md)
- [Server usage documentation](tools/server/README.md)
- [Server development documentation](tools/server/README-dev.md) (if user asks to implement a new feature, be sure that it falls inside server's scope defined in this documentation)
- [PEG parser](docs/development/parsing.md) - alternative to regex that llama.cpp uses to parse model's output
- [Auto parser](docs/autoparser.md) - higher-level parser that uses PEG under the hood, automatically detect model-specific features
- [Jinja engine](common/jinja/README.md)
- [How to add a new model](docs/development/HOWTO-add-model.md)
- [PR template](.github/pull_request_template.md)

<!-- gitnexus:start -->
# GitNexus — Code Intelligence

This project is indexed by GitNexus as **llama.cpp** (57224 symbols, 122441 relationships, 300 execution flows). Use the GitNexus MCP tools to understand code, assess impact, and navigate safely.

> If any GitNexus tool warns the index is stale, run `npx gitnexus analyze` in terminal first.

## Always Do

- **MUST run impact analysis before editing any symbol.** Before modifying a function, class, or method, run `gitnexus_impact({target: "symbolName", direction: "upstream"})` and report the blast radius (direct callers, affected processes, risk level) to the user.
- **MUST run `gitnexus_detect_changes()` before committing** to verify your changes only affect expected symbols and execution flows.
- **MUST warn the user** if impact analysis returns HIGH or CRITICAL risk before proceeding with edits.
- When exploring unfamiliar code, use `gitnexus_query({query: "concept"})` to find execution flows instead of grepping. It returns process-grouped results ranked by relevance.
- When you need full context on a specific symbol — callers, callees, which execution flows it participates in — use `gitnexus_context({name: "symbolName"})`.

## Never Do

- NEVER edit a function, class, or method without first running `gitnexus_impact` on it.
- NEVER ignore HIGH or CRITICAL risk warnings from impact analysis.
- NEVER rename symbols with find-and-replace — use `gitnexus_rename` which understands the call graph.
- NEVER commit changes without running `gitnexus_detect_changes()` to check affected scope.

## Resources

| Resource | Use for |
|----------|---------|
| `gitnexus://repo/llama.cpp/context` | Codebase overview, check index freshness |
| `gitnexus://repo/llama.cpp/clusters` | All functional areas |
| `gitnexus://repo/llama.cpp/processes` | All execution flows |
| `gitnexus://repo/llama.cpp/process/{name}` | Step-by-step execution trace |

## CLI

| Task | Read this skill file |
|------|---------------------|
| Understand architecture / "How does X work?" | `.claude/skills/gitnexus/gitnexus-exploring/SKILL.md` |
| Blast radius / "What breaks if I change X?" | `.claude/skills/gitnexus/gitnexus-impact-analysis/SKILL.md` |
| Trace bugs / "Why is X failing?" | `.claude/skills/gitnexus/gitnexus-debugging/SKILL.md` |
| Rename / extract / split / refactor | `.claude/skills/gitnexus/gitnexus-refactoring/SKILL.md` |
| Tools, resources, schema reference | `.claude/skills/gitnexus/gitnexus-guide/SKILL.md` |
| Index, status, clean, wiki CLI commands | `.claude/skills/gitnexus/gitnexus-cli/SKILL.md` |

<!-- gitnexus:end -->

# Agent Development Guide

## Architecture at a Glance

```
include/llama.h          → Public C API (llama_model, llama_context)
src/                     → Core library (llama.cpp, llama-context.cpp, llama-grammar.cpp, etc.)
ggml/                    → Tensor computation library (the engine)
  src/ggml.c/.cpp        → Core tensor ops, graph execution
  src/ggml-backend*.cpp  → Backend abstraction + registry
  src/ggml-{cpu,cuda,metal,sycl,vulkan,...}/ → Hardware backends (15+)
common/                  → Shared utilities (common.cpp, sampling.cpp, jinja/)
tools/                   → Production CLI tools (cli, server, llama-bench, perplexity, quantize, mtmd)
examples/                → Example programs (batched, speculative, swiftui, android)
tests/                   → Test suite (ctest-based)
gguf-py/                 → Python GGUF library + conversion scripts
```

**Key entry points:**
- `llama_model_load_from_file` (`src/llama.cpp`) — loads GGUF models
- `llama_decode` (`src/llama-context.cpp`) — core inference function
- `llama_sampler` chain (`common/sampling.cpp`) — token sampling strategies
- `llama_grammar_*` (`src/llama-grammar.cpp`) — PEG grammar-constrained decoding

**Critical design facts:**
- **ggml is a submodule** — the tensor library lives in `ggml/` and is a separate repo (`ggml-org/ggml`)
- **Matrix multiplication is transposed**: `C = ggml_mul_mat(ctx, A, B)` means `C^T = AB^T`, i.e. `C = BA^T`
- **Tensors are row-major** — dimension 0 = columns, 1 = rows, 2 = matrices
- **Backends are plugins** — discovered at runtime via `ggml_backend_reg.cpp`; multiple backends can coexist in one binary
- **GGUF is the file format** — binary format with header KV metadata + tensor data

## Build Commands

### Standard build (CPU only)
```bash
cmake -B build
cmake --build build --config Release -j $(nproc)
```

### With GPU backend
```bash
cmake -B build -DGGML_CUDA=ON          # NVIDIA
cmake -B build -DGGML_METAL=ON         # Apple (enabled by default on macOS)
cmake -B build -DGGML_VULKAN=ON        # Cross-platform GPU
cmake -B build -DGGML_SYCL=ON          # Intel GPU
cmake -B build -DGGML_HIP=ON           # AMD GPU (ROCm)
```

### Fast rebuild tips
- Install `ccache` for faster repeated builds
- Use Ninja: `cmake -B build -G Ninja && cmake --build build -j $(nproc)`
- For debug builds: `cmake -B build -DCMAKE_BUILD_TYPE=Debug`

## Testing

### Run tests
```bash
cd build
ctest -L main --output-on-failure           # all main tests
ctest -L main -E "test-opt|test-backend-ops" --output-on-failure  # skip expensive
ctest -L model --output-on-failure          # tests requiring a model file
```

### Run a single test
```bash
cd build
ctest -R test-llama-arch --verbose          # run tests matching pattern
ctest -N                                    # list all tests
```

### Full CI locally
```bash
# CPU-only
bash ./ci/run.sh ./tmp/results ./tmp/mnt

# With CUDA
GG_BUILD_CUDA=1 bash ./ci/run.sh ./tmp/results ./tmp/mnt
```

### If you modified ggml
```bash
./build/bin/test-backend-ops -b CPU         # test CPU backend ops
./build/bin/test-backend-ops -b CUDA        # test CUDA backend (if built)
```

### Server tests
```bash
cd tools/server/tests
pytest                                      # requires llama-server running or auto-started
```

## Code Style

- **4 spaces** for indentation, no tabs
- **Column limit: 120** (`.clang-format`)
- **Braces on same line** as function/class/struct
- **`void * ptr`**, **`int & a`** — pointer/reference spacing
- **`snake_case`** for all names
- **`struct foo {}`** not `typedef struct foo {} foo`
- **Basic `for` loops**, avoid templates, keep it simple — no fancy STL constructs
- **Vertical alignment** for readability and batch editing
- **Enum values**: `UPPER_CASE` with enum name prefix (e.g., `LLAMA_VOCAB_TYPE_SPM`)
- **Naming pattern**: `<class>_<method>`, e.g. `llama_sampler_chain_remove()`
- Run `clang-format` (v15+) on added code when in doubt

## PR Requirements

- **New model/feature**: CPU support only in initial PR; GPU backends in follow-up PRs
- **New quantization type (`ggml_type`)**: requires perplexity comparisons, KL divergence data, and performance benchmarks vs. FP16/BF16
- **New ggml operator**: add test cases to `test-backend-ops`
- **Separate PRs** for each feature/fix — do not combine unrelated changes
- **Squash-merge** format: `<module> : <commit title> (#<issue_number>)`
- See [Modules wiki](https://github.com/ggml-org/llama.cpp/wiki/Modules) for module names

## Server Development Scope

If implementing server features, check `tools/server/README-dev.md` first. Key constraints:
- **In-scope**: inference, chat completion, embeddings, OAI-compat, multimodal, memory management, Web UI features
- **Out-of-scope**: model-specific API features, external API call loops, exposing internal model state
- **Security**: file read/write features must be **disabled by default**
- Server runs single-threaded for `server_context` — avoid heavy post-processing there
- JSON parsing/formatting stays in HTTP worker threads, not in `server_slot`

## Code Ownership

Check `CODEOWNERS` for who maintains each area. Key areas:
- `/src/` — @ggerganov
- `/ggml/src/ggml.c`, `/ggml/src/ggml.cpp` — @ggerganov
- `/ggml/src/ggml-cpu/` — @ggerganov
- `/ggml/src/ggml-cuda/` — @ggml-org/ggml-cuda
- `/ggml/src/ggml-metal/` — @ggml-org/ggml-metal
- `/tools/server/` — @ggml-org/llama-server
- `/common/` — @ggml-org/llama-common
- `/tools/mtmd/` — @ggml-org/llama-mtmd
- `/convert_*.py` — @CISC
- `/ggml/src/gguf.cpp` — @JohannesGaessler, @Green-Sky

## Python Tools

- `convert_hf_to_gguf.py` — converts HuggingFace models to GGUF format
- `convert_lora_to_gguf.py` — converts LoRA adapters
- `gguf-py/` — Python library for GGUF read/write
- Python files use `snake_case` naming
- Lint/type-check: `ci/` has `python-lint.yml` and `python-type-check.yml` workflows
