# 某大学某学部某学部の指定水準を満たしたレポートテンプレート

## 想定環境

### Mac

- [MacTeX](https://texwiki.texjp.org/?MacTeX)
- [Visual Studio Code](https://texwiki.texjp.org/?Visual%20Studio%20Code)

#### Visual Studio Code 拡張機能

- [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)

## Visual Studio Codeの設定内容

1. ウィンドウメニューバーの `Code > 基本設定 > 設定` を開く
1. ユーザー設定タブの `拡張機能 > LaTeX Workshop` の項目から､適当に `settings.jsonで編集` のリンク文字をクリック
1. 以下を記述し､設定する
    ```json
    {
        "latex-workshop.latex.tools":[
            {
                "name":"ptex2pdf (uplatex)",
                "command": "ptex2pdf",
                "args": [
                    "-l",
                    "-u",
                    "-ot",
                    "-kanji=utf8 -synctex=1",
                    "%DOC%"
                ]
            },
        ],
        "latex-workshop.latex.recipes":
        [{
            "name": "toolchain",
            "tools": [
                "ptex2pdf (uplatex)",
                "ptex2pdf (uplatex)"
            ]
        }],
        "latex-workshop.view.pdf.viewer": "tab",
    }
    ```
1. コンパイルしたいtexファイルを開いた状態で､ウィンドウメニューバーの `表示 > コマンド パレット` を開く
1. `latex build` と入力して､`LaTeX Workshop: Build LaTeX project` を選択
1. おわり