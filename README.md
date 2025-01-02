# grdc-patch
FreeBSD grdc(6) patch file

# ビルド方法
適当なサブディレクトリを作成して、上記パッチのダウンロードとオリジナルソースをコピーする。
```
$ mkdir my-grdc
$ cd my-grdc
$ cp /usr/src/usr.bin/grdc/grdc.c .
$ cp somewhere/grdc-patch.txt .
# ソースにパッチを適用する
$ patch -p0 <grdc-patch.txt
Hmm...  Looks like a unified diff to me...
The text leading up to this was:
--------------------------
|--- /usr/src/usr.bin/grdc/grdc.c	2023-12-02 20:06:31.413163000 +0900
|+++ grdc.c	2024-09-05 11:45:10.260641000 +0900
--------------------------
Patching file grdc.c using Plan A...
Hunk #1 succeeded at 18.
Hunk #2 succeeded at 44.
Hunk #3 succeeded at 111.
Hunk #4 succeeded at 279.
done
# エラーが無ければOK
$ cc -O2 grdc.c -lncursesw -o my-grdc
# エラーが無ければOK
```
