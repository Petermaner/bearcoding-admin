1. 进入工作目录，git下载最新代码

```bash
cd /usr/local/soft/workspace/
git clone git@github.com:Petermaner/bearcoding-admin.git
```

2. 安装

```bash
npm install
cnpm install

# npm install 安装失败，请升级 nodejs 到 16 以上，或尝试使用以下命令：
npm install --registry=https://registry.npm.taobao.org

# npm install 如果出现 npm ERR! code ECONNRESET 错误，可尝试执行以下命令后再安装
npm config set registry http://registry.npmjs.org/
```

3. dev测试

```bash
npm run dev
```

4. 生产环境

```bash
1、执行 npm run build:pro，生成 dist 目录
2、将 dist 目录上传到服务器的 /home/admin/ 目录下
3、采用 Nginx ，在 server 节点下进行 location 配置。
location ^~ /admin-view {
	alias /home/admin/dist/; # 根 目 录
	index index.html;
}
```

