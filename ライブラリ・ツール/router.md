# Router

- reactで使用できるライブラリ(https://reactrouter.com/en/main)
- ルーティングを行えるようにするライブラリ  
- 複数画面がある構成だと大体使用する

## 使い方

``` react
import { BrowserRouter, Routes, Route } from "react-router-dom"

const App = () => (
    <BrowserRouter>
        <Routes>
            <Route path="/" element={<コンポーネント/>} />
            <Route path="/任意のパス" element={<コンポーネント/>} />
            <Route path="/任意のパス" element={<コンポーネント/>} />
        </Routes>
    </BrowserRouter>
)
```

上記のようにすると、各コンポーネントに対してパスが生成される  
`localhost/任意のパス`

こうすると直リンク貼り付けやlinkなどを用いて特定の画面に遷移できる  
※直リンクでのアクセスはホストしているサーバーの設定も関係してくるので注意
