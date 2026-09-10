# Silo 本地复现

原站：https://3dscenes.qualityf2p.workers.dev/silo ，作者 @Nal_uh。

这是原站公开前端资源的本地运行副本，不是从零重写的工程，不表示取得了原作者源码的开源授权。来源记录保留在本说明中；页面上的作者与打赏按钮已按要求移除，公开再分发前请核实适用条款和授权。

## 启动

```sh
npm install
npm run dev -- --host 127.0.0.1 --port 4173
```

## 构建

```sh
npm run build
```

`dist/client/` 是可部署到 GitHub Pages 的静态文件，支持仓库子路径。场景不需要后端。模板的 `dist/server/` 是可选的 Sites 适配层。

保留 Silo 18 / 17、144 层剖面、镜头预设、楼层详情、旋转缩放平移、键盘导航和手机布局。

## 改动和来源

只将资源路径改为同源相对路径，加入 Vite 启动与构建入口。没有 iframe、运行时 CDN 依赖；加载预览图也已本地保存。`source-manifest.json` 记录下载资源的 SHA-256。原 Three.js 注释保留在 bundle 中。

压缩后的代码不等同于原作者可维护的源码工程，大幅改造时建议后续逐模块重构。

## 中文版

已翻译导航、30 篇地点介绍、72 条楼层说明、20 条轮播知识及主要场景标牌，适配中文字体与行距。作者和打赏按钮继续移除。

翻译内容保存在 `translations-zh.json` 和 `translations-notes-zh.json`；其余界面词条位于 `scripts/localize-zh.py`。运行 `python scripts/localize-zh.py` 后执行 `npm run build` 即可重新生成中文版。英文输入副本保存在 `localization/`，不包含在网站运行文件中。

## Personal homepage
The root is a Paco.me-inspired personal homepage. Edit src/site.js for provisional profile text. Project routes: projects/silo/, projects/project-02/, projects/project-03/. The latter two are independent placeholders. Shared presentation is public/portfolio.css. Run npm run build before publishing dist/client.


## Additional project replicas
- projects/project-02/: Red Alert Armory. Source: https://www.yadongxie.com/lab/tanks . The original publicly served TankViewer component, styling and models are reused, with a standalone React entry and local paths. This is a replica, not an original portfolio work. Model credits remain in the viewer. Several models are CC BY 4.0; tacticalassaultmods Allied structures are CC BY-NC 4.0. Preserve individual source and license links; do not treat all assets as one license.
- projects/project-03/: terrain/flood visualisation. Source: https://tibetflood.qualityf2p.workers.dev/ . Original runtime, Copernicus terrain and imagery/map datasets are served locally. Original About panel and dataset attributions are retained. Its event narrative is source content and has not been independently fact-checked.
The two pages retain the original English interface. Homepage labels and back links are Chinese. No runtime hotlinking is required.
