---
title: "Polestarでの独自実装の話"
date: 2023-08-17T22:24:52+09:00

tags: ["psr"]
author: "Soli"

draft: false
---

Polestarで利用しているMisskeyは、本体のバージョンに追いつきつつ、独自の実装をしています。  
この記事では現時点での、独自実装について紹介します。

## myaize

Misskeyには「な」が「にゃ」に変換される猫モードが存在しますが、これを模倣したような機能で、「ま」が「みゃ」となったり、「みや」が「みゃ」に置き換えられます。
![myaize](https://media.soli0222.com/polestar/1d5999fb-d175-447e-ac1e-b6107d64d1cc.webp)

## サークル

Misskeyは公開範囲を選択することができ、その上で連合の有無を選択できますが、Polestarではフォロワーかつ連合なしという非常に閉鎖的な公開範囲が多用されています。

この公開範囲にするために、デフォルトでは公開範囲を選択してから、連合を切るといった動作が必要であり、手間であることから、1タップで切り替えられるようなボタンを配置しました。

サーバーメンバーがもともとTwitterのサークルのメンバーであることから、サークルとしています。

![circle1](https://media.soli0222.com/polestar/82d72c39-84cf-4279-af53-d6944817feca.png)
![circle2](https://media.soli0222.com/polestar/69186c96-5957-48d2-b8e8-07c83e394dea.webp)

## おわりに

この実装がなされたバージョンのMisskey 13.14.2-psr.2.0は[こちら](https://github.com/Soli0222/misskey)にソースコードがあります。  
今後、新しく独自実装がされたときはまた記事を書きます。
