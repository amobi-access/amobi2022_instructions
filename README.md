# amobi2022_instructions

## 速度測定プログラムのバグ
`vel_observe.py` や `observe_velocity.py` を利用する際，ラジコンが走り出さない現象への対処方法．

1. `refactored`の確認

   スクリプトファイルと同じディレクトリに `refactored` ディレクトリがあることを確認．無い場合には[こちら](https://github.com/AdvancedMobilityCourse/amobi2022.git "amobiサンプルプログラムレポジトリ")からクローン・コピー．

2. スクリプトの修正

   以下のように`vel_observe.py` / `observe_velocity.py` を修正．

   ![alt text][fig1]  
   ![alt text][fig2]  
    ```python
    from refactored.speed_observer import SpeedObserver
    ```
    ```python
    speed_ob = SpeedObserver(A_PIN=22, B_PIN=27)
    ```
    `22`, `27` は接続しているエンコーダのピン番号や変数に変更．
    ```python
    speed_ob.updateSpeed()
    velocity = speed_ob.getSpeed()
    ```


[fig1]: https://github.com/amobi-access/amobi2022_instructions/blob/main/figs/speed_observer-1.png "speed_observer-1"
[fig2]: https://github.com/amobi-access/amobi2022_instructions/blob/main/figs/speed_observer-2.png "speed_observer-2"
