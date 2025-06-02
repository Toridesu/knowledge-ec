# コンテンツ販売アプリ

このプロジェクトは、Next.js、Supabase、Stripe、Auth.jsを活用した E コマースプラットフォームの学習用プロジェクトです。

## ✨ 主な機能

- **商品一覧表示:** 商品をカテゴリ別に閲覧できます。
- **商品詳細表示:** 各商品の詳細情報（価格、説明、画像など）を確認できます。
- **カート機能:** 気に入った商品をカートに追加し、購入手続きに進めます。
- **ユーザー認証:** アカウントを作成し、ログイン・ログアウトができます。
- **決済機能:** Stripe と連携し、安全な決済処理を実現します。

## 🚀 技術スタック

- **フレームワーク:** Next.js (App Router, Turbopack)
- **言語:** TypeScript
- **UI:** React
- **スタイリング:** Tailwind CSS
  - `@tailwindcss/typography` - Markdown 等の整形用
  - `tailwindcss-animate` - アニメーション用ユーティリティ
- **UI コンポーネント:** shadcn/ui (Radix UI, Lucide React などを活用)
  - `tailwind-merge` - Tailwind クラスのマージ
- **認証:** NextAuth.js
- **データベース:** Supabase (`@supabase/supabase-js`) (想定)
- **決済:** Stripe (`@stripe/stripe-js`, `stripe`)
- **Markdown/YAML 処理:**
  - `gray-matter` - Frontmatter 解析
  - `js-yaml` - YAML 解析
  - `remark`, `remark-html` - Markdown から HTML への変換
- **テスト:** Playwright
- **リンター・フォーマッター:** ESLint, Prettier (設定されていれば追記)

## 🛠️ 開発環境のセットアップ

## 📁 プロジェクト構成 (src ディレクトリ)

```
src
├── app/            # Next.js App Routerのルーティングとページコンポーネント
│   ├── (root)/     # ルートパス ("/") に対応するページ(page.tsx), レイアウト(layout.tsx), グローバルCSS(globals.css)など
│   ├── api/          # APIルート (例: /api/stripe/webhook, /api/auth/*)
│   │   └── [route]/  # 各APIエンドポイントの処理
│   ├── (auth)/       # 認証関連ページ (例: /login, /register) のグループ (レイアウト共通化など)
│   ├── products/     # 商品一覧や商品詳細ページ関連
│   │   ├── [id]/     # 商品詳細ページ (例: /products/123)
│   │   └── page.tsx  # 商品一覧ページ (例: /products)
│   └── ...           # その他、カートページ、注文履歴ページなどの機能ごとのルーティングディレクトリ
├── components/     # 再利用可能なUIコンポーネント群
│   ├── ui/           # shadcn/ui から導入したベースUIコンポーネント (Button, Card, Inputなど)
│   └── *.tsx         # プロジェクト固有のカスタムコンポーネント (例: ProductCard, Header, Footerなど)
├── lib/            # 外部ライブラリの設定やユーティリティ、コアロジック
│   ├── supabase/     # Supabaseクライアントの設定や関連するヘルパー関数
│   ├── stripe/       # Stripe関連の処理 (クライアントサイド、サーバーサイド)
│   ├── auth/         # NextAuth.js の設定 (authOptionsなど)
│   └── utils.ts      # 汎用的なユーティリティ関数 (shadcn/uiのcnなど)
├── types/          # TypeScriptの型定義 (例: 商品の型、ユーザーの型など)
│   └── index.ts      # 型定義を集約するファイル (または機能ごとに分割)
└── ...             # actions/ (Server Actions), constants/, styles/ など、必要に応じて追加
```
