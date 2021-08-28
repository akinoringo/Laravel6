# Laravel6でJWT認証の実装

## 参考記事
https://pgmemo.tokyo/data/archives/1703.html

## 実装手順（Laravelインストール後）
1. JWTのインストール、シークレットの作成
1. Userモデルにimplements JWTSubject
1. UserモデルにJWTトークンに保存するIDなどを返すメソッドなどを追加
1. apiの認証ドライバーをjwtにする
1. routes/api.phpにlogin,logout,refresh,meのルートを追加（ミドルウェアはapi）
1. AuthControllerの作成、loginなどのメソッドを追加
1. Userを登録（Seeder）
1. ログインなどを試す
  1. ログインのポスト送信
    - Headers:
      - Accept: application/json
    - Params:
      - email: user-email
      - password: user-password
    
    →access_tokenやtoken_type, expires_inなどが返ってくる

その他（User情報の取得なども可能）
