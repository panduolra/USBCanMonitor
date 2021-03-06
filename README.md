# USBCanMonitor

## ダウンロード

```
$ git clone http://github.com/muratamuu/USBCanMonitor.git
```

## コンパイル

```
$ make
```

### フラッシュ焼き込み

予めPICの4番ピンをGNDにショートさせて焼き込みモードにしてから次のコマンドを実行

```
$ make flash
```

または
```
$ mphidflash -write main.hex -n -reset
```

### シリアルコマンド

- 通常モードで送受信開始
```
$ O (大文字オー)
```

- リスンオンリーモードで送受信開始
```
$ L
```

- 終了
```
$ C
```

- CANデータ送信  
`T` + `CH番号(1-4):1桁` + `CANID(000-7FF)` + `DLC(1-8)` + `Data(xx....):最大16桁`  

```
チャネル1からCANID(0x750)で3バイト(0x1122CC)を送る
$ T175031122CC
```

```
チャネル3からCANID(0x0B4)で8バイト(0x1234567812345678)を送る
$ T30B481234567812345678
```
