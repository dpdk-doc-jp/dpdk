# DPDKドキュメント日本語化プロジェクト(仮)


## 1. はじめに

[DPDK](https://www.dpdk.org/) (Data Plane Development Kit)の各種ドキュメントを
日本語化して公開するための有志プロジェクトです。


## 2. 使い方

DPDKのドキュメントは一部を除き全て
[開発リポジトリ](https://git.dpdk.org/dpdk/)
に含まれており、
他のソースコードと同様にmakeコマンドからビルドします。
ここではドキュメントの生成に必要な手順について説明します。

なおこのリポジトリ自体もDPDKから派生しており、
DPDKではドキュメントの種別としてHTML形式の他にPDF形式もサポートされていますが、
日本語ドキュメントは現在HTML形式のみです。

### 環境構築

ドキュメントのコンパイルに必要なツールは以下のようにインストールします
(注: PDF文書の生成にのみ必要なツールも含まれています)。
それぞれの詳細に関してはDPDKの
[Building the Documentation](https://doc.dpdk.org/guides/contributing/documentation.html#building-the-documentation)
を参照してください。

```sh
# Ubuntu/Debian.
$ sudo apt-get -y install doxygen python-pip inkscape latexmk
$ sudo pip install --upgrade sphinx sphinx_rtd_theme

# Red Hat/Fedora.
$ sudo dnf -y install doxygen python-pip inkscape latexmk
$ sudo pip install --upgrade sphinx sphinx_rtd_theme
```

### ソースコードの入手

```sh
$ git clone https://github.com/dpdk-doc-jp/dpdk.git
```

日本語ドキュメントは`doc-jp`ブランチにて作成されていますので、ブランチが適切かどうかを
念の為確認してください。

```sh
$ cd dpdk
$ git branch
* doc-jp
```

### HTML文書の生成

HTML文書のコンパイル方法は次の通りです。完了すると`build/doc/html/`にドキュメントが生成されます。

```sh
$ make doc-guides-html
$ ls build/doc/html/guides/
bbdevs        eventdevs      howto       mempool      prog_guide     search.html     testpmd_app_ug
compressdevs  faq            _images     nics         rawdevs        searchindex.js  tools
contributing  freebsd_gsg    index.html  objects.inv  rel_notes      _sources        windows_gsg
cryptodevs    genindex.html  linux_gsg   platform     sample_app_ug  _static
```
