# レンジ式
- http://www.kumikomi.net/archives/2009/07/verilog_hdl_2.php?page=3

```Verilog
//+:
bits = help_bits[20 +: 5]; // 24-20の配列
//-:
bits = help_bits[15 -: 5]; // 15-11の配列
```


# $readmemb
- [$readmemb()でメモリの初期値を設定する](https://www.k0b0srecord.com/entry/2019/02/05/210140)
- [SystemVerilogで遊ぼう！ システムタスク](https://sites.google.com/site/playsystemverilog/others/system_task)
- 
```Verilog
// 初期値(rom.dat)を設定
initial 
begin
    $readmemb("rom.hex", mem);
end
```
ROMデータを配列に読み込む

# casez
- [補足　- z,xに対する比較演算子とcase文](http://zakii.la.coocan.jp/hdl/59a_zx_compare.htm)
