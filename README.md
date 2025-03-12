# ひまわり衛星True Color補正プログラム

気象衛星ひまわり8号・9号衛星データの陸・海域を鮮明に見ることができるよう、ひまわりTrue colorの色補正を行うImageMagickコマンドです。

## 必要条件

- ImageMagick 6.9.10-68

## 使用方法

### フルディスク画像の補正

```bash
convert {input}.png -level 0%,100%,1.5 -modulate 100,250,102 -contrast -quality 99 {output}.png
```

#### パラメータの説明
- `-level 0%,100%,1.5`: 画像のレベルを調整します。入力の黒点と白点を0%と100%に設定し、ガンマ補正を1.5に設定しています。
- `-modulate 100,250,102`: 画像の明るさ、彩度、色相を調整します。明るさを100%、彩度を250%、色相を102%に設定しています。
- `-contrast`: 画像のコントラストを強調します。
- `-quality 99`: 出力画像の品質を99%に設定します。

### 日本域画像の補正

```bash
convert {input}.png -gamma 1.6 -modulate 100,290,102 -contrast -sharpen 2 -quality 99 {output}.png
```

#### パラメータの説明
- `-gamma 1.6`: 画像のガンマ補正を1.6に設定します。画像の中間トーンが明るくなります。
- `-modulate 100,290,102`: 画像の明るさ、彩度、色相を調整します。明るさを100%、彩度を290%、色相を102%に設定しています。
- `-contrast`: 画像のコントラストを強調します。
- `-sharpen 2`: 画像をシャープにします。シャープネスの強度を2に設定しています。
- `-quality 99`: 出力画像の品質を99%に設定します。

## 使用例

1. フルディスク画像の場合:
```bash
convert input_fulldisk.png -level 0%,100%,1.5 -modulate 100,250,102 -contrast -quality 99 output_fulldisk.png
```

2. 日本域画像の場合:
```bash
convert input_japan.png -gamma 1.6 -modulate 100,290,102 -contrast -sharpen 2 -quality 99 output_japan.png
```

## ライセンス

このプロジェクトはMITライセンスの下で公開されています。