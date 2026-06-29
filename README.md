# Things I Need / Things I Have

一个纯前端、可离线使用、数据保存在本地的购物清单与持有物管理网站。

## 本地打开

直接打开 `index.html` 可以使用主要功能，但 `file://` 模式通常不能启用 Service Worker。

如需测试离线缓存和安装能力，请用本地静态服务或部署到 HTTPS 后访问，例如：

```text
http://localhost:8000/
```

## 数据保存

数据保存在浏览器 LocalStorage 中：

- `compare_list_v1_data`
- `compare_list_v1_settings`
- `compare_list_v1_positions`

清理浏览器数据、换浏览器、使用无痕模式，都可能导致数据不可用。重要数据请在设置页导出 JSON 备份。

## 备份与恢复

进入 `#/settings`：

- 点击“导出全部 JSON”备份全部数据。
- 点击“导入 JSON”恢复之前导出的数据。
- 进入某个项目详情后，可导出当前项目 TXT 或 CSV。

CSV 字段为：

```text
section,itemTitle,type,text,quantity,note,done,parentText,createdAt,updatedAt
```

## PWA 离线缓存

项目包含：

- `index.html`
- `manifest.webmanifest`
- `service-worker.js`
- `icon-192.png`
- `icon-512.png`

`service-worker.js` 会缓存这些文件。以后修改功能时，更新 `service-worker.js` 里的缓存名版本号即可让浏览器刷新缓存。

## 部署到 GitHub Pages

1. 将本项目文件提交到 GitHub 仓库。
2. 在仓库设置里打开 `Settings > Pages`。
3. Source 选择对应分支，例如 `main`，目录选择根目录。
4. 保存后等待 GitHub Pages 生成网址。
5. 用生成的 HTTPS 地址打开网站。

本项目使用 `./` 相对路径，适合部署在 GitHub Pages 子路径下。

## 安装到设备

### 电脑 Chrome / Edge

1. 用 HTTPS 地址打开网站。
2. 点击地址栏右侧的安装图标，或浏览器菜单里的“安装应用”。
3. 安装后可以像普通应用一样打开。

### 安卓 Chrome

1. 用 Chrome 打开网站。
2. 点击右上角菜单。
3. 选择“添加到主屏幕”或“安装应用”。

### iPhone / iPad Safari

1. 用 Safari 打开网站。
2. 点击分享按钮。
3. 选择“添加到主屏幕”。

第一次在线打开后，网站会缓存主要文件，之后可离线继续使用。新增和修改的数据仍保存在当前浏览器本地。
