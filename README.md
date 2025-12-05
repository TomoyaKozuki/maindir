# DirectX Raytracing（DXR）の実装
 Direct3D 12を用いたレイトレーシングの実装を行いました．
## Environment
* API: DirectX 12
* GPU: NVIDIA GeForce RTX 4060Ti
* CPU: AMD Ryzen 7 5700X 8-Core Processor（32GB）
* Libraries: Imgui

## Cloning & Building
This code is primarily tested with Windows 11 and Visual Studio 2022.  
To clone this repo, run the following (note the --recursive flag):
```
git clone --recursive https://github.com/TomoyaKozuki/maindir
```
Next, create a build directory and run CMake:
```
cd (PATH_TO_CLONED_REPOSITORY)
mkdir build
cd build
cmake ..
```

## 実装機能
- DXR Tier 1.1 による GPU レイトレーシング
- Bottom Level / Top Level Acceleration Structure (BLAS / TLAS) の生成
- 最も近いヒット（closest hit）シェーダによる陰影計算
- Miss Shader による背景色処理
- Lambert / GGX ベースの簡易 PBR シェーディング
- sRGB 変換 & トーンマッピング

## License
This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.













