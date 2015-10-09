#Mac OS X 下Hexo的搭建教程
hexo的官网<http://hexo.io>上本来是有搭建教程的，可太过精简，身边好多小伙伴都弄不成功。所以我写一个麻烦版的，反正亲测是成功的。

- 安装 cURL： 复制并粘贴入iTerm内 

```
curl https://raw.github.com/creationix/nvm/master/install.sh | sh
```

- 安装brew 详见<http://brew.sh>

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"


brew install wget
```
- 安装 Wget  

```
 wget -qO- https://raw.github.com/creationix/nvm/master/install.sh | sh
```
- 重启iTerm

```
nvm install 0.10
```

- 安装 Hexo

```
npm install -g hexo-cli
```
`输入  which hexo   如有路径则证明安装成功`

- 创建并进入一个博客文件夹（略）

```
hexo init


npm install
```
- 新建博客

```
hero new “博客标题"
```
- 把.md的播客文件转换成html网页格式 

```
hexo g
```

- 把博客推送到本地服务器          

```
hexo s
```
`可以进入终端所提示的地址查看一下html效果`

- 注册github账号并且创建同名的repository账号： yourGitHubName/yourGitHubName.github.io

- 部署到github上，在你的博客文件夹下编辑文件 _config.yml

                   deploy：
                       type: git
                       repository: git@github.com:yourGitHubName/yourGitHubName.github.io.git
                       branch: master
          （严格遵守缩进格式，第二行空4格，冒号后空1格  ）

```
npm install hexo-deployer-git --save


ssh-keygen -t rss -C “你的邮箱地址"
```
会在家目录下生成一个.ssh文件夹，里面包含两个文件，cat 一下 id_rsa.pub 文件，复制其内容。打开自己的github设置里有一个SSH Keys，添加key（在这里粘贴，名字随意起）。

```
hexo g

hexo d     
```
到此，直接进入 yourGitHubName.github.io 就可以访问了