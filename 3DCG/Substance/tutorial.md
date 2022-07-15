# 新規 FBX読み込み
- ![image](https://user-images.githubusercontent.com/80798265/178391040-cee661bd-e687-45b2-b4eb-f50ccc8b0b7c.png)

## モデルの差し替え
- [【SubstancePainter】モデルを差し替える](https://summering26.com/substancepainter-mesh-replacement/)

# メッシュマップをベイク
編集 > メッシュマップをベイク

![image](https://user-images.githubusercontent.com/80798265/178239556-d9203d3f-bcf2-4699-963d-687a50adea37.png)
- 2k, 4kにする

![スクリーンショット 2022-07-11 181231](https://user-images.githubusercontent.com/80798265/178239888-9a752994-5a92-4cb4-8efc-d644ccca189c.jpg)
- アンチエイリアスを8xにする

![スクリーンショット 2022-07-11 181337](https://user-images.githubusercontent.com/80798265/178239870-b7ccca59-a13d-4ccd-b99a-e975144f3985.jpg)


#  色分けフォルダーと塗りつぶしレイヤー作成
1. フォルダ作成

![Ctrl+Gフォルダ分け](https://user-images.githubusercontent.com/80798265/178240215-27e65cd7-3ae5-4ff6-a1a6-8bc89182b2b9.jpg)

# マスク作成
## 右クリックでマスクを追加
![image](https://user-images.githubusercontent.com/80798265/178241114-1c6be127-2791-4b9b-9fc3-11e429931da2.png)
- レイヤーでマスクを分ける
![image](https://user-images.githubusercontent.com/80798265/178240157-434d43b0-57ca-4c16-be4f-235e8f1cc530.png)

## 塗りつぶし
### ポリゴン
1. マスクにする
![image](https://user-images.githubusercontent.com/80798265/178387493-fee4f192-11ac-4f4c-846e-74bd0237ab4d.png)

2. ポリゴン塗りつぶしでモデルを塗りつぶす
![image](https://user-images.githubusercontent.com/80798265/178387047-6bc2f32a-4eb1-4cea-aead-b5d2c8be8992.png)


# テクスチャの設定
塗りつぶし処理修正

ColorとRoughnessのみだけひとまず

![スクリーンショット 2022-07-11 180847](https://user-images.githubusercontent.com/80798265/178240324-3e05b899-b74c-4fb2-9cfd-30df509371f0.jpg)

# テクスチャ追加方法
1. リソースを追加
![スクリーンショット 2022-07-11 180607](https://user-images.githubusercontent.com/80798265/178240491-cb47825e-0d1e-4dff-91da-da5872151af8.jpg)

読み込み先  
![スクリーンショット 2022-07-11 180709](https://user-images.githubusercontent.com/80798265/178240582-77fc09d6-167f-41ef-b4c8-be37b3e223f1.jpg)

2. テクスチャに変更
 
![スクリーンショット 2022-07-11 180654](https://user-images.githubusercontent.com/80798265/178240667-73323063-6324-4dd2-b6a6-706def225676.jpg)

# カラー設定
3面投影

# ブラー

- https://orenda.co.jp/blog/1667/

# 半透明
1. shaderを pbr-metal-rough-with-alpha-blending にする。
2. テクスチャセットにopacityを追加する。
3. レイヤーを追加してOpacityをマスクでつける。 
- [Substance Painterで半透明を使う方法](https://www.betternowcgz.com/substance-painter-how-to-use-opacity/)


# テクスチャ出力
- 1024 8bit
![output_texture](https://user-images.githubusercontent.com/80798265/179138765-66594743-2ba8-4238-a8a8-ac8e3571cac4.jpg)
