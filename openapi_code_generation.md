# OpenAPIを使用したコード生成手順

このドキュメントでは、OpenAPI仕様書を使用してコードを生成する手順を説明します。

## 必要なツールのインストール

1. OpenAPI Generator CLIをインストールします。

```bash
npm install -g @openapitools/openapi-generator-cli
```

## OpenAPI仕様書の作成

1. プロジェクトのルートディレクトリに`openapi.yaml`ファイルを作成します。
2. APIのエンドポイント、リクエスト、レスポンスを記述します。

例:

```yaml
openapi: 3.0.0
info:
  title: Task Management API
  version: 1.0.0
paths:
  /api/tasks:
    get:
      summary: Retrieve a list of tasks
      responses:
        '200':
          description: A list of tasks
```

## コード生成

1. 以下のコマンドを実行してコードを生成します。

```bash
openapi-generator-cli generate -i openapi.yaml -g spring -o spring-my-playground/src/main/java/com/example/api
```

- `-i`: 入力ファイル（OpenAPI仕様書）
- `-g`: 使用するジェネレーター（ここではSpring）
- `-o`: 出力ディレクトリ

## 生成されたコードの統合

1. 生成されたコードをプロジェクトに統合します。
2. 必要に応じてカスタマイズを行います。

## 注意点

- 生成されたコードは自動生成されたものであるため、直接編集しないでください。
- カスタマイズが必要な場合は、別のクラスやファイルで拡張することを推奨します。