# 理想の python 環境

- 基本的には docker を使えば問題ない。他人からもらった jupyter も動かせるはず。
- jupyter を渡す時に環境ごと渡したい。

# pip とは

-　パッケージ管理ツール

# pyenv のインストール

## 必要なもの

- xcode-select
- Homebrew

## 前提知識

- xcode はデフォルトでインストールされているものがあって、それを使うと sudo が必要。xcode-select でインストールした方が良い。

```
smotoshei ~
木 11/ 21:49:49 xcode-select -p
/Library/Developer/CommandLineTools
```

上記の xcode 見てない場合は切り替え

- pyenv install 3.8.2 で

```
python-build: use openssl@1.1 from homebrew
python-build: use readline from homebrew
Downloading Python-3.8.2.tar.xz...
-> https://www.python.org/ftp/python/3.8.2/Python-3.8.2.tar.xz
Installing Python-3.8.2...
python-build: use readline from homebrew
python-build: use zlib from xcode sdk

BUILD FAILED (OS X 10.15.5 using python-build 20180424)

Inspect or clean up the working tree at /var/folders/st/40w481fj1g98n3b4mgppj65r0000gn/T/python-build.20200611220023.23196
Results logged to /var/folders/st/40w481fj1g98n3b4mgppj65r0000gn/T/python-build.20200611220023.23196.log

Last 10 log lines:
  File "<frozen zipimport>", line 259, in load_module
  File "/var/folders/st/40w481fj1g98n3b4mgppj65r0000gn/T/tmpeqwmqs5w/pip-19.2.3-py2.py3-none-any.whl/pip/_vendor/requests/utils.py", line 26, in <module>
  File "<frozen zipimport>", line 259, in load_module
  File "/var/folders/st/40w481fj1g98n3b4mgppj65r0000gn/T/tmpeqwmqs5w/pip-19.2.3-py2.py3-none-any.whl/pip/_vendor/requests/_internal_utils.py", line 11, in <module>
  File "<frozen zipimport>", line 259, in load_module
  File "/var/folders/st/40w481fj1g98n3b4mgppj65r0000gn/T/tmpeqwmqs5w/pip-19.2.3-py2.py3-none-any.whl/pip/_vendor/requests/compat.py", line 62, in <module>
  File "/private/var/folders/st/40w481fj1g98n3b4mgppj65r0000gn/T/python-build.20200611220023.23196/Python-3.8.2/Lib/urllib/request.py", line 2588, in <module>
    from _scproxy import _get_proxy_settings, _get_proxies
ModuleNotFoundError: No module named '_scproxy'
make: *** [install] Error 1
```

# vscode での設定

https://qiita.com/kahirokunn/items/512b9e502f8db49981f3

のようなエラーが発生したが、sudo をつけると問題なくインストールできた。

# 参考

python を書き始める前に見るべき Tips
https://qiita.com/icoxfog417/items/e8f97a6acad07903b5b0

pyenv インストール
https://qiita.com/crankcube/items/15f06b32ec56736fc43a

pyenv バージョン切り替え
https://qiita.com/koooooo/items/b21d87ffe2b56d0c589b

pyenv + anaconda
