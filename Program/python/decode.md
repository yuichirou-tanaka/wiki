# 'utf-8' codec can't decode byte 0x00 in position 0: invalid start byte　が出た場合
## 原因
- encode decodeで日本語のパスがあるなどでUTF-8にしている場合に発生する
## 解決策
- encode, decode箇所をshift_jisにすることで解決

※paramikoのライブラリはすべてUFT-8にしているため、日本語のパスは取得できない。
