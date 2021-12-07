# Docker_latex
[Aruneno](https://github.com/aruneko) 様の [aruneko/texlive](https://hub.docker.com/r/aruneko/texlive) を使って，Docker Container として TeX の執筆環境を作りました．

[Futa HIRAKOBA](https://github.com/korosuke613) 様の [爆速で日本語LaTeX執筆環境を用意する](https://korosuke613.hatenablog.com/entry/2019/06/24/171246) を参考にして，VSCode の LaTeX Workshop を使って執筆する環境を作りました．

本当にありがとうございます．

### 動作確認
- Linux (Docker Engine)
- Windows (WSL2 + Docker Desktop)

### ディレクトリ構造
```
|- .devcontainer/
|   |- .latexmkrc: latexmk の設定ファイル
|   |- devcontainer.json: VSCode の Remote Container 機能を使うときの設定
|   |- docker-compose.yml: コンテナの起動に対する処理
|   |- dockerfile: コンテナを作るための処理
|
|- .vscode/
|   |- setting.json: LaTeX Workshop の設定
```

### ここで採用しているコンパイルのルール
- 日本語文書
    - `platex` + `dvipdfmx` (`latexmk` として記述)
    - `pbibtex`
- 英語文書
    - `pdflatex`
    - `bibtex`
- スライド (beamer)
    - `xelatex`
    - `bibtex` or `pbibtex`

### 使い方
VSCode の LaTeX Workshop を使う．使い方は [ブログ](https://tachibana-ai.netlify.app/post/docker_latex/) に書いてます．