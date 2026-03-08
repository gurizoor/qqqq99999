# GitHubプロフィールサイト 仕様書

## 1. プロジェクト概要

### 1.1 プロジェクト名
qqqq99999 GitHubプロフィールサイト

### 1.2 プロジェクト目的
学校でアプリを開発するために作成したGitHubアカウントのプロフィールサイトとして、開発活動やプロジェクトを紹介する

### 1.3 ターゲットオーディエンス
- クラスメイト・同級生
- 学校の先生方
- 他校の学生開発者
- 技術系コミュニティ

### 1.4 コアコンセプト
- **シンプル**: 余白を活かしたミニマルなデザイン
- **モダン**: 最新のデザイントレンドを取り入れた洗練された見た目
- **学生開発**: 生徒同士で学びながら作るアプリ
- **成長記録**: 開発過程や学びを共有

## 2. 機能要件

### 2.1 必須機能（MVP）

#### 2.1.1 基本表示
- **SPEC-001**: GitHubユーザー名の表示
- **SPEC-002**: チーム名・活動内容の概要表示
- **SPEC-003**: GitHubプロフィールへのリンク
- **SPEC-004**: レスポンシブデザイン対応

#### 2.1.2 コンテンツ表示
- **SPEC-005**: ヒーローセクション（タイトルと概要）
- **SPEC-006**: 活動内容の紹介（3つの特徴）
- **SPEC-007**: アクションボタン（GitHubリンク、プロジェクト表示）

### 2.2 希望機能

#### 2.2.1 拡張機能
- **SPEC-008**: GitHub API連携によるリポジトリ表示
- **SPEC-009**: コンタクトフォーム
- **SPEC-010**: ダークモード対応
- **SPEC-011**: 多言語対応（日本語・英語）

#### 2.2.2 インタラクション
- **SPEC-012**: スムーススクロール
- **SPEC-013**: ホバーエフェクト
- **SPEC-014**: ローディングアニメーション

## 3. デザイン仕様

### 3.1 カラースキーム
```css
:root {
  /* モダンなニュートラルカラー */
  --primary: #000000;        /* 純黒 */
  --primary-light: #666666;   /* 濃いグレー */
  --secondary: #ffffff;       /* 純白 */
  --accent: #0066ff;         /* モダンブルー */
  
  /* グレースケール */
  --gray-50: #fafafa;
  --gray-100: #f5f5f5;
  --gray-200: #e5e5e5;
  --gray-300: #d4d4d4;
  --gray-400: #a3a3a3;
  --gray-500: #737373;
  --gray-600: #525252;
  --gray-700: #404040;
  --gray-800: #262626;
  --gray-900: #171717;
  
  /* 背景 */
  --bg-primary: #ffffff;
  --bg-secondary: #fafafa;
  --bg-tertiary: #f5f5f5;
}
```

### 3.2 タイポグラフィ
```css
:root {
  --font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  
  /* フォントサイズ */
  --text-xs: 0.75rem;    /* 12px */
  --text-sm: 0.875rem;   /* 14px */
  --text-base: 1rem;     /* 16px */
  --text-lg: 1.125rem;   /* 18px */
  --text-xl: 1.25rem;    /* 20px */
  --text-2xl: 1.5rem;    /* 24px */
  --text-3xl: 1.875rem;  /* 30px */
  --text-4xl: 2.25rem;   /* 36px */
  --text-5xl: 3rem;      /* 48px */
  --text-6xl: 3.75rem;   /* 60px */
  
  /* 行の高さ */
  --leading-tight: 1.25;
  --leading-normal: 1.5;
  --leading-relaxed: 1.75;
}
```

### 3.3 レイアウト構造
```
┌─────────────────────────────────────┐
│                                     │
│           ヒーローセクション          │
│  ┌─────────────────────────────────┐   │
│  │           @qqqq99999           │   │
│  │        生徒による開発チーム       │   │
│  │      クラスメイトと一緒に...     │   │
│  │    [GitHub] [プロジェクトを見る] │   │
│  └─────────────────────────────────┘   │
│                                     │
├─────────────────────────────────────┤
│          特徴セクション              │
│  ┌─────────┬─────────┬─────────┐   │
│  │ 仲間と  │ 学習記録 │ 挑戦と  │   │
│  │ の開発   │         │ 成長     │   │
│  └─────────┴─────────┴─────────┘   │
│                                     │
└─────────────────────────────────────┘
```

### 3.4 デザイン原則
- **ミニマリズム**: 必要な要素のみを配置、余白を重視
- **タイポグラフィ**: フォントの太さとサイズで階層を表現
- **モノクロームベース**: 黒・白・グレーを基調、アクセントに青を使用
- **クリーンなライン**: シンプルな罫線と区切り
- **統一感**: 一貫した余白と間隔

### 3.5 コンポーネント仕様

#### 3.5.1 ヒーローセクション
- **レイアウト**: Flexbox、中央揃え
- **最小高さ**: 70vh
- **背景**: 純白または薄いグレー
- **アニメーション**: シンプルなフェードイン
- **余白**: 十分な空白を確保

#### 3.5.2 タイトル
- **フォントサイズ**: 2.5rem - 3rem（デスクトップ）
- **ウェイト**: 300-400（Light to Regular）
- **カラー**: --primary（黒）
- **装飾**: なし、クリーンな表示

#### 3.5.3 ボタン
```css
.btn-primary {
  background: var(--primary);
  color: var(--secondary);
  padding: 12px 24px;
  border-radius: 4px;
  font-weight: 400;
  font-size: 0.9rem;
  transition: all 0.2s ease;
  border: 1px solid var(--primary);
}

.btn-secondary {
  background: transparent;
  color: var(--primary);
  border: 1px solid var(--gray-300);
  padding: 11px 23px;
  border-radius: 4px;
  font-weight: 400;
  font-size: 0.9rem;
  transition: all 0.2s ease;
}
```

#### 3.5.4 特徴カード
```css
.feature-card {
  background: var(--bg-primary);
  border: 1px solid var(--gray-200);
  border-radius: 8px;
  padding: 32px 24px;
  text-align: center;
  transition: all 0.3s ease;
}

.feature-card:hover {
  border-color: var(--gray-300);
  transform: translateY(-2px);
}
```

## 4. 技術仕様

### 4.1 使用技術
- **HTML5**: セマンティックマークアップ
- **CSS3**: CSS Variables, Flexbox, Grid, Media Queries
- **JavaScript**: ES6+, DOM操作
- **フォント**: Google Fonts (Inter)

### 4.2 ファイル構成
```
/
├── src/
│   ├── index.html          # メインページ
│   ├── style.css           # スタイルシート
│   └── script.js           # JavaScript
├── assets/
│   ├── images/
│   │   └── icons/          # アイコン類
│   └── fonts/              # フォントファイル
└── docs/
    └── SPECIFICATION.md    # 仕様書
```

### 4.3 ブラウザ対応
- **Chrome**: 最新版 + 1世代前
- **Firefox**: 最新版 + 1世代前
- **Safari**: 最新版 + 1世代前
- **Edge**: 最新版 + 1世代前

### 4.4 パフォーマンス要件
- **初回表示**: 2秒以内
- **インタラクション応答**: 100ms以内
- **Lighthouseスコア**: 90以上

## 5. コンテンツ仕様

### 5.1 ヒーローセクション
```html
<header class="hero">
  <div class="hero-content">
    <h1 class="title">@qqqq99999</h1>
    <p class="subtitle">生徒によるアプリ開発チーム</p>
    <p class="description">
      クラスメイトと一緒に学校生活をより良くするアプリを開発中。<br>
      失敗しながら学び、成長していく過程を記録しています。
    </p>
    <div class="hero-actions">
      <a href="https://github.com/qqqq99999" class="btn btn-primary">
        GitHub
      </a>
      <button class="btn btn-secondary">
        プロジェクトを見る
      </button>
    </div>
  </div>
</header>
```

### 5.2 特徴セクション
```html
<section class="features">
  <div class="feature-grid">
    <div class="feature-card">
      <h3>仲間との開発</h3>
      <p>クラスメイトと協力してアイデアを形にする楽しさ</p>
    </div>
    <div class="feature-card">
      <h3>学習記録</h3>
      <p>プログラミング学習の過程や発見をシェア</p>
    </div>
    <div class="feature-card">
      <h3>挑戦と成長</h3>
      <p>エラーを乗り越えながらスキルアップしていく日々</p>
    </div>
  </div>
</section>
```

## 6. レスポンシブデザイン

### 6.1 ブレークポイント
```css
/* モバイル */
@media (max-width: 768px) {
  .title { font-size: 2.5rem; }
  .feature-grid { grid-template-columns: 1fr; }
}

/* タブレット */
@media (min-width: 769px) and (max-width: 1024px) {
  .title { font-size: 3rem; }
  .feature-grid { grid-template-columns: repeat(2, 1fr); }
}

/* デスクトップ */
@media (min-width: 1025px) {
  .title { font-size: 4rem; }
  .feature-grid { grid-template-columns: repeat(3, 1fr); }
}
```

### 6.2 モバイルファースト設計
- 基本スタイルはモバイル向け
- メディアクエリで大画面向けに拡張
- タップ領域の確保（44px以上）
- フォントサイズの適切な調整

## 7. アクセシビリティ

### 7.1 WCAG 2.1 AA準拠
- **コントラスト比**: 4.5:1以上（通常テキスト）
- **キーボードナビゲーション**: 全機能アクセス可能
- **スクリーンリーダー**: 適切なARIAラベル

### 7.2 実装要件
- セマンティックHTMLの使用
- 代替テキストの設定
- フォーカスインジケーターの明確化
- ジャンプコンテンツの提供

## 8. SEO対策

### 8.1 メタ情報
```html
<meta name="description" content="学校アプリ開発チームqqqq99999のGitHubプロフィール。教育の未来を創造するアプリケーション開発について紹介します。">
<meta name="keywords" content="学校アプリ,教育技術,開発,GitHub,オープンソース">
<meta property="og:title" content="qqqq99999 - 学校アプリ開発チーム">
<meta property="og:description" content="教育の未来を創造するアプリケーション開発">
<meta property="og:type" content="website">
<meta property="og:url" content="https://qqqq99999.github.io/">
```

### 8.2 構造化データ
```json
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "qqqq99999",
  "description": "学校アプリ開発チーム",
  "url": "https://github.com/qqqq99999",
  "sameAs": ["https://github.com/qqqq99999"]
}
```

## 9. 開発スケジュール

### 9.1 フェーズ1: 基盤構築（1週間）
- HTML構造の実装
- 基本スタイルの適用
- レスポンシブ対応

### 9.2 フェーズ2: 機能実装（1週間）
- インタラクション実装
- アニメーション追加
- パフォーマンス最適化

### 9.3 フェーズ3: テストと改善（1週間）
- クロスブラウザテスト
- アクセシビリティ検証
- コンテンツ調整

## 10. 品質基準

### 10.1 コード品質
- HTML5バリデーション通過
- CSS3バリデーション通過
- ESLintルール準拠（JavaScript）

### 10.2 パフォーマンス
- PageSpeed Insights: 90点以上
- Lighthouse: 緑評価
- Core Web Vitals: 全項目合格

### 10.3 ユーザビリティ
- 直感的な操作感
- 読み込み速度の速さ
- モバイルでの使いやすさ
