2021-09-13T22:47:05

# Closure Tools DevTools

- https://github.com/mugi-uno/closure-tools-devtools
- https://blog.cybozu.io/entry/2021/09/13/080000

## メモ

- closure tools版のReact developer tools
- closure toolsは例えばこういうもの
    - https://google.github.io/closure-library/api/goog.ui.Component.html
- chrome 拡張の作り方をまるで知らない.
- devtoolsを拡張している. やり方はよく知らなかった.
    - inspected windowsで検査(content)
        - src/content/content.tsに以下の初期化コード?
            ```Typescript
            const script = document.constructor.prototype.createElement.call(document, "script");
            script.src = chrome.runtime.getURL("setupDevTools.js");
            document.documentElement.appendChild(script);
            script.parentNode.removeChild(script);
            ```
        - scanComponents.tsでコンポーネントツリー取得
    - devtools page がDevToolsパネル(panel)
        - React, Tailwind CSS
    - background 上記の橋渡し役
        - panelMessageListener
        - contentMessageListener
        - chrome.runtime.Portがソケット替わり?
    - TypeScriptでゴリゴリ

