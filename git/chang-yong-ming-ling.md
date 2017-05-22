# Git 常用命令

## 删除 untracked files

使用 `git clean`命令

```
# 删除 untracked files
git clean -f

# untracked 的目录也一起删掉
git clean -fd

# 删除 gitignore 里面的文件和目录
git clean -x

# 查看哪些文件会被删掉，加上参数 -n
git clean -nf
git clean -nfd
```

## 取消已经 add 的文件（取消暂存区域中的文件）

使用`git reset`命令

```
git add .
git reset HEAD <file>
```

取消对文件的修改（回退到修改之前的版本）

## 参考

[https://git-scm.com/book/zh/v1](https://git-scm.com/book/zh/v1)



