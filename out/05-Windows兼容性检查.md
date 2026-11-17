# Windows 兼容性检查结果

## 2. child_process 调用检查

## 3. 平台守卫检查

## 4. 路径和文件系统检查

## 5. Shell 脚本检查

### .sh 文件

- `./.claude/statusline.sh` — shebang: `#!/bin/bash` — PS1: ✗, CMD: ✗
- `./.github/actions/bundle_arch_package/entrypoint.sh` — shebang: `#!/usr/bin/env bash` — PS1: ✗, CMD: ✗
- `./app/assets/bundled/bootstrap/bash.sh` — shebang: ` # We need to prepend a space to all the top-level commands here to prevent` — PS1: ✗, CMD: ✗
- `./app/assets/bundled/bootstrap/bash_body.sh` — shebang: `# Note that WARP_SESSION_ID is expected to have been set when executing commands to` — PS1: ✗, CMD: ✗
- `./app/assets/bundled/bootstrap/bash_init_shell.sh` — shebang: `# command -p resolves the given command with the system default PATH, ensuring the shell` — PS1: ✗, CMD: ✗
- `./app/assets/bundled/bootstrap/bash_init_subshell.sh` — shebang: `# command -p resolves the given command with the system default PATH, ensuring the shell` — PS1: ✗, CMD: ✗
- `./app/assets/bundled/bootstrap/fish.sh` — shebang: `# Note that WARP_SESSION_ID is expected to have been set when executing commands to` — PS1: ✗, CMD: ✗
- `./app/assets/bundled/bootstrap/fish_init_shell.sh` — shebang: `set -g WARP_SESSION_ID @@WARP_SESSION_ID@@` — PS1: ✗, CMD: ✗
- `./app/assets/bundled/bootstrap/fish_init_subshell.sh` — shebang: `set -g WARP_SESSION_ID @@WARP_SESSION_ID@@` — PS1: ✗, CMD: ✗
- `./app/assets/bundled/bootstrap/unknown_init_subshell.sh` — shebang: `  # fish doesn't allow setting variables with `=`, so the easiest cross-shell compatible expression is` — PS1: ✗, CMD: ✗
- `./app/assets/bundled/bootstrap/zsh.sh` — shebang: ` setopt interactivecomments` — PS1: ✗, CMD: ✗
- `./app/assets/bundled/bootstrap/zsh_body.sh` — shebang: `# Note that WARP_SESSION_ID is expected to have been set when executing commands to` — PS1: ✗, CMD: ✗
- `./app/assets/bundled/bootstrap/zsh_init_shell.sh` — shebang: `# Each line starts with a leading space to leave these commands out of history.` — PS1: ✗, CMD: ✗
- `./app/assets/bundled/bootstrap/zsh_init_subshell.sh` — shebang: `# Ensure the histignorespace is set so all subsequent commands are omitted from history.` — PS1: ✗, CMD: ✗
- `./crates/ai/src/hooks/fixtures/factory_layout/acme-factory/agents/reviewer/hooks/reviewer_policy.sh` — shebang: `#!/bin/sh` — PS1: ✗, CMD: ✗
- `./crates/ai/src/hooks/fixtures/factory_layout/acme-factory/hooks/record_shell.sh` — shebang: `#!/bin/sh` — PS1: ✗, CMD: ✗
- `./crates/ai/src/hooks/fixtures/sample_project/.cursor/scripts/audit.sh` — shebang: `#!/bin/sh` — PS1: ✗, CMD: ✗
- `./crates/ai/src/hooks/fixtures/sample_project/.cursor/scripts/deny_dangerous.sh` — shebang: `#!/bin/sh` — PS1: ✗, CMD: ✗
- `./crates/ai/src/hooks/fixtures/sample_project/.cursor/scripts/log_prompt.sh` — shebang: `#!/bin/sh` — PS1: ✗, CMD: ✗
- `./crates/ai/src/hooks/fixtures/sample_project/.cursor/scripts/session_env.sh` — shebang: `#!/bin/sh` — PS1: ✗, CMD: ✗

### .ps1 / .cmd 文件

- `./app/assets/bundled/bootstrap/pwsh.ps1`
- `./app/assets/bundled/bootstrap/pwsh_init_shell.ps1`
- `./script/windows/bootstrap.ps1`
- `./script/windows/build_inno_sign_tool_command.ps1`
- `./script/windows/bundle.ps1`
- `./script/windows/install_build_deps.ps1`
- `./script/windows/prepare_bundled_resources.ps1`
- `./script/windows/test_tui_installer.ps1`

## 6. 信号处理检查

## 7. 符号链接检查

## 8. CI/CD 配置检查

### GitHub Actions

| 工作流 | Runner | 排除 Windows? |
|--------|--------|--------------|
| `changelog_draft.yml` |     runs-on: namespace-profile-ubuntu-small | — 仅 Linux/macOS |
| `check_approvals.yml` |     runs-on: ubuntu-latest | — 仅 Linux/macOS |
| `ci.yml` |     runs-on: ubuntu-latest,          - os: "macos",          - os: "linux",          - os: "windows",    runs-on: ${{ matrix.runner }} | ✓ 包含 Windows |
| `create_release.yml` |       build_macos:,      build_macos:,    runs-on: ubuntu-latest,    runs-on: macos-26-xlarge,          target_os: macos | ⚠ 排除/跳过 Windows |
| `cut_new_release_candidate.yml` |     runs-on: ubuntu-latest,    runs-on: ubuntu-latest | — 仅 Linux/macOS |
| `cut_new_releases.yml` |     runs-on: ubuntu-latest,    runs-on: ubuntu-latest | — 仅 Linux/macOS |
| `delete_release.yml` |     runs-on: ubuntu-latest | — 仅 Linux/macOS |
| `docubot_reply_to_comment.yml` |     runs-on: namespace-profile-ubuntu-20-04 | — 仅 Linux/macOS |
| `feature_flag_cleanup.yml` |     runs-on: namespace-profile-ubuntu-small,    runs-on: namespace-profile-ubuntu-small,    runs-on: namespace-profile-ubuntu-small | — 仅 Linux/macOS |
| `label_external_contributors.yml` |     runs-on: ubuntu-latest | — 仅 Linux/macOS |
| `notify-docs-settings-changed.yml` |     runs-on: ubuntu-latest | — 仅 Linux/macOS |
| `populate_build_cache.yml` |  | — 仅 Linux/macOS |
| `publish-agent-dev-image.yml` |     runs-on: namespace-profile-ubuntu-small | — 仅 Linux/macOS |
| `repo-sync.yml` |  | — 仅 Linux/macOS |
| `stale_requested_changes_prs.yml` |     runs-on: ubuntu-latest | — 仅 Linux/macOS |
| `sync-pr-checks.yml` |     runs-on: ubuntu-slim | — 仅 Linux/macOS |
| `update-dedupe-local.yml` |  | — 仅 Linux/macOS |
| `update-pr-review-local.yml` |  | — 仅 Linux/macOS |
| `update-triage-local.yml` |  | — 仅 Linux/macOS |

## 9. Docker / 容器检查

- `./.github/actions/bundle_arch_package/Dockerfile`
  基础镜像: FROM archlinux:base-devel
- `./app/tests/ssh/Dockerfile`
  基础镜像: FROM ubuntu:latest
- `./docker/agent-dev/Dockerfile`
  基础镜像: FROM ubuntu:24.04
- `./docker/linux-dev/Dockerfile`
  基础镜像: FROM debian:sid

> 注意: Dockerfile 假定 Linux 容器环境，不会在 Windows 原生运行。

## 检查总结

以上为自动化扫描结果。AI 应结合脚本输出和源代码分析，生成完整的 Windows 兼容性报告。
