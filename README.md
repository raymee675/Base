# Base Project
Unity での開発で必要な初期設定や便利なアセットを追加したベースプロジェクトです。  
対応バージョン Unity : 6000.3.9f1

---

## 使い方

1. Fork してコピーして利用してください。  
2. GitHub のページから Code -> Fork を選択してください。

3. Unity で開く  
対応バージョンは Unity 6000.3.9f1 です。  
GitHub DeskTop 等でローカルにクローンして開いてください。

4. 実行してみる  
画面上部中央の実行ボタンを押して、Console の出力を確認してください。  
"Hello World Raymee675!" と表示されると思います。

5. 変更要素を確認する  
Asset > Scenes > Base.unity を開いて、下記の変更要素を確認してください。  
確認出来たら、自分の開発を始めましょう。

---

## 変更要素

画面左のヒエラルキーから GameManager というオブジェクトを選択し、子オブジェクトを開いて見てください。

- **GManager（GameManager）**  
  static で public なシングルトンクラスです。  
  その名の通り、ゲーム全体の管理を担うクラスです。

- **InputManager**  
  GManager オブジェクトにアタッチされている、ユーザーのインプットを管理するクラスです。  
  管理をしやすくするため、インプットの処理はこのクラスで完結させてください。

- **VManager(VolumeManager)**  
  PostProcess の Volume を操作するためのオブジェクトです。  
  Post Process とは Unity のレンダリングを調整するフィルターのことで  
  これをうまく適用すればビジュアルが劇的に向上します。  
  Volume の値は Script から実行中に変更することも可能です。

- **CManager(CameraManager) と Back Camera オブジェクト**  
  Cmanager配下に 4 つの Camera があり、それとは別に GameManager 配下に BackCamera が存在します。

  + **MainCamera**  
    デフォルトのゲームオブジェクトを描画します。  
    また FreezeAspectRate.cs (後述) がアタッチされています。

  + **UICamera**  
    UI 専用のカメラです。

  + **FrontCamera**  
    Frontage レイヤーにあるオブジェクトのみを描画します。

  + **BackImageCamera**  
    BackImage レイヤーにあるオブジェクトのみを描画する他、上の３カメラのベースカメラとなり  
    UI > Frontage > Main > BackImage の順で描画します。

- **BackCamera**  
  下の FreezeAspectRate の為に、レターボックスを描画する専用のカメラです。

- **Letter Box**  
  下の FreezeAspectRate 用のレターボックスです。任意の画像を表示できます。

- **FreezeAspectRate.cs**  
  異なる解像度モニターでもアスペクトが一定で動くようにする Script です。  
  Aspect に 設定したアスペクト比を保ち続けます。  
  また Sup,Sdown,Sright,Sleft に任意の画像を適用すると、実行中にその画像がレターボックスとして表示されます。

- **UI Canvas**  
  UI を表示するための 親キャンバスです。  
  この子オブジェクトの Panel オブジェクトを配置することで、UI を規則正しく配置します。

---
## 困ったことがあったら
Raymee675 に連絡してください。
Twitter: @Raymee675 

---
## 困ったことがなかったら
お楽しみください。
