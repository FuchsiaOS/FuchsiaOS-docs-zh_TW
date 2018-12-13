# Fuchsia OS 中文社區正體中文文檔

原始英文文件 fork 自 https://fuchsia.googlesource.com/docs/

This `README.md` document is a top-level entry point to the Fuchsia
documentation.

此份 `README.md` 文件是關於 Fuchsia OS 文件的最先進入點：

 - [行為守則](CODE_OF_CONDUCT.md)
 - [約定術語](glossary.md) - 本文定義了常見通用的翻譯術語
 - [開發](development/README.md) - 本文詳述關於如何建置(building), 運行(running) 和測試(testing) Fuchsia OS，以及運行在 Fuchsia OS 中的軟體
 - [系統](the-book/README.md) - 介紹＝ Fuchsia OS 如何運作
 - [專案庫結構](map.md)
 - [Contributing changes](CONTRIBUTING.md)

Fuchsia OS 中文社群

- 網站 https://fuchsia-china.com
- 論壇 https://forum.fuchsia-china.com/
- Telegram https://t.me/FuchsiaOSzh
- QQ 群：788645873
- 微信：https://fuchsia-china.com/join

Other files in this repository are **system-wide** documentation articles for
Fuchsia. **Individual subprojects** have their own documentation within each
project repository. The articles above link to Individual documents both within
the system-wide repository and within Individual project repositories.


## 文件校對

### 為什麼要進行校對

文件初稿翻譯難免會有不太理想的地方，所以我們希望能有更多人志願參與校對工作，進一步讓中文文件更加完善。

### 文件的組成

文件由若干 `md` (Markdown) 和 `html` (HTML) 文件組成，翻譯即是將原始 `md` 和 `html` 文件中需要翻譯的文字用 tag 註解包起來，然後在拷貝一份進行翻譯。原始英文用符號 `<!-- -->` 註解掉，每一段英文對英一段中文，方便其他譯者 review，範例如下：

```
<!--
#### Kubernetes is

* **Portable**: public, private, hybrid, multi-cloud
* **Extensible**: modular, pluggable, hookable, composable
-->

#### Kubernetes 具有如下特色:

* **可攜性**: 不論是公有雲、私有雲、混合雲還是多雲架構全都支持
* **可擴展**: 模組化、可插拔、可掛载、可組合的
```

### 翻譯規範

- 翻譯之前，需參考[約定術語](https://github.com/servicemesher/istio-official-translation/issues/77)以規範翻譯一致性。
- 譯文中的英文與中文建議用空格分，可以考慮找個[自動化中英文格式 md 軟體](https://pypi.org/project/zhlint/)
- 專頁名稱不需要翻譯，盡可能用原始英文。
- 翻譯的中英文間隔不宜過長，盡可能一段英文註釋，一段中文翻譯，可以前後對應，方便其他譯者協助 review。
- 保持原始 `md` 或 `html` 格式不變，例如 **\_Server\_** 翻譯成 **\_伺服器\_**
- 對於長文章翻譯需要注意錨點連結不要移除，例如 **\[Server](#Client)** 翻譯成 **\[伺服器](#Client)** 錨點連結保留，但不翻譯。
- `md` 程式碼區塊與程式碼輸出內容也不需要翻譯。
- 如果是多人合譯的文章，需要同步好翻譯進度。
