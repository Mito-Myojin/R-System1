# R-System1
講義の課題1として提出したデバイスドライバです。LEDが光ります。

# Demo

# Features
- LEDの点灯
- LEDの消灯
- LEDを108回点滅

# Usage
1. 「Makefile」「myled.c」をラズパイの同一ディレクトリに保存。
2. 以下のコマンドを実行。
    ```
    $ make
    $ sudo insmod myled.ko
    $ sudo mknod /dev/myled0 c 240 0
    $ sudo chmod 666 /dev/myled0
    ```
3. 使いたい機能に合わせて以下のコマンドの何れかを実行。処理が完了しプロンプトが表示された状態であれば何度でもLEDの挙動を変えることができます。
    ```
    $ echo 0 > /dev/myled0    // LEDの消灯
    $ echo 1 > /dev/myled0    // LEDの点灯
    $ echo 2 > /dev/myled0    // LEDを108回点滅
    ```
4. カーネルモジュールをアンロードする場合は以下を実行。
    ```
    $ sudo rmmod myled.ko
    ```

# Requirement
- Raspbian（Linuxカーネル） 
- Raspberry Pi 3 Model B
