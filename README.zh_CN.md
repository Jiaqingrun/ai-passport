<p align="right">
  <strong>简体中文</strong> · <a href="README.md">English</a>
</p>

# AI Passport 项目

两个跑在 FoloToy AI Passport 上的应用——ESP32-C3、8 MB Flash、无 PSRAM、
240 × 320 屏幕、三个按键。每个应用有自己的仓库或分支，这一页是这个 fork 的目录，
告诉你在哪能找到当前的那个。

## 世界之尘 · 上帝模拟器

一片自己活着、玩家大部分时间只是在看的世界。六族——人、兽、羽、鳞、虫、木——
散落在一块生成的群岛上，自己建城、分裂、结盟、厮杀、灭绝；两族相遇时还可能诞生
人兽、羽鳞、兽羽、木虫这些混血，性状从父母各继承一部分。玩家从不指挥任何人：
神力花在降灾、赐福和回应祈愿上，编年史告诉你结果。

- **五页界面、三个按键**：世界、纪年、详情、物种、舆图。上／下负责选择与加速，
  确定负责执行与暂停，长按上／下翻页，长按确定息屏休眠——世界仍以最高 1× 继续演化。
- **三位有各自故事的统治者**：KANE 降下把文明拖向降级的荒唐诏令，妲己在兽族中被动
  祸乱敌国，始皇帝统一人族并在临朝时让时间变慢。
- **祈愿、圣地与奇观**：部族焚香祈愿时世界暂停等待回应；高阶文明会筑起星门、
  通天塔与大神殿。
- **终焉与轮回**：当世上出现帝国级族群、并且仍有四族存活时，黄昏开始倒计时；
  旧世终结、奇观化为残柱，下一次轮回在一块新大陆上重新开始。

仓库：[Jiaqingrun/ai-passport-dust-of-worlds](https://github.com/Jiaqingrun/ai-passport-dust-of-worlds)，
分支 `main`（v0.51）。同时发布在社区库（项目 `community-c04b753d`），并归档到上游
[`docs/reference/jiaqingrun/dust-of-worlds/`](https://github.com/FoloToy/ai-passport/tree/main/docs/reference/jiaqingrun/dust-of-worlds)。

## 余烬（Ashbox）

同一块板子上的离线末日基地建造：一处炉火之家、从它出发的远征、基地建造、贸易、
伤病与药物、流浪者，以及 USB 存档管理。它不是硬件测试 demo，也不是联网游戏——
射频关掉也能完整玩。

分支：本 fork 的 `feature/ashbox-ember`
（<https://github.com/Jiaqingrun/ai-passport/tree/feature/ashbox-ember>），
项目约定见 `PROJECT.md`，产品文档在 `docs/ashbox/`。

## 构建

两个应用都用 ESP-IDF 5.5.3 与 AI Passport 的默认分区表：

```bash
source ~/esp/esp-idf-v5.5.3/export.sh
idf.py build        # 应用镜像
idf.py merge-bin    # 整片 Flash 用的合并镜像
```

只烧应用分区会保留已存的世界或存档；覆盖整片的合并镜像不承诺保留。两个仓库各自
带着自己的构建与烧写说明，以它们为准，不要照抄这一页的命令。

## 参考

这两个应用背后的可复用经验都归档在上游的 `docs/reference/jiaqingrun/`：模拟与存档
格式、渲染与音频路径、整屏地图页、可选行的网格。它们是参考资料，不是硬性规则。
