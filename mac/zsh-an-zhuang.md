# zsh 安装 简明步骤

## 安装 zsh

一般Mac自带了zsh，但是并不是最新版本。我们用homebrew来安装到最新的版本。

```
brew install zsh
```

确认安装

```
zsh --version
```

## 安装 oh-my-zsh

```
curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh
```

## 修改默认shell

```
chsh -s /usr/local/bin/zsh
```

## 最后

重启Terminal。

## 还原默认shell

```
chsh -s /bin/bash
```



