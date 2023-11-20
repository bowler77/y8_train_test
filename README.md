# y8_train_test
提供 YOLOv8 物件偵測標註/訓練/測試等工具集

包含幾個工具:
* 1. y8_gt_editor (Windows 環境底下標註工具)
* 2.「YOLOv8_Tutorial」的副本 (Google Colab 環境)
* 3. y8_detect (Windows 環境底下偵測工具)
* 4. y8_active_learning (Windows 環境底下同時顯示偵測結果與標註工具)

## 1. 標註工具 - y8_gt_editor
此為 Windows 64-bit 環境底下一個 GUI 工具程式
操作方式: 透過拖曳方式將以下三個項目從檔案總管拖曳到 Dialog 上:
Class names file: 類別名稱定義檔，一行表示一個類別名稱，支援中文(UTF8格式)，不支援空白字元，參考範例: dataset/Pothole.v1/name.txt
GT Image Folder: YOLOv8 影像資料夾，參考範例: dataset/Pothole.v1/train/images
GT Text Folder: YOLOv8 Ground Truth 標記檔案資料夾，參考範例: dataset/Pothole.v1/train/labels
![](https://github.com/bowler77/y8_train_test/blob/master/images/y8_gt_editor.jpg)

## 2.「YOLOv8_Tutorial」的副本 (Google Colab 環境)
使用 Colab 開啟 「YOLOv8_Tutorial」的副本.ipynb 並建立個人副本
