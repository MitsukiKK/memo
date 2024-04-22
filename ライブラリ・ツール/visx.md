# visx

- reactで使用できるライブラリ(https://airbnb.io/visx/)
- データビジュアライズを行える
- 使い勝手のいいライブラリというより、各パーツが揃っているのでそれを組み合わせてカスタマイズするといったもの（扱いが難しいが自由度が高い）
- 基本的な構成は公式サイトにサンプルが用意されているので参照

## 基本的な使い方

``` react
インポート
import { scaleLinear, scaleBand } from "@visx/scale";
import { Bar } from "@visx/shape";
import { Group } from "@visx/group";
import { AxisBottom, AxisLeft } from "@visx/axis";
import { GridRows } from "@visx/grid";
etc...
```

パーツ一つ一つでインポートが必要なので結構膨大

``` react
// 最初にこれで囲う
<svg width={width} height={height}>

// 背景
<rect x={x} y={y} width={width} height={height} fill={"color"} rx={rx} />

// グラフ描画
<Group>
    {data.map((d) => [
        // 描画したい内容（棒グラフならBar）
    ])}
</Group>
```

## 使う上で詰まる点

- 色々なタイプのグラフを合わせようとすると大変  
サンプルで用意されていない場合だと少し難易度が上がる（描画のソースとなるデータの持ち方に工夫が必要）

- 更新頻度や扱うデータ量によっては他のライブラリ・構成を検討すべき  
