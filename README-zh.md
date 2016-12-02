# README的藝術
<!--
Notes on Chinese formatting:

* GitHub does not support inline styles, leading to appearance of oblique text which is wrong in Chinese. I have replaced some of these <em>'s with bold text.
* Do not try to use line breaks for Chinese, or you get a bunch of extra spaces. If you find the source ugly without linebreak, blame markdown and let it be.
-->
## 詞源
“README”（讀我）這個詞從何而來？

正式命名的日期可以追溯到**至少** 1970 年和 [PDP-10](http://pdp-10.trailing-edge.com/decuslib10-04/01/43,50322/read.me.html)；不過也有可能是來自更早之前放在打孔卡片上的便籤紙，上面潦草地寫著的“READ ME!”。

有位讀者<sup>[[1]](#footnote-1)</sup>則提議說，“README”可能是來自於《愛麗絲漫遊仙境》，其中一瓶藥水和一個月餅上分別貼著“DRINK ME”（喝我）和“EAT ME”（吃我）的標籤。

README 這個詞從出現開始就一直是大寫的。除了大寫單詞更醒目之外，UNIX 系統中大寫字母會排在小寫字母的前面，這樣 README 就會顯示在其它內容的前面
<sup>[[2]](#footnote-2)</sup>。

這樣做的目的顯而易見：“這是進行下一步之前的**重要信息**”。讓我們來看一下現代的“**重要信息**”是怎麼構成的。

## 針對創建者和使用者

這是一篇關於 README 的文章，介紹了做什麼、為什麼要做、怎麼才能做好。

README 是寫給模塊創建者的。模塊創建者的工作是創建一些能持續的東西，這是一種內在的動機，儘管作者可能並沒想分享他的工作。一個沒有文檔的模塊，往往時隔 6 個月後，就連作者自己都會覺得陌生。

README 也是寫給模塊使用者的。每個模塊的作者同時也是該模塊的使用者。Node 有一個非常健康的依賴關聯度：沒人會處在依賴樹的底部。

儘管內容主要是跟 Node 相關，也同樣適用於其它語言的生態系統。


## 很多模塊，有好有壞

Node 的生態系統源於它的模塊，[npm](https://npmjs.org)起著**關鍵**作用。Node 開發人員每週都會評估包含在他們的項目中的幾十個模塊。只要會寫`npm install`，就能在日常工作中使用各種成熟的模塊。

npm 可以非常方便的對模塊進行打包和分發，但是質量卻是良莠不齊：有新的、有舊的，甚至有些連用途都不知道。

什麼是壞的模塊？名字不清晰（猜猜 `fudge` 幹什麼的？）、沒有文檔、沒有測試、沒有註釋，還有函數名字不易於理解。

很多模塊沒有活躍的維護者。如果一個模塊沒人回答問題或者說明模塊的用途，再加上沒有文檔，就會變成一個火星上的東西，不可用並難以理解。

那些有文檔的模塊質量不好的原因又是什麼？有的是因為文檔裡只有一行描述: `"sorts numbers by their hex
value"`。有的是因為文檔裡只是一些代碼片段。這使得模塊使用者只能通過閱讀源代碼來理解模塊是怎麼工作的。編寫優秀的文檔可以使用戶不用閱讀源碼就能理解你模塊的精妙之處。

Node的生態環境非常廣泛：由大量的“只做一件事”的模塊構成。[例外](https://github.com/lodash/lodash)當然也有，但總之都是那些“只做一件事”的大眾統治著 Node 世界。

這就有一個易於發現的問題：找到你想要的**高質量**模塊很困難。

**沒事兒**。低門檻的生態、是否易於發現的問題總比出現封閉的社區文化問題好。

並且，事實證明可發現性問題總是容易解決的。

## 條條大路通向 README.md

Node 社區已經用不同的方法來著手解決可發現性的問題。

一些有經驗的 Node 開發者合力創建了高質量模塊的[列表](https://github.com/sindresorhus/awesome-nodejs)，篩選出了每個類別裡的最好的模塊。

受到社交圖譜的啟發，一個替代 `npm search` 的查找工具 [node-modules.com](http://node-modules.com/) 利用 GitHub 的社交圖譜來查找你的朋友喜歡或創建的模塊。

當然新的開發者還是可以用 npm 自帶的 [search](https://npmjs.org) 功能。

用戶無論是在 [npmjs.org](https://npmjs.org) 或者
[github.com](https://github.com) 或在其它途徑發現了你的模塊，首先映入他們眼簾的是 README。如何在這驚鴻一瞥中給他們留下深刻的印象？

## 專業模塊探討

### README：一站式服務

README 是使用者首先（或唯一）審視你作品的入口。用戶希望模塊能滿足他們的需要，所以你要清楚的說明你的模塊的主要作用和優勢。

你要做的是：

1.  告訴他們這是什麼 (使用場景)
2.  告訴他們在實際使用中是什麼樣子
3.  告訴他們使用的方法
4.  告訴他們其它相關的細節

這是 **你** 的工作。模塊作者要證明他的作品在眾多模塊中是廖落星辰裡的璀璨明珠。既然很多開發者第一眼看到的是你的 README，README 的編寫質量決定了是否能給人留下好的第一印象。

### 簡潔

README 必須要有，但是 README 內容的長度和質量沒什麼關係。理想的 README
應該儘可能的短。詳細的文檔可以在單獨的頁面裡描述。保持 README 簡潔。

### 以史為鑑

古人云：以史為鑑，可以知興替。開發者編寫文檔已經有多年的歷史了。值得我們花時間去看看在 Node 之前人們是怎麼正確寫文檔的。

在某些方面，Node 跟 Perl 非常類似。都是高級腳本語言、採用了很多 UNIX 的理念、推動了互聯網的發展、都有廣泛的模塊生態系統。

事實證明 Perl 社區的[聖僧們](http://perlmonks.org)在編寫[高質量 README](http://search.cpan.org/~kane/Archive-Tar/lib/Archive/Tar.pm)方面很有經驗。CPAN 是值得仔細閱讀的優秀資源， 可以學到一個社區如何能夠始終如一的編寫出高質量的文檔。


### 沒有 README 就沒有抽象

沒有 README 意味著開發者需要閱讀源碼才能理解你的模塊。

Perl 聖僧們所分享的智慧：

> 只要你的文檔是完備的，用戶就可以直接使用你的模塊而無需去閱讀源碼。這是非常重要的。通過文檔可以在很大程度上將你的模塊的外部接口和內部實現進行分離。這樣就可以在保持接口不變的情況下，靈活的修改內部實現。
>
> 記住: 對模塊進行定義的是文檔而不是代碼。
——[Ken Williams](http://mathforum.org/ken/perl_modules.html#document)


### 關鍵要素

有了 README 之後，勇敢的模塊探險家會閱讀它來判斷模塊是否滿足開發者的需要。這是他們的思維模式，一步一步的去了解模塊的細節。

比如說，當我想要一個 2D 碰撞檢測模塊時我找到了[`collide-2d-aabb-aabb`](https://github.com/noffle/collide-2d-aabb-aabb)。
我開始從頭開始檢查這個模塊：

1. **取名**：名字要能做到“其義自見”。`collide-2d-aabb-aabb` 聽起來是個不錯的匹配，儘管它假設我知道"aabb"是什麼意思。如果名字含義非常模糊或與我要找的沒什麼關係，我就會繼續查找其它的模塊了。

2. **一行流**：通過一句話簡明扼要的說明了這個模塊是做什麼的。
   `collide-2d-aabb-aabb` 的描述是：

   > Determines whether a moving axis-aligned bounding box (AABB) collides with
   > other AABBs.

   太棒了——描述了 AABB 的定義是什麼，並且說明了這個模塊是做什麼的。現在開始評測它是否適合我的代碼：

3. **用法**：在開始探究 API 文檔之前，最好看看這個模塊在實際應用中是什麼樣子。我可以快速決定用JS寫的示例程序是否符合我的代碼樣式和我要解決的問題。人們會在很多問題上意見相左，比如 promises/callbacks 和 ES6。如果符合我的要求，我會進一步去研究細節。

4. **API**：模塊的名字，描述和使用方法都符合我的胃口。在這一點上我很樂意使用這個模塊。我需要瀏覽API來確定這就是我需要的，並且很容易整合到我的代碼中。API 部分應該詳述模塊的對象和函數，以及它們的簽名，返回值，回調和事件。當類型不是特別明顯的時候，也無需進行描述。注意事項要描述清楚。

5. **安裝**：當我讀到這兒的時候我就要開始試用這個模塊了。 如果不是通用的安裝說明，就需要在這兒進行描述。即使是一句簡單的`npm install`也好。 對於使用Node的新用戶來說，放一個指向npmjs.org的鏈接和安裝命令，可以讓用戶快速上手使用模塊。

6. **授權**：大多數模塊把這個放在最末尾，但是最好還是往前放一些；非常有可能在把這個模塊整合完後才發現授權協議不合適。我通常使用 MIT/BSD/X11/ISC。如果你的協議不是很寬容，最好是放到最前面。

## 認知漏斗

上面的順序不是隨意選擇的。

模塊使用者需要用到很多模塊，需要查看很多模塊。

當你查看了上百個模塊之後，就可以體會到使用可以預測的模式的好處。

你也開始建立你自己的策略來快速的決定哪些是你需要的，哪些是不需要的。

因此，README應該包含以下信息:

1.  一個可以預測的格式
2.  某些關鍵元素

你不必非要用 **這個** 格式，但要保持統一以符合你的用戶的認知習慣。

這兒介紹的順序被簡稱為“認知漏斗”，
可以想象成是一個直立的漏斗，最寬的部分相關細節最寬泛，越往下移動細節越具體，只有對你的作品足夠感興趣的人才會關注這部分內容。最後，底部可以放一些作品背景的細節 (background，credits，biblio，...)

再一次，Perl聖僧們在這個主題上分享了他們的智慧：

> Perl模塊的文檔對於細節的描述是從少到多的。
> 你的簡介部分應該包含一個小的例子程序
> （或許只有一行代碼，省略掉不常用的用例或大多數用戶用不到的功能）
> 描述部分應該從總體上描述你的模塊，
> 通常只需要幾個段落；在隨後的章節中再詳細描述模塊的例程或方法，長的代碼示例，或其它的資料。
> 理想情況下，在點“下一頁”之前就能讓人大體上了解你的模塊。
> 隨著用戶繼續閱讀文檔，他們能夠漸進的獲得更多的知識。
>  —— `perlmodstyle`

## 珍惜時間

很棒；這些關鍵要素的排序應該讓人儘快“短路”並放棄你的模塊。

這聽起來有點淒涼，不是嗎？但是要這樣想：你的工作，當你用利他主義思想來做的時候，不是為了銷售給別人，而是為了讓人們儘可能客觀公正的評估你的作品，並判斷是否滿足他們的需要。而不是讓你的下載量和用戶數最大化。（老外的思想境界真是高）

並不是每個人都有這樣的心態；這需要有自我約束和實事求是的態度。你唯一要做的是簡潔的描述它的承諾，這樣模塊探險者們就可以或者使用你的作品或者別求他尋。

## 戰鬥的召喚！

前進，勇敢的模塊探險家，通過出色的文檔，讓你的作品能夠被發現和使用！

## 獎勵: 其它好的實踐

在文章的重點之外，有其它的實踐你可以遵循(或不遵循)來提高你的README的質量，最大限度地發揮其作用。

1.  考慮包涵一個 **背景** 部分，如果你的模塊依賴於重要但是不為人所熟知的抽象或生態系統。[`bisecting-between`](https://github.com/noffle/bisecting-between)的函數從它的名字上看不是特別明顯，所以在 **背景** 部分會描述定義，並且給出具體概念和抽象的鏈接，以便需要的人去使用和獲取。如果已經有相似的模塊在npm上存在了，這兒也是一個非常適合描述建立模塊的動機的地方。

2.  積極建立連接！如果你談及其它的模塊，想法，或者其他人的時候，在相關的引用內容上加上鍊接，這樣訪客就可以很容易的得到你的模塊背後的想法。極少有模塊是憑空誕生的：所有的作品來源於其它作品，因此很有必要讓用戶追溯你的模塊的歷史和靈感。

3.  包涵參數和返回值的類型的信息，當這些信息不明確的時候。 儘可能的符合約定(`cb` 代表回調函數，`num` 代表 `Number`)。

4.  在 **用法** 部分包含的示例代碼，要在repo中以文件的形式體現 -- 例如`example.js`。這樣當用戶clone項目後，就可以直接運行README中提及的代碼。

5.  使用徽章要慎重。經常會被[濫用](https://github.com/angular/angular)。它們會容易引起爭論。它們在你的README中加入了視覺噪聲，並且只有當用戶在聯網的瀏覽器裡閱讀你的markdown時才能看到徽章，因為圖片是存放在互聯網上的其它地方。對於每一個徽章，需要考慮：README中的徽章提供給典型讀者的真實含義是什麼？用一個CI徽章來顯示build/test狀態？這個信號更應該發郵件給維護者，或者自動創建一個issue -- 永遠要考慮你的README中的數據的受眾並且自問一下是否有一個流程能夠讓數據更好的送達到目標受眾。

6.  API 文檔格式沒有侷限。使用任何你認為是清晰的格式，但是要包含重要的細節：

    a. 參數是否可選，以及默認值

    b. 包含類型信息，如果類型不能清楚的根據約定進行體現

    c. 對於 `opts` 對象參數，描述它所接受的所有的 keys 和 values

    d. 為每個API提供一個小的調用示例，如果它們的用法不明顯或是在 **用法** 部分沒有體現。
      不過，也有可能是函數太複雜了，需要進行重構，劃分成更細粒度的函數，或者整體刪除。

    e. 為特殊術語建立鏈接! 在markdown中你可以把[腳註](https://daringfireball.net/projects/markdown/syntax#link) 放在文檔的末尾，可以很方便的多次引用它們。[這兒](https://github.com/noffle/common-readme/blob/master/api_formatting.md)有一些我的API文檔格式的個人偏好。

7.  如果你的模塊是無狀態函數的一個小的集合，在**用法** 部分以 [Node REPLsession](https://github.com/noffle/bisecting-between#example) 格式放一些調用和返回值的示例比運行一個示例文件更清晰。

8.  如果你的模塊提供了 CLI (command line interface)而不是 API，用命令調用的方式展示調用示例和輸出。如果你創建了或更改了一個文件，`cat` 它來展示更改前後的變化。

9.  不要忘記使用 `package.json`中的[關鍵字](https://docs.npmjs.com/files/package.json#keywords)來盛情邀請模塊探險者們。

10. API改的越多，越要努力的去更新文檔 -- 言外之意是讓你的API精簡併及早給出具體定義。需求一直在變化，但是我們要做的是建立一個抽象層: 模塊集合本身，而不是在API中做提前的假設。當需求**變更**時，並且'只做一件事'不能滿足要求的時候，只需寫一個新的模塊。'只做一件事'對npm生態系統來說能夠使一個模塊是有效的和有價值的，並且你的改進過程只是簡單的用一個模塊來替換另一個模塊。

11. 最後，請記住你的代碼倉庫和其中的README存在的時間要比你的[代碼倉庫託管主機](https://github.com)和你鏈接到的其它任何東西--特別是圖片--的時間都要長久。所以**內嵌**任何對將來要獲取你的作品的用戶來說是重要的東西。

## 獎勵：*common-readme*

不是巧合， 這也是
[**common-readme**](https://github.com/noffle/common-readme)用的文檔格式，一個README寫作指南和方便的command-line生成器。如果你喜歡這兒的內容，通過`common-readme`你可以節省編寫README的時間。你也可以找到使用這個格式的真實的模塊的例子。

你也可以在[標準Readme](https://github.com/richardlitt/standard-readme)中領略下更具結構化的通用Readme格式。

## 獎勵：實例

理論總是好的，但優秀的README長什麼樣呢？這裡有一些我認為體現了本文原則的實例：

*   [https://github.com/noffle/ice-box](https://github.com/noffle/ice-box)
*   [https://github.com/substack/quote-stream](https://github.com/substack/quote-stream)
*   [https://github.com/feross/bittorrent-dht](https://github.com/feross/bittorrent-dht)
*   [https://github.com/mikolalysenko/box-intersect](https://github.com/mikolalysenko/box-intersect)
*   [https://github.com/freeman-lab/pixel-grid](https://github.com/freeman-lab/pixel-grid)
*   [https://github.com/mafintosh/torrent-stream](https://github.com/mafintosh/torrent-stream)
*   [https://github.com/pull-stream/pull-stream](https://github.com/pull-stream/pull-stream)
*   [https://github.com/substack/tape](https://github.com/substack/tape)
*   [https://github.com/yoshuawuyts/vmd](https://github.com/yoshuawuyts/vmd)
*   [https://github.com/defstream/nl3](https://github.com/defstream/nl3)

如果你遇到了認為不錯的例子，請向我發起[pull request](https://github.com/noffle/art-of-readme/pulls)!

## 獎勵：README清單

一個有用的清單用來衡量你的README:

- [x] 一句話解釋模塊的目的
- [x] 必要的背景資料或鏈接
- [x] 為潛在不熟悉的術語提供到信息來源的鏈接
- [x] 簡潔可運行的實例
- [x] 安裝說明
- [x] 詳細的API文檔
- [x] 對[認知漏斗](#認知漏斗)的執行
- [x] 前面提到的注意事項和限制
- [x] 不要依賴圖片傳遞關鍵信息
- [x] 許可證


## 作者

我是 [noffle](http://blog.eight45.net/about/)。聯繫方式：
[blog](http://blog.eight45.net)，[tweet](https://twitter.com/noffle)，和
[hack](https://github.com/noffle).

這個小項目於5月份誕生在柏林的squatconf，在那兒我鑽研Perl的聖僧們怎麼編寫他們的文檔，同時嘆息在Node生態系統中的我寫的README。它促使我創建了
[common-readme](https://github.com/noffle/common-readme)。儘管"README Tips"部分滿是tips，我仍然決定集中寫一篇關於如何編寫README的文章。於是，Art of README誕生了!


## 腳註

1. <a name="footnote-1"></a>感謝,[Sixes666](https://www.reddit.com/r/node/comments/55eto9/nodejs_the_art_of_readme/d8akpz6)!

2. <a name="footnote-2"></a>參見[The Jargon File](http://catb.org/~esr/jargon/html/R/README-file.html)。然而，現在的多數系統不會將大寫字母排在小寫字母前面，弱化了這個約定的作用，全部大寫只能是在視覺上更顯著。

## 致謝

由衷地感謝 [@mafintosh](https://github.com/mafintosh) 和 [@feross](https://github.com/feross)，是他們的鼓勵讓我的這些想法得以落地，並開始寫作!

感謝下面這些值得尊敬的讀者，指正我的紕漏： :heart: :

- [@ungoldman](https://github.com/ungoldman)
- [@boidolr](https://github.com/boidolr)
- [@imjoehaines](https://github.com/imjoehaines)
- [@radarhere](https://github.com/radarhere)
- [@joshmanders](https://github.com/joshmanders)
- [@ddbeck](https://github.com/ddbeck)
- [@RichardLitt](https://github.com/RichardLitt)
- [@StevenMaude](https://github.com/StevenMaude)
- [@KrishMunot](https://github.com/KrishMunot)
- [@chesterhow](https://github.com/chesterhow)
- [@sjsyrek](https://github.com/sjsyrek)
- [@thenickcox](https://github.com/thenickcox)

感謝 [@qihaiyan](https://github.com/qihaiyan) 將《README的藝術》翻譯成中文! 以下用戶也為本文做出了貢獻：

- [@BrettDong](https://github.com/brettdong) 修改了中文版的標點符號。
- [@Alex-fun](https://github.com/Alex-fun)
- [@HmyBmny](https://github.com/HmyBmny)
- [@vra](https://github.com/vra)

感謝 [@lennonjesus](https://github.com/lennonjesus) 將《README的藝術》翻譯成巴西葡萄牙語！以下用戶也為本文做出了貢獻：

- [@rectius](https://github.com/rectius)

感謝 [@jabiinfante](https://github.com/jabiinfante) 將《README的藝術》翻譯成西班牙語！

最後，對於你們所有的反饋表示由衷感謝! 請在 [issue](https://github.com/noffle/art-of-readme/issues) 中分享你們的評論!

## 歡迎參與!

發現了錯誤? 存在某些無意義的東西? 向我發起一個[pull request](https://github.com/noffle/art-of-readme/pulls)吧!

## 許可證

[Creative Commons Attribution License](Creative Commons Attribution License)
