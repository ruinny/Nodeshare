# Nodeshare

RocketNode - 极速节点分享

一个极简的静态节点分享页面，基于 `index.html` + `nodes.json`。适合把免费/公益的加速节点以静态页面形式对外分享 — 你只需维护根目录下的 `nodes.json` 文件即可实时更新页面内容。

**特点**
- 静态且轻量：只需托管静态文件（HTML + JSON）。
- 友好的 UI：基于 TailwindCSS 和 Vue 3，支持复制、二维码展示等操作。
- 易于更新：覆盖 `nodes.json` 即可更新节点列表。

**文件说明**
- `index.html`：前端页面，默认从 `./nodes.json` 拉取数据（请查看脚本中 `API_URL` 变量）。
- `nodes.json`：节点数据源，示例格式见下。

**nodes.json 示例格式**
```json
{
	"nodes": [
		{
			"id": 1,
			"name": "香港高速 HK-01",
			"country_code": "hk",
			"protocol": "vmess",
			"ping": 45,
			"link": "vmess://eyJ..."
		},
		{
			"id": 2,
			"name": "日本东京 JP-T2",
			"country_code": "jp",
			"protocol": "ss",
			"ping": 89,
			"link": "ss://Ym..."
		}
	]
}
```

请确保 `nodes.json` 返回的顶级对象包含 `nodes` 数组（`index.html` 中默认使用 `data.nodes`）。

**本地预览（快速）**
在项目根目录运行一个静态服务器即可预览：

```bash
# 使用 Python 3 自带的简单静态服务器（推荐）
python3 -m http.server 8080

# 或者使用 node 的 serve（需先安装：npm install -g serve）
serve -s .  -l 8080
```

打开浏览器访问 `http://localhost:8080` 即可。

**如何更新节点**
- 直接编辑或替换仓库根目录的 `nodes.json` 文件，确保符合上面的 JSON 结构。
- 如果部署在远端（如 Vercel/Netlify/GitHub Pages），推送更新后页面会自动生效（取决于浏览器缓存）。

**部署建议**
- GitHub Pages：将仓库 `main` 分支的 `index.html` 放在根目录，即可启用 Pages。适合快速公开托管静态站点。
- Vercel / Netlify：支持静态网站并可配置自动构建/部署，推荐用于需要自定义域名或自动化部署的场景。

**贡献**
- 欢迎提交节点或改进 UI，建议通过 Pull Request 更新 `nodes.json` 或 `index.html`。

**许可证 & 联系**
- 该仓库示例内容可按需要修改。若你希望使用开源许可证，请在仓库根目录添加 `LICENSE` 文件（例如 MIT）。
- 联系：在仓库 Issues 中提交问题或建议。

---
更新于 2025。祝使用愉快！

