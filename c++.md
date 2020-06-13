# c++ について

Mac の場合、 デフォルトで入っている g++ コマンドは clang++ のエイリアスで、 brew install gcc で入ってくるのが本物の g++ コマンドである というひどい罠があります。
「clang がデフォルトで入っています」と言いながら g++を紹介するのは Mac では間違ってないですが、一般的に g++コマンドは gcc の一部であって clang のコマンドのことは指しません。
clang の C++コンパイラを使いたい場合はデフォルトで入っている clang++ を使い、gcc の C++コンパイラを使いたい場合は brew install gcc でインストールした後に g++ を使うべきであって、デフォルトで入っている g++ をそのまま使うのはあまり良い習慣ではないと思います。

# vscode でコンパイルするまで(command + m)

1. brew install gcc
2. シンボリック作成(リンク)
   ln -s /usr/local/bin/g++-9 /usr/local/bin/g++
3. 確認
   \$ which g++
   /usr/local/bin/g++
4. code-runner の設定

```settings.json
{
    "workbench.colorTheme": "Monokai Dimmed",
    "code-runner.runInTerminal": true,
    "workbench.sideBar.location": "left",
    "editor.suggestSelection": "first",
    "vsintellicode.modify.editor.suggestSelection": "automaticallyOverrodeDefaultValue",
    "runner.languageMap": {
        "cpp": "/Users/[user名]/vsc_run/cpp.sh"
    }
}
```

5. スクリプト作成

```
cd ~/
mkdir vsc_run
vim cpp.sh

#!/bin/zsh

file=$1
objfile=`echo $file | sed 's/\.[^\.]*$//'`

g++ -g -o $objfile $file
$objfile
```

6. 動作確認(command + m)

参考
Visual studio code で競プロ環境構築[mac OS]
https://qiita.com/EngTks/items/ffa2a7b4d264e7a052c6

C++で始める競プロ / VSCode の環境構築（Mac）
https://qiita.com/YasufumiNakama/items/6efa6975f551a1986e89
