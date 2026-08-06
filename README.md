# Korabli Mod 更新数据

存放 [Korabli 战绩查询](https://github.com/zfxsquare/korabli-mod-data) 客户端使用的更新数据：

- `ships_db.json` — 舰船数据库（`shipParamsId` → 名称/舰种/等级/国籍/index），从游戏 `GameParams` 提取
- `ship_names_cn.json` — 舰船中文名映射（index → 中文），来自 LocalizedKorabli 中文本地化
- `version.json` — 数据版本信息（更新时间、舰船数量等）

客户端通过以下原始链接获取更新（国内网络不可达时自动回退到 GitHub 代理镜像）：

```
https://raw.githubusercontent.com/zfxsquare/korabli-mod-data/main/ships_db.json
https://raw.githubusercontent.com/zfxsquare/korabli-mod-data/main/ship_names_cn.json
https://raw.githubusercontent.com/zfxsquare/korabli-mod-data/main/version.json
```

## 如何更新数据

在项目根目录执行：

```bash
python scripts/update_ships_db.py       # 从游戏解包并重新生成 ships_db.json
python scripts/update_ship_names_cn.py  # 拉取最新语言包并生成 ship_names_cn.json
```

然后把 `update-data/` 下的文件推送到本仓库。
