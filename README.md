# 3DGS Web Viewer

用 Three.js + [GaussianSplats3D](https://github.com/mkkellogg/GaussianSplats3D) 在浏览器中直接渲染 3D Gaussian Splatting (.ply) 的极简示例。

![预览](preview.png)

## 本地运行

.ply 必须通过 HTTP 服务加载（不能双击打开 HTML）：

```bash
python -m http.server 8000
```

浏览器打开 http://localhost:8000

操作：左键拖动旋转 · 滚轮缩放 · 右键拖动平移

## 文件说明

- `index.html` — 查看器页面（加载时会自动计算场景包围盒并对焦相机）
- `panda_cleaned.ply` — 3DGS 模型（大疆 Pocket 4 Pro 拍摄 → Brush 训练 → SuperSplat 清理）

## 更换自己的模型

把你的 `.ply` 放进本目录，改 `index.html` 里 `addSplatScene('xxx.ply')` 的文件名即可。

注意：COLMAP 坐标系 Y 轴朝下，页面已自动处理；如果场景颠倒，检查 `cam.up.set(0, -1, 0)`。
