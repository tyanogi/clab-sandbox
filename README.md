# Containerlab Network Development Environment

このリポジトリは、DevcontainerとContainerlabを使用したネットワーク検証およびOSSツールの開発環境です。

## 目的
1.  **OSSツールの機能開発**: `gnmic` などのネットワーク関連OSSのソースコードをクローンし、機能追加や修正を行います。
2.  **ネットワーク動作検証**: 開発したツールの動作確認や、ネットワーク構成の検証をContainerlabを用いて行います。

## ディレクトリ構成

```text
.
├── .devcontainer/             # Devcontainer設定 (開発環境の定義)
├── tools/                     # 開発対象のOSSソースコード配置場所
│   ├── gnmic/                 # 例: git clone ...
│   └── ...
├── topologies/                # Containerlabのトポロジ定義
│   ├── mini-topo/             # トポロジごとのディレクトリ
│   │   ├── mini-topo.clab.yml # ラボ定義ファイル
│   │   └── r1/                # 設定ファイルなど
│   └── ...
├── scripts/                   # 開発補助スクリプト (ビルド、デプロイなど)
├── docs/                      # ドキュメント
└── README.md                  # 本ファイル
```

## クイックスタート

### 1. Devcontainerの起動
VS Codeで本リポジトリを開き、"Reopen in Container" を実行して開発環境を立ち上げます。

### 2. トポロジの展開
```bash
sudo containerlab deploy -t topologies/mini-topo/mini-topo.clab.yml
```

### 3. ツールの開発と検証
`tools/` ディレクトリにOSSをクローンし、開発を行います。ビルドしたバイナリをContainerlab内のノードから実行、あるいは外部からノードに対して実行して動作を確認します。

## 注意点
- 本リポジトリの `.devcontainer` で利用しているイメージは、**arm64 Mac (Apple Silicon)** 向けに構成されています。
