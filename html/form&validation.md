
# HTMLのフォームとバリデーション

## HTML入力フォームの基本

HTMLで入力フォームを作成するには、`<form>` タグを使用します。フォーム内にはさまざまな入力要素を追加できます。

```html
<form action="/submit" method="POST">
    <label for="name">名前:</label>
    <input type="text" id="name" name="name" required>
    
    <label for="email">メールアドレス:</label>
    <input type="email" id="email" name="email" required>
    
    <label for="password">パスワード:</label>
    <input type="password" id="password" name="password" required>
    
    <input type="submit" value="送信">
</form>
```

## 入力要素の種類


- **テキストボックス**: `<input type="text">`
- **メールアドレス**: `<input type="email">` 
- **パスワード**: `<input type="password">`
- **ラジオボタン**: `<input type="radio">`
- **チェックボックス**: `<input type="checkbox">`
- **セレクトボックス**: `<select>`
- **日付**: `<input type="date">`

## バリデーション

- **`required`**: 入力が必須であることを指定します。
- **`minlength`**: 最小文字数を指定します。
- **`maxlength`**: 最大文字数を指定します。
- **`pattern`**: 正規表現に基づいたカスタムバリデーションを指定します。
- **`type`**: 入力の型を指定します（`email`, `url`, `number` など）。

```html
<form action="/submit" method="POST">
    <label for="username">ユーザー名:</label>
    <input type="text" id="username" name="username" minlength="3" maxlength="15" required>
    
    <label for="email">メールアドレス:</label>
    <input type="email" id="email" name="email" required>
    
    <label for="age">年齢:</label>
    <input type="number" id="age" name="age" min="1" max="120" required>
    
    <label for="password">パスワード:</label>
    <input type="password" id="password" name="password" minlength="8" required>
    
    <input type="submit" value="送信">
</form>
```

## フォームの送信

フォームが送信されると、指定した `action` 属性の URL にデータが送信されます。`method` 属性は、データの送信方法を指定します。

- **`GET`**: URLのクエリパラメータとしてデータを送信します。データがURLに表示されるため、少量の情報の送信に適しています。
- **`POST`**: ボディの中にデータを含めて送信します。大量のデータを送信する場合や、機密情報を送信する場合に適しています。
