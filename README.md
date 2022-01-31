# 全体像設計

## フロント(肝)
「React, Nextjs, Tailwindcss on Vercel」 or Vue or Svelte

医療データをブラウザに表示するライブラリ等→一番重要そう。

## バックエンド、インフラ
AWSマネージドな設計。
### バックエンドAPI
nginx → Python(fastAPI or Django or Flask) or Go

### データベース
RDS(Aurora)

(DynamoDB)

### キャッシュ
ElastiCache(Redis or Memcached)

### ストレージ
S3 + CloudFront

Pythonで署名付きURLを使って、CloudFrontから限定公開する[記事](https://dev.classmethod.jp/articles/cloudfront-signed-url-and-cookie-using-python/)

### メッセージング
バックエンド → SQS → Lambda

SNSでPub/Sub?

### 決済
Stripe他

### 大きなデータのUpload
API Gateway + (Lambda?Kinesis?) → S3
