Visual Studio CodeでC/C++を扱う際の設定集。

使用する場合には、`clone`の上、ファイルを任意のプロジェクトの`.vscode`フォルダに格納してください。

# ディレクトリ構成例

```terminal
$ tree
.
├── .vscode
│   ├── c_cpp_properties.json
│   ├── launch.json
│   ├── settings.json
│   └── tasks.json
├── bin
├── lib
├── src
├── いろいろ…
```

# 動作環境
`WSL2`, `Ubuntu24-04`。

# 使い方
ディレクトリ構成例のようにフォルダを配置してください。
そのあと、適当なC言語やC++などのファイルを開いて`F5`を押下すると起動します。

# なんでlunch設定が二つあるの？
デバッグ用とビルド用で分けています。
`vscode`の`Run and Debug`というタブを開いて、タブ上部にあるウィンドウからこの二つを切り替えることができます。
やりたいなら`Python`や`Ruby`などの設定を追加することもできます。

# コマンドライン引数を受け取りたいんだけど？

```c
#include <stdio.h>

int main(int argc, *argv[])
{
  FILE *fp = fopen(argv[1]);
  if (*fp == NULL)
  {
    ~~~
  }
}
```

こういったコマンドライン引数を受け取るアプリを作る際には次のように設定します。

`launch.json`を開き、`args`という項目を探します。そしてその値`[]`の中に必要なテキストを入力します。

例えば上のコードなら、`["filename.txt"]`と指定してやるといいです。

# clang使いたいんですけど
各ファイルにコメントを残しているので、それを見ながら書き換えてください。

# 質問などは
至急issue立ててくれや
