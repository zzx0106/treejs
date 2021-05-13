# 树状列表生成器

```
node tree.js -h // 查看所有的指令
```
## 下面是指令：
```
  .option('-d, --directory [dir]', '指定文件夹，不填就是当前文件夹', process.cwd())
  .option('-i, --ignore [ig]', '使用"a|b|c|d"来过滤文件')
  .option('-r, --regexp [rg]', '使用"正则"来过滤文件')
  .option('-e, --export [epath]', '输出路径')
  .option('-f, --only-folder', '是否只输出文件夹名称')
```

比如我想排除掉node_modules等文件夹

```
node tree.js -i "node_modules|.idea|.git|dist|t|medias|images" -e tree.md
```

注：-i后面接需要排除的文件夹，打印出来会有文件夹名，但不会有内部文件名
-e 为输出路径，其实还可以不用-e
例如

```
node tree.js -i "node_modules|.idea|.git|dist|t|medias|images" >> tree.md
```

使用>> 一样能输出，>>输出的是console打印的内容。vue-cli打印config也是用的>>

## 正则细化：

建议正则只对文件进行操作，比如我想在上面的基础上再过滤掉所有的.md和.json文件
```
node tree.js -i "node_modules|.idea|.git|dist|t|medias|images" -r ".md|.json" -e tree.md
```