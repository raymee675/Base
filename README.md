# Base Project
Unity での開発に必要な初期設定や便利なアセットを追加したベースプロジェクトです。  
対応バージョン：**Unity 6000.3.9f1**

---

## 使い方

### 1. プロジェクトをコピーする
GitHub の **Fork** 機能を使って、自分のアカウントにコピーしてください。  
GitHub ページ右上の **Code → Fork** を選択します。

### 2. ローカルにクローンする
GitHub Desktop などを使って、Fork したリポジトリをローカルにクローンします。

### 3. Unity で開く
Unity **6000.3.9f1** でプロジェクトを開いてください。

### 4. 実行して動作確認
Unity 上部中央の再生ボタンを押し、Console に  
`Hello World Raymee675!`  
と表示されることを確認します。

### 5. 変更要素を確認する
`Assets > Scenes > Base.unity` を開き、以下の「変更要素」を確認してください。  
確認後、自分の開発を開始できます。

---

## 変更要素

### GameManager 配下の構成
画面左のヒエラルキーから **GameManager** を選択し、子オブジェクトを確認してください。

---

### GManager（GameManager）
- static かつ public なシングルトンクラス  
- ゲーム全体の管理を担当する中心的なクラス

---

### InputManager
- GManager にアタッチされている入力管理クラス  
- ユーザー入力に関する処理はこのクラスに集約してください

---

### VManager（VolumeManager）
- PostProcess の Volume を操作するためのオブジェクト  
- Post Process は Unity のレンダリングを調整するフィルター  
- Script から実行中に Volume の値を変更可能

---

### CManager（CameraManager）と Back Camera
CManager 配下に 4 つのカメラ、GameManager 配下に BackCamera が存在します。

- **MainCamera**  
  - デフォルトのゲームオブジェクトを描画  
  - `FreezeAspectRate.cs` がアタッチされています  

- **UICamera**  
  - UI 専用のカメラ  

- **FrontCamera**  
  - Frontage レイヤーのオブジェクトのみ描画  

- **BackImageCamera**  
  - BackImage レイヤーのオブジェクトを描画  
  - 上記 3 カメラのベースカメラ  
  - 描画順：UI → Frontage → Main → BackImage  

- **BackCamera**  
  - FreezeAspectRate 用のレターボックス描画専用カメラ

---

### Letter Box
- FreezeAspectRate 用のレターボックス  
- 任意の画像を設定可能

---

### FreezeAspectRate.cs
- 異なる解像度でもアスペクト比を一定に保つスクリプト  
- `Aspect` に設定した比率を維持  
- `Sup, Sdown, Sright, Sleft` に画像を設定すると、実行中にレターボックスとして表示されます

---

### UI Canvas
- UI を表示するための親キャンバス  
- 子オブジェクトの Panel を配置することで UI を規則正しく配置できます

---
