# AI-Powered Search Application

AWS Bedrockを活用したインテリジェント検索アプリケーション

## 機能

- **AI クエリ分析**: AWS BedrockのClaude 3 Haikuを使用してユーザーの検索意図を分析
- **YouTube検索**: 動画コンテンツの検索
- **Web検索**: Google Custom Search APIを使用した一般的なWeb検索
- **最適化されたクエリ**: AIが検索タイプに応じてクエリを最適化

## セットアップ

### 1. 必要なAPIキーの取得

#### AWS Bedrock
1. AWSアカウントでBedrockサービスにアクセス
2. Claude 3 Haikuモデルへのアクセスを有効化
3. IAMユーザーにBedrock権限を付与

#### YouTube Data API
1. Google Cloud Consoleでプロジェクトを作成
2. YouTube Data API v3を有効化
3. APIキーを作成

#### Google Custom Search (Optional)
1. Google Cloud ConsoleでCustom Search APIを有効化
2. Custom Search Engineを作成
3. APIキーとSearch Engine IDを取得

### 2. 環境変数の設定

`backend/.env`ファイルを作成し、以下の情報を設定：

```env
# AWS設定
AWS_ACCESS_KEY_ID=your_aws_access_key
AWS_SECRET_ACCESS_KEY=your_aws_secret_key
AWS_DEFAULT_REGION=us-east-1

# Google API設定
GOOGLE_SEARCH_API_KEY=your_google_api_key
GOOGLE_SEARCH_CX=your_search_engine_id

# YouTube API設定
YOUTUBE_API_KEY=your_youtube_api_key
```

### 3. インストールと実行

#### バックエンド
```bash
cd backend
python -m venv myenv
source myenv/bin/activate  # Linux/Mac
# または myenv\Scripts\activate  # Windows
pip install -r requirements.txt
python app.py
```

#### フロントエンド
```bash
cd frontend
npm install
npm start
```

## 使用方法

1. アプリケーションにアクセス
2. 検索クエリを入力
3. AIが自動的に最適な検索戦略を決定
4. YouTube動画やWeb記事の結果を表示

## AI分析の特徴

- **学習系クエリ**: チュートリアル動画と参考記事の両方を検索
- **実演系クエリ**: YouTube動画を優先
- **情報系クエリ**: Web記事を優先
- **クエリ最適化**: 検索プラットフォームに応じてキーワードを調整