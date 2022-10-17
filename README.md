# 简介

NvChad 中有两个自带的重要工具
- Mason: 用于安装第三方编辑器的插件二进制文件 (比如 Vscode)，并让 nvim 能够使用这个插件
- Packer: nvim 的插件管理器之一 ( Packer 本身也是 nvim 的一个插件 )

需要注意的是： Mason 本身并不管理插件， 它只负责管理插件的二进制文件。 nvim 插件管理是 Packer 的工作

# 如何加入插件

若希望加入插件 "github/copilot"， 则在 custom/plugins/init.lua 中加入一行如下代码

```lua

-- ...

["github/copilot"] = {
    -- 花括号内配置 "github/copilot" 这个插件的配置
}
```

最后运行 `:PackerInstall` 即可
PS: 'PackerInstall' 会根据配置文件安装还未安装的插件


# 如何更改插件的配置

若希望更改插件 "github/copilot" 的配置， 则在 custom/plugins/init.lua 中修改 `["github/copilot"] = {...}` 花括号中的内容
最后运行 `:PackerCompile` 来让更改生效

PS: 每次更新 Packer 管理的插件的配置时， 都需要运行一下 `PackerCompile` 来让变更生效 


# 依赖

Mason 需要安装以下 LSP:
- python-lsp-server
- gopls: 提供了重命名， 语法高亮， lint 功能方面有问题需要依赖 golangci_lint_ls
- golangci_lint_ls: 提供 lint 功能
- marksman: markdown 语法 LSP



