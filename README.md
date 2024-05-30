
## Launch Pad

### 📔 修改日志

- 去除了 [imsyy/home](https://github.com/imsyy/home) 项目的 Launch Pad 以外的所有其他功能
- 获取数据从之前的直接从前端代码中获取改为了发请求获取json，目前请求的路径指向为当前项目的`/siteLinks.json`文件，在`npm run build`编译之后，可以通过修改`siteLinks.json`文件来实现数据的重新渲染
- 添加了比较全面的内网服务的图标，可以在`siteLinks.json`中直接调用

### 待修复的问题

- [ ] 通过鼠标滑轮横向滑动页面时，如果包含3页，从第1页滑向第2页后，会自动跳到第3页
- [ ] 通过鼠标按住滑动页面时，如果当前页只有少量卡片，则只有鼠标按住起始点在卡片内时，才可以进行翻页操作，在空白区域无法进行翻页操作

### ⚙️ 手动部署

- **安装** [node.js](https://nodejs.org/zh-cn/) **环境**

  > node > 16.16.0  
  > npm > 8.15.0

- 然后以 **管理员权限** 运行 `cmd` 终端，并 `cd` 到 项目根目录
- 在 `终端` 中输入：

```bash
# 安装依赖
npm install

# 预览
npm run dev

# 构建
npm run build
```

> 构建完成后，静态资源会在 **`dist` 目录** 中生成，可将 **`dist` 文件夹下的文件**上传至服务器，也可使用 `Vercel` 等托管平台一键导入并自动部署

### ⚙️ Docker 部署

#### 手动构建容器

> `/your/config/path/siteLinks.json`：换成宿主机的配置文件

```bash
# 构建
docker build -t launch-pad .
# 运行
docker run -d -p 80:80 -v /your/config/path/siteLinks.json:/usr/share/nginx/html/siteLinks.json launch-pad
```

#### 直接用我构建的容器一键部署

```shell
docker run -d -p 80:80 -v /your/config/path/siteLinks.json:/usr/share/nginx/html/siteLinks.json feiju12138/launch-pad:2.0
```

### 配置文件

#### 配置文件模板

- 如果是源代码，修改`/public/siteLinks.json`文件
- 如果是`dist`目录，修改`/siteLinks.json`文件
- 如果是Docker容器，在宿主机创建`siteLinks.json`文件并进行映射

```json
[
  {
    "icon": "Docker",
    "name": "服务名",
    "link": "http://127.0.0.1:3000/"
  }
]
```

#### 图标可选项

|图标|备注|
|---|---|
|Blog|博客|
|CloudDownloadAlt|下载|
|CloudUploadAlt|上传|
|SyncAlt|同步|
|Cloud|云盘|
|Server|服务器|
|PhotoVideo|相册|
|Gamepad|游戏|
|Home|主页|
|Docker|容器|
|Book|书籍|
|Camera|照相机|
|Film|影视|
|Search|搜索|
|PaintBrush|绘画|
|GitAlt|Git|
|Music|音乐|
|File|文件|
|NetworkWired|网络|
|ClipboardList|待办事项|

