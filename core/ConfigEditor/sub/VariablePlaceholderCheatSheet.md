# 変数プレースホルダー チートシート

## 📌 クイックリファレンス

|機能|書式例|説明|結果例|
|---|---|---|---|
|**変数宣言**|`{{var name='値'}}`|変数 `name` に「値」を保存|(値は保存される)|
|**変数参照**|`{{name}}`|変数 `name` の値を表示|`値`|
|**ランダム**|`{{rand(1,10)}}`|1～10 の乱数を生成|`7`|
|**加算**|`{{calc score += 5}}`|変数 `score` に 5 を加算|(score が更新)|
|**減算**|`{{calc hp -= 1}}`|変数 `hp` から 1 を減算|(hp が更新)|
|**乗算**|`{{calc attack *= 2}}`|変数 `attack` を 2 倍にする|(attack が更新)|
|**除算**|`{{calc total /= 2}}`|変数 `total` を 2 で割る|(total が更新)|

## 📝 `var` - 変数の基本

### 変数の宣言・保存

値を変数に保存します。ブラウザ/OBS を閉じるまで値は保持されます。

```javascript
{{var userName="視聴者A"}}
{{var score=100}}
{{var item="大吉"}}
{{var flag=true}}
```

### 変数の参照

保存した変数の値を取り出します。

```javascript
{{userName}}さん、こんにちは！
あなたのスコア: {{score}}
今日の運勢: {{item}}
```

### 変数の更新

同じ変数名で再度宣言すると、値が上書きされます。

```javascript
{{var text=" 最初 "}}{{var text=" 最後 "}}{{text}}
```

→ **結果: 「最後」**

### プレースホルダーとの連携

通常プレースホルダーの結果を変数に保存できます。

```javascript
{{var totalPrice +=<<price>>}}
ギフト合計: {{totalPrice}}
```

## 🔢 `rand` - ランダム数値

指定範囲の整数をランダムに生成します。

```javascript
// 基本形
ラッキーナンバー: {{rand(1, 100)}}

// 変数と組み合わせ
{{var dice=rand(1, 6)}}
サイコロの目: {{dice}}

// 複数回使用
攻撃力: {{rand(10, 20)}} / 防御力: {{rand(5, 15)}}
```

## 🧮 `calc` - 数値計算

### 四則演算

```javascript
// 初期化
{{var score=0}}

// 加算
{{calc score += 10}}  // score = 10

// 減算  
{{calc score -= 3}}   // score = 7

// 乗算
{{calc score *= 2}}   // score = 14

// 除算
{{calc score /= 2}}   // score = 7
```

### ランダム値との組み合わせ

```javascript
{{var damage=10}}
{{calc damage += rand(0, 5)}}
与ダメージ: {{damage}}
```

### 複雑な計算チェーン

```javascript
{{var base=50}}
{{calc base += rand(1, 20)}}
{{calc base *= 2}}
最終値: {{base}}
```

## ⚙️ 応用パターン

### 1. 値の評価ルール

|記述例|評価結果|説明|
|---|---|---|
|`{{var a='123'}}`|文字列 `"123"`|クォートあり = 文字列|
|`{{var b=123}}`|数値 `123`|数値のみ = 数値|
|`{{var c=foo}}`|変数 `foo` の値|既存変数 = その値|
|`{{var d=bar}}`|文字列 `"bar"`|未宣言 = 文字列|

### 2. 動的変数名

javascript

```javascript
{{var <<アイテム名>>=<<価格>>}}
```

→ `<<アイテム名>>` が「sword」、`<<価格>>` が「100」の場合

→ `{{var sword=100}}` として実行

### 3. カウンターの実装

```javascript
// 訪問回数をカウント
{{var visitCount=0}}
{{calc visitCount += 1}}
{{userName}}さんの訪問回数: {{visitCount}}回目
```

### 4. ランキングシステム

```javascript
// スコアを記録
{{var score=rand(1, 100)}}
{{var text=score}}  // 予約語「text」に値をセット

// 以下のように表示可能
{{userName}}さん: {{score}}点
```

## ⚠️ 予約語リスト

以下の変数名は特別な用途で使用されます（アイテムに値を渡す）。

|予約語|用途例|
|---|---|
|`text`|表示テキスト|
|`symbol`|シンボル/アイコン|
|`name`|名前/称号|
|`variant`|バリエーション種別|
|`unique`|ユニーク ID|
|`slot0`～`slot9`|追加データスロット|

**※各予約語の実際の用途は、接続するアイテムによって異なります。**

## 💡 実用例

### ゲーム風スコアリング

```javascript
{{var player=<<ユーザー名>>}}
{{var baseScore=rand(50,100)}}
{{var bonus=rand(1,30)}}
{{calc total = baseScore + bonus}}

{{player}}のスコア！基礎: {{baseScore}}点,ボーナス: +{{bonus}}点,合計: {{total}}点
```

## 🚫 制限事項

1. **数値範囲**: -999,999,999 ～ 999,999,999
2. **小数点**: 0.01 単位まで（それ以下は丸め）
3. **文字制限**: 変数名は英数字、先頭は英字のみ
4. **処理順**: プレースホルダー → 変数プレースホルダー