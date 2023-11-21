# y8_train_test
## 提供 YOLOv8 物件偵測標註/訓練/測試等工具集

包含幾個工具:
1. 標註工具 - [y8_gt_editor](./binary) (Windows 環境底下標註工具)
2. 訓練工具 - [「YOLOv8_Tutorial」的副本](./「YOLOv8_Tutorial」的副本.ipynb) (Google Colab 環境)
3. [y8_detect](./binary) (Windows 環境底下偵測工具)
4. [y8_detect_gt](./binary) (Windows 環境底下同時顯示偵測結果與標註工具)

## 1. 標註工具 - [y8_gt_editor](./binary)

此為 Windows 64-bit 環境底下一個 GUI 工具程式, <br />
操作方式 - 透過拖曳方式將以下三個項目從檔案總管拖曳到 Dialog 上: <br />
* Class names file: 類別名稱定義檔(文字檔)，每一行表示一個類別名稱，支援中文(UTF8格式)，參考範例: [dataset/Pothole.v1/name.txt](./dataset/Pothole.v1/name.txt) <br />
* GT Images Folder: YOLOv8 格式影像資料夾，參考範例: [dataset/Pothole.v1/train/images](./dataset/Pothole.v1/train/images) <br />
* GT Labels Folder: YOLOv8 格式Ground Truth標記檔案資料夾(一張影像檔對應一個文字檔)，參考範例: [dataset/Pothole.v1/train/labels](./dataset/Pothole.v1/train/labels) <br />

然後點選 Open, 瀏覽上下頁透過 PgUp, PgDn 按鍵，新增物件透過拖曳滑鼠方式(綠色框)，滑鼠右鍵(或Delete按鍵)移除物件，標記不同類別ID可以在物件上直接點選數字(1..9, 如果只有一個類別物件表示全為 1):
![](./images/y8_gt_editor.jpg)

## 2. 訓練工具 - [「YOLOv8_Tutorial」的副本](./「YOLOv8_Tutorial」的副本.ipynb) (Google Colab 環境)
使用 Colab 開啟 「YOLOv8_Tutorial」的副本.ipynb 並建立個人副本, <br />
包含以下幾個操作步驟: <br />
```
步驟1: 掛載 Google 雲端硬碟
步驟2: 將影像資料從 Google 雲端硬碟複製到 Colab
步驟3:　Setup 建置訓練環境
步驟4：開始訓練模型
步驟5: 將訓練好的模型(best.pt)模型複製到 Google 雲端硬碟
步驟6: 將訓練好的模型(best.pt)轉成其他格式(best.onnx)
```

## 3. 偵測工具 - [y8_detect](./binary)

此為 Windows 64-bit 環境底下一個 GUI 工具程式, <br />
操作方式 - 透過拖曳方式將以下三個項目從檔案總管拖曳到 Dialog 上: <br />
* YOLOv8 detection model (onnx format): ONNX格式模型檔，參考範例: [dataset/Pothole.v1/best.onnx](./dataset/Pothole.v1/best.onnx) <br />
* Class names file: 類別名稱定義檔(文字檔)，每一行表示一個類別名稱，支援中文(UTF8格式)，參考範例: [dataset/Pothole.v1/name.txt](./dataset/Pothole.v1/name.txt) <br />
* 若勾選 Live Webcam 則表示使用攝影機，忽略以下 Images 欄位
* Images (folder/image/video file): 測試影像(或影片)資料夾，參考範例: [dataset/Pothole.v1/test/images](./dataset/Pothole.v1/test/images) <br />

然後點選 Open, 瀏覽上下頁透過 PgUp, PgDn 按鍵，可以設定偵測門檻值(th, 範圍 0..1 間，門檻值愈高誤報愈少，偵測率愈低):
![](./images/y8_detect.jpg)
