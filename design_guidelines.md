# CNPトレカ究極版デザインガイドライン - Claude CODE指示文

## 基本指示文テンプレート

以下の指示文を使用して、CNPトレカの他の画面を統一されたデザインで作成してください。

---

### 【究極版デザイン継承】CNPトレカ [画面名] 制作用プロンプト

あなたは世界的なアワードを受賞するレベルの天才Webデザイナー兼フロントエンドエンジニアです。
既存の究極版LPのデザインテイストを完全に継承し、[画面名]を制作してください。

#### 1. デザインコンセプト（必須継承要素）

**テーマ**: "Future Luxury" & "Cyber Abyss" (未来的高級感とサイバーな深淵)

**カラーパレット**（厳守）:
```css
--primary-black: #000000;
--secondary-black: #050505;
--dark-gray: #111111;
--medium-gray: #1a1a1a;
--light-gray: #333333;
--accent-purple: #8b5cf6;
--accent-blue: #3b82f6;
--accent-cyan: #06b6d4;
--text-white: #ffffff;
--text-gray: #a1a1aa;
--text-light: #d4d4d8;
--glass-bg: rgba(255, 255, 255, 0.02);
--glass-border: rgba(255, 255, 255, 0.1);
--glow-purple: rgba(139, 92, 246, 0.3);
--glow-blue: rgba(59, 130, 246, 0.3);
```

**背景要件**:
- 全体を漆黒（#000000）で統一
- Three.jsによる1000個のパーティクルシステムを実装
- 紫から青へのグラデーション効果
- 有機的な波動アニメーション

#### 2. UI要素の統一仕様

**グラスモーフィズム要素**:
```css
background: rgba(0, 0, 0, 0.4);
backdrop-filter: blur(20px);
border: 1px solid rgba(255, 255, 255, 0.1);
```

**カード/パネルデザイン**:
```css
background: var(--glass-bg);
backdrop-filter: blur(20px);
border: 1px solid var(--glass-border);
border-radius: 20px;
padding: 3rem 2rem;
transition: all 0.5s ease;
```

**ホバーエフェクト（繊細な浮上）**:
```css
:hover {
    transform: translateY(-5px) translateZ(5px);
    border-color: var(--accent-blue);
    box-shadow: 0 20px 40px rgba(59, 130, 246, 0.1);
}
```

**ボタンスタイル（光が走るエフェクト）**:
```css
position: relative;
overflow: hidden;
border: 1px solid var(--accent-blue);
border-radius: 50px;

::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, transparent, var(--accent-blue), transparent);
    transition: left 0.6s ease;
}

:hover::before {
    left: 100%;
}
```

#### 3. タイポグラフィ仕様

**フォント使用ルール**:
- 見出し: `font-family: 'Zen Old Mincho', serif;` （高級感）
- 本文: `font-family: 'Noto Sans JP', sans-serif;` （可読性）
- 見出しサイズ: `clamp(2.5rem, 6vw, 5rem)`
- 文字間隔: 見出し `letter-spacing: 3px;` / 本文 `letter-spacing: 1px;`

**グラデーションテキスト**:
```css
background: linear-gradient(135deg, var(--accent-purple), var(--accent-blue));
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background-clip: text;
```

#### 4. アニメーション仕様

**スクロールフェードイン**:
```javascript
// Intersection Observer実装必須
const observerOptions = {
    threshold: 0.1,
    rootMargin: '0px 0px -50px 0px'
};
```

**タイプライターアニメーション**（必要な場合）:
```javascript
function typeWriter(element, text, speed = 150) {
    // 150ms/文字の速度で実装
}
```

**必須アニメーション**:
- 要素の出現: `opacity: 0` → `opacity: 1` + `translateY(30px)` → `translateY(0)`
- トランジション: すべて `0.5s ease` 以上の滑らかさ
- Three.jsパーティクル: 常時有機的に動く

#### 5. レイアウト原則

**余白の使い方**:
- セクション間: `padding: 6rem 2rem;`
- カード内: `padding: 3rem 2rem;`
- 要素間: 最低 `2rem` のギャップ

**グリッドシステム**:
```css
display: grid;
grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
gap: 2rem;
```

#### 6. 実装要件

**必須ライブラリ**:
```html
<!-- Three.js -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<!-- Lucide Icons -->
<script src="https://unpkg.com/lucide@latest/dist/umd/lucide.js"></script>
<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Zen+Old+Mincho:wght@400;700;900&family=Noto+Sans+JP:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

**レスポンシブ対応**:
- ブレークポイント: 768px
- モバイルではThree.js無効化（パフォーマンス優先）

#### 7. 画面固有の要件

[ここに画面固有の要件を記載]

---

## 使用例

### デッキビルダー画面の場合：
```
【究極版デザイン継承】CNPトレカ デッキビルダー画面 制作用プロンプト

[上記テンプレートを使用]

#### 7. 画面固有の要件
- カード一覧は半透明のグリッドで表示
- カードホバー時は3D回転エフェクト
- デッキ構築エリアはグラスモーフィズムパネル
- ドラッグ&ドロップ時は紫のグロー効果
- カード詳細モーダルは中央に浮遊する感じで表示
```

### ルール解説画面の場合：
```
【究極版デザイン継承】CNPトレカ ルール解説画面 制作用プロンプト

[上記テンプレートを使用]

#### 7. 画面固有の要件
- 各ルールセクションは折りたたみ可能なアコーディオン
- 図解エリアは半透明の大きなパネル
- ナビゲーションは左側固定のグラスモーフィズムサイドバー
- 重要ポイントは紫→青のグラデーションで強調
- 例示カードは浮遊アニメーション付きで表示
```

## 重要な注意点

1. **統一感の維持**: すべての画面で同じカラーパレット、フォント、アニメーションを使用
2. **高級感の演出**: 余白を大胆に使い、情報を詰め込まない
3. **パフォーマンス**: モバイルでは重いエフェクトを適切に無効化
4. **アクセシビリティ**: 美しさを保ちながら、使いやすさも確保

## チェックリスト

制作完了時に以下を確認：
- [ ] 漆黒の背景が基調となっているか
- [ ] Three.jsパーティクルが実装されているか
- [ ] グラスモーフィズム要素が適切に使われているか
- [ ] ホバーエフェクトが繊細で上品か
- [ ] フォントが仕様通りか
- [ ] アニメーションが滑らかか
- [ ] レスポンシブ対応ができているか
- [ ] 全体的に「Future Luxury」の世界観が表現されているか