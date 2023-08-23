# lvs： lontten 的 version manager
## 起源
fnm 在 nushell 上用不了，于是我打算写一个简单一些的nodejs的版本管理工具。
按理来说，这个工具名字应该叫 lnm 的。 lontten 的 node 版本管理工具。
不过 lnm 输入时有些不顺手，于是就叫了 lvs -- lontten 的 version manager 



```shell

lvs list
展示所有的本地的node版本列表
简写 lvs ls
展示效果

node list:
   15.1.1
   15.1.1 default
   15.1.1 lts
   15.1.1 default lts

╭───┬─────────┬─────┬─────────╮
│ # │ version │ lts │ default │
├───┼─────────┼─────┼─────────┤
│ 0 │ v15.1.1 │ lts │         │
│ 1 │ v15.1.1 │     │         │
│ 2 │ v15.1.1 │     │         │
│ 3 │ v15.1.1 │ lts │ default │
╰───┴─────────┴─────┴─────────╯
# 查看下一页请输入 lvs list-remote 2 // lvs lsr 2
# 已经到最后一页--每页默认10条

//设置默认版本
# lvs use 0
# lvs use v15.1.1
// set default is v15.1.1 success

//卸载某个版本
# lvs uninstall 0
# lvs uninstgall v15.1.1
# lvs ui 0
# lvs ui v15.1.1
// uninstall v15.1.1 success

# lvs list-remote
展示所有的远程的node版本列表
简写 lvs lsr
展示效果--current展示非lts版本，从最新到最旧，lts展示所有lts版本，从最新到最旧
╭───┬─────────┬───┬─────────╮
│ # │ current │ # │ lts     │
├───┼─────────┼───┼─────────┤
│ 0 │ v15.1.1 │ 4 │ v15.1.1 │
│ 1 │ v15.1.1 │ 5 │ v15.1.1 │
│ 2 │ v15.1.1 │ 6 │ v15.1.1 │
│ 3 │ v15.1.1 │ 7 │ v15.1.1 │
╰───┴─────────┴───┴─────────╯
# 查看下一页请输入 lvs list-remote 2 // lvs lsr 2
# 已经到最后一页--每页默认10条

# lvs set pageSize 30 //设置每页30条

// 安装某个版本
# lvs install 0
# lvs instgall v15.1.1
# lvs i 0
# lvs i v15.1.1
// install v15.1.1 success

```