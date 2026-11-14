# 享瘦 AI 體態分析 MVP 1.4

靜態網站，可直接部署至 GitHub Pages。入口為 index.html 或 posture.html。

## 資源
- MediaPipe Tasks Vision 固定 0.10.21，JS 和完整 SIMD / 非 SIMD WASM 同版本。
- Pose Landmarker Lite float16 模型版本 1。
- JS、WASM、模型全部從本站相對路徑載入，不依賴執行時 CDN。
- 套件來源：https://registry.npmjs.org/@mediapipe/tasks-vision/-/tasks-vision-0.10.21.tgz
- 模型來源：https://storage.googleapis.com/mediapipe-models/pose_landmarker/pose_landmarker_lite/float16/1/pose_landmarker_lite.task
- 官方文件：https://ai.google.dev/edge/mediapipe/solutions/vision/pose_landmarker/web_js
- 第三方授權位於 mediapipe/LICENSE；資源雜湊位於 ASSETS.sha256。

## 使用
以 HTTPS 開啟，輸入匿名代碼，啟動攝影機並允許相機權限。全身入鏡後可儲存數值、比較相同視角紀錄、匯出 JSON。紀錄只在目前瀏覽器保存，照片不會上傳或永久儲存。不同網域的舊紀錄不會自動移轉。

## 修正
保留 v1.3 攝影機優先流程、骨架與紀錄；改為同源載入。二維角度依實際影像寬高計算，肩線方向正規化。停止時取消動畫並清除骨架，推論錯誤時停用拍攝，頁面離開時關閉相機。

## 手機驗收
iPhone Safari 實機仍需確認相機授權、前後鏡頭、直橫向、全身骨架、儲存兩次與 JSON 匯出。桌面 Safari 測試不能取代實機驗收。
