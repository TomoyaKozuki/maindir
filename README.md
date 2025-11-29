# DirectX Raytracing（DXR）の実装
 Direct3D 12を用いたレイトレーシングの実装を行いました．
## 実装環境
* (GPU):NVIDIA GeForce RTX 4060Ti
* (CPU):AMD Ryzen 7 5700X 8-Core Processor（32GB）

## ビルド方法
1. Visual Studio 2022 / Windows SDK 10.0.22621 以上をインストール
2. DirectX Shader Compiler(dxc) を PATH に追加
3. 本リポジトリをクローン
   git clone ...
4. ソリューションを開きビルド（Release / Debug 選択可）

## 実装機能
- DXR Tier 1.1 による GPU レイトレーシング
- Bottom Level / Top Level Acceleration Structure (BLAS / TLAS) の生成
- 最も近いヒット（closest hit）シェーダによる陰影計算
- Miss Shader による背景色処理
- Lambert / GGX ベースの簡易 PBR シェーディング
- sRGB 変換 & トーンマッピング

## ディレクトリ構成
/Source        ... C++ DXR 本体
/Shaders       ... RayGen / Miss / HitGroup.hlsl
/Assets        ... モデル、テクスチャ
