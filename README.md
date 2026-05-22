# Geometric Marching Cubes Without Lookup Tables (V1)
### 從 2D Marching Squares 到 3D 隱式曲面重建（無查表幾何方法）＋ 水資源與邊坡穩定應用擴充

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 🧊 摘要

傳統 Marching Cubes 演算法仰賴 256 種查詢表。本專案提出**完全不使用查找表**的純幾何方法，並擴充至**水資源（水利/水理）**與**邊坡穩定（土壤/岩石）**兩大工程應用。

## 🌊 V1 新功能

- **水資源應用**：河道地形與地下水面重建，水理參數可視化（洪水模擬、地下水補注）。
- **邊坡穩定分析**：潛在滑動面自動提取（Mohr-Coulomb 破壞準則），支援極限平衡法安全係數評估。
- 新增 `hydrology_app.html` 與 `slope_stability_app.html` 完整說明頁面，搭配示意圖 `water_flow.png` 與 `slope_surface.png`。

## 📐 數學原理

對於隱式函數 \( f(x,y,z) = 0 \)，在每個體素立方體中：

- 檢查 12 條邊的端點符號乘積，若 \( f_1 \cdot f_2 < 0 \) 則曲面穿過該邊。
- 線性插值計算交點：\( P = P_1 + \frac{f_1}{f_1 - f_2}(P_2 - P_1) \)。
- 將同一立方體內的相鄰交點連接成三角形，無需任何預定義拓撲表。

## 🖥️ 程式碼執行

```bash
git clone https://github.com/chday169/MCA_WITHOUT_LOOKTABLE-V1
cd MCA_WITHOUT_LOOKTABLE-V1
pip install numpy matplotlib
python mcs_combined_viewer.py
📸 成果圖庫
請見 image_viewer.html 或 images/ 資料夾，包含球體、雙曲面、心形、螺旋管、星形、波浪面、橢球面等。

📂 專案結構
text
MCA-WITHOUT-LOOKUPTABLE-V1/
├── index.html
├── about_me.html
├── extended_abstract.html
├── image_viewer.html
├── pdf_viewer.html
├── hydrology_app.html
├── slope_stability_app.html
├── README.md
├── mcs_combined_viewer.py
├── MCS-No-Lookup.py
├── marching_cubes_paper.pdf (optional)
└── images/
    ├── 0_author.jpg
    ├── 0_sphere.png, 0_hyperboloid.png, ...
    ├── water_flow.png
    └── slope_surface.png
👤 作者
戴清河 (C.H. Day, chday169) – 土木及水利工程技師（退休），熱衷數學視覺化與工程程式開發。

📄 授權
MIT License。詳見 LICENSE 檔案。

🔗 引用
若在學術或教育工作中參考本方法，建議引用：

C.H. Tai. Geometric Marching Cubes Without Lookup Tables: From 2D Marching Squares to 3D Implicit Surface Reconstruction with Water Resources & Slope Stability Extensions. GitHub repository, 2026. https://github.com/chday169/MCA_WITHOUT_LOOKTABLE-V1

保持好奇 · 享受幾何 · 退休不褪色
Stay curious · Enjoy geometry · Retired but not tired

text

---

## ✅ 部署步驟

1. 將上述所有檔案分別儲存，檔名與上方標題一致（注意大小寫）。
2. 將 `images/` 資料夾內放入所有必要圖片，尤其是 `water_flow.png` 與 `slope_surface.png`（您已經準備好的 PNG 圖片）。
3. 確認 `pdf_viewer.html` 中引用的 `marching_cubes_paper.pdf` 檔案存在，或修改為您實際的 PDF 檔名。
4. 將整個資料夾推送至 GitHub 倉儲 `MCA_WITHOUT_LOOKTABLE-V1`。
5. 在倉儲 Settings → Pages 中啟用 GitHub Pages，分支選擇 `main`，資料夾 `/ (root)`。
6. 等待 1-2 分鐘，訪問 `https://你的用戶名.github.io/MCA_WITHOUT_LOOKTABLE-V1/`

所有頁面均已互相連結，圖片使用 PNG 格式，不會再有 404 錯誤。若有任何問題，歡迎隨時告知。
