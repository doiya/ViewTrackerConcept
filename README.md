# ViewTracker

## 概要

舞台などを複数台のカメラで配信する際、カメラのスイッチングが必要となる。

このプロジェクトでは、観客の顔の向きから舞台上の注目場所を判断し、自動でカメラのスイッチングを行う。

現在はそのコンセプトを作成中。

## 実装

コンセプトである現段階では、左右の目と鼻の距離を比較して顔の向きを判定している。

計算式
```
(左目と鼻の距離) = | (左目のx座標) - (鼻のx座標) |
(右目と鼻の距離) = | (右目のx座標) - (鼻のx座標) |

(左目と鼻の距離) / (右目と鼻の距離) < 3/5 -> 下手カメラ
3/5 <= (左目と鼻の距離) / (右目と鼻の距離) <= 5/3 -> 正面カメラ
(左目と鼻の距離) / (右目と鼻の距離) > 5/3 -> 上手カメラ
```

また、JSのライブラリであるp5.jsを映像の取得に利用し、ml5.jsを顔の各パーツの座標取得に利用している。

## デモ

以下でデモを確認できる。

https://doiya.github.io/ViewTrackerConcept

※ 使用するデバイス、ブラウザなどの環境によっては動作しないことがあります。
