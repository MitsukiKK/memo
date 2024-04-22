# amplify-ui

- reactで使用できるライブラリ(https://ui.docs.amplify.aws/)
- cognitoを用いたログイン画面を簡単に利用でき、カスタムも可能
- ボタンなどのパーツも用意されているので利用可（細かいデザインの編集はできないのであまりお勧めではない）

## ログイン画面

``` react
インポート
import { withAuthenticator } from "@aws-amplify/ui-react"

const App = ({ signOut, user }) => {
    // 描画内容
}

export default withAuthenticator(App);
```

これにより既存のログイン画面を使うことが可能  
使用するAWSアカウントなどの設定が別途必要だが今回は省く

`signOut` は ユーザからのサインアウト時に用いるもので、  
`user` は ログインしたユーザ情報が入っている（ユーザ名やらなんやら）  
他で定義したコンポーネント内で使いたいときはコンテキストなどで渡すこと

`export default withAuthenticator(App, { hideSignUp: true });`  
こうするとサインアップ画面を消したりできる  
その他のカスタムも結構あるので公式参照

ログイン画面は基本英語になるので  
`import { translations } from "@aws-amplify/ui-react"`
を追加し  
``` react
I18n.putVocabularies(translations);
I18n.setLanguage("ja");
```
とやると日本語にできる
