# レンジ式
- http://www.kumikomi.net/archives/2009/07/verilog_hdl_2.php?page=3

```
+:
```

```
bits = help_bits[20 +: 5]; // 24-20
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
