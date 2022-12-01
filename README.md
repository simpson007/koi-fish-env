# 我的开发环境

## 使用方法

1. 安装最新版 Docker 客户端
2. 打开 Docker 客户端的配置
    1. 找到 Docker Engine 选项卡，配置 registry-mirrors（自行搜索教程）
    2. 找到 Resources 选项卡，配置 Proxies（可跳过）
3. `git clone https://github.com/FrankFang/oh-my-env-1.git` 
4. 打开 Windows 的终端，运行 `docker network create network1`
5. 打开 VSCode
    1. 安装 Remote - Container 插件
    2. 打开 koi-fish-env 目录
    3. 输入 Ctrl + Shift + P，然后输入 Reopen，回车，等待
6. 等上一步启动完毕之后，新建终端
    1. 运行 `nvm use system` 和 `node --version` 得到 node 运行环境
    2. 运行 `rvm use 3` 和 `ruby --version` 得到 ruby 运行环境

## 如何升级



1. 删掉本地的旧镜像

    ```bash
    docker rmi simpson007/koi-fish-docker:koi-fish
    ```
2. 删除之前的 koi-fish-env 目录，下载最新的 koi-fish-env，然后用 VSCode 打开，输入 Ctrl + Shift + P，然后输入 Reopen，回车，等待
    1. 如果你之前是用 `git clone` 下载的 koi-fish-env，那么你也可以用 `git pull` 命令来更新代码

## 如何 trojan

1. 运行 `code ~/.config/trojan.conf`，将你自己购买的 trojan 服务器的 JSON 配置复制进去，保存文件
2. 运行命令 `fq`
    * 这是我写在 bashrc 里的 alias，会去运行 `trojan` 命令
    * 这个命令会在后台运行，运行日志在 /tmp/trojan.log
    * 如果你想关闭它，可以运行 `killall trojan` 命令
4. 如果你的本地代理端口不是 1080， 那么你需要运行 `code ~/.config/proxychains.conf`，将 1080 改为你的端口，然后保存文件
5. 在你的任意命令前加 pc 即可，例如：
    1. pc git clone git@xxxxx
    2. pc curl -L https://twitter.com

