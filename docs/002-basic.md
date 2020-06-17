# basic
> 一个 hello world 级别的小例子。

## steps
1. 初始化一个 mini 的 `config.rb`;
   ```shell
   mina init
   ```
2. 这样在 `config/deploy.rb` 会有一些代码产生; 需要修改对应的配置信息。
3. 在 `mina deploy` 之前需要执行一次： `mina setup`
   1. 这个做的事情也比较简单
   2. 登录服务器，建立你配置好的目录如： `/root/data/dev.com`，大体的目录结构如下：
    ~~~
    [root@liebian:~/data/dev.com]
    $ tree -L 2
    .
    ├── current -> /root/data/dev.com/releases/2
    ├── releases
    │   ├── 1
    │   └── 2
    ├── scm
    │   ├── FETCH_HEAD
    │   ├── HEAD
    │   ├── branches
    │   ├── config
    │   ├── description
    │   ├── hooks
    │   ├── info
    │   ├── objects
    │   ├── packed-refs
    │   └── refs
    ├── shared
    │   ├── log
    │   ├── public
    │   ├── tmp
    │   └── vendor
    └── tmp


    ~~~
3. 基本原理是：
   1. nginx 指向 ~/data/dev.com/current
   2. current 会指向每次的最新的 release/xx-version 版本
   3. tmp 是临时文件
