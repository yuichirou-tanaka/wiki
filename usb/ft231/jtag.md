# usbをjtagに変換する方法の調査メモ
RXD,TXDだけで行けるっぽい。

# 信号線
- TCK（クロック）
- TDI（データ入力）
- TDO（データ出力）
- TMS（状態制御）
 
- TRST(リセット信号（オプション）)
 

# link
## repository
- https://github.com/osafune/usjtag


# FTDIの資料
- https://ftdichip.com/document/application-notes/
- [JTAGとは何か](http://www.tokudenkairo.co.jp/jtag/whatisjtag.html)
## blog記事
- http://suz-avr.sblo.jp/article/65099152.html

# AE_FT232HL
- https://akizukidenshi.com/catalog/g/gK-06503/
- MPSSEでつなげるピンが載っている。
- ![image](https://user-images.githubusercontent.com/80798265/158094172-b252c08f-24d7-46d8-a0ff-8c5706629f21.png)

# Bit Bang モードについて
- [できる！Bit Bangモード](https://ore-kb.net/wordpress/wp-content/uploads/2013/03/how_to_use_bitbang.pdf)
- 汎用IOを変更できる
