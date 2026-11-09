# 中文文件读写规则（重要。本节内容仅适用于Codex。Claude Code直接走默认方式即可，无需理会本节）

- 如果在使用下列流程指定的工具进行中文文件读写时遇到错误、乱码，请务必报告用户；
- Windows 下补丁文件必须通过 `functions.exec` 内的原生 `tools.apply_patch(patch)` 完成；不要在 PowerShell 中调用 `apply_patch`、`apply_patch.bat` 或 `codex --codex-run-as-apply-patch`。禁止使用Unicode编码编写中文（\uXXXX）。
- 该项目为UTF-8编码，PowerShell 的 `Get-Content` 用系统默认编码解读 UTF-8 会显示为乱码，务必记得加上 -Encoding utf8 或用 Node.js `fs.readFileSync(path, 'utf8')` 读取
