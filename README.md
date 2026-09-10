# JupyterLab Template

JupyterLabの環境のテンプレート

## プロジェクトの構成

- Docker Compose + uv
- Python 3.14 (w/ GIL)
- JupyterLab 4.6
- ライブラリ
  - NumPy 2.5
  - SciPy 1.18
  - pandas 3.0
  - matplotlib 3.11
  - Seaborn 0.13
  - OpenCV 5
  - scikit-learn 1.9

Dockerを使っていますが、ローカルにuvがインストールされている場合は、uv単体でも動きます。macOSなどLinux以外では、uv単体の方がメモリ消費が節約できると思います。

LinuxでDocker（実際にはcontainerd+nerdctl）を、またmacOSでuvを利用して、動作確認済です。

## 使い方

### Dockerの場合

JupyterLab を起動
`$ docker compose up`

シェル環境へ
`$ docker compose exec jupyter bash`

### uv単体の場合

ライブラリのインストール
`$ uv sync --frozen`

JupyterLabを開始
`$ uv run jupyter lab --notebook-dir=notebooks`
