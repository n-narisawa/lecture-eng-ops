# 手順

## IAMロールの設定
- cloud buildのサービスアカウント
- compute engineのサービスアカウント
    - cloud build 編集者
    - storage管理者
    - viewer

## Cloud buildによるビルド・デプロイ
```
gcloud builds submit
```

## Cloud runへのアクセス方法
```
SERVICE_URL=$(gcloud run services describe demo-cicd --format 'value(status.url)' --region us-central1)
curl -H "Authorization: Bearer $(gcloud auth print-identity-token)" $SERVICE_URL
```
