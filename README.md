# nr-data

这个仓库只放两样东西，**不放源码**：

- `version.json`：最新版本号、更新包地址、更新说明
- `blocked.json`：封禁名单（整机封 / 只封部分功能）

程序联网时会读这两个文件：
- 有新版本就去 `version.json` 里的 `zip` 下载，覆盖代码（`data/` 不动）
- 机器码出现在 `blocked.json` 里就停服务，直到名单里删掉

`blocked.json` 的格式：

```json
{
  "blocked": ["DBEF-4AAD-207A"],
  "partial": {"A3F9-2C7B-8E14": ["video", "music"]},
  "note": "学校机房整机停用"
}
```

`partial` 里的功能名可选：`news` `video` `music` `search` `mirror` `anime`。
