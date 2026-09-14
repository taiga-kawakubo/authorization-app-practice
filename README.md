# authorization-app-practice

## 概要
COACHTECH 教材 Tutorial 10-3「認可機能 ハンズオン演習」で作成した成果物です。
投稿一覧ページを表示し更新、削除を投稿者が行えるよう実装。

## 使用技術
- PHP 8.x
- Laravel 10.x
- Policy / Gate（認可）
- Laravel Fortify（認証）

## 学んだこと
- Policy機能の実装。
  Policyに認可の条件を記述し、Controllerで$this->authorize()を記述し設定する。
- 認証と認可の違いについて。

## 動作確認
以下の手順でアプリケーションを起動し、認証・認可機能の動作を確認できます。

### 1. 環境ファイルの準備

```bash
cp .env.example .env
```

### 2. Dockerコンテナの起動

Docker Desktopを起動したうえで、以下を実行します。

```bash
./vendor/bin/sail up -d
```

### 3. アプリケーションキーの生成

```bash
./vendor/bin/sail artisan key:generate
```

### 4. データベースの作成と初期データ投入

```bash
./vendor/bin/sail artisan migrate:fresh --seed
```

### 5. ブラウザでアクセス

```text
http://localhost
```

ログイン画面を確認する場合は、以下にアクセスします。

```text
http://localhost/login
```

### 6. テストアカウント

Seederで作成される以下のユーザーでログインできます。

| ユーザー | メールアドレス | パスワード |
| --- | --- | --- |
| ユーザーA | usera@example.com | password |
| ユーザーB | userb@example.com | password |

### 7. 確認する内容

- 未ログイン状態で投稿一覧にアクセスすると、ログイン画面へ遷移すること
- ログイン後、投稿一覧画面を表示できること
- 自分の投稿を編集できること
- 自分の投稿を削除できること
- 他のユーザーの投稿は編集・削除できないこと

### 8. 終了方法

動作確認が終わったら、以下のコマンドでコンテナを停止します。

```bash
./vendor/bin/sail down
```


## 動作確認のスクリーンショット
![docs/alt text](image.png)
![docs/alt text](image-1.png)
![docs/alt text](image-2.png)
