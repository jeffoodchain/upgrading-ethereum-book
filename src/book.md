# 前言 <!-- /preface/ -->

## 升級以太坊

歡迎閱讀這本關於升級以太坊的書：邁向權益證明（proof of stake）及更遠未來的以太坊。

早在 2018 年，我與 [Teku](https://docs.teku.consensys.io/introduction) 客戶端團隊一起工作，協助從零打造並實作以太坊全新的權益證明協定。我很快就意識到，光是赤裸裸的規格本身，遺漏了許多形塑它的洞見與微妙之處，於是我著手進行一個專案，為[規格加上註解](https://benjaminion.xyz/eth2-annotated-spec/phase0/beacon-chain/)，附上我自己的評註。

本書的核心工作之一，就是隨著時間推移、隨著一次次升級的演進，持續維護那份[註解規格](/part3/)。這件事的價值與日俱增，因為[官方共識規格](https://github.com/ethereum/consensus-specs)的組織與維護方式，使得人們無處可以在同一個地方看到完整的當前規格。

註解規格完成後，似乎適合再加入一些較具敘事性的章節，試著在不受規格結構束縛的情況下，教導並解釋以太坊的權益證明機制。在這些章節裡，我盡量不預設讀者懂太多。構想是從相當平易的地方開始，再逐步推進到較為複雜的部分。

想了解以太坊內部運作的人，會遇到兩個重大難題。其一，雖然可取得的資訊相當多，卻散落各處，難以蒐羅並拼湊成一幅連貫的圖像。其二，文章與解說往往很快就過時，讓人難以分辨何者仍屬最新、何者已然陳舊。我希望在這兩方面都有所幫助：首先是蒐集並整理這些資訊，其次是仔細地為一切標註版本——因此才有 Altair、Bellatrix、Capella 等等版本。

有鑑於此，我希望本書既能作為共識規格的實用參考，也能作為探索以太坊共識層（consensus layer）的教科書。

### 進行中的作品！

我是倒著寫這本書的。由下而上。從細節開始，再朝著全局圖像推進。

第一個大致完成的部分是[第 3 部：註解規格](/part3/)。這些是機器的五臟六腑。就像電腦的內部，所有元件都裸露在外、線路懸垂著：一切都攤開來展示。但有了這些內臟到位，其餘的一切就能環繞著它們建立起來，把雜亂之處都整齊地收納妥當。

我現在正在撰寫[第 2 部：技術概觀](/part2/)，它在註解規格之外包上第一層、但願更平易近人的內容。同樣地，我也是倒著寫，從協定的[構成要素](/part2/building_blocks/)與[激勵機制](/part2/incentives/)開始，再往前推進到一個說明這一切如何環環相扣的較高層次敘事。目前的重點是[共識](/part2/consensus/)這一章。

**警告：** 在 1.0 版推出之前，任何內容都可能變動。我會盡量不更動註解規格部分的網址與錨點，但無法保證。其餘的一切，包括整個章節與小節，都應視為不穩定。

### 可以期待什麼

這是一本寫給想在技術層面理解以太坊&nbsp;2.0——也就是權益證明版的以太坊——的人的書。它做什麼？它如何運作？它為何是這個樣子？

我是為誰而寫？為了像我這樣的人！為那些樂於理解事物如何運作的人。但更進一步，是為那些想知道事物_為何_是現在這個樣子的人。本書無意成為一部學術著作；比起嚴謹，我更在意洞見。不過在相關之處，我會盡量連結到相關的學術論文與形式化分析。

雖然我自己是以太坊的質押者，也是以太坊的使用者，但本書主要並不是為質押者或使用者而寫。[質押](/appendices/staking/)一章中某些通用性的內容或許有點關聯（如果我哪天真的抽得出空寫的話），但你會在像 [EthStaker](https://ethstaker.cc/) 這樣優秀的社群裡找到更好的協助。

本書的範圍涉及（我所認定的）以太坊&nbsp;2.0 協定。以太坊&nbsp;2.0 近來已成為一個定義較不明確的詞。但對我而言，它大致包括：

  - 一切與權益證明及信標鏈（beacon chain）相關的事物，
  - 以太坊藉以轉向權益證明的「合併」（The Merge）過程，
  - 協定內的資料分片（data sharding），以及
  - 一系列潛在的未來強化。

我不會涵蓋任何歷史上的以太坊&nbsp;1.0 協定，包括以太坊虛擬機（EVM），除非它與「合併」有所牽涉。[《精通以太坊》](https://github.com/ethereumbook/ethereumbook)一書是極佳的資源，儘管如今已相當過時。雖然 Rollup 以及其他所謂的第二層（layer 2）方案，已迅速成為整體以太坊&nbsp;2.0 系統的一部分，但它們依定義並不在協定之內，我在此不會涵蓋。我也不會討論 DeFi、DAO、NFT，或任何能建構在這項驚人技術之上的美好事物。

這是一份份量不小的排除清單，但仍然有[大量內容值得一談](/contents/)。

### 版本

本版涵蓋已部署的以太坊&nbsp;2.0 共識層的 Capella 版本。信標鏈於 2020 年 12 月 1 日以 [Phase&nbsp;0](/part4/history/phase0/) 上線。它在 2021 年 10 月 27 日升級至 [Altair](/part4/history/altair/)，2022 年 9 月 6 日升級至 [Bellatrix](/part4/history/bellatrix/)，並在 2023 年 4 月 12 日升級至 [Capella](/part4/history/capella/)。

具體而言，除非另有說明，凡是提及共識規格之處，指的都是[標記為 v1.3.0](https://github.com/ethereum/consensus-specs/tree/v1.3.0) 的版本（即 [Gamlum](https://github.com/ethereum/consensus-specs/releases/tag/v1.3.0) 發行版）。

《升級以太坊》的歷史版本與當前版本皆可於線上取得：

  - 舊的 [Altair 規格版本](/../altair/)，
  - 舊的 [Bellatrix 規格版本](/../bellatrix/)，
  - 當前的 [Capella 規格版本](/../capella/)，以及
  - [最新版本](/../latest/)，目前即為 Capella。

我為 Phase&nbsp;0 版本所寫的原始註解規格[也仍可取得](https://benjaminion.xyz/eth2-annotated-spec/phase0/beacon-chain/)，不過如今大多只剩歷史價值，並已併入本書。

### 為&ldquo;Eth2&rdquo;辯護

當我開始這個寫作計畫時，權益證明版的以太坊普遍被稱為以太坊&nbsp;2.0，簡稱 Eth2，自 2014 年以來一直如此。這反映出一個事實：以太坊&nbsp;2.0 的願景在許多方面都與原本的以太坊&nbsp;1.0 實作分道揚鑣。2016 年的[《以太坊 2.0 淺紫皮書》](https://docs.google.com/document/d/1maFT3cpHvwn29gLvtY4WcQiI6kRbN_nbCf3JlgR3m_8/edit#)很好地捕捉了這個發展方向。我們最終實作的細節與該文所呈現的有所不同，但即便在當時，各項要素就都已就位。Eth2 要交付的不只是權益證明，還有新的密碼學、新的點對點網路、新的加密經濟學，以及在可擴展性上的新方向等等。這些正是我們所達成的。

2022 年，以太坊基金會[宣告](https://blog.ethereum.org/2022/01/24/the-great-eth2-renaming)，我們必須強調連續性而非斷裂性，把以太坊&nbsp;2.0 重新更名回平凡老舊的「以太坊」。以「合併」當時逐漸成形的樣貌來看，從以太坊使用者的角度而言，這有幾分道理。轉向權益證明後，使用者與開發者的體驗幾乎不會改變。

然而，我主要並不是以以太坊使用者或以太坊開發者的身分在寫作。從一位_協定工程師_的角度來看，「合併」是一個深刻斷裂的時刻。權益證明版的以太坊與工作量證明版的以太坊截然不同——本書的篇幅與複雜度就是充分的證據。憑藉以太坊的新架構，我們交付了當年淺紫皮書所擘劃的相當一大部分內容。

這就是為什麼我經常繼續把權益證明版的以太坊稱為以太坊&nbsp;2.0 或 Eth2[^fn-ef-overreach]，而我對此毫不致歉。我有信心你會明白我的意思，而且這樣做有助於澄清而非造成混淆。

[^fn-ef-overreach]: 這是原因之一；另一個原因是我是個固執的守舊派，不喜歡被一個中心化的權威指揮我該做什麼、說什麼。以太坊基金會聲稱「自 2021 年底起，核心開發者已停止使用該術語」，這說法荒謬到可笑的地步，根本不是事實。

### 為英語辯護

<a id="british-english"></a>
既然談到這裡，還有一件我不會致歉的事，就是使用英式英語的拼字、標點與古雅的慣用語。請把它當成一項特色，而不是一個臭蟲（bug）。

### 致謝

最重要的是，我要感謝我的前雇主 [Consensys](https://consensys.io/)。本書大部分是在我自己的時間裡寫成的，但 Consensys 非常支持我在日常工作之餘投入此事。特別是在 2023 年第二季，公司給了我三個月的寫作假，讓我全職投入本書。他們也允許我為一切內容採用寬鬆的授權條款。這一切都非常夠意思，我深懷感激。Consensys 是一家絕佳的雇主，是生態系中一股了不起的良善力量，也是一個無比美好的工作場所。

我所做的事，有非常大一部分都涉及書寫他人的成果，而本書中幾乎一切內容都是他人的成果。我深深珍視以太坊社群的開放與慷慨。對我而言，這是它最具代表性的特質之一。本書通篇引用了許多人的貢獻，我虧欠你們所有人。能成為 Eth2 開發社群的一員，是我人生中最美好的經歷。

感謝眾多 GitCoin 補助的支持者，你們捐款支持了最初的註解規格，以及我定期發行的《What's New in Eth2》電子報。也感謝慷慨的加密貨幣朋友們，無論匿名與否，多年來給予的善意餽贈。在我與規格的繁瑣細節纏鬥之際，你們的支持給了我莫大的鼓勵。我真心熱愛這個社群。

# Part 1: Building <!-- /part1/ -->

## Introduction <!-- /part1/introduction/* -->

TODO

### Why Ethereum 2.0?

TODO

### The Cathedral and the Bazaar

TODO

### A Brief History of Ethereum's Future

TODO

### Who's who

TODO

### Outline of the Book

TODO

## Goals <!-- /part1/goals/* -->

### Introduction

TODO

### Design Goals

TODO

### Attacks and Defences

TODO

## Making the Sausage <!-- /part1/making/* -->

### Introduction

TODO

### The Specifications

TODO

### The Implementations

TODO

# Part 2: Technical Overview <!-- /part2/ -->

## Introduction <!-- /part2/introduction/* -->

TODO: Intro

## The Beacon Chain <!-- /part2/beacon/* -->

### Introduction

TODO

### Terminology

TODO

### Design Overview

TODO

### Architecture of a Node

TODO

### Genesis

TODO

## 共識 <!-- /part2/consensus/ -->

以下是[一篇論文](https://arxiv.org/abs/2110.10086)的開場白，這篇論文探討對以太坊&nbsp;2.0 共識協定的攻擊：

> 權益證明（PoS）的以太坊共識協定，是透過在分叉選擇規則 LMD GHOST 之上套用最終性裝置（finality gadget）Casper FFG 而構成；LMD GHOST 是「貪婪最重觀測子樹」（Greedy Heaviest-Observed Sub-Tree，GHOST）規則的一種變體，它只考慮每個參與者最近一次的投票（最新訊息驅動，Latest Message Driven，LMD）。

如果這段話對你而言完全說得通，那麼歡迎你直接跳過整章。否則，請繼續讀下去！

我們的目標是徹底理解那句話的每一個部分。要拆解的東西很多，但我們會慢慢來。我們會先從一些[預備知識](/part2/consensus/preliminaries/)開始，涵蓋共識的基礎，這些基礎並非以太坊所特有。

在對整個共識協定如何環環相扣做了高層次的[概觀](/part2/consensus/overview/)之後，我們會深入它的各個組成部分，先是 [LMD GHOST](/part2/consensus/lmd_ghost/)，然後是 [Casper FFG](/part2/consensus/casper_ffg/)。在 [Gasper](/part2/consensus/gasper/) 一節，我們會看到這兩者如何結合在一起。

LMD GHOST 與 Casper FFG 兩種協定的互動方式，衍生出夠多的微妙之處與邊角案例（edge case），因此我特地把本章的最後一節用來討論這些[問題](/part2/consensus/issues/)。

### 預備知識 <!-- /part2/consensus/preliminaries/ -->

<div class="summary">

  - 共識是一種用不可靠的元件來打造可靠的分散式系統的方法。
  - 以區塊鏈為基礎的分散式系統，目標是對單一的交易歷史達成一致。
  - 工作量證明與權益證明本身並不是共識協定，但它們使共識協定得以實現。
  - 許多區塊鏈共識協定是「會分叉的」（forkful）。
  - 會分叉的鏈使用分叉選擇規則，有時也會經歷重組。
  - 在一個「安全」（safe）的協定中，壞事永遠不會發生。
  - 在一個「活躍」（live）的協定中，好事總會發生。
  - 沒有任何實用的協定能夠永遠安全且永遠活躍。

</div>

#### 引言

本節涵蓋共識、分叉選擇與最終性的基礎。其中大部分並非以太坊所特有，目的是建立一般性的背景理解。

共識協定試圖解決的難題，是在不可靠的基礎設施之上打造一個可靠的分散式系統。共識協定的研究可回溯到 1970 年代甚至更早，但我們在以太坊中試圖解決的難題，其規模在企圖心上要高出好幾個數量級。

我們在以太坊共識層的目標，是讓全球數以萬計的獨立節點彼此完全步調一致地推進。每個節點都維護一份帳本，內含每一個帳戶的狀態，而每一份帳本都必須與其他所有帳本相符。不能有任何分歧；節點必須達成一致，而且必須迅速達成。這就是我所謂「可靠的分散式系統」的意思。

這些節點往往跑在[消費級硬體](https://stakefromhome.com/)上。它們透過網際網路連線進行通訊，而這些連線可能頻寬低、延遲高、會掉封包，或在不確定的時間內斷線。節點營運者有時會把軟體設定錯誤，或沒有保持更新。而且，讓這一切更加刺激的是，還可能存在大量惡意行為者，為了自身利益而運行流氓節點或竄改通訊。這就是我所謂「不可靠的基礎設施」的意思。

以太坊有一個明確的設計目標：它不該只在每個節點都運作良好、通訊良好時才表現良好。我們已盡最大努力設計出一個系統，即使在它腳下的世界正在分崩離析時，它仍會盡其所能持續運作。

#### 達成共識

以太坊網路由大量的個別節點所組成。每個節點都獨立運作，節點之間透過一個不可靠、非同步的網路——也就是網際網路——進行通訊。任何一個節點都可能是誠實的（始終行為正確），也可能以任意方式出錯：可能單純當機或不通訊、可能遵循不同版本的協定、可能主動試圖誤導其他節點、可能發布相互矛盾的訊息，或任何其他形式的錯誤。

使用者把交易提交給這個節點網路，而共識協定的目標，是讓所有正確的節點最終對交易歷史達成單一、一致的看法。也就是交易被處理的順序，以及處理的結果。因此，如果我有 1&nbsp;ETH，而我同時告訴網路我要把這 1&nbsp;ETH 寄給 Alice，又要寄給 Bob，我們期望網路最終會達成一致：我要嘛把它寄給了 Alice，要嘛把它寄給了 Bob。如果 Alice 和 Bob 都收到了我的以太幣，或兩人都沒收到，那就是一種失敗[^fn-alice-bob]。

[^fn-alice-bob]: 前者屬於安全性失敗，後者屬於活躍性失敗。

共識協定就是促成這種「對交易排序達成一致」的過程。

以太坊的共識協定實際上是把兩種不同的共識協定「拴在一起」。一種叫做 [LMD GHOST](/part2/consensus/lmd_ghost/)，另一種叫做 [Casper FFG](/part2/consensus/casper_ffg/)。兩者的組合後來被稱為 [Gasper](/part2/consensus/gasper/)。在後續各節中，我們會分別、也會合在一起來看這兩者。

#### 拜占庭將軍

在 1982 年的[一篇論文](https://lamport.azurewebsites.net/pubs/byz.pdf)中，Leslie Lamport 以相當[異想天開的方式](https://www.microsoft.com/en-us/research/publication/byzantine-generals-problem/)描述了共識系統試圖解決的根本問題——打造可靠的分散式系統。

> 我們設想拜占庭軍隊的數個師團紮營在一座敵城之外，每個師團都由自己的將軍指揮。將軍們彼此之間只能透過信使通訊。在偵察敵情之後，他們必須決定一個共同的行動計畫。

這種表述方式清楚地指出：並不存在一個整體的、全觀的視角，沒有那種一眼看盡全局再做決定的「上帝模式」。我們只不過是將軍之中的一員，我們關於其他將軍的唯一資訊來源，就是我們收到的訊息——這些訊息可能正確、可能是謊言、可能是基於有限資訊而產生的誤判、可能延遲，或在傳遞途中遭到竄改。我們只有非常有限的局部視角，卻必須對整個系統的狀態形成一個判斷。

務必時時把這一點記在心裡。當我們畫出區塊鏈與區塊樹的示意圖時，很容易誤以為這某種程度上就是整個系統的「狀態」。但這些圖永遠只代表系統中單一參與者的局部視角。我的節點對系統的看法很可能與你的節點對系統的看法不同，即使只是暫時不同，因為我們是在一個不可靠的網路上運作。舉例來說，你看到區塊的時間會與我看到的時間不同，順序也可能不同，甚至看到的區塊本身就與我看到的不同。

Lamport 以下面這種方式刻劃了系統的故障性質。

> 然而，某些將軍可能是叛徒，試圖阻止忠誠的將軍達成一致。

這些奸詐的將軍展現出我們後來所稱的「拜占庭行為」（Byzantine behaviour）或「拜占庭故障」（Byzantine fault）。他們可以用任意方式行動：延遲訊息、重新排序訊息、徹底說謊、對不同的收件者發送相互矛盾的訊息、完全不回應，或任何我們想得到的其他行為。

<a id="img_consensus_messages"></a>
<figure class="diagram" style="width: 50%">

![一張節點接收訊息的示意圖。](images/diagrams/consensus-messages.svg)

<figcaption>

我從其他節點收到一大堆訊息，但我完全不知道哪些是準確的、它們是以什麼順序送出的，也不知道是否有訊息遺失或只是延遲。無論如何，我們都必須達成一致。

</figcaption>
</figure>

忠誠的將軍需要一種方法，能可靠地依照下列條件產生結果。

> A. 所有忠誠的將軍決定採取相同的行動計畫〔例如「進攻」或「撤退」〕，而且
>
> B. 少數叛徒無法使忠誠的將軍採用一個糟糕的計畫。

在這樣一個拜占庭式的分散式系統中達成共識並不是個容易解決的問題，但多年來已出現幾種相當成功的做法。

第一個主流的解決方案是 Liskov 與 Castro 於 1999 年發表的[實用拜占庭容錯](https://www.scs.stanford.edu/nyu/03sp/sched/bfs.pdf)（Practical Byzantine Fault Tolerance，PBFT）演算法。它依賴一組相對小而有限的已知共識參與者（稱為_副本_，replica）。以[下文](#safety)所討論的意義而言，PBFT 永遠是「安全」的，而且不會分叉。

中本聰共識（Nakamoto consensus）是中本聰於 2008 年為比特幣[所發明](https://bitcoinpaper.org/bitcoin.pdf)的，採取一種根本不同的做法。它不把參與者限縮在一個已知的集合內，而是用工作量證明來無須許可地（permissionlessly）為共識選出一位暫時的領導者。與 PBFT 不同，中本聰共識允許分叉，在形式上並不「安全」。

此後又冒出了這些做法的眾多變體，以及其他新穎的替代方案，例如 [Avalanche 系列](https://arxiv.org/pdf/1906.08936)協定。[Avalanche 白皮書](https://arxiv.org/pdf/1906.08936)第 7 節「相關工作」對目前區塊鏈世界中各式各樣使用中的共識協定，做了不錯的綜覽。

#### 權益證明與工作量證明

這裡正適合提一下：工作量證明與權益證明本身都不是共識協定。它們經常被（偷懶地）稱為共識協定，但每一種都只是共識協定的促成者。

在絕大部分情況下，工作量證明與權益證明都是[女巫攻擊抵抗](/part2/incentives/staking/#introduction)（Sybil resistance）機制，對參與協定一事課加成本。這可防止攻擊者以低成本或零成本壓垮協定。[^fn-types-of-proof]

[^fn-types-of-proof]: 在工作量證明中，你所提出的「證明」是一個能讓區塊雜湊值成為某個特定值的數字。這證明了你做了計算它所需的工作。在權益證明中，你的證明是一把私鑰，這把私鑰關聯到區塊鏈上的一筆質押存款。也還有其他的證明機制，例如[時空證明](https://en.wikipedia.org/wiki/Proof_of_space#Proof_of_space-time)（proof of space and time）。

不過，工作量證明與權益證明通常都透過[分叉選擇規則](#fork-choice-rules)，與它們所支援的共識機制相當緊密地耦合在一起。它們提供了一種有用的方式，為一條區塊鏈賦予權重或分數：在工作量證明中是所完成的總工作量；在權益證明中則是支持某條特定鏈的價值多寡。

除了這些基本因素之外，工作量證明與權益證明都能讓許多種不同的共識協定建構在其上，每一種都有自己的動態特性與取捨。同樣地，[Avalanche 白皮書](https://arxiv.org/pdf/1906.08936)第 7 節「相關工作」的綜覽很有參考價值。

#### 區塊鏈

支撐區塊鏈技術的基本原語（primitive），當然就是區塊。

一個區塊由一組交易構成，這些交易是由一位領導者（區塊提議者）所組裝的。區塊的內容（其酬載，payload）可能依協定而異。

  - 以太坊執行鏈上區塊的酬載是一份使用者交易清單。
  - 合併前的權益證明信標鏈上，區塊的酬載（大多）是其他驗證者所做出的一組證明。
  - 合併後的信標鏈區塊還包含執行酬載（也就是使用者交易）。
  - 一旦 [EIP-4844](https://eips.ethereum.org/EIPS/eip-4844) 在以太坊上實作，區塊除了那份有序的使用者交易清單之外，還會包含對不透明資料 blob 的承諾。

除了特殊的創世區塊之外，每個區塊都建構在某個父區塊之上、並指向該父區塊。於是，我們最終得到一條由區塊串成的鏈：區塊鏈。無論區塊的內容為何，協定的目標都是讓網路上所有節點對同一份區塊鏈歷史達成一致。

<a id="img_consensus_block_chain"></a>
<figure class="diagram" style="width: 90%">

![一條線性區塊鏈的示意圖。](images/diagrams/consensus-block_chain.svg)

<figcaption>

一條區塊鏈。時間由左向右推移，除了創世區塊之外，每個區塊都指向它所建構於其上的父區塊。

</figcaption>
</figure>

當節點把自己的區塊加到鏈的頂端時，鏈就成長。這是透過暫時選出一位「領導者」來完成的——一個有權延伸該鏈的個別節點。在工作量證明中，領導者是第一個為自己的區塊解出工作量證明謎題的礦工。在以太坊的權益證明中，領導者則是從活躍質押者池中以偽隨機方式選出的。

領導者（通常稱為區塊提議者）為鏈加上單一一個區塊，並對該區塊內容的選擇與排序負完全的責任，不過它的區塊必須依照協定規則為有效，否則網路上其餘的節點就會直接忽略它。

使用區塊是一種最佳化。原則上我們可以把交易一筆一筆地加到鏈上，但那會帶來龐大的共識開銷。所以區塊是一批批的交易，而[人們有時會爭論](https://www.bitrawr.com/bitcoin-block-size-debate-explained)這些區塊應該要多大。在比特幣中，區塊大小受區塊內資料的位元組數所限制。在以太坊執行鏈中，區塊大小受區塊 Gas 上限所限制（也就是處理區塊內交易所需的工作量）。[信標區塊](/part3/containers/blocks/#beaconblockbody)的大小則受寫死的常數所限制。把交易捆成區塊，主要的好處來自區塊彼此之間的間隔（Eth2 中是 12 秒，比特幣中平均是 10 分鐘）。這個間隔給了網路收斂的時間——讓盡可能多的節點看到每一個區塊，從而對哪個區塊是鏈頭達成一致。

#### 區塊樹

我們那張漂亮線性鏈的整潔示意圖，大部分時候會反映我們在實務上所看到的情形，但並非總是如此。有時候，也許是由於網路延遲、不誠實的區塊提議者，或客戶端的臭蟲，某個特定節點看到的東西可能更像是下面這樣。

<a id="img_consensus_block_tree"></a>
<figure class="diagram" style="width: 90%">

![一張區塊樹的示意圖。](images/diagrams/consensus-block_tree.svg)

<figcaption>

一般而言，我們最終得到的可能是一棵區塊樹，而不是一條區塊鏈。同樣地，時間由左向右推移，每個區塊都指向它所建構於其上的父區塊。

</figcaption>
</figure>

在真實的網路中，我們最終得到的東西可能更像一棵區塊樹，而不是一條區塊鏈。在這個例子裡，極少有區塊建構在它「顯而易見」的父區塊之上。

為什麼區塊 $C$ 的提議者選擇建構在 $A$ 之上，而不是 $B$？

  - 可能是 $C$ 的提議者在準備好做出提議時，還沒收到區塊 $B$。
  - 可能是 $C$ 的提議者刻意想把區塊 $B$ 排除在自己的鏈之外，例如為了竊取它的交易，或為了審查 $B$ 中的某筆交易。
  - 可能是 $C$ 的提議者基於某種原因認為區塊 $B$ 是無效的。

至少前兩個原因，對更廣大的網路而言是無法區分的。我們所知道的只是 $C$ 建構在 $A$ 之上，而我們永遠無法確知原因。

同樣地，為什麼區塊 $D$ 的提議者選擇建構在 $B$ 之上，而不是 $C$？上述任何一個原因都適用，而我們還可以再加一個：

  - $D$ 的提議者可能基於某種依據判斷，更廣大的網路最終納入 $B$ 的機會大於納入 $C$。因此，把 $D$ 建構在 $B$ 之上，會比把 $D$ 建構在 $C$ 之上更有機會進入最終的區塊鏈。

區塊樹中的各個分支稱為「分叉」（fork）。分叉是網路與處理延遲的自然後果。但它們也可能因為客戶端故障、客戶端的惡意行為，或變更規則的協定升級——使得舊區塊相對於新規則變成無效——而發生。最後這種情況有時稱為「硬分叉」（hard fork）。

共識協定中分叉的存在，是「優先考量活躍性而非安全性」的後果（依[下文](#safety-and-liveness)所討論的意義）：如果你去詢問遵循不同分叉的節點，它們會就系統的狀態給你不同的答案。也存在不會分叉的共識協定，例如古典共識世界中的 [PBFT](https://www.scs.stanford.edu/nyu/03sp/sched/bfs.pdf)，以及區塊鏈世界中的 [Tendermint](https://blog.cosmos.network/the-4-classes-of-faults-on-mainnet-bfabfbd2726c#a2f1)。這些協定永遠產生單一一條線性鏈，因此在形式上是「安全」的。然而，它們在像網際網路這樣的非同步網路上犧牲了活躍性：在艱困的網路條件下，它們不會分叉，而可能就乾脆完全停擺。

#### 分叉選擇規則

如我們所見，基於各式各樣的原因——網路延遲、網路中斷、訊息接收順序錯亂、對等節點的惡意行為——網路上各個節點最終會對網路狀態形成不同的看法。最終，我們希望網路上每個正確的節點都對一份相同的、線性的歷史看法達成一致，從而對系統的狀態形成共同的看法。促成這種一致，正是協定的_分叉選擇規則_所扮演的角色。

給定一棵區塊樹，以及一些基於節點對網路之局部視角的判斷準則，分叉選擇規則的設計目的，是要從所有可用的分支中，選出最有可能最終進入那條最終的、線性的、正典鏈（canonical chain）的分支。也就是說，當節點試圖收斂到一份正典的看法時，它會選出最不可能在之後被從區塊樹中修剪掉的分支。

<a id="img_consensus_block_tree_resolved"></a>
<figure class="diagram" style="width: 90%">

![一張示意圖，將一條區塊鏈呈現為區塊樹的子集。](images/diagrams/consensus-block_tree_resolved.svg)

<figcaption>

分叉選擇規則從候選區塊之中選出一個鏈頭區塊。鏈頭區塊確定了一條唯一的、回溯至創世區塊的線性區塊鏈。

</figcaption>
</figure>

分叉選擇規則藉由選出某個分支頂端的區塊（稱為鏈頭區塊）來隱含地選出一個分支。

對任何正確的節點而言，任何分叉選擇規則的首要準則，都是它所選的區塊必須依協定規則為有效，而且它的所有祖先區塊也都必須有效。任何無效的區塊都會被忽略，而任何建構在無效區塊之上的區塊本身也是無效的。

在此前提下，有許多不同分叉選擇規則的例子。

  - 以太坊與比特幣的工作量證明協定使用「最重鏈規則」[^fn-no-ghost]（有時稱為「最長鏈」，雖然這說法並不嚴謹精確）。鏈頭區塊是那條代表在工作量證明下累積完成最多「工作」的鏈的頂端。
  - 以太坊權益證明 Casper FFG 協定的分叉選擇規則是「跟隨包含高度最高之已證成檢查點的那條鏈」，並且永遠不回退已最終確定的區塊。
  - 以太坊權益證明 LMD GHOST 協定的分叉選擇規則就明示在它的名稱裡：取「最貪婪最重觀測子樹」（Greediest Heaviest Observed SubTree）。它牽涉到計算驗證者對各區塊及其後代區塊累積的投票。

我們稍後會在各自的章節中適切地拆解上述第二項與第三項。

你或許看得出來，這些分叉選擇規則每一種都是一種為區塊賦予數值分數的方式。獲勝的區塊，也就是鏈頭區塊，擁有最高的分數。其構想是：所有正確的節點，當它們最終看到某個區塊時，都會毫不含糊地一致認定它就是鏈頭，並選擇跟隨它的分支，不論它們各自對網路的看法中還發生著什麼其他事。如此一來，所有正確的節點最終都會對「一條回溯至創世的單一正典鏈」達成共同的看法。

[^fn-no-ghost]: 與一般認知相反，以太坊的工作量證明協定[並未在](https://ethereum.stackexchange.com/a/50693)其分叉選擇中使用任何形式的 GHOST。這個誤解非常頑固，可能是由於[以太坊白皮書](https://ethereum.org/en/whitepaper/#modified-ghost-implementation)的緣故。我最後就此事問了 Vitalik，他向我證實，雖然 GHOST 曾在工作量證明之下被規劃過，但因為對某些未明說的攻擊有疑慮，它從未被實作。最重鏈規則比較簡單，也經過充分測試。它一直為我們發揮良好的作用。

#### 重組與回退

當節點收到新的區塊（在權益證明下，還包括對區塊的新投票）時，它會根據這些新資訊重新評估分叉選擇規則。最常見的情況是，新區塊會是節點目前視為鏈頭之區塊的子區塊，於是新區塊就成為鏈頭區塊。

然而，有時新區塊可能是區塊樹中其他某個區塊的後代。（請注意，如果節點還沒有新區塊的父區塊，它就必須向對等節點索取，對於任何它知道自己缺少的區塊也都如此辦理。）

無論如何，在更新後的區塊樹上執行分叉選擇規則，可能會指出一個與先前鏈頭處於不同分支的鏈頭區塊。發生這種情況時，節點就必須進行一次重組（reorg，reorganisation 的縮寫），也稱為回退（reversion）。它會踢掉（回退）先前已納入自己鏈中的區塊，並改採新鏈頭所在分支上的區塊。

在下面的示意圖中，節點評估出區塊 $F$ 為鏈頭區塊，因此它的鏈由區塊 $A$、$B$、$D$、$E$、$F$ 所構成。節點知道有區塊 $C$，但它並未出現在節點對鏈的看法中；它位於一條側分支上。

<a id="img_consensus_reversion_0"></a>
<figure class="diagram" style="width: 70%">

![一張回退之前的區塊鏈示意圖。](images/diagrams/consensus-reversion-0.svg)

<figcaption>

此時，節點認為區塊 $F$ 是最佳鏈頭，因此它的鏈是區塊 $[A \leftarrow B \leftarrow D \leftarrow E \leftarrow F]$。

</figcaption>
</figure>

過了一段時間之後，節點收到區塊 $G$，它並非建構在節點目前的鏈頭區塊 $F$ 之上，而是建構在另一條分支上的區塊 $C$ 之上。依分叉選擇規則的細節而定，節點可能仍評估 $F$ 是比 $G$ 更好的鏈頭，因而忽略 $G$。但在這個例子裡，我們假設分叉選擇規則指出 $G$ 才是較佳的鏈頭區塊。

區塊 $D$、$E$、$F$ 並非 $G$ 的祖先，因此它們需要從節點的正典鏈中移除。那些區塊所包含的任何交易或資訊都會被回退，彷彿它們從未被收到過一樣。節點必須完整倒回到它在處理完區塊 $B$ 之後所處的狀態。

倒回到 $B$ 之後，節點就可以把區塊 $C$ 與 $G$ 加進自己的鏈並據以處理。完成之後，節點就完成了對自身鏈的重組。

<a id="img_consensus_reversion_1"></a>
<figure class="diagram" style="width: 70%">

![一張回退之後的區塊鏈示意圖。](images/diagrams/consensus-reversion-1.svg)

<figcaption>

現在節點認為區塊 $G$ 是最佳鏈頭，因此它的鏈必須改為區塊 $[A \leftarrow B \leftarrow C \leftarrow G]$。

</figcaption>
</figure>

往後也許會出現一個建構在 $F$ 之上的區塊 $H$。如果分叉選擇規則指出 $H$ 應當成為新的鏈頭，那麼節點就會再進行一次重組，把區塊回退到 $B$，再重新播放 $H$ 所在分支上的區塊。

在工作量證明與以太坊的權益證明協定中，由於區塊傳播的網路延遲，一兩個區塊的短重組並不罕見。長得多的重組則應當極為罕見，除非該鏈正遭受攻擊，或者分叉選擇規則的表述方式——或客戶端對它的實作——存在臭蟲。

#### 安全性與活躍性

在討論共識機制時經常出現的兩個重要概念，是_安全性_（safety）與_活躍性_（liveness）。

##### 安全性

非正式地說，若「壞事永遠不會發生」，就說一個演算法是安全的。[^fn-safety-liveness]

[^fn-safety-liveness]: 我所引用的這組有用而直觀的安全性與活躍性定義，以簡短形式出現在 Lamport 1977 年的論文[《證明多行程程式的正確性》](https://lamport.azurewebsites.net/pubs/proving.pdf)中，而此處的措辭則依照 Gilbert 與 Lynch 2012 年的論文[《CAP 定理的觀點》](https://groups.csail.mit.edu/tds/papers/Gilbert/Brewer2.pdf)。

在區塊鏈情境中，可能發生的壞事，例子有：一枚代幣被雙重花費，或兩個相互衝突的檢查點被最終確定。

分散式系統中安全性的一個重要面向是「一致性」（consistency）。也就是說，如果我們在鏈推進過程中的某一點，去詢問不同的（誠實的）節點關於鏈狀態的問題，例如某個帳戶在某個特定區塊高度的餘額，那麼無論我們問哪個節點，都應當總是得到相同的答案。在一個安全的系統中，每個節點都對鏈的歷史抱持一份相同且永不改變的看法——重組永遠不會發生。

實際上，安全性意味著我們的分散式系統「表現得就像一個中心化的實作，一次一個地原子性地執行操作」（引用 [Castro 與 Liskov](https://www.scs.stanford.edu/nyu/03sp/sched/bfs.pdf) 的話）。以 Vitalik 對中心化所做的[分類](https://medium.com/@VitalikButerin/the-meaning-of-decentralization-a0c92b76a274)來說，一個安全的系統是邏輯上中心化的。

##### 活躍性

同樣非正式地說，若「好事終究會發生」，就說一個演算法是活躍的。

在區塊鏈情境中，我們一般把這理解為：鏈總是能加上一個新區塊；它永遠不會陷入某種僵局，以致無法產生一個裝有交易的新區塊。

「可用性」（availability）是看待這件事的另一種方式。我希望鏈是可用的，意思是：如果我把一筆有效的交易送給一個誠實的節點，它終究會被納入某個延伸該鏈的區塊中。

##### 兩者不可兼得！

CAP 定理是分散式系統理論中一個著名的結果，它指出沒有任何分散式系統能同時提供以下三者：(1) 一致性、(2) 可用性、(3) 分區容忍性（partition tolerance）。分區容忍性是指在節點之間的通訊不可靠時仍能運作的能力。例如，網路故障可能把節點分裂成兩個或更多彼此無法通訊的群組。

在我們的區塊鏈情境中，要展示 CAP 定理很容易。想像 Amazon Web Services 離線了，使得所有託管於 AWS 的節點彼此之間能通訊，卻沒有任何一個能與外界對話。或者某個國家對所有進出連線設下防火牆，使得任何流言流量都無法通過。這兩種情境中的任何一種，都會把節點分成兩個不相交的群組 $A$ 與 $B$。

<a id="img_consensus_partition"></a>
<figure class="diagram" style="width: 50%">

![一張網路分區的示意圖。](images/diagrams/consensus-partition.svg)

<figcaption>

網路被分區了：$A$ 中的節點彼此之間能對話，但無法與 $B$ 中的任何節點對話，反之亦然。

</figcaption>
</figure>

假設有個連到群組 $A$ 之網路的人送出一筆交易。如果 $A$ 中的節點處理了那筆交易，那麼它們最終所處的狀態，就會與沒看到那筆交易的群組 $B$ 中的節點不同。於是，整體而言，我們失去了所有節點之間的一致性，因而失去了安全性。要避免這一點的唯一辦法，是讓群組 $A$ 中的節點拒絕處理那筆交易，但這樣一來我們就失去了可用性，因而失去了活躍性。

總而言之，CAP 定理意味著我們不能指望設計出一個在所有情況下都既安全又活躍的共識協定，因為我們別無選擇，只能在一個不可靠的網路——網際網路——上運作。[^fn-flp-theorem]

[^fn-flp-theorem]: CAP 定理與另一個著名結果有關，該結果由 Fisher、Lynch 與 Paterson 在他們 1985 年的論文[《一個故障行程即不可能達成分散式共識》](https://groups.csail.mit.edu/tds/papers/Lynch/jacm85.pdf)中提出，通常稱為 FLP 定理。它證明了：即使在一個可靠的非同步網路中（也就是訊息被接收所需的時間沒有上限），單單一個故障的節點就能阻止系統達成共識。也就是說，即使是這種未分區的系統，在形式上也無法同時做到活躍與安全。Gilbert 與 Lynch 的[論文](https://groups.csail.mit.edu/tds/papers/Gilbert/Brewer2.pdf)在第 3.2 節討論了 FLP 定理。

##### 以太坊優先考量活躍性

以太坊的共識協定在良好的網路條件下同時提供安全性與活躍性，但在情況不那麼順利時則優先考量活躍性。在網路分區的情況下，分區兩側的節點都會繼續產生區塊。然而，最終性（一種安全性性質）將不再於分區兩側同時發生。依各側所掌管之質押的比例而定，要嘛其中一側、要嘛兩側都不會繼續最終確定。

最終，除非分區獲得解決，否則由於那套新穎的[怠惰洩漏](/part2/incentives/inactivity/)機制，兩側都會重新取得最終性。但這會導致終極的安全性失敗。每條鏈都會最終確定一份不同的歷史，而這兩條鏈將永遠變得無法調和、各自獨立。

#### 最終性

我們在接下來幾節中會相當深入地討論最終性，它是鏈的一種安全性性質。

最終性是這樣一種概念：存在一些區塊將永遠不會被回退。當一個區塊已被最終確定，網路上所有誠實的節點都已一致同意該區塊將永遠是鏈歷史的一部分，因此它的所有祖先也都將留在鏈的歷史中。最終性讓你買披薩的付款，變得就像你已交出現金一樣不可撤回。它是對抗雙重花費的終極保護。[^fn-finality-not-absolute]

[^fn-finality-not-absolute]: 值得一提的是，最終性從來都不是絕對的。無論任何協定怎麼宣稱，只要超級多數的節點同意（例如透過軟體升級）回退一批已最終確定的區塊，那這件事就會發生。歸根結柢，一如世間萬事，最終性的概念從屬於社會共識。進一步的討論請見[《論結算最終性》](https://blog.ethereum.org/2016/05/09/on-settlement-finality)。

某些共識協定，例如古典的 PBFT 或 Tendermint，每一輪（每一個區塊）都最終確定。一輪份量的交易一旦被納入鏈中，所有節點就一致同意它將永遠在那裡。一方面，這些協定非常「安全」：交易一旦被納入鏈上，就永遠不會被回退。另一方面，它們易受活躍性失敗之害：如果節點無法達成一致——例如其中超過三分之一當機或不可用——那麼就無法有任何交易被加進鏈中，鏈會徹底停擺。

其他共識協定，例如比特幣的中本聰共識，則完全沒有任何最終性機制。永遠存在某人會揭示出一條替代的、更重的鏈的可能性。發生這種情況時，所有誠實的節點都必須據此重組自己的鏈，回退它們先前處理過的任何交易。諸如「你的區塊有多少個確認數」這類經驗法則，只是對最終性的近似，並不是保證。[^fn-cdc-40k]

[^fn-cdc-40k]: 撰寫本文時，至少有一家交易所對來自以太坊經典（Ethereum Classic）網路的存款要求 [40000 個確認](https://www.reddit.com/r/Crypto_com/comments/w9qmbx/40000_confirmations_and_7_days_to_send_etc_to_cdc/)。這意味著，在該交易所處理之前，必須有四萬個區塊建構在那個包含存款交易的區塊之上，這大約要花六天。這項要求反映出對 ETC 低雜湊率工作量證明鏈易受 51% 攻擊之害的疑慮——攻擊者要任意回退區塊相對容易。現實是，面對一場精心策劃的 51% 攻擊，任何數量的確認都不是真正安全的。

以太坊的共識層優先考量活躍性，但也力求在情況有利時以最終性的形式提供一種安全性保證。這是一種兩全其美的嘗試。Vitalik 曾如下[為此辯護](https://ethresear.ch/t/explaining-the-liveness-guarantee/4228/8?u=benjaminion)。[^fn-liveness-during-nonfinality]

> 一般性的原則是，你想給使用者「盡可能多的共識」：如果有 $>2/3$，那我們就得到常規共識；但如果只有 $<2/3$，那麼當鏈顯然仍有可能繼續成長（儘管新區塊暫時處於較低的安全等級）時，就沒有理由乾脆停擺、什麼都不提供。如果某個個別的應用程式不滿意那個較低的安全等級，它大可以忽略那些區塊，直到它們被最終確定為止。

[^fn-liveness-during-nonfinality]: 這件事的價值在 2023 年 5 月 12 日顯而易見，當時信標鏈[停止最終確定](https://offchain.medium.com/post-mortem-report-ethereum-mainnet-finality-05-11-2023-95e271dfd8b2)約一小時。在那段期間，共識的參與率從超過 99% 的驗證者掉到約 40%。然而，一般的以太坊使用者與應用程式幾乎不會察覺。區塊仍持續產生（雖然比平常少），交易也持續被執行。

以太坊共識層的最終性，是由我們很快就會探討的 Casper FFG 機制所交付的。其構想是：所有誠實的驗證者會週期性地對相當近期、且他們將永不回退的檢查點區塊達成一致。那個區塊以及它的所有祖先區塊於是就「最終」了——它們將永不改變，而且如果你去詢問網路中任何誠實的節點關於它們或它們祖先的問題，你總是會得到相同的答案。

<a id="img_consensus_finality"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示鏈的一段已最終確定部分與一段會分叉的部分。](images/diagrams/consensus-finality.svg)

<figcaption>

誠實的節點已一致同意，該檢查點及其所有祖先區塊都是「最終的」，永遠不會被回退。因此在該檢查點之前不會有分叉。從該檢查點往下延伸的鏈仍可能發生分叉。

</figcaption>
</figure>

以太坊的最終性是「經濟性最終性」。協定在理論上有可能最終確定兩個相互衝突的檢查點，也就是對鏈歷史的兩種互相矛盾的看法。然而，這只可能在巨大且可量化的代價下發生。除了最極端的攻擊或故障情境之外，最終就是最終。

[Casper FFG 一節](/part2/consensus/casper_ffg/)會深入探討這個最終性機制如何運作的細節。

#### 另見

凡是 Leslie Lamport 經手過的東西都永遠值得一讀，而 Lamport、Shostak 與 Pease 1982 年探討[《拜占庭將軍問題》](https://lamport.azurewebsites.net/pubs/byz.pdf)的原始論文蘊含許多洞見。雖然他們所提出的演算法以現代標準來看效率低落得無可救藥，但這篇論文是針對共識協定進行推理的不錯入門。Castro 與 Liskov 1999 年那篇開創性的論文[《實用拜占庭容錯》](https://www.scs.stanford.edu/nyu/03sp/sched/bfs.pdf)也是如此，它對以太坊 Casper FFG 協定的設計有重大影響。不過，你或許會想把這些「古典」做法，與中本聰在 2008 年[比特幣白皮書](https://bitcoinpaper.org/bitcoin.pdf)中所描述的工作量證明那種優雅的簡潔性，拿來對比一番。如果說工作量證明有哪一點值得稱道，那就是它的簡潔。

我們在上文提到了 Gilbert 與 Lynch 2012 年的論文[《CAP 定理的觀點》](https://groups.csail.mit.edu/tds/papers/Gilbert/Brewer2.pdf)。它對一致性與可用性（在我們的情境中即安全性與活躍性）這些概念的探索非常易讀。

以太坊信標鏈在 2022 年 5 月經歷了一次七個區塊的重組，原因是各客戶端對分叉選擇規則的實作存在差異。這些差異在當時是已知的，並被認為無害。事實證明並非如此。Barnabé Monnot 對該事件的[記述](https://barnabe.substack.com/p/pos-ethereum-reorg)很有啟發性。

Vitalik 的部落格文章[《論結算最終性》](https://blog.ethereum.org/2016/05/09/on-settlement-finality/)對最終性這個概念提供了更深入、更細緻的探索。

對於我們正在打造的系統，我們的理想是：它們在_政治上_是去中心化的（為了無須許可與抗審查）、在_架構上_是去中心化的（為了韌性，沒有單一故障點），但在_邏輯上_是中心化的（如此一來它們才會給出一致的結果）。這些準則強烈影響著我們設計共識協定的方式。Vitalik 在他的文章[《去中心化的意義》](https://medium.com/@VitalikButerin/the-meaning-of-decentralization-a0c92b76a274)中探討了這些議題。

### Overview <!-- /part2/consensus/overview/ -->

<div class="summary">

  - Nodes and validators are the actors of the consensus system.
  - Slots and epochs regulate consensus time.
  - Blocks and attestations are the currency of consensus.
  - Ethereum's consensus protocol combines two separate consensus protocols.
  - "LMD GHOST" essentially provides liveness.
  - "Casper FFG" provides finality.
  - Together they are sometimes known as "Gasper".

</div>

#### Introduction

The last section gave a broad view of blockchain consensus; in this section we will tighten the focus to Ethereum's proof of stake consensus. I've tried to follow a path that gives enough information to make sense of things, without wandering off into the detailed technical weeds on either side. All those weeds are well explored in the [annotated specification](/part3/) and other chapters, and I've included some links for those who want to branch off and go exploring.

我們必須先涵蓋的第一件事，是我們通篇都會用到的、以太坊所特有的術語。

##### 節點與驗證者

以太坊網路的主要參與者是_節點_（node）。節點的角色是驗證共識，並與其他節點構成通訊骨幹。

共識是由_驗證者_（validator）所形成的，而驗證者（以十足的以太坊風格）被取了一個糟透了的名字，因為它們其實並不驗證任何東西——驗證是由節點完成的。每個驗證者代表一筆初始 32 ETH 的質押。它有自己的[祕密金鑰](/part2/building_blocks/signatures/#key-pairs)，以及相關的公鑰，該公鑰就是它在協定中的身分。驗證者附屬於節點，而單一一個節點可以託管從零到數百或數千個不等的驗證者。附屬於同一個節點的驗證者並不獨立行動，它們共享同一份對世界的看法。[^fn-validators-nodes]

[^fn-validators-nodes]: 在針對以太坊的去中心化程度做出論斷時，把這一點放在心上對我們會很有幫助。比方說，網路上有 60 萬個活躍的驗證者，距離有 60 萬個獨立的行為者還差得遠。觀察節點的數量，以及驗證者在各節點間的分布，會給出對以太坊去中心化更有用的衡量指標。

權益證明有一個有趣的特性，使它有別於工作量證明：在 PoS 之下，我們知道我們的驗證者集合。我們有一份完整的清單，列出我們預期在任何時刻都會活躍的所有公鑰。知道我們的驗證者集合，使我們得以達成最終性，因為我們能夠辨識出我們何時取得了參與者的多數投票。[^fn-accountable-safety-jargon]

[^fn-accountable-safety-jargon]: 用共識領域的行話來說，我們能擁有「可問責的安全性」（accountable safety）。

##### 時段與紀元

時間在以太坊的權益證明共識中受到嚴格的規範，這相對於工作量證明是一項重大的改變；工作量證明與時間只有隨意的關係——PoW 多少會嘗試讓區塊間隔平均維持恆定，但僅止於此。

兩個最重要的間隔是_時段_（slot），它恰好是 [12 秒](/part3/config/configuration/#seconds_per_slot)，以及_紀元_（epoch），它是 [32 個時段](/part3/config/preset/#slots_per_epoch)，或 6.4 分鐘。無論網路上還發生著什麼其他事，時段與紀元都規律而不停歇地推進。

##### 區塊與證明

每個時段，恰好有一個驗證者被[選出](/part3/helper/accessors/#get_beacon_proposer_index)來提議一個_區塊_。該區塊[包含](/part3/containers/blocks/#beaconblockbody)對信標狀態的更新，包括提議者所知道的證明，以及包含以太坊使用者交易的[執行酬載](/part3/containers/execution/#executionpayload)。提議者透過一個流言協定把它的區塊分享給整個網路。

一個時段可以是空的：區塊提議者可能離線、可能提議一個無效的區塊，或它的區塊隨後被重組出鏈外。在一條運作良好的信標鏈上，這些事情不應經常發生，但協定的用意是要在空時段出現時仍具韌性。

每個紀元，每個驗證者都恰好有一次機會以一份_證明_（attestation）的形式分享它對世界的看法。一份證明[包含](/part3/containers/dependencies/#attestationdata)對鏈_鏈頭_的投票（將被 LMD GHOST 協定使用），以及對_檢查點_的投票（將被 Casper FFG 協定使用）。證明也會被流言傳播給整個網路。如同區塊一樣，證明也可能因為各式各樣的原因而缺失，協定能在不同程度上容忍這一點——粗略地說，隨著證明者的參與率下降，共識的品質也會下降。[^fn-attestation-rate]

[^fn-attestation-rate]: [Beaconcha.in](https://beaconcha.in) 網站以每個紀元為單位顯示證明參與率（也稱為投票參與率，Voting Participation）。它是衡量網路健康狀況的好指標。這個比率經常超過 99%，對一個大規模分散式共識協定而言，這是出色的效能水準。

紀元的作用是把處理所有那些證明的工作負載分散開來。藉由做出證明，每個驗證者都在把自己對世界的看法告知其他每一個驗證者，如果這一切都一次做完，可能會構成極為龐大的網路流量與處理負載。把證明的工作負載分散到一個紀元的全部 32 個時段，能讓資源使用維持在低水準。在每個時段，只由佔驗證者 $\frac{1}{32}$ 的委員會做出證明。

協定透過一套針對驗證者的獎勵與懲罰系統，來激勵區塊與證明的產生及其準確性。我們現在不需要深入這些；有一[整章另闢篇幅](/part2/incentives/)講述這一切。

##### 罰沒

在工作量證明中，產生一個區塊代價高昂。這對礦工是一種強烈的誘因，使他們依協定的目標好好行事，以確保自己的區塊被納入。

在權益證明中，建立區塊與證明幾乎是免費的[^fn-nothing-at-stake]。我們需要某種辦法來防止攻擊者利用這一點來擾亂網路。這就是_罰沒_（slashing）的角色。對區塊或證明含糊其辭（equivocate）的驗證者，會面臨被[罰沒](/part2/incentives/slashing/)的處置，意思是它們會被逐出驗證者集合，並被罰掉其質押的一部分。簡單地說，含糊其辭意味著說出兩件相互矛盾的事。它可能是為同一個時段提議兩個不同的區塊，或做出兩份彼此不一致的證明——這些都是任何誠實遵循協定的驗證者不會做出的。

[^fn-nothing-at-stake]: 這有時稱為「無利害關係問題」（nothing at stake problem）。

#### 機器中的幽靈

有了一些術語墊底，我們就可以開始勾勒以太坊實際的共識機制。

以太坊的權益證明共識協定，實際上是兩種獨立共識協定的組合，這兩者各自被稱為 LMD GHOST[^fn-lmd-name] 與 Casper FFG[^fn-ffg-name]。這兩者被「拴在一起」，構成了我們為 Eth2 所實作的共識協定——這個合併後的協定有時以混成詞「Gasper」為人所知。

[^fn-lmd-name]: 「最新訊息驅動、貪婪最重觀測子樹」（Latest Message Driven, Greedy Heaviest Observed Subtree）。我會在專門的 [LMD GHOST 章節](/part2/consensus/lmd_ghost/#naming)中拆解這個命名。

[^fn-ffg-name]: 「友善最終性裝置 Casper」（Casper the Friendly Finality Gadget）。同樣地，等我們講到專門的 [Casper FFG 章節](/part2/consensus/casper_ffg/#naming)時，我會拆解這個略顯古怪的命名。

把這兩者組合在 Gasper 中，是一種在活躍性與安全性兩方面都想兩全其美的嘗試。本質上，LMD GHOST 提供逐時段的活躍性（讓鏈持續運作），而 Casper FFG 提供安全性（保護鏈不受長回退之害）。LMD GHOST 讓我們能持續一個接一個地產出區塊，但它會分叉，因此在形式上並不安全。Casper FFG 修改了 LMD GHOST 的分叉選擇規則，週期性地為鏈賜予最終性。儘管如此，如[先前所討論](/part2/consensus/preliminaries/#ethereum-prioritises-liveness)，以太坊優先考量活躍性。因此，在 Casper FFG 無法賦予最終性的情況下，鏈仍會透過 LMD GHOST 機制繼續成長。

這個拴在一起的共識機制並不總是優美。我們有時看得見接縫，而兩者之間的互動導致了一些微妙的問題，我們會在[後文](/part2/consensus/issues/)討論。然而，以以太坊的精神而言，它是一個可行的工程解決方案，在實務上一直為我們發揮良好的作用。

##### 歷史

Gasper 的詳細歷史與它各個組成部分——LMD GHOST 與 Casper FFG——的發展密不可分，我們會在各自的章節中回顧。但我們在此指出：Casper FFG 從一開始就不是被設計成獨立的共識機制。

如 [Casper FFG 論文](https://arxiv.org/abs/1710.09437)所述：

> 友善最終性裝置 Casper 是疊加在一個_提議機制_——一個提議區塊的機制——之上的一層。

所以，有一個底層的區塊提議機制——這意味著有一個底層的共識機制——而 Casper FFG 坐落在它之上，交付一種為區塊鏈賦予最終性的後設共識（meta-consensus）。

最初的計畫，是把 Casper FFG 當成一層權益證明的疊加層，套用在以太坊的工作量證明共識之上。Casper FFG 會週期性地——比方說每 100 個區塊——為鏈賦予最終性，這是工作量證明鏈所缺乏的性質。這原本打算作為讓以太坊戒除工作量證明的第一步。有了最終性的保證，我們本可降低工作量證明的區塊獎勵，從而降低整體的雜湊算力，作為將來某天以完全的權益證明取代挖礦的過渡步驟。

到 2017 年底，這個計畫已變得相當成熟。[EIP-1011](https://eips.ethereum.org/EIPS/eip-1011)「混合式 Casper FFG」詳細描述了這個架構，甚至還有一個[測試網](https://hackmd.io/@aTTDQ4GiRVyyce6trnsfpg/Hk6UiFU7z?type=view)在 2017 年 12 月 31 日[上線](https://web.archive.org/web/20230630135033/https://nitter.it/karl_dot_tech/status/947503029166546946)。

然而，在 2018 年初，那個計畫被取代了。以太坊虛擬機有限的頻寬，限制了 EIP-1011 所能支援的驗證者集合大小，進而導致 1500&nbsp;ETH 的最低質押額，這被認為不甚理想。大約在同一時間，通往一個完整、可擴展性高得多的權益證明協定的路徑變得更為清晰，於是我們開始著手後來成為以太坊&nbsp;2.0 的設計。

由於 Casper FFG 的通用本質，它得以在這次重新設計中存活下來，並被納入以太坊&nbsp;2.0，但不是作為工作量證明上的疊加層，而是作為一個名為 LMD GHOST 的新權益證明協定上的疊加層。

##### 一個最終性裝置

當我們說 Casper FFG 疊加在一個既有的區塊提議機制之上時，我們的意思是它取一棵既有的區塊樹，並以一種特定的方式修剪它。Casper FFG 藉由讓底層區塊樹的某些分支變得無法觸及，來修改它的分叉選擇。

考慮這棵由某個底層共識機制——無論是工作量證明，還是權益證明中的 LMD GHOST——所產生的區塊樹。

<a id="img_gasper_blocktree"></a>
<figure class="diagram" style="width: 70%">

![一張帶有三個分叉的區塊樹示意圖。](images/diagrams/gasper-blocktree.svg)

<figcaption>

一棵任意的、帶有三個分叉（分支）的區塊樹。區塊 $I$、$E$、$M$ 中的任何一個都可能是鏈的頂端。（這些區塊標籤只是為了方便，並不暗示某種特定的排序。）

</figcaption>
</figure>

在這個情況中，我們有三個候選的鏈頭區塊：$I$、$E$、$M$。在工作量證明的最長鏈規則之下，鏈頭區塊的選擇顯而易見：我們必須選 M，因為它的區塊高度最大，或者（幾乎等價地）所完成的工作量最多。在 LMD GHOST 之下，我們無法單憑這項資訊選出鏈頭區塊，我們需要看到其他驗證者的投票才能做出選擇。

難題在於，從區塊 $J$ 到 $M$ 的這條鏈可能來自一個攻擊者。攻擊者可能祕密地挖出了那條鏈，然後在一場所謂的 51% 攻擊中於事後揭示出來。工作量證明的節點別無選擇，只能重組，讓 $M$ 成為鏈頭，從而偏袒攻擊者的鏈，並可能變得易受雙重花費之害。

Casper FFG 的最終性在這裡能幫上我們的忙。假設區塊 $D$ 被 Casper FFG 標記為最終的（這會自動最終確定區塊 $A$、$B$、$C$）。最終確定會修改底層協定的分叉選擇規則，使得任何與區塊 $D$ 競爭的分支——也就是包含並非由 $D$ 衍生而來之區塊的分支——都被排除。等價地說，分支會被修剪，使得在那個已最終確定的區塊之前不存在任何分叉。

<a id="img_gasper_blocktree_finalised"></a>
<figure class="diagram" style="width: 70%">

![一張示意圖，顯示其中一條分支上的區塊被最終確定之後的同一棵區塊樹。](images/diagrams/gasper-blocktree_finalised.svg)

<figcaption>

我們有著與上方相同的區塊樹，但現在區塊 $D$ 已被最終確定。Casper FFG 的分叉選擇規定，任何不包含區塊 $D$ 的鏈都會被忽略，所以我們的鏈頭區塊現在毫不含糊地就是 $E$。

</figcaption>
</figure>

當區塊 $D$ 被最終確定時，分叉選擇必須忽略以區塊 $F$ 與 $J$ 起頭的那些分支。我們最終得到單一一個候選鏈頭區塊 $E$。

本質上，Casper FFG 所交付的最終性可防止長重組（回退）。任何已最終確定的區塊，或已最終確定區塊的祖先，都永遠不會被回退。在以太坊的 Casper FFG 實作中，我們必須為「永遠」加上但書：「除非燒掉全部質押以太幣總額至少 1/3」。這就是權益證明鏈所提供的經濟性最終性。

#### 結語

回想一下，[這](/part2/consensus/)就是我們試圖徹底理解其每一部分的那句話。

> 權益證明（PoS）的以太坊共識協定，是透過在分叉選擇規則 LMD GHOST 之上套用最終性裝置 Casper FFG 而構成；LMD GHOST 是「貪婪最重觀測子樹」（Greedy Heaviest-Observed Sub-Tree，GHOST）規則的一種變體，它只考慮每個參與者最近一次的投票（最新訊息驅動，Latest Message Driven，LMD）。

我們花了一些時間談共識協定是什麼、做什麼，也稍微觸及了權益證明。我們談了最終性，而我在高層次上說明了 Casper FFG 如何構成一個套用在作為區塊提議機制的 LMD GHOST 之上的「最終性裝置」。

然而，還有許多工作尚待完成。在接下來幾節中，我們會更深入地探討 [LMD GHOST](/part2/consensus/lmd_ghost/)、[Casper FFG](/part2/consensus/casper_ffg/)，以及它們如何結合而構成 [Gasper](/part2/consensus/gasper/) 協定。

#### 另見

關於這一切如何匯聚在一起的歷史，Vitalik 發過一串精彩的[推文連發](https://web.archive.org/web/20230630135150/https://nitter.it/VitalikButerin/status/1029900695925706753)。整理過的版本可在[這裡](https://web.archive.org/web/20180816143143/https://www.trustnodes.com/2018/08/16/vitalik-buterin-tells-story-race-vlad-zamfir-implement-proof-stake-casper)與[這裡](https://hackmd.io/@liangcc/BJZDR1mIX?type=view)取得。他稍微討論了弱主觀性，我們會在[後文](/part2/validator/weak_subjectivity/)處理這個主題。

[《權益證明常見問答》](https://web.archive.org/web/20231109183738/https://vitalik.ca/general/2017/12/31/pos_faq.html)至今仍是我們將要涵蓋之諸多主題的絕佳入門讀物。

Joachim Neu 的演講[《PoS 以太坊共識問題的為何與如何》](https://www.youtube.com/watch?v=2nMS-TK_tMw)（發表於 Devconnect 2022 的 ETHconomics 場次），對「可用性—最終性」之間的取捨，以及以太坊如何試圖駕馭它，提供了非常平易近人的洞見。等我們講到 [Gasper 協定](/part2/consensus/gasper/)時，會再續談「巢狀帳本」（nested ledger）的概念。

### LMD GHOST <!-- /part2/consensus/lmd_ghost/ -->

<div class="summary">

  - LMD GHOST 是節點用來判定最佳鏈的一種分叉選擇規則。
  - 它依據所有活躍驗證者的投票，為各分支賦予權重。
  - LMD GHOST 並不提供最終性，但確實支援一條確認規則（confirmation rule）。
  - 罰沒被用來解決「無利害關係」問題。

</div>

#### 引言

在本節中，我們會孤立地考慮 LMD GHOST，完全忽略 Casper FFG 那層最終性疊加層[^fn-casper-and-gasper-next]。LMD GHOST 本身就是一個共識機制的精髓——它是一個分叉選擇規則，正如中本聰共識中的最重鏈規則也是一樣——並有它自己的一組性質與取捨。

[^fn-casper-and-gasper-next]: 下一節涵蓋 [Casper FFG](/part2/consensus/casper_ffg/)，再下一節則涵蓋兩者結合而成的 [Gasper](/part2/consensus/gasper/)。

目前我們只會考慮這個故事中「它如何運作」的部分——順利的流程。我們稍後會在[問題與修正](/part2/consensus/issues/)一節看「它可能如何出錯」的部分。

#### 命名

LMD GHOST 這個名稱由兩個首字母縮寫組成，分別代表「最新訊息驅動」（Latest Message Driven）與「貪婪最重觀測子樹」（Greedy Heaviest-Observed Sub-Tree）。我們先拆解 GHOST，再拆解 LMD。

##### GHOST

GHOST 協定源自 2013 年 [Sompolinsky 與 Zohar 的一篇論文](https://eprint.iacr.org/2013/881)，內容是如何安全地提升比特幣的交易吞吐量。增大區塊大小，或縮短區塊之間的間隔，會使鏈在一個延遲（時延）不受控制的網路——例如網際網路——中更容易分叉。會分叉的鏈會有更多重組，而重組對交易安全不利。把比特幣的最長鏈分叉選擇規則換成 GHOST 分叉選擇，已被證明在有時延存在時更為穩定，從而允許更頻繁地產生區塊。

GHOST 這個名稱代表「貪婪最重觀測子樹」（Greedy Heaviest-Observed Sub-Tree），它描述了演算法如何運作。我們會在[下文](#finding-the-head-block)展開說明。簡言之，GHOST 的分叉選擇並不跟隨最重的鏈，而是跟隨最重的子樹。它認識到，對一個區塊投的票不只是投給那個區塊，同時也隱含地是投給它每一個祖先的票，所以整棵整棵的子樹都有一個關聯的權重。

比特幣從未採用 GHOST，而（儘管那篇論文如此聲稱）工作量證明下的以太坊也未採用，雖然它[最初](https://ethereum.org/en/whitepaper/#modified-ghost-implementation)曾被規劃過，而舊的工作量證明「叔塊」（uncle）獎勵與它有關。

##### LMD

我們在以太坊權益證明中所使用的 GHOST 協定，已被擴充以能夠處理證明。在工作量證明中，投票者是區塊提議者。他們藉由在某個分支之上建構自己的區塊來為該分支投票。在我們的權益證明協定中，所有驗證者都是投票者，每一個都平均每 6.4 分鐘藉由發布一份證明來為它對網路的看法投下一票。所以在 PoS 之下，我們對於參與者對網路之看法，可取得的資訊要多得多。

這就是「訊息驅動」（message driven）的含意，它給了我們 LMD 中的 MD。分叉選擇不是由提議者所加入的區塊驅動，而是由所有驗證者所發布的訊息（證明、投票）驅動。

「L」代表「最新」（latest）：LMD GHOST 只考慮來自每個驗證者的_最新_訊息，也就是我們從那個驗證者收到的最近一份證明。驗證者所有較早的訊息都被丟棄，但它最新的一票會被保留，並無限期地具有權重。

順帶一提，還有其他版本的訊息驅動 GHOST。Vitalik [最初偏好](https://web.archive.org/web/20230630135311/https://nitter.it/VitalikButerin/status/1029906757512966144#m) IMD，即「即時訊息驅動」（Immediate Message Driven）GHOST。就我所能判斷[^fn-imd-tricky]，這種版本無限期地保留所有證明，而分叉選擇依當時為現行的那份證明來做選擇。然後還有 [FMD](https://ethresear.ch/t/saving-strategy-and-fmd-ghost/6226?u=benjaminion)，即「新鮮訊息驅動」（Fresh Message Driven）GHOST，它只考慮來自當前與前一個紀元的證明。還有 [RLMD](https://ethresear.ch/t/a-simple-single-slot-finality-protocol/14920?u=benjaminion)，即「近期最新訊息驅動」（Recent Latest Message Driven）GHOST，它只在一個可參數化的紀元數內記住驗證者的最新證明。

[^fn-imd-tricky]: 我至今還沒找到一份清晰明瞭的 IMD GHOST 闡述。回頭翻看[最初的迷你規格](https://ethresear.ch/t/beacon-chain-casper-mini-spec/2760?u=benjaminion)的歷史能得到一些資訊，但很難理解當時真正發生的是什麼。它最初被稱為[「對證成的遞迴鄰近度」](https://web.archive.org/web/2/https://nitter.it/VitalikButerin/status/1029906887376961536#m)（recursive proximity to justification），因為它與 Casper FFG 緊密交纏在一起，而 LMD GHOST 並非如此。

#### 它如何運作

LMD GHOST 最重要的是一個[分叉選擇規則](/part2/consensus/preliminaries/#fork-choice-rules)。給定一棵區塊樹與一組投票，LMD GHOST 會告訴我應該把哪個區塊視為最佳鏈頭，從而給我一份從那個鏈頭一路回溯到創世的線性歷史看法。這個判定是基於我對鏈的局部視角，而局部視角又是基於我的節點所收到的訊息（區塊與證明）——記住，並不存在「上帝視角」，我的局部視角就是我所能憑藉的全部，而它很可能與其他節點的局部視角不同。其構想是：誠實的驗證者會把它們的區塊建構在它們所見的最佳鏈頭之上，並進而依它們所見的最佳鏈頭區塊投下它們的票。

一個好的分叉選擇規則會交付的若干特性如下。[^fn-good-fork-choice-rule]

[^fn-good-fork-choice-rule]: 我是根據 Vitalik 的一篇舊文[《PoS 分叉選擇規則之所求》](https://ethresear.ch/t/pos-fork-choice-rule-desiderata/2636?u=benjaminion)改寫的。我暫時把他關於最終性的那一點延後處理。就我所知，並沒有太多針對 LMD GHOST 在這類性質上的形式化分析；事實上，我們對 LMD GHOST 的實作在某些方面[可能表現不太好](https://arxiv.org/pdf/2302.11326.pdf)。但在我們探討這個機制如何運作時，這些目標值得放在心上。

  - 多數誠實則前進：如果超過 50% 的節點藉由遵循分叉選擇規則來建構區塊，那麼鏈就會前進，並且（以指數方式）不太可能回退較舊的區塊。
  - 穩定性：當前的分叉選擇能夠很好地預測未來的分叉選擇。
  - 抗操縱性：即使攻擊者掌握了某個小參與者集合的暫時性超級多數，攻擊者也不太可能有辦法回退區塊。

這些要點全都互有關聯。穩定性尤其對區塊提議者很重要。當我提議一個區塊時，我想要盡我所能地確定那個區塊將永遠留在鏈中。等價地說，確定它不會被重組出去。找到鏈頭區塊，意味著找到那個——當我在它之上建構時——最有可能使我的新區塊在其他節點看來成為鏈頭的區塊。

我們會把對 LMD GHOST 如何運作的探討一分為二。我們先看 LMD 的部分，即最新訊息，再看 GHOST 的部分，即找到鏈頭。

##### 最新訊息

在這個情境中，訊息就是證明中所含的鏈頭區塊投票。

###### LMD GHOST 中的投票

在一份證明的[資料](/part3/containers/dependencies/#attestationdata)中，鏈頭投票就是 `beacon_block_root` 欄位：

```python
class AttestationData(Container):
    slot: Slot
    index: CommitteeIndex
    # LMD GHOST vote
    beacon_block_root: Root
    # FFG vote
    source: Checkpoint
    target: Checkpoint
```

每個誠實的驗證者每個紀元恰好做出一份證明，其中包含它在做出證明的那一刻、它視角中對最佳鏈頭區塊所投的票。在每個紀元內，驗證者集合會被切分開來，使得每個時段只有 $1/32$ 的驗證者在做出證明。（這個結構中的 `index` 欄位，與證明驗證者出於運作上的原因、在每個時段被進一步劃分成最多 64 個[委員會](/part2/building_blocks/committees/)有關，但這與 LMD GHOST 的運作機制無關，我們將忽略它。）

節點接收證明的方式有兩種：直接的，透過證明流言；以及間接的，包含在區塊裡。原則上，節點也可以透過其他方式收到證明——如果我願意，我大可以從鍵盤打進一份證明——但實務上，投票只透過證明流言以及在區塊內傳播。

###### 儲存最新訊息

不論透過什麼方式收到一份證明，節點都會呼叫分叉選擇的 [`on_attestation()`](/part3/forkchoice/phase0/#on_attestation) 處理常式。在繼續之前，`on_attestation()` 處理常式會對該證明執行一些基本的[有效性檢查](/part3/forkchoice/phase0/#validate_on_attestation)：

  - 它太舊了嗎？
    - 它必須來自當前或前一個紀元。見[證明採計延遲](/part2/consensus/issues/#attestation-consideration-delay)。
  - 它太新了嗎？
    - 它必須來自不晚於前一個時段。見[證明的近期性](/part2/consensus/issues/#attestation-recency)。
  - 我們知道它所投票支持的那個區塊（`beacon_block_root`）嗎？
    - 我們必須已經收到那個區塊。如果沒有，我們可能會試著向某個對等節點取得它。
  - 它的簽章正確嗎？
    - 驗證者為證明簽章，並為它們負責。
  - 這份證明是可罰沒的嗎？
    - 我們必須忽略與其他證明相衝突的證明。見[證明含糊其辭](/part2/consensus/issues/#attestation-equivocation)。

通過這些以及一些其他檢查之後，這份證明就會被考慮插入節點的 Store；Store 是節點關於鏈狀態之資訊的儲存庫，也就是它的視角。這是在 [`update_latest_messages()`](/part3/forkchoice/phase0/#update_latest_messages) 中完成的。如果我們還沒有該驗證者的鏈頭區塊投票，那麼就為它儲存這一份。如果我們已有該驗證者的鏈頭區塊投票，那麼若這一份較為近期，就以它取代舊的。

於是，隨著時間推移，節點的 Store 會建立起一份清單，其中對每個它聽說過的驗證者各含一份最新投票。

請注意，一份投票只有在我們於它被做出的同一個紀元、或之後的那個紀元聽說它時，才能被插入 Store。然而，一旦它進入 Store，它就會無限期地留在那裡，並持續對分叉選擇有所貢獻，直到它被一份較近期的投票更新為止。這是 LMD GHOST 與——比方說——[Goldfish 協定](https://arxiv.org/pdf/2209.03255.pdf)或 [RLMD GHOST](https://arxiv.org/pdf/2302.11326.pdf)之間的一項關鍵差異。

##### 找出鏈頭區塊

本質上，LMD GHOST 分叉選擇規則是一個函式 $\text{GetHead}(\text{Store}) \rightarrow \text{HeadBlock}$。如我們所見，節點的 Store 就是它對世界的看法：它所收到、可能影響分叉選擇的一切相關資訊。對於我們此處所看的純粹 LMD GHOST 演算法，[Store](/part3/forkchoice/phase0/#store) 的相關部分如下。

  - 區塊樹，它其實只是一份區塊清單。各區塊的父區塊連結在邏輯上把它們連成一棵樹。
  - 來自驗證者的最新訊息（投票）清單。
  - 驗證者的[有效餘額](/part2/incentives/balances/)（基於某個狀態），因為這些提供了演算法中所用的權重。

GHOST 演算法的目標，是從給定的區塊樹中選出單一一個葉區塊，其中葉區塊是指沒有任何後代的區塊。這就會是我們所選出的鏈頭區塊。

我們將假設區塊樹中所有區塊都衍生自單一一個根區塊。在純粹的 GHOST 演算法中，那會是創世區塊：依定義，所有區塊都必須衍生自創世。在我們完整的共識實作中，那個根區塊會是最近一個已證成的檢查點區塊。就我們目前的目的而言，我們需要知道的只是：GHOST 演算法從一個給定的區塊出發，並忽略所有並非衍生自該區塊的區塊。

###### 取得權重

我們做的第一件事，是計算樹中每個分支的「權重」。某種意義上，一個分支的權重就是它的分數。

一票的權重，是做出該投票之驗證者的[有效餘額](/part2/incentives/balances/)。這通常會是 32 ETH，即最大有效餘額，但也可能更少。回想一下，一票就是我們從該驗證者收到的最新訊息。

一個分支的權重，是對該分支根區塊所投之票的權重，加上該區塊各子分支的權重。藉由把子分支的權重納入，我們承認了「對一個區塊投的票，同時也是對該區塊每一個祖先投的票」。一個只由葉區塊構成的分支，其權重就只是對那個區塊所投之票的權重。

<a id="img_annotated_forkchoice_get_weight_0"></a>
<figure class="diagram" style="width: 90%">

![一張區塊樹示意圖，為每個區塊標示出分支權重與投票權重。](images/diagrams/annotated-forkchoice-get-weight-0.svg)

<figcaption>

$B_N$ 是最近一次鏈頭投票投給區塊 $N$ 之驗證者的有效餘額總和，而 $W_N$ 是以區塊 $N$ 為根的分支之權重。

</figcaption>
</figure>

在分支的權重 $W_x$ 與對各區塊所投之票的權重 $B_x$ 之間，存在一些顯而易見的關係。

  - 對於一個只由葉區塊 $L$ 構成的分支，$W_L = B_L$。
  - 一個分支的權重，是對其根區塊所投之票的權重，加上它底下所有分支的權重總和。所以在圖中，$W_1 = B_1 + W_2 + W_3$。
  - 一個分支的權重，是對構成該分支之子樹中所有區塊所投之全部票的權重總和。

由於投票總是帶有正的權重，沒有任何區塊的權重會大於根區塊，而根區塊的權重，就是對樹中所有區塊所投之全部票的權重總和。每個驗證者至多有一份最新訊息——也就是一票——所以那個權重的上界，就是所有活躍驗證者的有效餘額總和。[^fn-ignoring-proposer-boost]

[^fn-ignoring-proposer-boost]: 此處忽略提議者加成（proposer boost），我們會在[後文](/part2/consensus/issues/#proposer-boost)處理它。

###### 取得鏈頭

一旦我們有了每個分支或子樹的權重，演算法就會遞迴地進行下去。給定一個區塊，我們選出從它衍生而來的最重分支。然後我們對那個分支根部的區塊重複這個過程。如果一個區塊只有一個子區塊，那麼選擇顯而易見，沒有工作要做。如果有兩個或更多分支權重相等，我們就任意地選出以區塊雜湊值最大的子區塊為根的那個分支。最終我們會抵達一個沒有子區塊的區塊。這就是一個葉區塊，也會是演算法的輸出。

拆解 GHOST 這個名稱，我們看到這個演算法：是「貪婪」（Greedy）的，意思是它立即取「最重觀測」（Heaviest-Observed）的分支，不再往更遠處看；並且處理的是「子樹」（Sub-Trees），一個分支的權重，就是對該子樹中各區塊所投之票的全部權重總和。

這裡有一個簡單的例子。在這些示意圖中，我區分了：(1) 對某個特定區塊所投之票的權重，也就是附在每個區塊上的數字；(2) 各分支的權重，我把它加在連接區塊與其父區塊的線上。

首先，從 Store 中的最新訊息，我們計算出對樹中每個區塊所投之票的權重。

<a id="img_annotated_forkchoice_lmd_ghost_0"></a>
<figure class="diagram" style="width: 85%">

![一張區塊樹示意圖，顯示對每個區塊所投之票的權重。](images/diagrams/annotated-forkchoice-lmd-ghost-0.svg)

<figcaption>

`get_head()` 從區塊樹的根區塊 $A$ 出發。圖中數字顯示對每個區塊所投之票的權重。

</figcaption>
</figure>

其次，從對每個區塊所投之票的權重，我們可以計算出每個分支或子樹的權重。

<a id="img_annotated_forkchoice_lmd_ghost_1"></a>
<figure class="diagram" style="width: 85%">

![一張區塊樹示意圖，顯示每個區塊的權重以及每個分支（或子樹）的權重。](images/diagrams/annotated-forkchoice-lmd-ghost-1.svg)

<figcaption>

`get_weight()` 函式套用在一個區塊上時，會回傳該區塊及其所有後代所構成之子樹的總權重。這些權重顯示在子區塊與父區塊之間的線上。

</figcaption>
</figure>

第三，我們遞迴地穿過位於各子樹根部的區塊，每一步都選出權重最高的分支或子樹。最終，我們會抵達一個葉區塊，也就是我們所選出的鏈頭區塊。

<a id="img_annotated_forkchoice_lmd_ghost_2"></a>
<figure class="diagram" style="width: 85%">

![一張區塊樹示意圖，顯示 GHOST 規則所選出的分支。](images/diagrams/annotated-forkchoice-lmd-ghost-2.svg)

<figcaption>

在區塊 $A$ 處，分支 $C$ 較重。在 $C$ 處，分支 $E$ 較重。區塊 $E$ 是一個葉區塊，所以它就是 GHOST 為鏈頭所做的選擇。我們的區塊鏈是 $[A \leftarrow C \leftarrow E]$。「最長鏈」規則本會選出區塊 $G$，儘管那條分支只獲得驗證者中少數的支持。

</figcaption>
</figure>

假如以 $B$ 與 $C$ 為根的子樹權重相等，我們就會依區塊 $B$ 與 $C$ 之中哪一個的區塊雜湊值較大來做選擇——這是一個完全任意的平手決勝機制。

###### 規格

在規格中實作這一切的程式碼是 [`get_head()`](/part3/forkchoice/phase0/#get_head)，它從根區塊向上穿過樹，在每個分叉處取最重的分支。計算一棵子樹之權重的程式碼是 [`get_weight()`](/part3/forkchoice/phase0/#get_weight)。

如果你查看 [`get_weight()`](/part3/forkchoice/phase0/#get_weight)，你會發現它比我們此處所涵蓋的更複雜，這是由於一種稱為「提議者加成」（proposer boost）的東西。我們會在[問題與修正](/part2/consensus/issues/)一節詳細討論提議者加成。

#### 直覺

看過 GHOST 協定如何運作之後，要對「我們為何偏好它而不偏好最長鏈規則」獲得一些直覺，或許會比較容易。分叉的出現，暗示了區塊傳播時間已變得與區塊產生間隔（時段）相當，甚至超過了它。簡言之，並非所有驗證者都及時看到了所有區塊，因而來不及為它們做出證明或在它們之上建構。[^fn-toward-12s]

[^fn-toward-12s]: Vitalik 的[《邁向 12 秒區塊時間》](https://blog.ethereum.org/2014/07/11/toward-a-12-second-block-time)對工作量證明情境下的這個議題做了引人入勝的分析。然而，其中沒有太多能延續到我們的 PoS 實作，除了「GHOST 有助於理解一個會分叉的網路」這一點之外。

在這種情況下，我們想善用一切可取得的最大量資訊。對同一個父區塊的兩個不同子區塊所投的票，應被視為「所有那些驗證者都偏好該父區塊的分支」的佐證，即使對於子區塊存在分歧。GHOST 達成這一點的辦法很簡單，就是讓對一個子區塊投的票為它所有的祖先增添權重。如此一來，面臨選擇時，我們就偏好獲得驗證者總支持最多的分支。我已在[上方的示意圖](#img_annotated_forkchoice_lmd_ghost_2)中說明了這一點：分支 $C$ 較分支 $B$ 受青睞，儘管區塊 $B$ 比區塊 $C$ 有更多的直接票數，因為整體而言有更多驗證者為分支 $C$ 投下了最新票。

最長鏈規則丟棄了這一切資訊，並可能讓一個分支勝出，即使只有少數驗證者一直在它上面下工夫。

#### 確認規則

在工作量證明中，唯一可作為分叉選擇輸入的資料來自區塊產生，它代表單一一個礦工在發布區塊那一刻的看法。

在以太坊的權益證明協定中，除了區塊提議者的看法之外，我們還有多得多的資訊可以取用，其形式是每 12 秒由 $\frac{1}{32}$ 的驗證者集合所投下的鏈頭區塊票。

原則上，所有這些額外的資訊，應當讓我們能很快、很有把握地判斷區塊將維持正典，還是有被回退的危險。工作量證明的鏈傾向使用一種圍繞「一個區塊已收到多少確認數」的經驗法則。也就是說，假設一個區塊上面建構的區塊越多，它被回退的可能性就以指數方式越低。這大致為真，但在高時延的環境中（例如攻擊者祕密地造出一條更長的鏈）可能嚴重失靈。

權益證明對此的終極解答是最終性，我們會在下一節探討它。LMD GHOST 本身並不提供最終性。然而，思考一下我們是否有某種類似於工作量證明確認規則的經驗法則可用，是很有意思的，而結果證明[確實有](https://ethresear.ch/t/confirmation-rule-for-ethereum-pos/15454?u=benjaminion)。事實上，它優於 PoW 的確認規則，因為它對一個區塊的安全性給出的是「是／否」的陳述，而不是一個機率。

確認規則的細節由 Aditya Asgaonkar 在一篇[部落格文章](https://web.archive.org/web/20240422100537/https://www.adiasg.me/confirmation-rule-for-ethereum/)以及一篇[隨附的論文](https://arxiv.org/abs/2405.00549)中描述。一般性的構想是：對於一個區塊 $b$，我們計算兩個值 $q$ 與 $q_\text{min}$。當 $q > q_\text{min}$，_並且_網路維持接近同步時，那個區塊就被確認為「安全」。我們可以完全有信心它不會被重組。

量 $q^n_b$ 定義為：在時段 $n$ 時以 $b$ 為根之子樹的權重，除以自 $b$ 被產生以來所投下之全部票的總權重。簡單地說，如果在 $b$ 被提議以來的那些時段中，有 80% 的驗證者為 $b$ 或 $b$ 的某個後代投了票，那麼 $q^n_b$ 就會是 $0.8$。

$q_\text{min}$ 定義為 $\frac{1}{2} + \beta$，其中 $\beta$ 是我們認為受對手控制的質押比例。這個比例是未知的，但假設它小於三分之一，否則我們就有大麻煩了。

現在，如果對於 $b$ 以及它所有（未最終確定的）祖先 $b'$，都有 $q^n_{b'} > q_\text{min}$，那麼 $b$ 就被視為已確認，或「安全」。

其構想是：一旦一條到區塊 $b$ 為止的分支，累積了可用投票權重的簡單多數，那麼所有誠實的驗證者都會繼續為那條分支投票，所以它會無限期地維持其多數地位。這件事失靈的一種方式，是不誠實的驗證者把它們的票換到另一條分支，反倒讓那條分支取得多數。這就是為什麼我們在基本的多數安全參數 $\frac{1}{2}$ 之上加了一個比例 $\beta$，如此一來，即使所有不誠實的驗證者都換了分支，我們的分支仍維持多數。它失靈的另一種方式，是網路開始遭受延遲或分區（失去同步），使得某些誠實的驗證者看不到其他誠實驗證者的票，這也就是為何要依賴網路維持足夠的同步。

雖然這看起來非常直覺，但有一些與「整合 Casper FFG」相關的重要微妙之處與複雜性，會修改這條確認規則，所以任何處理這件事的人都應參閱[完整論文](https://arxiv.org/abs/2405.00549)。此外，[提議者加成](/part2/consensus/issues/#proposer-boost)使得有對抗意圖的區塊提議者更容易重組一個區塊，所以我們也需要把那一點納入考量。

下表總結了對一個區塊而言，確認規則與最終性之間的差異。

| &nbsp;   | 確認      | 最終性 |
| ----     | --------          | -------- |
| 時間 | 理想情況下為一個時段，一般情況下不到一分鐘多一點。 | 至少兩個紀元／13 分鐘。 |
| 假設 | 網路在最終確定之前維持同步。 | 不假設同步。 |
| 失效 | 若網路未維持同步，一個已確認的區塊可能被重組。 | 若超過 $\frac{1}{3}$ 的驗證者犯下一項可罰沒的行為，一個相衝突的區塊可能被最終確定。 |

撰寫本文時，確認規則尚未在客戶端軟體中實作，但應當會在適當時機透過[安全區塊](/part3/safe-block/)規格提供。

#### LMD GHOST 中的激勵

加密經濟系統用來確保自身安全的方式之一，是獎勵好的行為、懲罰壞的行為。在我們對 LMD GHOST 的實作中，提議者與證明者都會因為準確地找出鏈頭而以不同的方式獲得獎勵。

區塊提議者建構在最佳鏈頭之上的誘因很清楚。如果它沒有這麼做，那麼它的區塊很有可能不會被納入最終的正典鏈——它會被孤立（orphaned）——在這種情況下，提議者就不會收到它的任何區塊獎勵。這是一種隱含的誘因，而非明示的誘因；工作量證明中的礦工處境類似。

相比之下，驗證者則因為準確地投票而直接獲得獎勵。當一個驗證者做出準確的鏈頭投票，而它的證明在緊接著的下一個時段被納入某個區塊時，它會收到[一份微獎勵](/part2/incentives/rewards/#introduction)。一個表現完美的驗證者，會從做出準確的鏈頭投票中獲得它協定總獎勵的約 22%。提議者反過來也受到激勵去把這類證明納入區塊，因為它們每設法納入一份，就會收到一份成比例的微獎勵。

一票是準確的，如果它與最終進入正典鏈的東西相符。所以如果驗證者為前一個時段的某個區塊投了票，而正典鏈在那裡有一個相符的區塊，那麼它就收到它的獎勵。如果它為某個更早時段的區塊投了票，藉此指出有一個被跳過的時段，而正典鏈在那個區塊與當前之間確實有被跳過的時段，那麼它同樣會收到它的獎勵。

如果驗證者做出不準確的鏈頭投票，或它們的鏈頭投票沒有在一個時段內被納入鏈上，並沒有任何懲罰。在信標鏈承受壓力、出現遲到與缺失區塊時，要把鏈頭投票投對是困難的。這往往不是驗證者本身的過錯，而在這種情況下懲罰它們被認為並不公平。[^fn-head-block-penalty]

[^fn-head-block-penalty]: 最初的 Phase 0 規格對於錯失的鏈頭投票[確實有一項懲罰](https://benjaminion.xyz/eth2-annotated-spec/phase0/beacon-chain/#components-of-attestation-deltas)。這在 [Altair 升級](/part4/history/altair/)的記帳改革中被移除了。

#### LMD GHOST 中的罰沒

權益證明設計上的重大突破之一，是採用罰沒作為繞過[「無利害關係」問題](https://ethereum.stackexchange.com/questions/2402/what-exactly-is-the-nothing-at-stake-problem)的辦法。這個問題本質上是：在權益證明之下，驗證者藉由發布多份相互矛盾的訊息來含糊其辭，幾乎是無代價的。

結果這個解決方案相當優雅。我們偵測出驗證者何時含糊其辭，並懲罰它。這項懲罰稱為[「罰沒」](/part2/incentives/slashing/)，它牽涉到扣除驗證者質押的一部分，並把該驗證者逐出協定。由於驗證者為它們的訊息加上數位簽章，找到兩份相互矛盾的已簽章訊息，就是對不當行為的絕對證明，所以我們可以有把握地進行罰沒。

「罰沒」（slashing）這個名稱源自 Vitalik 2014 年初的 [Slasher](https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm) 演算法。那是解決無利害關係問題的一個非常早期的提案。我們目前的設計看起來不太像 Slasher，但有些東西延續了下來，尤其是這個名稱。

##### 提議者罰沒

當輪到某個驗證者在某個特定時段產生一個區塊時，該驗證者理應執行[分叉選擇規則](/part2/consensus/preliminaries/#fork-choice-rules)，以決定它要把自己的區塊建構在哪個既有的區塊之上。它的目標是辨識出——根據它所擁有的證據——最有可能最終成為正典的那個分叉。也就是整個正確驗證者集合將收斂到的那一個。

<a id="img_consensus_nas_0"></a>
<figure class="diagram" style="width: 70%">

![一張帶有分叉的區塊樹示意圖，提議者在其中可以選擇要建構在哪個鏈頭區塊上。](images/diagrams/consensus-nas-0.svg)

<figcaption>

一個區塊的提議者需要選擇要建構在哪個區塊之上。最佳策略是建構在分叉選擇規則所指出的、最不可能被重組的那個區塊之上。

</figcaption>
</figure>

然而，何必選擇呢？在權益證明之下——不像在工作量證明之下——驗證者產生區塊幾乎是無代價的。因此，一個好的策略似乎是提議多個區塊，在每一個可能的鏈頭上各建一個，這樣一來，我的區塊中至少有一個保證會成為最終正典鏈的一部分。

<a id="img_consensus_nas_1"></a>
<figure class="diagram" style="width: 70%">

![一張帶有分叉的區塊樹示意圖，提議者在其中於分叉的兩側都進行建構。](images/diagrams/consensus-nas-1.svg)

<figcaption>

在沒有懲罰的情況下，一個懶惰或不誠實的提議者可能選擇延伸分叉的兩側。

</figcaption>
</figure>

這是不可取的，因為它會延長任何分叉，並阻止網路收斂到一份線性的歷史。鏈的使用者可能無法判斷哪一個分叉才是正確的，而那會使他們易受雙重花費攻擊之害，這正是我們希望避免的事。

這說明了[無利害關係問題](https://ethereum.stackexchange.com/questions/2402/what-exactly-is-the-nothing-at-stake-problem)。如上所述，解決方案是偵測出那兩個相互矛盾的區塊，並罰沒提議它們的那個驗證者。

提議者含糊其辭不是在協定內偵測的，而是依賴第三方以一個 [`ProposerSlashing`](/part3/containers/operations/#proposerslashing) 物件的形式構造一份含糊其辭的證明。這份證明僅由兩個已簽章的信標區塊標頭構成：那就足以證明提議者在同一個時段為兩個區塊背書。後續的某個區塊提議者會把這份證明納入一個區塊中（並因此獲得豐厚的獎勵），協定則會罰沒那個犯規驗證者的餘額，並把它逐出活躍驗證者集合。

##### 證明者罰沒

同樣地，當輪到某個驗證者發布一份證明時，它理應執行它的分叉選擇規則，並為它認為最佳的鏈頭區塊投票。這裡的問題是，攻擊者可能做出多份相互矛盾的證明，以挑起或延長分叉，並阻止網路收斂到單一一條鏈。即使是一個大致誠實的驗證者，也可能受到誘惑而為一個處於臨界的遲到區塊做出兩份證明：一份投票支持該區塊，一份投票支持一個空時段。若這不是會受罰的行為，這麼做就能對沖「投錯方向而錯失獎勵」的可能性。

補救之道是一樣的：偵測並懲罰相互矛盾的證明。也就是由同一個驗證者在同一個時段為不同鏈頭區塊所做出的證明。

#### 歷史

以太坊中的 LMD GHOST 分叉選擇，其起源在於 Vlad Zamfir 對 Casper CBC 協定的研究（當時稱為 Casper TFG，不要與 Casper FFG 混淆，後者是相當不同的東西[^fn-naming-in-ethereum]）。Casper TFG 的[最初公告](https://blog.ethereum.org/2015/08/01/introducing-casper-friendly-ghost)在 2015 年，而在他 2017 年的論文[《友善幽靈 Casper》](https://raw.githubusercontent.com/vladzamfir/research/master/papers/CasperTFG/CasperTFG.pdf)中，Zamfir 描述了把 Sompolinsky 與 Zohar 的 [GHOST](https://eprint.iacr.org/2013/881) 協定與一個「最新訊息」構造結合起來。

[^fn-naming-in-ethereum]: 歡迎來到在以太坊中為事物命名的樂趣。

2018 年 8 月，Vitalik [仍然偏好](https://web.archive.org/web/20230630135358/https://nitter.it/VitalikButerin/status/1029906887376961536#m)一種稱為 [IMD GHOST](https://ethresear.ch/t/immediate-message-driven-ghost-as-ffg-fork-choice-rule/2561?u=benjaminion) 的分叉選擇（先前稱為「對證成的遞迴鄰近度」），它比我們今天所擁有的純粹 LMD GHOST 更能感知最終確定與證成。隨著 [Eth2 共識迷你規格](https://ethresear.ch/t/beacon-chain-casper-mini-spec/2760?u=benjaminion)的演進，IMD GHOST 在 2018 年 11 月被改為 LMD GHOST[^fn-see-the-changes]。這是由於對 IMD GHOST [穩定性性質](https://ethresear.ch/t/beacon-chain-casper-mini-spec/2760/17?u=benjaminion)的疑慮。

[^fn-see-the-changes]: 你可以藉由點擊標題附近的鉛筆圖示，查看[迷你規格](https://ethresear.ch/t/beacon-chain-casper-mini-spec/2760?u=benjaminion)的變更歷史。

2018 年 11 月[迷你規格](https://ethresear.ch/t/beacon-chain-casper-mini-spec/2760?u=benjaminion)中對 LMD GHOST 的那份描述，本質上就是我們今天所使用的。

#### 另見

請記住，本節只涵蓋了 LMD GHOST 的純粹形式。在以太坊完整的共識協定中，LMD GHOST 會因為與 Casper FFG 整合而被修改，我們會在 [Gasper](/part2/consensus/gasper/) 一節看到這一點。它也會被[提議者加成](/part2/consensus/issues/#proposer-boost)修改，我們同樣會在後文討論。

共識規格儲存庫中的[分叉選擇](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/fork-choice.md)文件包含相關的規格。它們在我的註解規格中於下列各處有所涵蓋。

  - [`get_head()`](/part3/forkchoice/phase0/#get_head) 是分叉選擇的進入點，用於我們想取得對當前最佳鏈頭區塊之意見時。
  - [`get_weight()`](/part3/forkchoice/phase0/#get_weight) 是 LMD GHOST 演算法被實作之處。
  - [`on_attestation()`](/part3/forkchoice/phase0/#on_attestation) 處理常式是分叉選擇得知 LMD GHOST 投票之處。
    - 驗證那些投票，大多在 [`validate_on_attestation()`](/part3/forkchoice/phase0/#validate_on_attestation) 中處理。
    - [`update_latest_messages()`](/part3/forkchoice/phase0/#update_latest_messages) 負責處理圍繞最新訊息的記錄工作。

Vitalik [註解版分叉選擇](https://github.com/ethereum/annotated-spec/blob/master/phase0/fork-choice.md)的引言是一份絕佳的概觀（雖然規格本身的某些細節如今已過時）。Vitalik 的 [CBC Casper 教學](https://web.archive.org/web/20231102070341/https://vitalik.ca/general/2018/12/05/cbc_casper.html)中 LMD GHOST 的部分有一段不錯的講解。請忽略後面關於 Casper CBC 中最終性的內容——那與我們無關。

LMD GHOST 目前在以太坊中所實作之形式的一些弱點，在 [RLMD GHOST](https://arxiv.org/pdf/2302.11326.pdf) 論文中有所檢視。例如，LMD GHOST 並未安全地處理動態參與——也就是大量驗證者離線時——以及其他一些問題。我們會在[後文](/part2/consensus/issues/)考慮其中一些問題，但如果你想先行領先一步，那篇論文的引言值得一讀。

### Casper FFG <!-- /part2/consensus/casper_ffg/ -->

<div class="summary">

  - Casper FFG 為 Eth2 共識協定增添最終性。
  - 它作為 LMD GHOST 共識上的一層疊加層運作，修改它的分叉選擇規則。
  - 當少於 $\frac{1}{3}$ 的驗證者為故障或具對抗意圖時，Casper FFG 在非同步環境下具有古典意義的安全性。
  - 此外，當超過 $\frac{1}{3}$ 具對抗意圖時，罰沒讓 Casper FFG 得以提供可問責的安全性，也稱為經濟性最終性。

</div>

#### 引言

已有許多文章寫來解釋 Casper FFG 的基本運作機制——它_如何_運作——但關於它_為何_運作的內容卻很少。我希望讀完本節時，你會覺得自己對 Casper FFG 為何有效獲得了一些洞見。

Casper FFG 的運作機制並不十分複雜。即便如此，在你讀下去時，請記住：Casper FFG 的有效性真正歸結於兩個大構想。第一是兩階段提交（two-phase commit，即證成與最終確定），第二是可問責的安全性（accountable safety）。

兩階段提交賦予 Casper FFG 古典意義的共識安全性。它使我們得以宣告區塊為最終的，並確信沒有任何誠實的驗證者會回退它們。但這只有在超過三分之二的質押由誠實驗證者控制時才可強制執行，而這一點我們並不總能假定。

在此之上，Casper FFG 還提供一項額外的保證，稱為可問責的安全性，適用於超過三分之一的驗證者不誠實的情況。萬一鏈遭受相衝突的最終性之害，全部質押以太幣總額中至少三分之一將被燒毀。這是藉由罰沒違反兩條 Casper 誡命中任一條的驗證者來強制執行的。

#### 概觀

Casper FFG 是一種後設共識協定。它是一層疊加層，可以在一個底層共識協定之上運行，以便為它增添最終性。回想一下，[最終性](/part2/consensus/preliminaries/#finality)是這樣一種性質：鏈中存在一些區塊，保證永遠不會被回退：它們將永遠是鏈的一部分。在以太坊的權益證明共識中，底層協定是 [LMD GHOST](/part2/consensus/lmd_ghost/)，它並不提供最終性——總是有可能驗證者決定建構一條競爭的鏈，而這麼做並沒有真正的懲罰。Casper FFG 作為一個「最終性裝置」運作，我們用它來為 LMD GHOST 增添最終性。

Casper FFG 善用了這個事實：身為一個權益證明協定，我們知道我們的參與者是誰：管理質押以太幣的那些驗證者。這意味著我們可以用數票的方式，來判斷我們何時看到了誠實驗證者的多數票。更精確地說，是來自管理多數質押之驗證者的票——在接下來的一切中，每個驗證者的票都依它所管理之質押的價值加權，但為求簡潔，我們不會每次都明說。

我們是在一個非同步的網路——網際網路——上運作，這意味著如果我們想同時達成安全性與活躍性，至多只能容忍 $\frac{1}{3}$ 的驗證者具對抗意圖（或故障）。這是共識理論中一個眾所周知的結果[^fn-bracha-toueg]，推理如下。

  - 我們總共有 $n$ 個驗證者，其中有一定數量 $f$ 可能以某種方式故障或具對抗意圖。
  - 為了保住活躍性，我們需要在僅聽取了 $n - f$ 個驗證者之後就能做出決定，因為那 $f$ 個故障的驗證者可能扣住它們的票不投。
  - 但這是一個非同步的環境，所以那 $f$ 個沒有回應的驗證者，可能只是延遲了，根本不是故障。
  - 因此，我們必須把「我們所收到的 $n - f$ 份回應中，最多有 $f$ 份來自故障或具對抗意圖的驗證者」這件事納入考量。
  - 為了保證我們在聽取了 $n - f$ 個驗證者之後，總是能達成誠實驗證者的簡單多數，我們要求 $(n - f)/2 > f$。也就是 $n > 3f$。

[^fn-bracha-toueg]: 例如可參見 Bracha 與 Toueg 的論文[《非同步共識與廣播協定》](https://dl.acm.org/doi/10.1145/4221.214134)（1985）。Pease、Shostak 與 Lamport 較早的著作[《在故障存在下達成一致》](https://lamport.azurewebsites.net/pubs/reaching.pdf)（1980）給出了相同的界限，但它是基於一個驗證者可以偽造訊息之系統中的同步通訊。我們的環境是非同步、訊息不可偽造的，所以 Bracha 與 Toueg 的分析才是相關的。

總而言之，如同所有古典的拜占庭容錯（BFT）協定，當總驗證者集合中少於三分之一為故障或具對抗意圖時，Casper FFG 能夠提供最終性。當足夠多的誠實驗證者宣告某個區塊已最終確定時，所有誠實的驗證者都會跟隨，而那個區塊將不會被回退。然而，如我們將見，與古典 BFT 協定不同，Casper FFG 即使在驗證者集合中超過三分之一為故障或具對抗意圖時，仍能提供經濟性最終性（可問責的安全性）。

在本節中，我們會就 Casper FFG 本身來考慮它，不太花時間在它如何與 LMD GHOST 整合上。這符合 [Casper FFG 論文](https://arxiv.org/pdf/1710.09437.pdf)的精神，該論文對底層的區塊鏈共識機制著墨甚少。我們會在[下一節](/part2/consensus/gasper/)看這兩者如何結合成 Gasper。

#### 命名

再一次，Casper FFG 這個名稱由兩個部分組成，兩者都值得一看。

##### Casper

名稱中的 Casper 部分似乎要歸功於 Vlad Zamfir。他在他《Casper 的歷史》[第 5 部](https://medium.com/@Vlad_Zamfir/the-history-of-casper-chapter-5-8652959cef58)中如下解釋。

> 在這一章，我重述 Casper 誕生的故事，它最初是把 Aviv Zohar 與 Jonatan Sompolinsky 的 GHOST 原則應用到權益證明上。
>
> 我把它稱為「友善幽靈」，是因為那些被設計來保證對寡頭壟斷者具抗審查性的激勵：那些激勵迫使該卡特爾對非卡特爾的驗證者友善。

他提到的 GHOST 協定，與我們在[前一節](/part2/consensus/lmd_ghost/#ghost)所看的相同。如果你共享這樣的文化背景——「友善幽靈 Casper」是一個[自 1940 年代以來](https://en.wikipedia.org/wiki/Casper_the_Friendly_Ghost)就存在的卡通人物——對於理解這一切會有幫助。

Zamfir 的協定最初稱為 Casper TFG（The Friendly Ghost，友善幽靈），後來改名為 Casper CBC（Correct By Construction，依構造即正確）。Vitalik 的 Casper FFG 與 Zamfir 的 Casper TFG/CBC 是並肩成長的——這大概解釋了命名上的相互呼應——但兩者其實沒什麼共通之處。事實上，Casper FFG 甚至不使用 GHOST 協定。[^fn-casper-confusion]

[^fn-casper-confusion]: 這當然相當令人困惑。但它遠遠稱不上是以太坊命名中最令人困惑的事，所以我們就將就著接受了。

##### FFG

FFG 的部分代表「友善最終性裝置」（Friendly Finality Gadget），如同 [Casper FFG 論文](https://arxiv.org/pdf/1710.09437.pdf)的標題。

這顯然是在玩 Zamfir 的 TFG 名稱，但也指出了 Casper FFG 並不是一個完全自成一體的區塊鏈協定，而是一個能為底層共識協定增添最終性的「裝置」。

#### 術語

一如既往，我們所使用的行話，就是理解這個協定如何構成的入口。

##### 紀元與檢查點

為了對最終性做出決定，Casper FFG 機制需要處理來自至少 $\frac{2}{3}$ 驗證者集合的票。在以太坊中，驗證者集合有可能非常龐大，要讓數十萬個驗證者的票同時被廣播、流言傳播並處理是不可行的。

為了繞過這一點，投票被分散在一個紀元[^fn-epoch-dynasty]的時長內進行；在 Eth2 中，一個紀元是 32 個各為 12 秒的時段。在每個時段，總驗證者集合中的 $\frac{1}{32}$ 被排定要廣播一票，所以每個驗證者每個紀元恰好被排定投一次票。為了效率，我們把每個驗證者的 Casper FFG 投票與它的 LMD GHOST 投票捆在一起，不過這絕非必要。

[^fn-epoch-dynasty]: Casper FFG 論文除少數例外，一般以「朝代」（dynasty）一詞指稱紀元。它是同一回事。

為了確保在紀元期間於不同時間投票的驗證者，有某個共同的東西可以投票支持，我們讓它們為一個檢查點投票，而檢查點就是一個紀元的第一個時段。紀元 $N$ 中的檢查點位於時段編號 $32N$（記住時段與紀元都從零開始編號）。

<a id="img_consensus_slots_epochs_checkpoints"></a>
<figure class="diagram" style="width: 90%">

![一張示意圖，顯示一個紀元，第一個時段有一個檢查點，每個時段內有區塊。](images/diagrams/consensus-slots-epochs-checkpoints.svg)

<figcaption>

一個紀元被劃分成 32 個時段，每個時段通常含有一個區塊。一個紀元的第一個時段就是它的檢查點。時間由左向右增加。

</figcaption>
</figure>

順帶一提，人們常常偷懶地說最終確定紀元，但那並不正確。Casper FFG 最終確定的是檢查點，即紀元的第一個時段。當我們最終確定了紀元 $N$ 中的檢查點時，我們就最終確定了直到並包含時段 $32N$ 為止的一切。這包含整個紀元 $N-1$ 以及紀元 $N$ 的第一個時段。但我們尚未最終確定紀元 $N$——它裡頭仍有 31 個未最終確定的時段。

目前我們會假設每個時段裡都有一個區塊。這是因為最初 Casper FFG 的檢查點是基於區塊高度而非時段編號。等我們看 [Gasper](/part2/consensus/gasper/) 時，我們會放寬這個假設，以允許空時段與空檢查點。

在協定內部，一個 [`Checkpoint`](/part3/containers/dependencies/#checkpoint) 物件單純地含有該檢查點的紀元編號，以及該紀元第一個時段中鏈頭區塊的雜湊樹根（`root`）：

```python
class Checkpoint(Container):
    epoch: Epoch
    root: Root
```

##### 證成與最終確定

如同古典的 BFT 共識協定，Casper FFG 透過一個兩輪的過程來達成最終性。

在第一輪，我把我對當前紀元檢查點（比方說 $X$）的看法廣播給網路的其餘部分，並聽取網路其餘部分的看法是什麼。如果有一個超級多數告訴我它們也支持 $X$，那就讓我得以_證成_它。證成只就我的網路視角而言為局部的：在這個階段，我相信網路的多數相信 $X$ 適合被最終確定。但我還不知道網路的其餘部分是否也得出了相同的結論。在對抗的條件下，有可能有足夠多數的其他驗證者未能就 $X$ 達成決定。我們會在[後文](#conflicting-justification)看這樣的情境。

在第二輪，我廣播這樣一個事實：我已聽到一個超級多數的驗證者支持 $X$（也就是我已證成 $X$），並且我聽取網路的其餘部分是否相信有一個超級多數的驗證者支持 $X$（也就是它們是否已證成 $X$）。如果我聽到一個超級多數的驗證者與我一致認為 $X$ 已被證成，那麼我就會_最終確定_ $X$。最終確定是一種全域的性質：一個檢查點一旦被最終確定，我就知道沒有任何誠實的驗證者會回退它。即使它們在自己的視角中還沒把該檢查點標記為已最終確定，我也知道它們至少已把它標記為已證成，並且不存在任何（非可罰沒的）行為能夠回退那項證成。

總而言之，要讓我絕對確定整個網路都同意某個區塊不會被回退，需要下列步驟。[^pbft-prepare-commit]

  1. 第 1 輪（理想情況下導向證成）：
     1. 我告訴網路我認為最佳的檢查點是什麼。
     2. 我從網路聽取所有其他驗證者認為最佳的檢查點是什麼。
     3. 如果我聽到 $\frac{2}{3}$ 的驗證者與我一致，我就證成該檢查點。
  2. 第 2 輪（理想情況下導向最終確定）：
     1. 我告訴網路我已證成的檢查點，也就是我從第 1 輪所獲得的集體看法。
     2. 我從網路聽取所有其他驗證者認為集體看法是什麼，也就是它們已證成的檢查點。
     3. 如果我聽到 $\frac{2}{3}$ 的驗證者與我一致，我就最終確定該檢查點。

[^pbft-prepare-commit]: 這兩輪大致對應到[古典 PBFT](https://www.scs.stanford.edu/nyu/03sp/sched/bfs.pdf) 共識的 `PREPARE` 與 `COMMIT` 階段。PBFT 的 `PRE-PREPARE` 階段，多多少少對應於 Casper FFG 中一個檢查點區塊被廣播。

簡言之，當我證成一個檢查點時，我做出一項永不回退它的承諾。當我最終確定一個檢查點時，我知道所有誠實的驗證者都承諾永不回退它。

<a id="img_consensus_two_rounds"></a>
<figure class="diagram" style="width: 95%">

![一張示意圖，說明這兩輪中的投票。](images/diagrams/consensus-two-rounds.svg)

<figcaption>

在第 1 輪，我廣播我的最佳檢查點，並聽取所有其他人的最佳檢查點。理想情況下這會導向證成。在第 2 輪，我廣播我所聽到的眾人最佳檢查點，並聽取它們的看法。理想情況下這會導向最終確定。

</figcaption>
</figure>

在理想條件下，每一輪持續一個紀元，所以證成一個檢查點要花一個紀元，最終確定一個檢查點要再花一個紀元。在紀元 $N$ 的開頭，我們的目標是已證成檢查點 $N-1$，並已最終確定檢查點 $N-2$。

把這量化，在協定內最終確定一個檢查點要花 12.8 分鐘，也就是兩個紀元。在 Casper FFG 中，這兩輪是重疊並以管線方式進行的，所以雖然從頭到尾最終確定一個檢查點要花 12.8 分鐘，我們卻能每 6.4 分鐘——每個紀元一次——最終確定一個檢查點。

請注意，從協定外部，有可能比完整的 12.8 分鐘稍早一點就看出一個檢查點很可能會被最終確定（前提是沒有長鏈重組）。具體而言，有可能在第二輪走完 $\frac{2}{3}$ 時，也就是大約 11 分鐘之後，就已蒐集到足夠的票。然而，協定內的證成與最終確定只在紀元結束時的處理中進行。

關於命名法的一段旁白：「最終確定」（finalised）與「證成」（justified）這兩個詞並未出現在古典共識文獻中。要看出「最終確定」從何而來很容易，但對「證成」或許就不然了，老實說，在這裡用這個詞挺奇特的。就我所能判斷，它的起源在於 Vlad Zamfir 的 [Casper TFG](https://github.com/vladzamfir/research/blob/master/papers/CasperTFG/CasperTFG.pdf) 協定。在那部著作中，訊息含有一份「證成」（justification）來支持所做出的投票。那篇論文任何地方都沒用到「justified」這個詞，但我猜我們就是從那裡得來的。在 Casper FFG 中，我的「證成」就是已看到「有 $\frac{2}{3}$ 的驗證者和我喜歡同一個檢查點」的證據。

##### 來源與目標、連結與衝突

Casper FFG 中的一票有兩個部分：一個_來源_（source）檢查點投票，以及一個_目標_（target）檢查點投票。它們就是一份證明[資料](/part3/containers/dependencies/#attestationdata)中的 `source` 與 `target` 欄位：

```python
class AttestationData(Container):
    slot: Slot
    index: CommitteeIndex
    # LMD GHOST vote
    beacon_block_root: Root
    # FFG vote
    source: Checkpoint
    target: Checkpoint
```

來源與目標投票是以一個_連結_（link）${s \rightarrow t}$ 的形式同時做出的，其中 $s$ 是來源檢查點，$t$ 是目標檢查點。

我的目標投票的作用，是廣播我對「我認為下一個應被證成的檢查點」的看法。以上文的術語來說，它就是我的第 1 輪投票。我的目標投票是一項軟性的（有條件的）承諾：只要我聽到 $\frac{2}{3}$ 的驗證者也對那個檢查點做出承諾，我就不回退那個檢查點。

我的來源投票的作用，是廣播「我已看到網路中 $\frac{2}{3}$ 對檢查點 $s$ 的支持，而它是我所知道的最近一個這樣的檢查點」。以上文的術語來說，它就是我的第 2 輪投票，宣告我所聽到的集體看法。藉由做出這個來源投票，我把我先前「不回退該檢查點」的軟性承諾，升級為「永不回退它」的硬性（無條件的）承諾。

<a id="img_consensus_ffg_vote"></a>
<figure class="diagram" style="width: 50%">

![一張示意圖，說明這兩輪的投票如何被結合進一份證明。](images/diagrams/consensus-ffg-vote.svg)

<figcaption>

Casper FFG 把來源與目標投票結合進單一一則訊息：一個對連結 ${s \rightarrow t}$ 所投的票。

</figcaption>
</figure>

一個誠實驗證者的來源投票，永遠會是它對鏈之看法中最高的已證成檢查點。它的目標投票，會是當前紀元中、衍生自該來源檢查點的那個檢查點。來源與目標檢查點不需要是相鄰連續的；跳過檢查點是被允許的。但當信標鏈運作順利時，某個紀元的目標投票，會是下一個紀元的來源投票。

<a id="img_consensus_source_target"></a>
<figure class="diagram" style="width: 50%">

![一張示意圖，顯示一個從來源到目標的有效連結。](images/diagrams/consensus-source-target.svg)

<figcaption>

一個從已證成檢查點，連到「衍生自它的那條鏈上之檢查點」的連結，是有效的。此處只顯示檢查點；為求清晰，中間的區塊已被省略。

</figcaption>
</figure>

在一個有效的連結中，來源檢查點永遠會是目標檢查點的祖先。若非如此，我就是在自相矛盾：來源投票宣告了我永不回退檢查點 $s$ 的承諾；如果目標檢查點 $t$ 並非衍生自 $s$，那麼那就會是一張回退 $s$ 的票。然而，發布這樣一個無效的連結並不是一項可罰沒的過錯[^fn-conflicting-link-slashable]。

[^fn-conflicting-link-slashable]: 在 Casper FFG 的[較早版本](https://medium.com/@VitalikButerin/minimal-slashing-conditions-20f0b500fc6c)中，連結相衝突的檢查點曾是一項可罰沒的過錯，但這在我們今天所使用的 Casper FFG 設計中被簡化掉了，依據是 [Casper FFG 論文](https://arxiv.org/pdf/1710.09437.pdf)的註腳 4。

<a id="img_consensus_conflict"></a>
<figure class="diagram" style="width: 50%">

![一張示意圖，顯示一個從來源連到一個相衝突目標的無效連結。](images/diagrams/consensus-conflict.svg)

<figcaption>

一個從已證成檢查點，連到「並非衍生自它的那條鏈上之檢查點」的連結，是無效的。這兩個檢查點被說成是_相衝突的_（conflicting），因為兩者都不衍生自對方。

</figcaption>
</figure>

在 Eth2 的實作中，有效的 Casper FFG 投票必須滿足一些圍繞時效性的特定準則。我們會在 [Gasper 一節](/part2/consensus/gasper/)更深入地討論這些，因為它們並不適用於我們此處所考慮的抽象 Casper FFG 協定。

在權衡 Casper FFG 投票時，只考慮已在區塊中收到的票。與 LMD GHOST 的分叉選擇不同，我們不考慮任何僅透過流言、信鴿，或任何其他方式收到的 Casper FFG 投票。這是因為我們對於圍繞最終性的決策，必須永遠擁有一份共同的記錄，而區塊歷史提供了那份共同記錄。所以，當我在上文說「我告訴網路」時，那是「我廣播一份證明，它將被某個區塊提議者撿起並納入一個區塊」的簡稱。而當我說「我從網路聽取」時，那是「我處理了某個區塊中所納入的證明」的簡稱。

另外，容我重申，Casper FFG 中的投票是依驗證者的[有效餘額](/part2/incentives/balances/)加權的。來自一個有效餘額為 24 ETH 之驗證者的一票，所帶的權重，是來自一個有效餘額為 32 ETH 之驗證者一票的 75%。我會經常說諸如「三分之二驗證者的票」這樣的話；你應該把這理解為「管理三分之二質押之驗證者的票」。

##### 超級多數連結

如上所述，一個_連結_是一對連起來源與目標檢查點 ${s \rightarrow t}$ 的 Casper FFG 投票。

一個連結 ${s \rightarrow t}$ 是一個_超級多數連結_（supermajority link），當超過 $\frac{2}{3}$ 的驗證者（依質押加權）已發布相同的連結（並讓它們的票及時被納入區塊）時。

#### Casper FFG 的運作機制

有了（大部分的）術語與關鍵概念墊底，我們現在可以詳細看 Casper FFG 如何運作。它相當直截了當。

##### 證成

當一個節點看到一個從已證成檢查點 $c_1$ 連到檢查點 $c_2$ 的超級多數連結時，它就把檢查點 $c_2$ 視為_已證成_。

<a id="img_consensus_justified"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示一個超級多數連結證成了一個檢查點。](images/diagrams/consensus-justified.svg)

<figcaption>

我的節點已看到一個超級多數連結 ${C_N \rightarrow C_{N+2}}$，因此我把 $C_{N+2}$ 標記為已證成。已證成的檢查點以斜線填滿並標記「J」。

</figcaption>
</figure>

證成意味著：我已看到超過 $\frac{2}{3}$ 的驗證者集合所做出的承諾——只要它們得到至少 $\frac{2}{3}$ 的驗證者「同樣不會回退 $c_2$」的確認，它們就不會回退檢查點 $c_2$。

##### 最終確定

當一個節點看到一個從已證成檢查點 $c_1$ 連到檢查點 $c_2$ 的超級多數連結，而且檢查點 $c_2$ 是 $c_1$ 的直接子檢查點時，它就把檢查點 $c_1$ 視為_已最終確定_。

換句話說，一個已最終確定的檢查點，就是一個「其直接子檢查點已被證成」的已證成檢查點。

<a id="img_consensus_finalised"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示當一個已證成檢查點的直接子檢查點被證成時，該父檢查點就被最終確定。](images/diagrams/consensus-finalised.svg)

<figcaption>

我的節點已看到一個超級多數連結 ${C_N \rightarrow C_{N+1}}$，因此我把 $C_{N+1}$ 標記為已證成。由於在檢查點樹中 $C_{N+1}$ 是 $C_N$ 的直接子檢查點，我也把 $C_N$ 標記為已最終確定。已最終確定的檢查點以交叉斜線填滿並標記「F」。

</figcaption>
</figure>

最終確定意味著：我已看到超過 $\frac{2}{3}$ 的驗證者所給的確認——它們已看到超過 $\frac{2}{3}$ 的驗證者所做出「它們不會回退檢查點 $c_1$」的承諾。檢查點 $c_1$ 現在已無法被回退，除非至少 $\frac{1}{3}$ 的驗證者可被證明地改變了心意，因而遭到罰沒。

上述最終確定一個檢查點的規則，就是最初 Casper FFG 論文所描述的那一條。在實務上，我們可以使用這條規則的一個輕微推廣形式，而不影響[安全性證明](#proof-of-accountable-safety)。這個推廣形式稱為 [k-最終性](#k-finality)，我們稍後會看它。

##### Casper 誡命

在 Casper FFG 論文中，每個檢查點都有一個既定的高度：如果 $c$ 是一個檢查點，那麼 $h(c)$ 就是那個檢查點的高度。檢查點高度隨著與創世區塊的距離而單調遞增。

在 Eth2 對 Casper FFG 的實作中，檢查點高度就是該檢查點的紀元編號：$h(c) = \texttt{c.epoch}$。回想一下，一個檢查點同時由一個區塊雜湊與一個紀元編號構成。只要這兩者中有任一者不同，那兩個檢查點就是不同的。

Casper FFG 對可問責安全性的證明，依賴於「任何違反下列兩條規則（或稱「誡命」）中任一條的驗證者都會被罰沒」。

###### 不可雙重投票

**誡命 1**：驗證者不得發布兩份不同的投票 ${s_1 \rightarrow t_1}$ 與 ${s_2 \rightarrow t_2}$，使得 $h(t_1) = h(t_2)$。

簡單地說，驗證者對任何目標紀元至多只能投一票。

<a id="img_consensus_commandment_1a"></a>
<figure class="diagram" style="width: 60%">

![一張示意圖，顯示違反不可雙重投票規則的一種方式：從不同的來源檢查點為同一個目標檢查點投票。](images/diagrams/consensus-commandment-1a.svg)

<figcaption>

違反不可雙重投票規則的一種方式：從不同的來源檢查點為同一個目標檢查點投票：${0 \rightarrow 3}$ 與 ${1 \rightarrow 3}$。

</figcaption>
</figure>

<a id="img_consensus_commandment_1b"></a>
<figure class="diagram" style="width: 60%">

![一張示意圖，顯示違反不可雙重投票規則的另一種方式：為不同分支上、位於同一高度的目標檢查點投票。](images/diagrams/consensus-commandment-1b.svg)

<figcaption>

違反不可雙重投票規則的另一種方式：在同一個紀元為不同的目標檢查點投票：${0 \rightarrow 3}$ 與 ${0 \rightarrow 3'}$。

</figcaption>
</figure>

###### 不可包圍投票

**誡命 2**：驗證者不得發布兩份不同的投票 ${s_1 \rightarrow t_1}$ 與 ${s_2 \rightarrow t_2}$，使得 $h(s_1) < h(s_2) < h(t_2) < h(t_1)$。

也就是說，驗證者不得做出這樣一票：它的連結要嘛包圍、要嘛被包圍於它先前所投的某個連結。

<a id="img_consensus_commandment_2a"></a>
<figure class="diagram" style="width: 60%">

![一張示意圖，顯示在單一分支上違反不可包圍投票規則。](images/diagrams/consensus-commandment-2a.svg)

<figcaption>

違反不可包圍投票規則的一種方式：連結 ${0 \rightarrow 3}$ 包圍了連結 ${1 \rightarrow 2}$。

</figcaption>
</figure>

<a id="img_consensus_commandment_2b"></a>
<figure class="diagram" style="width: 60%">

![一張示意圖，顯示在相衝突的分支上違反不可包圍投票規則。](images/diagrams/consensus-commandment-2b.svg)

<figcaption>

違反不可包圍投票規則的另一種方式：同樣地，連結 ${0 \rightarrow 3}$ 包圍了連結 ${1 \rightarrow 2}$，儘管是在不同的分支上。

</figcaption>
</figure>

關於上述第二種情況何時變得重要的一個例子，請見 [Holešky Pectra 事件](https://github.com/ethereum/pm/blob/master/Pectra/holesky-postmortem.md)的復原工作。在這次測試網事件中，管理超級多數質押的客戶端成功證成了一個無效的區塊，也就是圖中下方分支上的「Epoch 1」檢查點，而少數正確的客戶端則繼續在上方分支上前進。要把出錯的客戶端復原到好的鏈上，迫使它們做出包圍投票，因而被罰沒。

##### 罰沒

任何違反 Casper 誡命中任一條的驗證者，都會面臨被罰沒的處置。這意味著它的部分或全部質押被扣除，並且它被逐出驗證者集合。

罰沒藉由為壞行為——具體而言，是可能導致相衝突檢查點被最終確定的行為——標上代價，來支撐 Casper 可問責安全性的保證。罰沒在 LMD GHOST 中也[有出現](/part2/consensus/lmd_ghost/#slashing-in-lmd-ghost)，而[激勵層一章](/part2/incentives/slashing/)有更多關於罰沒詳細運作機制的資訊。

對誡命的違反，有可能難以在協定內偵測。尤其，偵測包圍投票可能需要搜尋一段相當可觀的驗證者先前投票歷史[^fn-proto-surround-vote]。基於這個原因，我們依賴外部的罰沒偵測服務[^fn-slasher-implementations]來偵測對罰沒條件的違反，並把證據提交給區塊提議者。網路上只需要有一個這樣的服務，只要它可靠就行。實務上我們有更多個，但絕對沒有必要讓每個節點營運者都運行一個罰沒偵測器。

一旦找到了違反某條誡命的證據，要在鏈上證明該驗證者違反了規則就很容易。驗證者為它們發布的每一份證明簽章，所以給定兩份相衝突的證明，要驗證它們的簽章並顯示該驗證者在發布它們時違反了規則，就是[一件簡單的事](/part3/transition/block/#attester-slashings)。

[^fn-proto-surround-vote]: 關於尋找包圍投票之難處的一些分析，請見 Protolambda 的 [`eth2-surround`](https://github.com/protolambda/eth2-surround) GitHub 儲存庫。

[^fn-slasher-implementations]: 罰沒偵測軟體已由 [Lighthouse 團隊](https://lighthouse-book.sigmaprime.io/advanced_slasher.html)與 [Prysm 團隊](https://prysm.offchainlabs.com/docs/configure-prysm/slasher/)所打造。

Casper FFG 論文中所呈現的協定假設：在被證明違反了某項罰沒條件時，「該驗證者的全部存款都會被取走」。我們為 Eth2 實作了[這個做法的一個變體](/part2/incentives/slashing/#the-correlation-penalty)，它讓「驗證者質押中被沒收的比例」與「給定期間內被罰沒之質押總額」成比例地縮放。如果在一個 36 天的窗口內，全部質押的 $\frac{1}{3}$ 違反了罰沒條件，那麼就會像古典 Casper FFG 協定那樣，整筆質押都被沒收。但如果在那個窗口內其他的罰沒非常少，那麼幾乎不會有質押被沒收。至少自從信標鏈的 [Bellatrix 升級](/part4/history/bellatrix/)賦予了 [`PROPORTIONAL_SLASHING_MULTIPLIER`](/part3/config/preset/#proportional_slashing_multiplier) 常數它的最終值以來，這個巧妙之處在實務上並不改變 Casper FFG 的保證。

##### 分叉選擇規則

Casper FFG 的分叉選擇規則，其形式是對底層共識機制之分叉選擇規則的一項修改。依 Casper FFG 論文，底層的共識機制必須：

> 跟隨包含高度最高之已證成檢查點的那條鏈。

純粹的 [LMD GHOST](/part2/consensus/lmd_ghost/) 協定，總是從鏈的根部——即創世區塊——開始它對鏈頭區塊的搜尋。被 Casper FFG 的分叉選擇規則修改之後，LMD GHOST 會從它所知道的最高已證成檢查點開始它對鏈頭區塊的搜尋，並忽略那些並非衍生自最高已證成檢查點的潛在鏈頭區塊。等我們講到 [Gasper](/part2/consensus/gasper/) 時，會更深入地討論這一點。

對底層共識協定之分叉選擇規則所做的這項修改，正是賦予最終性的東西。當一個節點在它的局部視角中證成了一個檢查點時，它就承諾永不回退它。因此，底層的鏈必須永遠包含那個檢查點；所有不包含那個檢查點的分支都必須被忽略。

請注意，這條分叉選擇規則與 Casper FFG 的[似真活躍性](#plausible-liveness)保證是相容的。

#### Casper FFG 的保證

Casper FFG 共識協定做出兩項保證，它們類比於、但不同於古典共識中安全性與活躍性的概念：可問責的安全性，以及似真活躍性（plausible liveness）。

##### 可問責的安全性

古典 PBFT 共識只有在少於三分之一的驗證者具對抗意圖（故障）時，才能保證安全性。如果超過三分之一具對抗意圖，它就完全不做出任何承諾。

當控制少於三分之一質押的驗證者具對抗意圖時，Casper FFG 帶有本質上相同的安全性保證：已最終確定的檢查點將永不被回退。此外，它還提供進一步的保證：萬一相衝突的檢查點被最終確定，代表至少三分之一質押以太幣的驗證者將被罰沒。這稱為「可問責的安全性」。它之所以可問責，在於我們能精確地辨識出哪些驗證者行為不良，並直接懲罰它們。

這項保證所提供的額外安全性，並不是共識協定通常意義下的安全性，而是一種特別具加密經濟性質的安全性：壞行為被協定大力地反向激勵。它常被稱為「經濟性最終性」。

###### 可問責安全性的證明

Casper FFG 可問責安全性的證明相當直覺。我會在下面大致按照 Casper FFG 論文所呈現的方式勾勒這個證明，但改用紀元，而非論文所使用的較抽象的「檢查點高度」。

我們將證明：如果少於 $\frac{1}{3}$ 的驗證者（依質押加權）違反某條 [Casper 誡命](#the-casper-commandments)，那麼兩個相衝突的檢查點就不可能都被最終確定。我們會藉由顯示「一個相衝突檢查點能被最終確定的唯一途徑，是存在一個被另一個超級多數連結所包圍的超級多數連結」來做到這一點，而那與本段開頭的假設相矛盾，因為包圍投票違反了[第二誡命](#no-surround-vote)。

我們會需要的第一個方便的觀察是：在這個假設下，任何紀元中至多只能有一個檢查點被證成（在誠實節點的視角中）。這直接由不可雙重投票誡命推得。

讓我們取兩個相衝突的已最終確定檢查點 $a_m$ 與 $b_n$，分別位於紀元 $m$ 與 $n$。由於這兩個檢查點相衝突，兩者都不是對方的後代。由前一個觀察，我們知道 $m \ne n$。不失一般性，我們取 $m < n$，於是 $b_n$ 是較高的那個已最終確定檢查點。

現在，必定存在一連串連續的已證成檢查點，從根檢查點通向 $b_n$，它們之間有超級多數連結。也就是說，存在一個由 $k$ 個超級多數連結構成的集合 $\{{r \rightarrow b_{i_1}},\allowbreak {b_{i_1} \rightarrow b_{i_2}},\allowbreak {b_{i_2} \rightarrow b_{i_3}},\allowbreak \ldots,\allowbreak {b_{i_{k-1}} \rightarrow b_{i_k}}\}$，其中 $i_k = n$。這由證成的定義推得。於是，通向 $b_n$ 的已證成檢查點集合為 $\mathcal{B} = \{r, b_{i_1},\allowbreak b_{i_2}, b_{i_3},\allowbreak \ldots,\allowbreak b_{i_{k-1}}, b_{i_k}\}$。我們可以想像從根部沿著超級多數連結跳躍，在跳到下一個之前先落在這些檢查點的每一個上。

<a id="img_consensus_justification_chain"></a>
<figure class="diagram" style="width: 85%">

![一張示意圖，顯示一連串已證成檢查點，由從根部一路到一個已最終確定區塊的連續超級多數連結串接而成。](images/diagrams/consensus-justification-chain.svg)

<figcaption>

對於任何已最終確定的檢查點，例如 $b_{10}$，都存在一條連續的超級多數連結鏈，從根部 $r$ 通向它。此處的這條連結鏈證成了檢查點集合 $\mathcal{B} = \{r, b_1,\allowbreak b_4, b_5,\allowbreak b_9, b_{10}\}$。有陰影的檢查點是已證成的（也可能是已最終確定的）；交叉斜線填滿的檢查點是已最終確定的（也標記「F」）。

</figcaption>
</figure>

現在考慮相衝突的已最終確定檢查點 $a_m$。由最終確定的定義，必定存在一個從 $a_m$ 連到下一個紀元中 $a_{m+1}$ 的超級多數連結 ${a_m \rightarrow a_{m+1}}$。顯然 $a_m$ 與 $a_{m+1}$ 都不在集合 $\mathcal{B}$ 中，因為那會使 $a_m$ 成為 $b_n$ 的祖先而不相衝突。此外，集合 $\mathcal{B}$ 不含任何檢查點 $b_m$ 或 $b_{m+1}$，因為一個紀元中我們只能有一個已證成的檢查點。

有了這些觀察，這對檢查點 $(a_m, a_{m+1})$ 必然落在 $\mathcal{B}$ 中兩個連續元素——比方說 $b_{i_{j-1}}$ 與 $b_{i_j}$——的紀元之間。也就是說，存在一個 $j$ 使得 $i_{j-1} < m < m+1 < i_j$。

最後，我們可以看出必定存在一個_包圍_了超級多數連結 ${a_m \rightarrow a_{m+1}}$ 的超級多數連結 ${b_{i_{j-1}} \rightarrow b_{i_j}}$。除非至少 $\frac{1}{3}$ 的驗證者違反了第二條 Casper 誡命，否則包圍的連結或被包圍的連結就無法存在，而我們已假設它們並未違反。

因此，我們已（用反證法）證明了：如果少於 $\frac{1}{3}$ 的驗證者（依權重）違反某條 Casper 誡命，那麼兩個相衝突的檢查點就不可能都被最終確定。

<a id="img_consensus_conflicting_finalised"></a>
<figure class="diagram" style="width: 85%">

![一張示意圖，顯示最終確定一個相衝突的檢查點必定牽涉一次包圍投票。](images/diagrams/consensus-conflicting-finalised.svg)

<figcaption>

假設一個較早的、相衝突的檢查點 $a_6$ 被最終確定。最終確定意味著必定存在一個超級多數連結 ${a_6 \rightarrow a_7}$。$b$ 鏈上的某個超級多數連結——在這個例子中是 ${b_5 \rightarrow b_9}$——必定橫跨 ${a_6 \rightarrow a_7}$。

</figcaption>
</figure>

在這個證明中，我們依賴的最終確定定義是：存在一個從「正被最終確定的檢查點」連到「緊接著的下一個紀元中之檢查點」的超級多數連結。結果我們可以把那個定義稍微放寬一點，以 $k$-最終性的形式來計算最終性。我們會在[下文](#k-finality)討論這一點。

###### 經濟性最終性

可問責安全性的證明立基於下列各點成立：

1. 不存在兩個目標為「同一高度上不同檢查點」的超級多數連結，以及
2. 不存在使得「其一包圍另一」的兩個超級多數連結。

這些條件由兩條 [Casper 誡命](#the-casper-commandments)強制執行。由於一個超級多數連結需要 $\frac{2}{3}$ 驗證者（依質押）的支持，如果存在兩個違反這些規則之一的超級多數連結，那麼必定有至少 $\frac{1}{3}$ 的驗證者為這兩個連結都投了票。也就是說，至少 $\frac{1}{3}$ 的驗證者做出了一次[雙重投票](#no-double-vote)或一次[包圍投票](#no-surround-vote)。

如我們[已經看到](#slashing)的，任何違反某條誡命的驗證者都會面臨被罰沒的處置，也就是被扣除全部或部分質押，並被逐出驗證者集合。因此，萬一發生相衝突的最終確定，我們就有保證：質押以太幣中至少 $\frac{1}{3}$ 將被罰沒。

如此一來，罰沒就為攻擊鏈標上了代價，並為「成功攻擊鏈」標上一筆龐大（且可計算）的代價[^fn-current-cost-of-attack]。如 Vitalik 所[言](https://medium.com/@VitalikButerin/minimal-slashing-conditions-20f0b500fc6c)：

> 基本上，如果一個區塊被最終確定了，那麼那個區塊就是鏈的一部分，而要造成那一點改變是非常、非常昂貴的。

[^fn-current-cost-of-attack]: 截至 2025 年 7 月，信標鏈上質押了 3570 萬 ETH，所以一次最終性回退會導致至少 1190 萬 ETH 被罰沒。以當時的價格計算，這相當於超過 350 億美元、用以對抗回退的經濟性安全保障。

我們把這稱為「經濟性最終性」。它不是由軟體所強制執行的最終性，而是由一次攻擊的代價所強制執行的最終性。驗證者的質押是一份「良好行為保證金」，一旦被證明它們違反了協定的規則，這份保證金就可以從它們手中被取走。驗證者以它們用來為所有訊息簽章的祕密金鑰為形式，擁有獨一無二的身分，所以要追究個別驗證者的責任、並非常具針對性地懲罰它們，是有可能的。

你或許會納悶，我們究竟為什麼需要經濟性最終性這樣的概念。畢竟，PBFT 沒有這樣一個構造也能交付最終性。協定難道不能就乾脆拒絕最終確定一個相衝突的檢查點嗎？

差別在於，PBFT 享有一個硬性安全假設這份奢侈：少於三分之一的驗證者具對抗意圖。同樣地，在 Casper FFG 中，一個擁有少於三分之一質押的對手無法最終確定相衝突的檢查點。然而，在無須許可的區塊鏈世界裡，對於「超過三分之一質押具對抗意圖」的情況，我們必須有某種防禦。那個防禦就是罰沒，它給了我們經濟性最終性的保證：如果超過三分之一的驗證者願意行為不良，我們無法阻止它們最終確定相衝突的檢查點，但我們可以為這麼做標上一筆龐大的代價。[^fn-economic-finality-pow]

[^fn-economic-finality-pow]: 這在概念上與在工作量證明中發動 51% 攻擊的代價有些相似。只不過，在 PoW 中，一次成功攻擊的代價可以是零，因為攻擊者獲得全部的區塊獎勵，而且這場攻擊可以用同一套硬體無限次重複。罰沒所提供的經濟性最終性要高得多。以 Vlad Zamfir 的名言來說，被罰沒「就好比你若參與了一次 51% 攻擊，你的 ASIC 礦場就燒個精光」。

在一篇部落格文章[《論結算最終性》](https://blog.ethereum.org/2016/05/09/on-settlement-finality)中，Vitalik 是這麼說的：

> 我們無法保證「X 永遠不會被回退」，但我們_能_保證一個稍弱的主張：「要嘛 X 永遠不會被回退，要嘛一大群驗證者會自願摧毀他們自己數百萬美元的資本」。

面對一個擁有超過三分之一質押的攻擊者以及一個非同步的網路，讓驗證者單純地在協定內拒絕最終確定相衝突的檢查點，是沒有用的。能夠最終確定相衝突檢查點的攻擊，仰賴的是把誠實驗證者的集合分區，使它們看不到彼此的票，也不知道另一側最終確定了什麼。在這類強大攻擊的威脅之下，經濟性最終性是一項強而有力的安全性保證。萬一發生相衝突的最終確定，最終的補救之道是人為介入。如 Vitalik 在同一篇文章中所觀察到的：「圍繞某項鏈上資產的使用者社群，大可以單純地運用常識，來判斷哪一個分叉並非攻擊、並且實際上代表了當初被一致同意為已最終確定的那些交易的結果」。

##### 似真活躍性

Casper FFG 本身並不提供古典意義下的活躍性，也就是確保使用者的交易被納入鏈上。所有的區塊產生與鏈的建構，都是底層共識機制的責任，在我們的情況中就是 LMD GHOST。

然而，在某種意義上我們確實希望 Casper FFG 是活躍的：只要至少三分之二的驗證者誠實，我們就總是希望能夠繼續證成並最終確定檢查點，而不會有任何那些驗證者遭到罰沒。反過來說，我們絕不希望落入這樣的僵局：不讓誠實的驗證者被罰沒，就無法最終確定一個新的檢查點。這符合活躍性「好事終究會發生」的[定義](/part2/consensus/preliminaries/#safety-and-liveness)。

以 [Vitalik 的話](https://medium.com/@VitalikButerin/minimal-slashing-conditions-20f0b500fc6c)來說：

> 似真活躍性基本上意味著「演算法不應有可能『卡住』而完全無法最終確定任何東西」。

更正式地說，引用 Casper 論文：

> 只要存在能延伸已最終確定之鏈的子區塊，就總是可以加入超級多數連結來產生新的已最終確定檢查點。

證明是這樣進行的。會有一個既有的最高已證成檢查點 $a$，而會有一個位於相同高度或更高（不一定衍生自 $a$）的檢查點 $b$，它是「任何驗證者曾為之做出目標投票」的最高檢查點。

設 $c$ 是位於紀元 $h(b) + 1$（也就是緊接在 $b$ 之後的那個紀元）、衍生自 $a$ 之鏈上的一個檢查點。

所有驗證者都可以為連結 ${a \rightarrow c}$ 投票而不必擔心被罰沒，因為：(1) 它不可能是雙重投票，因為先前沒有任何驗證者以目標 $h(c)$ 投過票；(2) 它不可能是包圍投票，因為先前沒有任何誠實的驗證者使用過高於 $h(a)$ 的來源，它也不可能是被包圍的投票，因為現有的連結都沒有高於 $h(b)$ 的目標。

<a id="img_consensus_plausible_liveness"></a>
<figure class="diagram" style="width: 65%">

![一張示意圖，顯示我們總能找到一個衍生自最高已證成檢查點、且能在不違反誡命的情況下被最終確定的檢查點。](images/diagrams/consensus-plausible-liveness.svg)

<figcaption>

為連結 ${a \rightarrow c}$ 投票是安全的，因為 (1) 先前沒有人以 $c$ 為目標投過票，因為到目前為止 $b$ 擁有最高的目標投票，並且 (2) 它不可能包圍另一個連結，因為沒有比 $a$ 更高的已證成檢查點可用作來源投票。

</figcaption>
</figure>

因此我們可以證成檢查點 $c$。接著，顯然所有驗證者都可以安全地投票 ${c \rightarrow d}$，其中 $d$ 是 $c$ 的直接子檢查點，於是我們就能在不違反任一條誡命的情況下最終確定 $c$。

這項對似真活躍性的要求，支撐著 Casper FFG 的[分叉選擇規則](#fork-choice-rule)：底層的共識機制必須跟隨包含高度最高之已證成檢查點的那條鏈。只要底層的鏈持續建構在最高已證成檢查點之上，那麼根據這個證明，我們就保證能在它上面持續最終確定檢查點，而不會有任何人被罰沒。

#### 練習

作為一段插曲，把 Casper FFG 可能有的各種行為方式想過一遍，是個既有趣又有用的練習。

例如，像下面這張圖這樣的情況可能如何發生？也就是超級多數連結持續不斷地跳過檢查點，導致一串已證成的檢查點，卻沒有一個被最終確定。

<a id="img_consensus_exercise_0"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示一條已證成檢查點鏈，其超級多數連結持續不斷地跳過一個檢查點。](images/diagrams/consensus-exercise-0.svg)

<figcaption>

總在證成卻從不最終確定。我們怎麼會落入這樣的情況？

</figcaption>
</figure>

答案在[下方](#answer-to-the-exercise)，但請花點時間把可能導致這種情況的種種狀況想過一遍。

#### Casper FFG 雜項

##### 激勵

在 LMD GHOST 中，我們看到「在下一個時段被納入某個區塊」的正確鏈頭投票會收到一份獎勵。但對於遲到或不正確的鏈頭投票並沒有懲罰。

在 Casper FFG 的實作中，獎勵與懲罰稍微複雜一些。驗證者[有充分的誘因](/part2/incentives/rewards/#introduction)去做出準確且及時的 Casper FFG 投票：驗證者潛在質押獎勵中有 22% 來自來源投票，41% 來自目標投票。此外，不準確或遲到的來源或目標投票，會被處以與獎勵等額的懲罰。

要拿到任何 Casper FFG 獎勵，驗證者的來源投票都必須正確。也就是說，它必須與最終正典鏈所收斂到的歷史相符。如果來源投票不正確，那麼就彷彿該驗證者根本沒有投票，它會因為錯失來源與目標兩者而收到完整的懲罰。這麼做的理由是：來源錯誤意味著它一直在一條與「最終成為正典的那條」不同的分支上下工夫。因此它的投票是在與共識競爭，而不是在支持共識。

要收到來源投票獎勵，來源投票必須正確，而且還必須及時。如果驗證者的投票在五個時段內被納入某個區塊，那麼它就收到來源投票獎勵，否則它會收到一筆等額的懲罰。關於這五個時段限制之原因的一些討論，見[註解規格](/part2/incentives/rewards/#timeliness)。

要收到目標投票獎勵，目標投票必須正確，而且還必須及時。如果驗證者的投票在三十二個時段內被納入某個區塊，那麼它就收到目標投票獎勵，否則它會收到一筆等額的懲罰[^fn-deneb-change-to-target-inclusion-time]。

[^fn-deneb-change-to-target-inclusion-time]: 這在 Deneb 升級時將[被改變](https://github.com/ethereum/consensus-specs/pull/3360)。對當前或前一個紀元的目標投票都會有效，而不再於 32 個時段後失效。

註解規格有一份[完整矩陣](/part2/incentives/penalties/#penalties-rewards-table)，列出不同程度的投票正確性與時效性所對應的獎勵與懲罰。

##### 動態驗證者集合

在以上的一切中，我們都是就一個靜態的驗證者集合來討論 Casper FFG，假設沒有驗證者進入或退出協定。這並不完全符合現實，因為我們希望能夠迎入新的質押者，並允許質押者退出。

Casper FFG 論文討論了「當驗證者集合逐紀元變動時，可問責的安全性如何能夠維持」。它以前向與後向驗證者集合的角度來分析這一點。以太坊 2.0 中的實作忽略了這個機制，改而藉由嚴格地限制驗證者啟用與退出的速率來繞過它。每個紀元，我們允許的驗證者啟用與停用，其數量約佔完整驗證者集合的 0.0015%（見 [`CHURN_LIMIT_QUOTIENT`](/part3/config/configuration/#validator-cycle)）。

這個簡化的效果在 [Gasper 論文](https://arxiv.org/pdf/2003.03052.pdf)第 8.6 節有所分析。藉由限制進入與退出的速率、卻不考量前向與後向驗證者集合，我們在比例上稍微降低了可問責安全性的水準。也就是說，萬一最終確定一個相衝突的檢查點，有可能略少於三分之一的質押被罰沒。具體而言，如果兩個相衝突的已最終確定檢查點之紀元之間的驗證者集合，相差一個質押數額 $\varepsilon$，那麼經濟性最終性（會被罰沒的最低質押量）就會變成 $\frac{2}{3} - \varepsilon$ 而非 $\frac{2}{3}$。實務上，驗證者集合變動的速率限制如此嚴格，以致這個差異微不足道。

##### k-最終性

最初的 Casper 論文要求：要最終確定一個檢查點，我們必須有一個從該檢查點連到它直接後代的超級多數連結。結果我們可以把這一點推廣，而不影響安全性證明的有效性。

安全性證明所依賴的關鍵觀察，是「在 $\mathcal{B}$ 的兩個連續成員之間，存在一個橫跨『最終確定 $a_m$ 的超級多數連結 ${a_m \rightarrow a_{m+1}}$』的超級多數連結」。然而，如果存在一個超級多數連結 ${a_m \rightarrow a_{m+k}}$，其中 $a_m$ 與 $a_{m+k}$ 之間的所有檢查點都在 $a$ 分支上被證成，那麼 $b$ 分支上那個包圍的連結仍然必定存在。這是因為，若情況如此，$\mathcal{B}$ 就不可能在紀元 $m$ 到 $m+k$ 之間有成員。

<a id="img_consensus_k_finality_proof"></a>
<figure class="diagram" style="width: 85%">

![一張示意圖，顯示我們可以用一個橫跨多個連續已證成檢查點的超級多數投票，安全地最終確定一個檢查點。](images/diagrams/consensus-k-finality-proof.svg)

<figcaption>

如果我們在「存在一個從某檢查點出發、只跳過已證成檢查點的超級多數連結」時最終確定該檢查點，那麼可問責安全性證明的種種保證全都延續成立。此處，$a_5$ 與 $a_6$ 已被證成，所以我們可以用超級多數連結 ${a_4 \rightarrow a_7}$ 安全地最終確定 $a_4$。

</figcaption>
</figure>

所以，我們推廣後的最終性規則是：當我們有一個超級多數連結 ${a_m \rightarrow a_{m+k}}$，並且檢查點 $a_{m+1}$、$a_{m+2}$、$\ldots$、$a_{m+k-1}$ 全都已被證成時，我們就可以最終確定檢查點 $a_m$。

這稱為 $k$-最終性，在 [Gasper 論文](https://arxiv.org/pdf/2003.03052.pdf)第 4.5 節有所討論。

計算最終性時，一個人可能想考慮多少個檢查點 $k$，取決於他願意做多少記錄工作。在以太坊&nbsp;2.0 信標鏈上，我們採用了 $2$-最終性：我們為四個連續紀元保留一份證成狀態的記錄，並允許處理兩個紀元的目標投票（更舊的目標投票被視為無效）。

<a id="img_consensus_2_finality"></a>
<figure class="diagram" style="width: 65%">

![一張示意圖，顯示 2-最終性的四種情境。](images/diagrams/consensus-2-finality.svg)

<figcaption>

2-最終性的四種情況。在每種情況中，超級多數連結都使其起點的檢查點（來源）變成已最終確定，並使其終點的檢查點（目標）變成已證成。情況 2 與情況 4 是古典的 1-最終性。檢查點編號標在底部。

</figcaption>
</figure>

幾乎在所有情況下，我們都會預期只看到 $1$-最終性的情況，尤其是情況 4。$2$-最終性的情況只會在「許多證明被延遲」、或「我們非常接近三分之二參與門檻」的狀況下發生。請注意，這些評估是可疊加的，所以舉例來說，有可能規則 2 最終確定 $C_{n-2}$，接著規則 4 立即最終確定 $C_{n-1}$。

這一切的詳細運作機制，在紀元處理期間於 [`weigh_justification_and_finalization()`](/part3/transition/epoch/#def_weigh_justification_and_finalization) 函式中執行[^fn-danny-k-finality-video]。

[^fn-danny-k-finality-video]: Danny Ryan 在 Devcon V 的[這段影片](https://www.youtube.com/watch?v=N5DdClfLQfw&t=601s)中簡短地討論了 $k$-最終性。

##### 為什麼是三分之二？

最終確定所用的 $\frac{2}{3}$ 多數門檻從何而來？這其實[並不顯而易見](https://ethresear.ch/t/latest-casper-basics-tear-it-apart/151/58?u=benjaminion)，我們本可以選一個不同的值來定義超級多數連結。我們把這個門檻稱為 $p$：如果驗證者集合中比例為 $p$ 的部分投票要最終確定一個檢查點，那麼它就被最終確定。

我們試圖在兩個因素之間取得平衡。一方面，比例為 $1-p$ 的具對抗意圖或故障的驗證者，可以阻止最終性，這是一種活躍性失敗。

另一方面，我們想最大化最終確定的可問責安全性。也就是「為了最終確定相衝突的檢查點而必須含糊其辭」的質押比例。這個比例是 $2p-1$。

在這些約束下，設 $p = \frac{2}{3}$ 既最大化了對活躍性攻擊的容錯——少於三分之一的驗證者無法阻止最終確定——同時也最大化了對安全性故障的容忍——萬一相衝突的區塊被最終確定，至少三分之一的驗證者會被罰沒。

<a id="img_consensus_two_thirds"></a>
<figure class="diagram" style="width: 40%">

![一張圖表，顯示活躍性容錯與安全性容錯之間的取捨。](images/diagrams/consensus-two-thirds.svg)

<figcaption>

同時最大化可問責安全性與活躍性故障容忍度的門檻是 $p = \frac{2}{3}$。

</figcaption>
</figure>

Vitalik 在[《最小罰沒條件》](https://medium.com/@VitalikButerin/minimal-slashing-conditions-20f0b500fc6c#44b0)一文的註腳 2 中就此寫了一些筆記。

##### 如何不被罰沒

兩條 Casper 誡命相當簡單，而避免被罰沒在原則上很直截了當：別違反規則就是了。

到目前為止，驗證者被罰沒最常見的原因，是它們的祕密簽章金鑰同時在不同的節點上運行。如果這些節點對網路的看法有任何分歧——例如，由於某個檢查點區塊被其中一個節點遲遲才看到、卻沒被另一個看到——那麼該驗證者的每個實例，就可能最終為同一個紀元簽下不同的票，違反第一條誡命。

避免這件事的基本辦法，就是別那麼做。任何時候都只在一個地方運行你的金鑰。客戶端軟體實作往往會提供諸如[分身偵測](https://docs.teku.consensys.net/how-to/enable-doppelganger-detection)（doppelganger detection）這類防禦機制，以協助保護質押者不至於無意中這麼做。分身偵測會在開始為證明簽章之前先等候幾個紀元；如果在這段期間它看到鏈上有來自另一個使用相同金鑰之實例的簽章，它就拒絕啟動。另一種做法是把投票的簽章工作委派給一個中心化的簽章器，它維護一份你的驗證者過往投票的資料庫，並會拒絕簽署任何違反誡命的東西。[Web3Signer](https://docs.web3signer.consensys.net/) 就是這樣的一個簽章服務。

在罕見的情況下，即使是驗證者的單一一個實例，也有可能陷入它會做出可罰沒證明的處境。例如，假如主機的時鐘在時間上往回跳。或者當鏈上發生一次大於一個紀元的長回退時，驗證者的職責可能被重新計算。它可能發現自己由於舊的職責已在該紀元投過一次票，然後它新的職責又要求它在該紀元稍後再投一次票，這就會導致一次可罰沒的雙重投票。

基於這類原因，所有客戶端軟體都包含罰沒保護機制。不同的客戶端採取不同的做法，但對於罰沒保護資料，有一個經一致同意的共同交換格式 [EIP-3076](https://eips.ethereum.org/EIPS/eip-3076)，可在必要時用於客戶端之間的遷移。Teku 對此採取一種非常穩健、極簡的做法。對於 Teku 節點所管理的每個驗證者，它[維護一個文字檔](https://docs.teku.consensys.net/concepts/slashing-protection#validator-slashing-protection-file)，記下該驗證者迄今最高來源投票與最高目標投票的紀元編號。一份新的證明要能被簽署，它的來源必須不低於所儲存的來源，而它的目標必須高於所儲存的目標。這就足以保證 Teku 驗證者的單一一個實例不會為同一個目標紀元做出雙重投票，也不會做出包圍投票。

##### Casper FFG 與 PBFT 的比較

如 Vitalik 所[承認](https://web.archive.org/web/2/https://nitter.it/VitalikButerin/status/1029903234226216960#m)，Casper FFG 的技術根源在於 1980 與 1990 年代發展出的古典 BFT（拜占庭容錯）共識協定。尤其，它與 1999 年發表的 PBFT（[實用拜占庭容錯](https://www.scs.stanford.edu/nyu/03sp/sched/bfs.pdf)）演算法有些相似之處。

儘管如此，Casper FFG 並不是 PBFT，兩者之間有一些顯著的差異。接下來的內容並非嚴謹的比較，但觸及了主要的幾點。

PBFT 與 Casper FFG 都是「以輪為基礎」的，並且牽涉一個兩階段提交的過程。在 Casper FFG 中，一個完整的輪是兩個紀元，但各輪是重疊的、或說是以管線方式進行的，所以某一輪的 `PREPARE` 步驟（證成）與前一輪的 `COMMIT` 步驟（最終確定）同時發生。這種重疊使 Casper FFG 得以只用一種訊息類型（一份證明），其中含有兩票（來源與目標）。古典 PBFT 仰賴副本（驗證者）廣播分開的 `PREPARE` 與 `COMMIT` 訊息，而且各輪嚴格地循序進行。

PBFT 與 Casper FFG 都以某種方式仰賴一位領導者。Casper FFG 中的領導者，是底層共識機制的區塊提議者，並預期每一輪都會更換。PBFT 中的領導者稱為主節點（primary），只有在其他副本認定它離線或故障時才會更換。PBFT 有一整套「視圖變更」（view change）機制，用以在必要時處理切換到一位新領導者。

重要的是，如果超過三分之一的驗證者離線，PBFT 會停擺，因為它將無法執行視圖變更。在這種情況下，區塊產生會完全停止，這是 PBFT 及其近親「重安全性而輕活躍性」的後果。如果超過三分之一的驗證者離線，Casper FFG 也會停擺，意思是最終確定不會往前推進。然而，沒有任何東西阻止底層的鏈繼續取得進展、並為整個系統提供活躍性。這源自 Casper FFG 作為「疊加在底層區塊提議機制之上的一層」的本質。

最後，兩者的安全性保證有所不同。PBFT 中的安全性（最終性）是這樣一項保證：當少於三分之一的副本故障時，一輪的輸出將永不被改變。當然，這一如既往地受制於社會共識。PBFT 是一個有許可的協定，落在權威證明（proof of authority）的類別。如果所有被授權的參與者串通起來更新它們的軟體，它們相當容易就能回退系統的狀態。

Casper FFG 中的安全性加上了進一步的加密經濟保證：不燒掉至少三分之一的質押，就無法最終確定一個相衝突的檢查點。這是一種大不相同的保證類型，但與以太坊權益證明協定無須許可的本質非常契合。

##### Casper 誡命是最優的嗎？

關於兩條 [Casper 誡命](#the-casper-commandments)是否理想，有一場有意思的討論可談。例如，存在一些情況——像[上文](#img_consensus_commandment_2a)所示的第一個包圍投票——它們無害，卻仍然會導致該驗證者被罰沒。Daniel Lubarov 在[一篇文章](https://ethresear.ch/t/casper-ffg-leniency-tweak/2286?u=benjaminion)中討論了另一個這樣的情境，該文提議把第二條誡命替換為：「驗證者必須被禁止在另一票的跨距之內投下一張_最終確定_票」（我們目前禁止所有被橫跨的投票）。

沿著類似的思路，Justin Drake 提出了[一條緊湊而直覺的 Casper 罰沒條件](https://ethresear.ch/t/a-tight-and-intuitive-casper-slashing-condition/3359?u=benjaminion)，把兩條誡命統一成單一一條誡命。

> 驗證者不得投下一張「跳過」（hops over）他某張最終確定票 ${\tilde{s} \rightarrow \tilde{t}}$ 的票 ${s \rightarrow t}$，亦即 $h(s) \le h(\tilde{s})$ 且 $h(t) \ge h(\tilde{t})$〔且其中目標投票相衝突〕。

Jacob Eliosoff [更進一步](https://ethresear.ch/t/simplifying-casper-votes-to-remove-the-source-param-take-two/6398?u=benjaminion)，建議我們把來源投票整個移除，並據此重新改寫罰沒規則。

雖然值得想過一遍，但我認為像這樣的提案之所以未能獲得進展，純粹是因為我們現有的東西已經夠好了，本著「沒壞就別修」的原則。在實作、分析以及形式化驗證當前版本的 Casper FFG 上已下了許多工夫，現在做出任何不能為我們帶來巨大好處（例如單時段最終性）的改變，不太可能值得那番努力。

#### 相衝突的證成

如果你想測試自己對這套分散式共識玩意兒進行推理的能力——而這並不容易——那麼把「我們為什麼同時需要『已證成』與『已最終確定』兩種狀態」想過一遍是值得的。為什麼我不能立刻把任何我已看到 $\frac{2}{3}$ 超級多數投票支持的檢查點標記為已最終確定？

關鍵的一點是：證成是一種局部的性質；最終性則是全域的。

我_證成_一個檢查點，意味著我已從 $\frac{2}{3}$ 的驗證者那裡聽到它們認為該檢查點是好的。但這只是我的局部視角，因為其他驗證者可能聽到了不同的東西——它們是否如此，我毫無頭緒。儘管如此，身為一個誠實的驗證者，我承諾永不回退任何我在自己局部視角中已證成的檢查點。

我_最終確定_一個檢查點，意味著我已從 $\frac{2}{3}$ 的驗證者那裡回頭聽到「它們已從 $\frac{2}{3}$ 的驗證者那裡聽到該檢查點是好的」。我現在知道 $\frac{2}{3}$ 的驗證者知道 $\frac{2}{3}$ 的驗證者已把那個檢查點標記為已證成，因此知道全域上有一個超級多數的驗證者已承諾永不回退它。那個檢查點在全域上已安全免於回退。

這一切都有點燒腦，所以或許最好的理解方式，是去看「如果我們不做完整的往返、不去確認『大家都確認了我所確認的東西』，事情可能會如何出錯」[^fn-blue-eyes-puzzle]。

[^fn-blue-eyes-puzzle]: 如果你_真的_想測試你對這一整套「我確認大家都確認了大家都確認了」玩意兒的理解——它正是共識安全性的核心——那麼我強烈推薦你挑戰[藍眼睛謎題](https://xkcd.com/blue_eyes.html)。我想是 Joseph Poon 在 2018 年初向我介紹這個謎題的。我足足搔了好幾個鐘頭的頭才解出來，但這番努力是值得的。解答就在外頭，但我力勸你在查閱之前先好好地對這個謎題下一番工夫。

##### 簡化模型

讓我們考慮一個極端的情況。我們有四個驗證者 $A$、$B$、$C$、$D$。它們全都是誠實的，但網路可能遭受不確定長度的延遲。為了說明的目的，我們會在每個區塊高度都設一個檢查點。我們會任意地把紀元從 $0$ 開始編號，但區塊 $0$ 並不打算是創世區塊——它可以是，但那會稍微改變接下來的描述。

###### 紀元 1——布置

<a id="img_consensus_conflicting_justification_0"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示驗證者 A 與驗證者 B、C、D 在紀元 1 中有共同的看法。](images/diagrams/consensus-conflicting-justification-0.svg)

<figcaption>

在紀元 $1$ 中，區塊 $1$ 含有足夠的票來證成檢查點 $0$。每個人都投 ${0 \rightarrow 1}$。

</figcaption>
</figure>

回想一下，只有區塊中所含的 Casper FFG 投票才會影響證成與最終確定。一開始，所有驗證者都有共同的看法。它們全都看到區塊 $1$，而它含有足夠的票來證成檢查點 $0$。到目前為止這是順利的流程。四個驗證者全都做出相同的投票 $0 \rightarrow 1$：它們的來源檢查點是 $0$，那是它們剛剛證成的；它們的目標檢查點是 $1$，即當前紀元的檢查點。這是一個超級多數投票，_理應_導向檢查點 $1$ 被所有人證成。

###### 紀元 2——不一致的證成

事情就是在這裡出錯的。在紀元 $2$，驗證者 $A$ 被選來提議，但由於某種原因，$A$ 的區塊沒有被其他人看到——它在網路上嚴重延遲了，或許是因為一次阻斷服務攻擊。因此，驗證者 $B$、$C$、$D$ 看不到它所含的、那個證成檢查點 $1$ 的超級多數連結，所以它們不知道有任何其他人喜歡檢查點 $1$。我們現在有了分裂的看法：驗證者 $A$ 已證成檢查點 $1$，並且不可撤回地對它做出承諾；其他驗證者仍認為檢查點 $0$ 是最高的已證成檢查點。

<a id="img_consensus_conflicting_justification_1"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示驗證者 A 與驗證者 B、C、D 的看法在紀元 2 中已分歧。驗證者 A 已證成檢查點 1，但其他人尚未。](images/diagrams/consensus-conflicting-justification-1.svg)

<figcaption>

在紀元 $2$，驗證者 $A$ 提議區塊 $2$。它含有全部四份 ${0 \rightarrow 1}$ 投票，但驗證者 $B$、$C$、$D$ 從未看到它。驗證者 $A$ 已看到一個超級多數連結 ${0 \rightarrow 1}$，所以它把檢查點 $1$ 標記為已證成。驗證者 $B$、$C$、$D$ 在這個紀元沒看到任何投票，它們最佳的已證成檢查點仍是 $0$。$A$ 投 ${1 \rightarrow 2}$；$B$、$C$、$D$ 投 ${0 \rightarrow X}$，其中 $X$ 是一個空檢查點。

</figcaption>
</figure>

問題的根源在於：$A$ 已看到其他每個人都同意，但其他人沒有那項同意的證據。就 $B$、$C$、$D$ 所知，每一個都是孤軍奮戰。它們別無選擇，只能暫且維持現狀，並試著在下一輪達成一致[^fn-less-contrived]。

[^fn-less-contrived]: 它們很可能已透過流言看到彼此的票，而在一個更貼近現實的模型中——每個紀元有多個區塊——它們很可能會把這些票納入後續的區塊。但這並沒有保證，而在我們這個刻意造出的、簡化的模型中，這是不可能的。

對這個例子而言並不重要，但值得一提的是：藉由證成檢查點 $1$，驗證者 $A$ 也已最終確定檢查點 $0$。驗證者 $A$ 知道檢查點 $0$ 在全域上將永不被回退，因為它知道至少 $\frac{2}{3}$ 的驗證者認為它已被證成（它們把它用作來源投票），因此無論還發生著什麼其他事，它們都將永不回退它。

至於在紀元 $2$ 的投票，驗證者 $A$ 會投 ${1 \rightarrow 2}$，而另外三個會投 ${0 \rightarrow X}$，其中 $X$ 表示它們把紀元 2 中的檢查點看成空的。我們還沒討論過空檢查點——等我們講到 Gasper 時會涵蓋它們——目前你可以這樣理解：對空檢查點 $X$ 投的票，是一項聲明：紀元 $2$ 中鏈的鏈頭仍是區塊 $1$。

###### 紀元 3——相衝突的證成

現在假設紀元 $3$ 中的區塊由 $B$、$C$、$D$ 之一所提議。它含有那三份 ${0 \rightarrow X}$ 投票，但無法含有 $A$ 的票，因為那有不同的來源。反過來，驗證者 $A$ 會認為區塊 3 是無效的，因為它含有「來源不是 $A$ 最高已證成檢查點——檢查點 $1$」的證明。在 $B$、$C$、$D$ 的看法中，那三份票足以構成一個超級多數，所以它們順理成章地證成了檢查點 $X$。

<a id="img_consensus_conflicting_justification_2"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示驗證者 A 與驗證者 B、C、D 的看法在紀元 3 中進一步分歧。驗證者 A 已證成檢查點 1，但其他人已證成紀元 2 中的一個空檢查點。](images/diagrams/consensus-conflicting-justification-2.svg)

<figcaption>

在紀元 $3$，$B$、$C$、$D$ 之一發布區塊 $3$。它含有那三份 ${0 \rightarrow X}$ 投票，所以驗證者 $B$、$C$、$D$ 有一個證成空檢查點 $X$ 的超級多數連結。驗證者 $A$ 認為區塊 $3$ 是無效的。

</figcaption>
</figure>

此時，驗證者 $A$ 的處境已無法挽回。$BCD$ 那條鏈將永不做出以檢查點 $1$ 為來源的投票，所以驗證者 $A$ 將永不認為它們的證明或它們的區塊有效，反之亦然。$A$ 的鏈上無法推進證成，因為它只看得到 $\frac{1}{4}$ 的投票權重。唯一的補救之道，是讓託管 $A$ 的節點清除它的資料庫，並重新同步到正典鏈上。屆時驗證者 $A$ 就能像平常一樣再次加入，不會有任何違反 Casper 誡命的風險[^fn-extreme-and-contrived]。

[^fn-extreme-and-contrived]: 應當體認到，這是一個相當極端、刻意造出的例子。在實務上要發生像這樣的事會非常不尋常。

請注意，我們還沒回答我們的問題。如果驗證者 $A$ 當初立刻把區塊 $1$ 標記為最終的、而不只是已證成的，那會怎樣？在這個例子裡，那不會造成實質的差別。區塊 $1$ 最終出現在由 $B$、$C$、$D$ 所推進的正典鏈中，所以把它標記為最終的本來會是沒問題的。

##### 現在加上對抗的行動

為了看出「跳過證成步驟」為何危險，我們會引入一些對抗的行動。假設 $C$ 與 $D$ 不是誠實的驗證者。

如上所述，當 $B$、$C$、$D$ 三者全都誠實行事時，在紀元 $2$ 它們會為衍生自區塊 $1$ 的空檢查點 $X$ 投票，然後在紀元 $3$ 證成它。這把它們鎖定，使它們必須把區塊 $1$ 納入它們的正典鏈，因為 Casper FFG 的分叉選擇此時阻止它們建構一條相衝突的分支。

然而，如果 $B$、$C$、$D$ 中的多數不誠實，它們可以（藉由不投票而）不去證成 $X$，並在紀元 $3$ 選擇在區塊 $0$ 上建構一條新分支，而區塊 $0$ 仍是它們最高的已證成檢查點。這麼做時，它們會把區塊 $1$ 孤立。關鍵在於，它們可以_在不違反任何罰沒規則的情況下_做到這一點。

<a id="img_consensus_conflicting_justification_3"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示不誠實的驗證者可以孤立區塊 1。](images/diagrams/consensus-conflicting-justification-3.svg)

<figcaption>

當 $B$、$C$、$D$ 中的多數不誠實時，它們可以不去證成檢查點 $X$，並建構一條把區塊 $1$ 孤立的分支。

</figcaption>
</figure>

現在我們講到重點了。如果驗證者 $A$ 當初立刻把區塊 $1$ 標記為最終的，那對任何「依賴驗證者 $A$ 的節點來取得鏈相關資訊」的應用程式或使用者而言，都會是場災難。它們本會看到一個「從未出現在由 $B$、$C$、$D$ 所維護之後續正典鏈中」的已最終確定區塊。也就是說，它們本會看到一個「已最終確定」的區塊在沒有任何罰沒的情況下被回退，違反了 Casper FFG 可問責安全性的保證。[^fn-ffg-split-views]

[^fn-ffg-split-views]: 如果我們當初假設 $C$ 與 $D$ 從一開始就受對手控制，並且對手對「$A$ 或 $B$ 之中誰看到它們的區塊」有某種掌控，那麼對手要分裂 $A$ 與 $B$ 的看法、使每一個都在不同分支上證成一個檢查點，就相當簡單。我會把展示這一點留作給讀者的練習——其流程與上文相似。

請注意，我們把這件事框定在對抗行動的角度。但實際上，要證明我們的論點，不誠實的假設_並非必要_。或許是一次網路延遲，使得來自 $C$ 與 $D$ 的紀元 $2$ 投票無法上鏈。顯然，過早最終確定的種種惡果，並不取決於「存在超過三分之一的不誠實驗證者」，而這頗為災難性。

總而言之，保證安全性的唯一辦法是透過兩階段提交。它保證一個被標記為已最終確定的區塊將永遠出現在正典鏈中，除非至少三分之一的驗證者被罰沒。

##### 總結與反思

藉由這個玩具模型，我們已看到，唯有使用兩階段提交，我們才能達成 Casper FFG 的種種保證。我們不能在看到一個超級多數連結時，跳過證成而直接走到最終確定。

即使是這個極度簡化的信標鏈模型，要對它進行推理也相當棘手。但這一切對種種事情的確認與再確認，正是分散式系統的本質所在。如果我們有一個受信任的中央權威，一切都會容易得多。例如，在一場全國領導人選舉中，我們全都投下我們的票，中央權威把它們點清並廣播結果——這是一個單輪的過程。但萬一那個中央權威結果是腐敗的，後果可能非常糟糕。兩階段提交，就是讓我們的協定不可腐化所付出的代價。

#### Casper FFG 的歷史

以太坊 2.0 權益證明共識協定的發展有一段漫長的歷史，Vitalik 在一串[推文](https://web.archive.org/web/20230630135150/https://nitter.it/VitalikButerin/status/1029900695925706753)（整理於[此處](https://hackmd.io/@liangcc/BJZDR1mIX?type=view)）中，以及在由該處連出的 Vlad Zamfir 回憶錄中，都做了非常好的總結。

其起源可遠溯至 2014 年 1 月、Vitalik 的[《Slasher：一個懲罰性的權益證明演算法》](https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm)一文。雖然 Slasher 演算法如今幾乎沒有任何部分仍在使用，它卻引入了「因違反協定規則而懲罰行為不良之驗證者」的構想，從而解決了我們在 LMD GHOST 下[討論過](/part2/consensus/lmd_ghost/#slashing-in-lmd-ghost)的無利害關係問題。罰沒為[經濟性最終性](#economic-finality)的構想鋪了路。

2015 年，Vitalik 在研究[「以下注達成共識」](https://blog.ethereum.org/2015/12/28/understanding-serenity-part-2-casper)（consensus by bet），它的一種形式在 2016 年出現在[《以太坊 2.0 淺紫皮書》](https://docs.google.com/document/d/1maFT3cpHvwn29gLvtY4WcQiI6kRbN_nbCf3JlgR3m_8/edit#heading=h.v9zt0v8gvrdh)中。他把以下注達成共識[形容](https://web.archive.org/web/20230630150818/https://nitter.it/VitalikButerin/status/1029902353703391233#m)為「一段漫長、且最終並無成果的岔路」。然而，以下注達成共識確實開創了「在一個會分叉的區塊產生機制之上、回溯性地賦予最終性」的構想，而這正是 Casper FFG 的精髓。

我們今天所擁有的 Casper FFG 機制，真正開始成形是在 2017 年，在 Vitalik [重回](https://web.archive.org/web/20230630151614/https://nitter.it/VitalikButerin/status/1029903234226216960#m)古典 PBFT 文獻之後。[後來浮現的設計](https://medium.com/@VitalikButerin/minimal-slashing-conditions-20f0b500fc6c)，在我們今天看來開始相當眼熟，雖然它還沒用「證成」這個術語，仍偏好 PBFT 的 `PREPARE` 與 `COMMIT` 用詞。它提供的一項真正新穎的特性，是透過使用罰沒條件來達成經濟性最終性。當時有四條罰沒條件，它們[後來被減為](https://web.archive.org/web/20230630153358/https://nitter.it/VitalikButerin/status/1029903583897051136#m)兩條[^fn-four-to-two-casper]，並採用[一種訊息類型](https://ethresear.ch/t/casper-ffg-with-one-message-type-and-simpler-fork-choice-rule/103?u=benjaminion)。

[^fn-four-to-two-casper]: [Casper FFG 論文](https://arxiv.org/pdf/1710.09437.pdf)的註腳四解釋了把訊息類型數量從四種減為兩種背後的思路。

Vitalik 的 Casper FFG 與 Vlad Zamfir 的 Casper CBC 共識協定，在這段期間是並肩成長的。如 Vitalik 在 2016 年 12 月一篇[部落格文章](https://blog.ethereum.org/2016/12/04/ethereum-research-update)中所描述，Casper FFG 的設計要務是「打造一個簡單的權益證明協定，它能以盡可能少的、相對於工作量證明的改變，來提供所期望的種種性質」。他把這種一貫務實的做法，與 Zamfir 那種更純粹主義式、想「從零重建共識」的渴望相對比。令人困惑的是，由此產生的兩個 Casper 協定，除了通用的權益證明事物之外幾乎沒有共通之處。儘管如此，Vitalik 偶爾仍表達一種希望：以太坊也許[最終會切換](https://www.reddit.com/r/ethereum/comments/ajc9ip/comment/eeudjjw/)到類似 Casper CBC 的東西。

[《友善最終性裝置 Casper》](https://arxiv.org/abs/1710.09437)論文的第一個版本上傳於 2017 年 10 月。它由 Vitalik 與 Virgil Griffith 撰寫，並且大致描述了我們今天所使用的方案——但須加上我們會在[下一節](/part2/consensus/gasper/)涵蓋的、為了 Gasper 所做的種種修改。

如[前文](/part2/consensus/overview/#history)所述，最初的計畫，是把 Casper FFG 當成一層疊加層，套用在以太坊既有的工作量證明協定之上。這項努力進展得相當深入，一個 [EIP-1011](https://eips.ethereum.org/EIPS/eip-1011) 測試網在 2017 年 12 月 31 日[上線](https://web.archive.org/web/20230630135033/https://nitter.it/karl_dot_tech/status/947503029166546946)。

PoW 疊加層計畫在 2018 年被放棄，改為透過一個運行 Gasper（LMD GHOST 加 Casper FFG）共識架構的新信標鏈架構，直接邁向完全的權益證明——這就是我們今天所擁有的架構。

信標鏈上 Casper FFG 最初的規格維護於 [Ethresear.ch](https://ethresear.ch/t/beacon-chain-casper-mini-spec/2760?u=benjaminion)（你可以在那裡看到文件歷史）。它包含 $k$-最終性、一個略顯古怪版本的 Casper FFG 分叉選擇規則，以及我們今天所使用的這兩條 Casper 誡命。然而，信標鏈現在使用 32 個時段的紀元，而非 64 個，而且我們並未實作動態驗證者集合機制。

當前的 Casper FFG 規格，作為信標鏈狀態轉換函式中[紀元處理](/part3/transition/epoch/)的一部分而維護。

#### 練習解答

以下是[上方練習](#exercise)的解答。

<details>
<summary>解答</summary>

假設證明總是恰好被延遲一個紀元，使得在紀元 $N$ 做出的票要到紀元 $N+1$ 才被處理，並考慮以下 Casper FFG 演算法的推進過程。

<a id="img_consensus_answer_0"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示驗證者為一個從檢查點 0 到檢查點 1 的超級多數連結投票。](images/diagrams/consensus-answer-0.svg)

<figcaption>

我們從檢查點&nbsp;0 已被證成開始。在紀元&nbsp;1 期間，每個人照常投 ${0 \rightarrow 1}$。超級多數連結的投票以虛線顯示，因為這些票的處理會被延遲到下一個紀元。

</figcaption>
</figure>

<a id="img_consensus_answer_1"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示驗證者為一個從檢查點 0 到檢查點 2 的超級多數連結投票。](images/diagrams/consensus-answer-1.svg)

<figcaption>

在紀元&nbsp;1 結束時，由於延遲，還沒有任何票被看到，所以檢查點&nbsp;1 仍未被證成。在紀元&nbsp;2 期間，每個人投 ${0 \rightarrow 2}$。

</figcaption>
</figure>

<a id="img_consensus_answer_2"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示驗證者為一個從檢查點 1 到檢查點 3 的超級多數連結投票。](images/diagrams/consensus-answer-2.svg)

<figcaption>

在紀元&nbsp;2 結束時，我們可以處理紀元&nbsp;1 的投票，它們證成了檢查點&nbsp;1（並最終確定 0，但那無關緊要）。檢查點&nbsp;2 仍未被證成，因為我們還沒看到紀元&nbsp;2 的投票。在紀元&nbsp;3 期間，每個人投 ${1 \rightarrow 3}$。

</figcaption>
</figure>

<a id="img_consensus_answer_3"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示驗證者為一個從檢查點 2 到檢查點 4 的超級多數連結投票。](images/diagrams/consensus-answer-3.svg)

<figcaption>

由於延遲的證明，證成持續落後一個紀元。在紀元&nbsp;4 期間，每個人投 ${2 \rightarrow 4}$。

</figcaption>
</figure>

<a id="img_consensus_answer_4"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示一串已證成的區塊，其超級多數連結每隔一個就跳過一個檢查點。](images/diagrams/consensus-answer-4.svg)

<figcaption>

我們現在永久地被鎖在這種跳蛙式的行為中：投票總是跳過一個檢查點，因為被跳過之檢查點的證成總是晚一個紀元才發生。

</figcaption>
</figure>

</details>

#### 另見

最初的[《友善最終性裝置 Casper》](https://arxiv.org/pdf/1710.09437.pdf)論文至今仍是正典的參考文獻。雖然我們在以太坊&nbsp;2.0 中實作的細節在某些方面有所不同，但基礎仍然相同。

那篇論文也討論了使用「怠惰洩漏」來從災難性的崩潰中復原（第 4.2 節）。我已在[別處](/part2/incentives/inactivity/)涵蓋了我們如何在 Eth2 中實作怠惰洩漏。

再一次，Vitalik 的 Casper 歷史[推文連發](https://web.archive.org/web/20230630135150/https://nitter.it/VitalikButerin/status/1029900695925706753)（也可在[這裡](https://web.archive.org/web/20180816143143/https://www.trustnodes.com/2018/08/16/vitalik-buterin-tells-story-race-vlad-zamfir-implement-proof-stake-casper)與[這裡](https://hackmd.io/@liangcc/BJZDR1mIX?type=view)取得）為 Casper 共識協定 CBC 與 FFG 的發展，提供了極佳的第一手背景。

在共識層規格中：

  - 證成與最終確定的計算在紀元處理期間執行，進入點是 [`process_justification_and_finalization()`](/part3/transition/epoch/#def_process_justification_and_finalization)，主要的工作由 [`weigh_justification_and_finalization()`](/part3/transition/epoch/#def_weigh_justification_and_finalization) 完成，包括 $k$-最終性的處理。
  - 獎勵與懲罰在紀元處理期間由 [`process_rewards_and_penalties()`](/part3/transition/epoch/#def_process_rewards_and_penalties) 套用，但這只是把在 [`process_attestation()`](/part3/transition/block/#def_process_attestation) 中逐區塊計算出的獎勵單純地加總起來。
  - Casper FFG 罰沒違規由 [`process_attester_slashing()`](/part3/transition/block/#def_process_attester_slashing) 處理。

我所找到關於 Casper FFG 較佳的文章之一，出自 [Juin Chiu](https://medium.com/unitychain/intro-to-casper-ffg-9ed944d98b2d) 之手。它在 Casper FFG 與古典 PBFT 之關係這方面尤其出色。Vitalik 的[《最小罰沒條件》](https://medium.com/@VitalikButerin/minimal-slashing-conditions-20f0b500fc6c)一文蘊含許多洞見（即使那些罰沒條件結果並非最小）。

關於 Casper FFG 種種保證的一些形式化驗證工作（針對原始論文所呈現的版本，也就是不含 $k$-最終性等等的版本），在[《在 Coq 證明輔助器中驗證 Casper》](https://core.ac.uk/download/pdf/161954227.pdf)（2018）論文中有所描述。它含有一些有用的洞見，尤其澄清了似真活躍性證明背後的假設。

### Gasper <!-- /part2/consensus/gasper/* -->

TODO

#### Gasper 中的安全性與活躍性

TODO

##### 鏈頭與鏈尾

TODO

### 問題與修正 <!-- /part2/consensus/issues/ -->

#### LMD GHOST

<!-- [RLMD GHOST paper](https://arxiv.org/pdf/2302.11326.pdf). -->

TODO

##### 證明採計延遲

TODO <!-- 1 slot delay in consideration -->

##### 證明的近期性

TODO。見[註解版分叉選擇](/part3/forkchoice/phase0/#attestation-timeliness)。

##### 證明含糊其辭

TODO。見[註解版分叉選擇](/part3/forkchoice/phase0/#on_attester_slashing)。

##### 重組與回退

TODO

###### 事前重組

TODO

###### 事後重組

TODO

##### 提議者加成

TODO。見[註解版分叉選擇](/part3/forkchoice/phase0/#proposer-boost)。

#### Casper FFG

##### Casper FFG 的分叉選擇可能導致長重組

Casper FFG 的[分叉選擇規則](/part2/consensus/casper_ffg/#fork-choice-rule)規定，底層的共識協定必須跟隨擁有最高已證成檢查點的那條鏈。這保證了 Casper FFG 的[似真活躍性](/part2/consensus/casper_ffg/#plausible-liveness)，但在例外的情況下也可能導致長重組。

這樣一起事件在 2023 年 7 月 28 日發生於以太坊的 Goerli 測試網。下面的解釋以 [Potuz 出色的分析](https://web.archive.org/web/20230922104428/https://nitter.net/potuz1/status/1685736037321166848)為依據。

如果我們看 Goerli 測試網上的[紀元 192879](https://goerli.beaconcha.in/epoch/192879)，我們會注意到它在[時段 6172128](https://goerli.beaconcha.in/slot/6172128)有一個初始區塊，但該紀元中所有後續的區塊要嘛完全缺失，要嘛被孤立了。一個分叉選擇視覺化工具[顯示](https://web.archive.org/web/20230922104428/https://nitter.net/potuz1/status/1685736037321166848)，[紀元 192880](https://goerli.beaconcha.in/epoch/192880)中的提議者直接忽略了紀元 192879 第一個時段之後的一切，轉而選擇建構在時段 6172128 中的區塊之上。

那麼，發生了什麼事？

1. 不尋常地，由於沒有累積到足夠的票，檢查點 192878 到紀元 192878 結束時還沒被證成。
2. 位於紀元 192879 起頭、[時段 6172128](https://goerli.beaconcha.in/slot/6172128)的那個區塊，含有足夠的票來證成檢查點 192878，但這個區塊發布得非常晚。
3. 後續的提議者因為時段 6172128 的區塊遲到而正確地忽略了它，轉而在時段 6172126 的區塊上建構一條鏈。它們在整個紀元 192879 期間持續建構這條鏈。
   - 然而，這條新鏈上的區塊並未納入「本可證成檢查點 192878」的那些票。依設計，區塊中容納證明的[空間有限](/part3/config/preset/#max-operations-per-block)。由於有好幾個時段是空的，證明空間變得壅塞。
   - 它們到紀元 192879 結束時，也沒有足夠的票來證成檢查點 192879。
4. 在紀元 192879 結束時的紀元處理之後，我們有兩條分支：
   1. 第一條在紀元 192879 中含有單一一個區塊，位於時段 6172128，而檢查點 192878 是最高的已證成檢查點；
   2. 第二條在紀元 192879 中含有許多區塊，而檢查點 192877 是最高的已證成檢查點。
5. 在紀元 192880 的起頭，Casper FFG 的分叉選擇規定，區塊 6172128 必定是新的鏈頭，因為它擁有最高的已證成檢查點，而[紀元 192879](https://goerli.beaconcha.in/epoch/192879)中所有後續的區塊都必須被忽略。

<a id="img_consensus_issues_ffg_reorg"></a>
<figure class="diagram" style="width: 95%">

![一張示意圖，說明這個導致一整個紀元的區塊被孤立的分叉。](images/diagrams/consensus-issues-ffg-reorg.svg)

<figcaption>

在 192879 結束時的紀元處理期間，上方分支含有證成檢查點 192878 的票，而下方分支不含足以證成 192878 或 192879 任一者的票。Casper FFG 的分叉選擇迫使 192880 中的提議者建構在證成程度較高的那條分支上。結果，時段 6172130 至 6172159 中的所有區塊都被孤立（重組掉）了。大方塊是檢查點，圓角方塊是區塊。

</figcaption>
</figure>

這並非由於實作上的臭蟲，而是由於 Casper FFG 的分叉選擇。如果下方分叉在紀元 192880 中仍維持為正典，那麼任何跟隨上方分叉、且要到很久之後才看到下方分叉上區塊的驗證者，最終都會被迫把它的已證成紀元從 192878 往回移到 192877，這可能使它們將來必須做出可罰沒的包圍投票。

這次重組的嚴重程度被下列因素加劇：

  - 紀元的長度，記帳每 32 個時段才執行一次；
  - 整體參與率接近 67% 的超級多數門檻；
  - 一個含有關鍵證成資訊的區塊（位於時段 6172128）發布得太晚；
  - 好幾個空時段造成了對區塊空間的爭奪，使得重要的證明被排除在紀元 192879 中較長的那條鏈之外；以及
  - 證明可被納入的時間窗口太緊，這應該會因 [EIP 7045](https://eips.ethereum.org/EIPS/eip-7045) 所規劃的變更而獲得改善。

請注意，這一切都與圍繞[未實現證成](/part3/forkchoice/phase0/#unrealised-justification)的另一個獨立議題無關。

這個情境在以太坊主網上非常不可能發生，主要是因為參與率幾乎總是超過 99%，遠高於超級多數門檻，而且區塊被錯失的情形比測試網上罕見得多。

#### Gasper

TODO

##### 未實現證成

TODO。見[註解版分叉選擇](/part3/forkchoice/phase0/#unrealised-justification)。

### 弱主觀性 <!-- /part2/validator/weak_subjectivity/* -->

為了讓權益證明能成為世界經濟活動的穩固基礎，必須解決的兩大問題是：(1) 無利害關係問題，以及 (2) 長程攻擊（long range attack）。

以太坊的共識用一個罰沒機制解決了無利害關係問題——也就是「權益證明的驗證者對每一個區塊提議含糊其辭、在每一個分叉上都建構而不擇一，是無代價的」這個問題。長程攻擊問題則藉由[擁抱弱主觀性](https://blog.ethereum.org/2014/11/25/proof-stake-learned-love-weak-subjectivity)來解決。

<!-- Vlad's earlier post has a good viewpoint on weak subjectvity: https://blog.ethereum.org/2015/08/01/introducing-casper-friendly-ghost -->

TODO

## 一個時段的進程 <!-- /part2/slot/* -->

### 引言

TODO

### 提議

TODO

### 做出證明

TODO

### 聚合

TODO

### 同步委員會的參與

TODO

## 一個紀元的進程 <!-- /part2/epoch/* -->

### 引言

TODO

### 套用獎勵與懲罰

TODO

### 證成與最終確定

TODO

### 其他狀態更新

TODO

## 驗證者生命週期 <!-- /part2/validator/* -->

### 引言

TODO

## 存款與提領 <!-- /part2/deposits-withdrawals/ -->

<div class="summary">

  - 存款是把以太幣從執行層轉到共識層。
  - 提領是把以太幣從共識層轉到執行層。
  - 兩層各自的記帳是完全分開的。
  - 質押者把交易送往存款合約以進行質押。
  - 質押是無須許可的。
  - 提領是週期性且自動的。
  - 提領分為部分提領或完整提領。

</div>

### 概觀

身為一個權益證明協定，以太坊仰賴質押者把資本鎖在協定之內（存款），並在最終連同他們所賺得的獎勵一起取回那筆資本（提領）。

被質押的資本形式是以太幣（ETH），即以太坊的原生貨幣。共識層上的以太幣，與一般以太坊帳戶與合約中的以太幣分開存在、分開記帳。共識層上的以太幣，其形式是驗證者帳戶的餘額。驗證者帳戶極其受限：它們有一個餘額，會因存款與獎勵而增加，因提領與懲罰而減少。你無法在驗證者帳戶之間轉帳，也無法對它們執行任何種類的交易。驗證者帳戶餘額被當成[信標狀態](/part3/containers/state/)的一部分來追蹤，並不構成一般以太坊執行狀態的一部分。請注意，執行層餘額以 Wei（$10^{-18}$ ETH）為單位，而驗證者餘額以 Gwei（$10^{-9}$ ETH）為單位。

基本的架構（我們會在接下來幾節徹底涵蓋）是：質押者藉由把一筆以太坊交易送往存款合約來做出存款，而存款合約是執行層上一個標準的以太坊智慧合約。重要的是，質押是完全無須許可的。任何人都可以藉由在一筆一般的以太坊交易中把 32&nbsp;ETH 送往存款合約，來進行質押並取得運行一個驗證者的權利。

收到一筆存款時，存款合約會發出一份收據。過一陣子之後，這份收據被共識層撿起，於是一個驗證者帳戶被建立，並被記入該存款金額。質押者接著就可以運行一個以太坊驗證者。

一切順利的話，該驗證者會賺得獎勵。這些獎勵會被週期性地、自動地從該驗證者的餘額中扣除，並記入提領憑證中所指定的 Eth1 帳戶，也就是提領位址。

當該驗證者最終發出訊號表示它想退出協定（或它被罰沒）時，任何剩餘的餘額都會被從該驗證者帳戶中扣除，並記入提領位址。

整個流程在下面的示意圖中說明。

<a id="img_deposits_withdrawals_overview"></a>
<figure class="diagram" style="width: 98%">

![一張示意圖，描繪存款與提領在執行層與共識層之間的流動。](images/diagrams/deposits-withdrawals-overview.svg)

<figcaption>

一張描繪某個驗證者之存款與提領流動的示意圖。時間大致由上往下流動。加值存款是選擇性的，但為求完整而顯示出來。帳戶 1 與帳戶 2 可能是同一個，也可能是合約。帳戶 2 是提領位址。

</figcaption>
</figure>

從這張圖可得到一個有趣的觀察：存款合約上並沒有附加任何負號：隨著驗證者退出又重新質押，存款合約的餘額是「只增不減」的。當一個驗證者退出又重新質押時，存款合約的餘額增加 32&nbsp;ETH，而其他一切本質上都沒變。如果這發生了 320 萬次（在目前已質押超過五十萬個驗證者的情況下，這並非不可想像），那麼存款合約的餘額就會超過有史以來流通過的以太幣總量，約 1.2 億 ETH。這並不重要，只是用以強調：存款合約的餘額應被視為已燒毀，並在加總以太坊的總供給量時計為零。[^fn-deposit-contract-balance]

[^fn-deposit-contract-balance]: 既然 Engine API 現已可用，我們原則上可以在每次有收據於共識層被處理時減少存款合約的餘額，但只為了修正這個怪癖而增添的複雜度並不可取。

更重要的是，存款有兩種類型，提領也有兩種類型。當一個驗證者的第一筆存款被共識層處理時，該驗證者就被建立（這筆存款不一定足以啟用它）。同一個驗證者後續的任何存款都是加值存款（top-up deposit），有著略微不同、驗證較少的工作流程。

至於提領，部分提領（partial withdrawal）是把驗證者餘額中任何超過 32&nbsp;ETH 的部分定期轉到執行層。完整提領（full withdrawal）則發生在驗證者已退出協定並變得「可提領」之時，屆時該驗證者全部剩餘的餘額都會被轉出。這兩種類型的提領都會自動且週期性地發生。

在接下來幾節中，我們會先看[做出存款](/part2/deposits-withdrawals/staking/)的運作機制，接著深入研究[存款合約](/part2/deposits-withdrawals/contract/)。我們會以看共識層處理[存款](/part2/deposits-withdrawals/deposit-processing/)與[提領](/part2/deposits-withdrawals/withdrawal-processing/)的運作機制作結。

接下來幾節貫穿始終的一個主題是：當前存款與提領流程中的許多複雜性，是由於以太坊奇特的歷史而產生的。存款合約的增量式 Merkle 樹、Eth1Data 投票期、Eth1 跟隨距離——這一切都是由於我們在權益證明上打造一條獨立的信標鏈時，執行層仍停留在工作量證明上。整個 BLS 提領憑證的曲折歷程，則源自我們當時對路線圖的不確定。

另一個主題是：在合併之後，我們有機會把這當中的一些東西清理乾淨。[EIP-6110](https://eips.ethereum.org/EIPS/eip-6110) 是一項大幅精簡存款處理的提案。儘管如此，有些複雜性會永遠跟著我們。

### 做出存款 <!-- /part2/deposits-withdrawals/staking/ -->

<div class="summary">

  - 初始存款建立一個驗證者的記錄。
  - 加值存款增加一個既有驗證者的餘額。
  - 做出存款牽涉到把一筆交易送往存款合約。
  - 以太坊 Launchpad 為此提供了一個不錯的介面，不過也存在替代方案。
  - 存款 CLI 工具等等可以建立存款資料與 BLS 金鑰庫（keystore）。

</div>

#### 引言

這不是一份操作指南，所以我只會把主要的工具與工作流程當作對這些概念的引介來談。

以太坊基金會的 [Staking Launchpad](https://launchpad.ethereum.org/) 是許多獨立質押者的入口。大型營運單位可能會用智慧合約來[批次](https://github.com/stakefish/eth2-batch-deposit)提交存款，但我們會聚焦於單一一筆 32&nbsp;ETH 的存款。

Launchpad 會引導你使用[質押存款 CLI 工具](https://github.com/ethereum/staking-deposit-cli)[^fn-eth-staking-smith]。強烈建議你離線運行存款 CLI 工具，可能在一台氣隙隔離（air-gapped）、以 live 模式開機的機器上。這是為了讓你的助記種子詞組（mnemonic seed phrase）盡可能保持安全[^fn-safe-mnemonic]。

[^fn-eth-staking-smith]: [Eth-staking-smith](https://github.com/ChorusOne/eth-staking-smith) 是一個替代方案。我沒用過它，無法為它擔保，不過其原始碼是正當的。它有一個有趣的特性，能夠使用 PBKDF2 作為金鑰衍生函式——見[下文](#keystores)。

[^fn-safe-mnemonic]: 從前保護你的助記詞更為重要，因為它既掌控你的提領憑證、也掌控你的簽章金鑰。如今它通常只會被用於你的簽章金鑰——攻擊者用它對你造成的傷害，比用提領憑證來得小。

#### 初始存款

做出一筆初始存款時——也就是為一個尚不存在的驗證者——質押 CLI 可以如下以互動方式運行。

```bash
./deposit new-mnemonic --execution_address '0x00....09'
```

預設情況下，若沒有 `--execution-address` 參數，質押 CLI 會產生舊式的 [BLS 提領憑證](/part2/deposits-withdrawals/withdrawal-processing/#bls-withdrawal-credentials)。你會想要使用新式的 [Eth1 提領憑證](/part2/deposits-withdrawals/withdrawal-processing/#eth1-withdrawal-credentials)，所以在這裡指定一個你所控制的以太坊帳戶位址。如果你現在不這麼做，你之後就需要[更改它](/part2/deposits-withdrawals/withdrawal-processing/#credential-changes)，才能收到你的獎勵並取回你的質押。

這個工具會用你機器的隨機性產生一個新的 256 位元種子，並依據 [BIP-39 標準](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki)把它轉換成一個 24 個字的助記詞組。單一一個助記種子詞組可用來產生大量的 BLS12-381 [私鑰—公鑰對](/part2/building_blocks/signatures/#key-pairs)，從而產生大量的驗證者。把這個助記詞組非常安全地保存在某處，而且絕不要放在線上。萬一你需要重新建立你的驗證者金鑰，以及在你退出你的驗證者時，你都會需要它。

你可以根據同一個助記詞，一次為多個驗證者產生金鑰庫。只要告訴存款 CLI 數量即可。不過，每一個都會需要它自己的 32&nbsp;ETH 質押。

跑完所有的提示與確認之後，存款 CLI 會產生一些檔案。會有單一一個 `deposit_data-xxx.json` 檔案，以及每個你所產生的驗證者各一個 `keystore-m_12381_3600_0_0_n_xxx.json` 檔案。

##### 存款資料

`deposit_data-xxx.json` 檔案是 Launchpad 工作流程的一部分；其他工具可能有不同的做法。當你把存款資料檔案提交給 Launchpad 時，它會為每個驗證者建立一筆存款交易，你用你一般的以太坊錢包為它簽章，從而把 32&nbsp;ETH 送往存款合約。

這個檔案為每個驗證者含有像這樣的一段（為求方便，我截短了某些行）。

```json
{
  "pubkey": "a70d57e5fd4615bd3110a709be82be7a8b966fe881290f2738e4d8d0b38f39fe...",
  "withdrawal_credentials": "0100000000000000000000000001020304050607080900010203040506070809",
  "amount": 32000000000,
  "signature": "a6821877521df6ea65e7458fd599ef6430d23f64789cf7d89a75658eccdaf841...",
  "deposit_message_root": "047eb9f043b4cd464084c44db76ddb937e3fda11a63fde59a6149f74b8c50685",
  "deposit_data_root": "5a05c42ace9518a92c5ec950e6f58a6fd490a06b7619370d1b700d8d93b2cbbe",
  "fork_version": "00000000",
  "network_name": "mainnet",
  "deposit_cli_version": "2.5.0"
}
```

各欄位如下。

  - `pubkey` 由「從你的助記詞所產生的祕密金鑰」產生而來。它是該驗證者在共識層上獨一無二的身分。舉例來說，你可以在 [Beaconcha.in](https://beaconcha.in) 瀏覽器上查找它。
  - 如果你指定了 `execution_address`，`withdrawal_credentials` 會以 `01` 開頭，並以「提領將前往之以太坊帳戶」的 40 個十六進位數字結尾。如果你沒有指定 `execution_address`，那麼 `withdrawal_credentials` 會以 `00` 開頭，後面跟著一份 BLS 提領承諾。
  - `amount` 以 Gwei 為單位。`32000000000` 是 32&nbsp;ETH。
  - `signature` 是一份對前述三個欄位、使用你的祕密簽章金鑰所做的 [BLS 簽章](/part2/building_blocks/signatures/)。
  - `deposit_message_root` 是實際被 `signature` 簽署的資料。它是 [`DepositMessage`](/part3/containers/dependencies/#depositmessage) 物件的[雜湊樹根](/part2/building_blocks/merkleization/)。它在技術上是多餘的，因為它很容易重新計算，但 Launchpad 用它作為校驗碼，以驗證所提交的資料與簽章是否全都正確驗證通過。
  - `deposit_data_root` 是由上述前四個欄位（亦即存款訊息加上它的簽章）所建立之 [`DepositData`](/part3/containers/dependencies/#depositdata) 物件的雜湊樹根。這被存款合約用作校驗碼。
  - `fork_version` 指定這筆存款是給哪一條鏈的。`fork_version` 被編碼進簽章中，使得存款只在所意圖的那條鏈上有效。為存款簽章時，總是使用該鏈的 [`GENESIS_FORK_VERSION`](/part3/config/configuration/#genesis_fork_version)。

其餘的欄位只是行政記錄。

##### 金鑰庫

存款 CLI 也會為每個驗證者產生一個金鑰庫（keystore）檔案。這個檔案含有該驗證者加密過的祕密金鑰。金鑰庫會被質押者的客戶端軟體所使用，並需要依該客戶端的說明來安裝。金鑰庫的內容由運行存款 CLI 時所提供的密碼保護，這個密碼也需要提供給質押客戶端。每個客戶端處理這件事的方式不同，所以請查閱文件。

<details>
<summary>金鑰庫範例</summary>

一個金鑰庫檔案的內容像下面這樣。你可以看到 `pubkey` 與上方存款資料檔案中的 `pubkey` 相符。我不會深入這個的細節，但其格式在 [ERC-2335](https://eips.ethereum.org/EIPS/eip-2335) 中有所描述。衍生 `path` 參數在 [ERC-2334](https://eips.ethereum.org/EIPS/eip-2334) 中有所討論。

```json
{
  "crypto": {
    "kdf": {
      "function": "scrypt",
      "params": {
        "dklen": 32,
        "n": 262144,
        "r": 8,
        "p": 1,
        "salt": "d6679024b3693066eba27bbe7c2269fc62c98a1accf225c916d6eafb24abcdae"
      },
      "message": ""
    },
    "checksum": {
      "function": "sha256",
      "params": {},
      "message": "402eb9c5d6042f354bb8013ed19019b9d8cfa7deed1ed44eb2c0680615df1b13"
    },
    "cipher": {
      "function": "aes-128-ctr",
      "params": {
        "iv": "4ced4174acc07417f34106eb1cb5c685"
      },
      "message": "e7adc1ab79c2870fccd87b9cbd09830fcf0654cccca944ff3c9c26a1f6fb10b5"
    }
  },
  "description": "",
  "pubkey": "a70d57e5fd4615bd3110a709be82be7a8b966fe881290f2738e4d8d0b38f39fe..."
  "path": "m/12381/3600/0/0/0",
  "uuid": "7b25b4a7-9241-4ad8-9540-f0ed096f30cd",
  "version": 4
}
```

</details>

金鑰衍生函式（KDF）被用來以一個密碼保護祕密金鑰。KDF 的設計目的，是讓「以暴力法解密該祕密金鑰」在計算上不可行。

存款 CLI 使用 [Scrypt KDF](https://en.wikipedia.org/wiki/Scrypt)，它依設計是緩慢的，並且使用大量記憶體，每把金鑰約 300MB。對於載入一兩把金鑰的獨立質押者而言這沒問題，但對於在啟動時載入數百或數千把金鑰的大型質押服務而言，它可能成為一個顯著的瓶頸。

ERC-2335 金鑰庫也支援 [PBKDF2](https://en.wikipedia.org/wiki/PBKDF2) 作為 KDF，它快得多，也較不耗記憶體。視一個人「以金鑰安全性換取載入速度」的意願而定，PBKDF2 可能較為可取。[`ethdo`](https://github.com/wealdtech/ethdo) 與 [`eth-staking-smith`](https://github.com/ChorusOne/eth-staking-smith) 工具能夠使用 PBKDF2 來產生金鑰庫。

#### 加值存款

加值存款是給已經存在之驗證者的存款。如果一個驗證者的[有效餘額](/part2/incentives/balances/)掉到 32&nbsp;ETH 以下，你可能會想為它加值，以便把它恢復到最大的有效性。

Staking Launchpad 提供一個[加值](https://launchpad.ethereum.org/en/top-up)介面。要做出一筆加值存款，你不需要存取你的金鑰庫或助記詞。事實上，任何人都可以在任何時候為任何驗證者加值。

為了加值而送往存款合約的交易，本質上與初始存款的交易相同，但有下列差異：

  - 公鑰必須與某個既有驗證者的公鑰相符，
  - 簽章不會被檢查，可以是一個「空的」虛設簽章[^fn-top-up-signature]，以及
  - 提領憑證會被忽略。

[^fn-top-up-signature]: 看來區塊瀏覽器[並不知道這一點](https://github.com/ConsenSys/teku/issues/7060)，並可能不正確地把加值交易標記為無效。

隨著時間推移逐步累積一個驗證者的質押是有可能的：先做一筆少於 32&nbsp;ETH 的初始存款，再做一筆或多筆加值存款。當該驗證者的有效餘額達到 32&nbsp;ETH 時，它就會變得活躍。然而，如果你打算這麼做，當最後一筆加值是 1&nbsp;ETH 時，要當心一個牽涉遲滯（hysteresis）的棘手[邊角案例](/part2/incentives/balances/#an-edge-case)。

##### 另見

[Ethereum.org 網站](https://ethereum.org/en/staking/solo/)有更多關於獨立質押的資訊，並比較了存款 CLI 工具的替代方案。

如果你想擺弄一下共識層的金鑰與錢包，[`ethdo`](https://github.com/wealdtech/ethdo) 工具極為有用。它已經過[稽核](https://www.wealdtech.com/articles/ethdo-audit/)，並有著範圍極廣的功能，也能[處理基本工作](https://medium.com/coinmonks/creating-ethereum-2-withdrawal-keys-using-ethdo-6e41b14ddd7b)。

關於共識層的金鑰處理，已提出三項 ERC 標準。

  - [ERC-2333：BLS12-381 金鑰產生](https://eips.ethereum.org/EIPS/eip-2333)。
  - [ERC-2334：BLS12-381 確定性帳戶階層](https://eips.ethereum.org/EIPS/eip-2334)。
  - [ERC-2335：BLS12-381 金鑰庫](https://eips.ethereum.org/EIPS/eip-2335)。

### 存款合約 <!-- /part2/deposits-withdrawals/contract/ -->

<div class="summary">

  - 存款合約是協定進行質押的進入點。
  - 任何人都可以無須許可地透過該合約質押 32&nbsp;ETH。
  - 收到一筆有效存款時，該合約會發出一份收據。
  - 一棵增量式 Merkle 樹維護著一個涵蓋所有存款的 Merkle 根。
  - 存款合約無法驗證一筆存款的 BLS 簽章。
  - 存款合約的餘額永遠不會減少。
  - 送往存款合約的以太幣應被視為已燒毀。

</div>

#### 概觀

存款合約是質押者把他們的以太幣交付給協定、以取得運行一個驗證者之權利的途徑。

該合約的原始碼可在[規格儲存庫](https://github.com/ethereum/consensus-specs/tree/dev/solidity_deposit_contract)取得，而經驗證的位元組碼[已部署在鏈上](https://etherscan.io/address/0x00000000219ab540356cbb839cbe05303d7705fa#code)。

##### 功能

存款合約是執行（Eth1）層上運行的一個一般以太坊智慧合約。任何想為了運行一個驗證者而下注質押的人，都可以透過一筆一般的以太坊交易把 32&nbsp;ETH 送往存款合約。

除了所轉移的以太幣之外，存款交易還必須含有如下進一步的資料。

第一，驗證者的公鑰。一個驗證者的公鑰由它的祕密簽章金鑰衍生而來，是它在共識層上的主要身分。質押者會把祕密簽章金鑰另外提供給共識客戶端，供日常運作使用。

第二，提領憑證，指定所賺得的獎勵將被送往哪一個以太坊帳戶。這也會是該驗證者最終退出時接收其全部餘額的位址。提領憑證有兩種形式，我們會在[後文](/part2/deposits-withdrawals/withdrawal-processing/#withdrawal-credentials)討論。

第三，一份對公鑰、提領憑證以及存款金額、使用一般簽章金鑰所做的簽章。這份簽章的主要作用，是充當對該驗證者祕密金鑰的「持有證明」（proof of possession），這繞開了一種討厭的[流氓公鑰攻擊](/part2/building_blocks/signatures/#proof-of-possession)。

第四，存款資料根，它是對上述所有資料的一個 [SSZ Merkle 化](/part2/building_blocks/merkleization/)結果，充當一種合約可以驗證的校驗碼。

存款合約對這些參數做一些驗證。尤其，存款金額會受到檢查，存款資料根也會被驗證。如果這兩者中有任一者失敗，那麼這筆存款就會被拒絕——也就是說，存款交易會被回退。

然而，存款合約並不驗證簽章——EVM 還沒有用以做這件事的橢圓曲線機件，而要在一般的位元組碼中做這件事，代價會高得令人卻步。簽章稍後會由共識層驗證，而如果發現它不正確（對新的驗證者而言），這筆存款就會失敗，那筆以太幣也會喪失。

一旦存款合約盡其所能地確信這筆存款有效，它就會發出[一份收據](#deposit-receipts)（一個 EVM 日誌事件），其中含有存款資料。這份收據稍後會被共識層撿起以進行處理。

##### 開發

最初的存款合約[是以 Vyper 編寫的](https://github.com/ethereum/deposit_contract)，那是一種類似 Python 的智慧合約語言。合約程式碼的工作始於 2018 年 1 月，比信標鏈被構思出來還早幾個月：它是極少數從以太坊較早期權益證明設計中延續下來的東西之一。然而，信標鏈之前的那個版本省略了所有 Merkle 樹的機件，因為當時不需要[^fn-6110-no-merkle]。使用增量式（也稱為漸進式）Merkle 樹，是 Vitalik 在 2019 年 1 月[所建議的](https://github.com/ethereum/consensus-specs/pull/490)。

[^fn-6110-no-merkle]: 有了 [EIP-6110](https://eips.ethereum.org/EIPS/eip-6110)，我們最終可能會朝那個方向走回去，不再需要 Merkle 根。

大約在 2020 年 4 月，把存款合約以 Solidity（一種更主流的智慧合約語言）重寫的工作開始了。[新儲存庫](https://github.com/ethereum/consensus-specs/tree/dev/solidity_deposit_contract)中所陳述的原因如下，它與形式化驗證該合約有關。

> 最初的動機，是想在編譯器中運行 SMTChecker 以及新的 Yul IR 產生器選項（`--ir`）。

Runtime Verification 的[驗證工作](https://github.com/runtimeverification/deposit-contract-verification/blob/master/deposit-contract-verification.pdf)引用了「社群對〔當時〕現行 Vyper 編譯器的疑慮」作為重寫的動機。這些疑慮被記載於 Suhabe Bugrara 最初對 [Vyper 合約的審查](https://github.com/suhabe/eth-deposit-contract-vyper-review/blob/master/EthDepositContractVyperReview.pdf)中，並在以太坊基金會的[部落格文章](https://blog.ethereum.org/2020/06/23/eth2-quick-update-no-12#solidity-deposit-contract-and-formal-verification)中有所討論。

所部署的存款合約是從 [Solidity 原始碼](https://etherscan.io/address/0x00000000219ab540356cbb839cbe05303d7705fa#code)編譯而來的。

##### 驗證工作

由於以太坊合約一旦部署便不可變更，存款合約的正確性至關重要：它的餘額會變成所有以太幣中相當大的一部分。為此，進行了各式各樣的分析與形式化驗證活動。

2020 年 6 月，Runtime Verification 進行了一次[形式化驗證](https://github.com/runtimeverification/deposit-contract-verification)，涵蓋兩個面向。

1. 驗證增量式 Merkle 樹演算法等價於一個完整的 Merkle 樹構造。
2. 使用 KEVM 驗證器，驗證位元組碼是從 Solidity 原始碼正確產生的。

就在合約部署之前，Consensys 的 Franck Cassez 進行了一些進一步的工作，如他的論文[《以 Dafny 驗證增量式 Merkle 樹演算法》](https://arxiv.org/pdf/2105.06009.pdf)以及 [GitHub 儲存庫](https://github.com/ConsenSys/deposit-sc-dafny)中所描述。這比 Runtime Verification 的工作更進一步，使用 Dafny 形式化驗證語言完整地機械化驗證了增量式 Merkle 樹演算法。

##### 部署

存款合約於 2020 年 10 月 14 日 09:22:52 UTC [被部署](https://etherscan.io/tx/0xe75fb554e433e03763a1560646ee22dcb74e5274b34c5ad644e7c0f619a7e1d0)到以太坊位址 [`0x00000000219ab540356cbb839cbe05303d7705fa`](https://etherscan.io/address/0x00000000219ab540356cbb839cbe05303d7705fa)。

[部署用的帳戶](https://etherscan.io/address/0xb20a608c624ca5003905aa834de7156c68b2e1d0)大概是藉由不斷研磨（grinding）金鑰而產生的，目的是讓它的第一筆交易能把合約部署到一個帶有獨特八個零前綴的位址：以太坊合約位址[是由](https://ethereum.org/en/developers/docs/accounts/#contract-accounts)部署者的帳戶位址與 nonce 值計算出來的。這大概要花 $2^{32}$（43 億）次數量級的金鑰產生嘗試。

撇開垃圾交易不談，與這個部署帳戶相關的交易只有三筆。

  - 該帳戶透過一筆[來自 Tornado Cash 的轉帳](https://etherscan.io/tx/0x1956761ad42396786160cb4cbca845409dadc5366c46a2b4e178d63dc0f17578)被注資 1&nbsp;ETH（扣除手續費）。
    - 結果，我們無從辨識部署者的身分。由於合約的位元組碼是公開可取得的，它可能是任何人。
  - [存款合約的部署](https://etherscan.io/tx/0xe75fb554e433e03763a1560646ee22dcb74e5274b34c5ad644e7c0f619a7e1d0)花費了 0.31478286&nbsp;ETH。
  - 剩下的 ETH 被轉到[維基解密的捐款位址](https://etherscan.io/tx/0x8aa30f7d95cd5f22dd02e59434c0e66794c6e370ed2659ea532ed6fe49f9cce5)。

#### 程式碼

接下來的闡述以 [Etherscan 上經驗證](https://etherscan.io/address/0x00000000219ab540356cbb839cbe05303d7705fa#code)的 Solidity 原始碼為依據，它應當與[共識規格儲存庫](https://github.com/ethereum/consensus-specs/blob/v1.3.0/solidity_deposit_contract/deposit_contract.sol)中的原始碼相符。

為求簡潔，我省略了介面樣板程式碼以及一些冗長的註解。

##### `DepositContract`

```solidity
contract DepositContract is IDepositContract, ERC165 {
    uint constant DEPOSIT_CONTRACT_TREE_DEPTH = 32;
    // NOTE: this also ensures `deposit_count` will fit into 64-bits
    uint constant MAX_DEPOSIT_COUNT = 2**DEPOSIT_CONTRACT_TREE_DEPTH - 1;

    bytes32[DEPOSIT_CONTRACT_TREE_DEPTH] branch;
    uint256 deposit_count;

    bytes32[DEPOSIT_CONTRACT_TREE_DEPTH] zero_hashes;

    constructor() public {
        // Compute hashes in empty sparse Merkle tree
        for (uint height = 0; height < DEPOSIT_CONTRACT_TREE_DEPTH - 1; height++)
            zero_hashes[height + 1] = sha256(abi.encodePacked(zero_hashes[height], zero_hashes[height]));
    }
```

在宣告它的介面之後——我們會在[下文](#supportsinterface)看 ERC165——接著是常數與儲存。

`DEPOSIT_CONTRACT_TREE_DEPTH` 指定內部 Merkle 樹中的層數。深度為 32 時，它可以有 $2^{32}$ 個葉，容許至多 43 億筆存款（`MAX_DEPOSIT_COUNT`[^fn-max-deposit-count]）[^fn-eip-6110-max-deposits]。一筆存款最少為一 ETH，所以有足夠的空間讓現存的每一枚 ETH 都被存進去 35 次。

[^fn-max-deposit-count]: 關於 `MAX_DEPOSIT_COUNT` 的那則註解，它當然容得進 32 位元，那肯定小於 64。重點在於，共識層上的 `uint` 標準化為 64 位元的大小，而我們不想讓它溢位。

[^fn-eip-6110-max-deposits]: 有了 [EIP-6110](https://github.com/ethereum/consensus-specs/pull/3177) 中所提議用於存款處理的機制，我們就不再需要 Merkle 證明，原則上可以解除這個上限。然而，它被不可變更地編碼進存款合約中，所以在實務上不可能做到。

存款合約底層的資料結構是一棵增量式 Merkle 樹。這是一棵只支援兩種操作的 Merkle 樹：(1) 附加一個葉，以及 (2) 計算根。像這樣限制資料，讓我們得以避免儲存整棵 Merkle 樹（那會非常龐大）。合約改為只儲存最後的 `branch`——區區 32 個節點——這就是計算 Merkle 根所需的全部資訊。

要獲得這份效率，我們需要一個 `zero_hashes` 陣列。在樹的任何給定層級，零雜湊就是「假如某節點底下所有的葉都為零，該節點會有的值」。由於我們依序指派各個葉，樹中極大的部分都能由零雜湊來表示。

`constructor()`（它不取任何引數）只初始化 `zero_hashes` 結構，利用了 EVM 的一項預設：未初始化的 `zero_hashes[0]` 儲存值會是零。

<a id="img_deposits_withdrawals_zero_hashes"></a>
<figure class="diagram" style="width: 75%">

![一張示意圖，顯示 zero_hashes 陣列如何構造。](images/diagrams/deposits-withdrawals-zero-hashes.svg)

<figcaption>

要構造 $Z_n$，我們從 $Z_0 = 0$ 開始，並定義 $Z_{i+1} = \text{Hash}(Z_i, Z_i)$。

</figcaption>
</figure>

##### `get_deposit_root`

```solidity
    function get_deposit_root() override external view returns (bytes32) {
        bytes32 node;
        uint size = deposit_count;
        for (uint height = 0; height < DEPOSIT_CONTRACT_TREE_DEPTH; height++) {
            if ((size & 1) == 1)
                node = sha256(abi.encodePacked(branch[height], node));
            else
                node = sha256(abi.encodePacked(node, zero_hashes[height]));
            size /= 2;
        }
        return sha256(abi.encodePacked(
            node,
            to_little_endian_64(uint64(deposit_count)),
            bytes24(0)
        ));
    }
```

按需計算存款根，省得我們必須用一個儲存槽位來把它存起來。`view` 函式的本地執行是免費的，而寫入區塊鏈狀態則非常昂貴。

演算法的運作如下。在一棵二元 Merkle 樹中，一個節點要嘛是左子節點，要嘛是右子節點。

  - 如果一個節點是左子節點（`size & 1 == 0`），我們知道它的兄弟節點必定是一個零雜湊，因為這棵樹是增量式的。
  - 如果一個節點是右子節點，我們就從 `branch` 取它的兄弟節點。因此，`branch` 中重要的元素，是那些「為 `deposit_count` 的當前值儲存左子節點」的元素。

實際上，我們是用 `zero_hashes`（$Z_n$）與 `branch` 值（$B_n$）來摘要樹中極大的部分。$Z_n$ 是一棵子樹的根，該子樹的 $2^n$ 個葉全為零，其中 $Z_0 = 0$。$B_n$ 是一棵子樹的根，該子樹全部 $2^n$ 個葉都先前已被指派，其中 $B_0$ 是最後一個被插入的左葉。等到我們抵達根部時，我們實際上已把所有的葉都納入了計算。

由於這是一棵增量式 Merkle 樹，我們知道位於 `deposit_count` 處之葉的值為零：這個計數從零開始，所以葉 `deposit_count` 尚未被指派；它會是下一個被指派的葉。

要計算父節點，我們把它的左、右子節點的值一起雜湊。Solidity 的 [`abi.encodePacked()`](https://docs.soliditylang.org/en/v0.8.11/abi-spec.html#non-standard-packed-mode) 函式被用來串接每個兄弟節點的 32 個位元組。

請注意，對於 $n > \log_2 i$（其中 $i$ 是 `deposit count`），我們不使用任何 $B_n$——任何我們所造訪、高於此處的節點都將只會是左節點。我們在一筆新存款之後[更新 `branch`](#updating_branch) 時會利用這一點。

###### 玩具範例

增量式 Merkle 樹的妙處在於：我們只需在儲存中維護 $\log_2 N$ 個值、加上 `deposit_count`、再加上 $\log_2 N$ 個常數，就能為一棵至多有 $N$ 個葉的樹計算出一個根。

<a id="img_deposits_withdrawals_deposit_root"></a>
<figure class="diagram" style="width: 75%">

![一張示意圖，說明一棵增量式 Merkle 樹的根如何計算。](images/diagrams/deposits-withdrawals-deposit-root.svg)

<figcaption>

找出一棵三層增量式 Merkle 樹的根。已指派了五個葉 $v_0$ 到 $v_4$，雖然我們不儲存它們的值。在演算法中，`node` 從頂端的葉到底部的根，造訪那些虛線節點。$B_n$ 是由 `deposit()` 所維護的 `branch` 值，而 $Z_n$ 是預先計算好的 `zero_hashes`。

</figcaption>
</figure>

這張圖顯示一棵有三層的增量式 Merkle 樹。我們已用值 $v_0$ 到 $v_4$ 填滿了其中五個葉，但我們實際儲存的東西只有 `branch` 的三個 $B_n$ 值，以及 `zero_hashes` 的三個 $Z_n$ 值。在每一層 $n$，我們會使用 $B_n$ 或 $Z_n$ 之一來計算父節點。

`deposit_count` 是 5，所以我們從標記為「5」的葉處的 `node` 開始，我們知道它會是零，因為它尚未被指派。這是一個右子節點，因此我們把它與作為其左兄弟節點的 $B_0$ 結合。我們知道 $B_0$ 會等於最後被插入的葉值 $v_4$。（如果它是一個左子節點，我們就會把它與 $Z_0 = 0$ 結合。）

移到第 1 層，`node` 現在是一個左子節點，所以我們把它與第 1 層的零雜湊 $Z_1$ 結合。我們知道由那個 $Z_1$ 節點衍生而來的所有葉都是零。

在第 2 層，`node` 又是一個右子節點，所以我們把它與我們所儲存的 $B_2$ 值結合，以取得樹根處的值。

###### 我們為什麼需要存款根？

如我們稍後將見，每個質押節點都各自維護它自己的存款 Merkle 樹，獨立於存款合約之外，而它是用來自執行層的存款收據建構這棵樹的。那麼，我們為什麼需要把所有這套複雜的機件放進存款合約裡來計算根呢？

使用存款根，提供了一個自成一體的方式來驗證一個區塊中的存款資料是否正確。在 Eth2 的早期階段，「所有信標鏈節點都會連到 Eth1 客戶端」這一點完全不明朗。事實上，在合併之前，一個非質押節點不連到 Eth1 客戶端是完全沒問題的。那些節點需要某種辦法來能夠拒絕含有假存款的區塊。透過一份 Merkle 證明把證據放上鏈，讓它們得以做到這一點。

藉由[下文所描述](/part2/deposits-withdrawals/deposit-processing/#eth1-voting-and-follow-distance)的投票過程，驗證者週期性地把一個存款根從合約匯入信標鏈上。當一個提議者把存款納入它的區塊時，它必須附上一份證明，證明那些存款被包含在那個存款根中。這讓每個處理鏈的節點都能驗證每一筆存款，而不必去查詢 Eth1 鏈。

有意思的是，在合併之後，所有節點（無論是否運行驗證者）都被要求同時包含共識客戶端與執行客戶端，而執行酬載也被包含在信標區塊中。因此，如今，我們驗證存款所需的資料理所當然地就在鏈上，我們也不再嚴格需要擺弄這一整套存款根的東西。事實上，[EIP-6110](https://eips.ethereum.org/EIPS/eip-6110) 提議在鏈上明確地揭露驗證者存款，在那之後，存款合約中維護根的程式碼就會是多餘的。儘管如此，由於它不可變更，它會永遠繼續存在。

##### `get_deposit_count`

```solidity
    function get_deposit_count() override external view returns (bytes memory) {
        return to_little_endian_64(uint64(deposit_count));
    }
```

這裡唯一的小麻煩是位元組順序（endianness）的轉換。共識層使用小端（little-endian）格式來序列化整數，而 EVM 使用大端（big-endian）。共識層呼叫這個函式來得知新的存款，所以以正確的格式取得輸出很方便。

##### `deposit`

```solidity
    function deposit(
        bytes calldata pubkey,
        bytes calldata withdrawal_credentials,
        bytes calldata signature,
        bytes32 deposit_data_root
    ) override external payable {
        // Extended ABI length checks since dynamic types are used.
        require(pubkey.length == 48, "DepositContract: invalid pubkey length");
        require(withdrawal_credentials.length == 32, "DepositContract: invalid withdrawal_credentials length");
        require(signature.length == 96, "DepositContract: invalid signature length");

        // Check deposit amount
        require(msg.value >= 1 ether, "DepositContract: deposit value too low");
        require(msg.value % 1 gwei == 0, "DepositContract: deposit value not multiple of gwei");
        uint deposit_amount = msg.value / 1 gwei;
        require(deposit_amount <= type(uint64).max, "DepositContract: deposit value too high");
```

這是這個合約做正事的部分——質押者的存款在這裡被做出。

一筆存款由下列項目構成。

  - 驗證者的公鑰：`pubkey` 是由質押者的祕密簽章金鑰所衍生的 48 位元組（壓縮過的）BLS 公鑰。
  - 提領憑證：`withdrawal_credentials` 是 32 個位元組，要嘛是 `0x00` 的 [BLS 憑證](/part3/config/constants/#bls_withdrawal_prefix)，要嘛是 `0x01` 的 [Eth1 憑證](/part3/config/constants/#eth1_address_withdrawal_prefix)。除了長度之外，提領憑證在合約中任何地方、甚至在共識層上，都不會被驗證。
  - `signature` 是一份 96 位元組的 [BLS 簽章](/part2/building_blocks/signatures/)。它是用驗證者的簽章金鑰，對一個 [`DepositMessage`](/part3/containers/dependencies/#depositmessage) 物件（`public_key`、`withdrawal_credentials` 與 `deposit_amount`）的雜湊樹根簽章而產生的。
  - `deposit_data_root` 基本上是一種校驗碼。它如何被驗證見下文。
  - 最後是一個 `msg.value`。訊息值是隨交易送出的以太幣數量（以 Wei 為單位，亦即 $10^{-18}$ ETH）。對一個新的驗證者而言，這通常會是 32&nbsp;ETH，但可以更多或更少。它必須是：
    - 至少一 ETH，
    - 一個整數的 Gwei[^fn-gwei]，以及
    - 少於 $2^{64}$ Gwei，也就是 184 億 ETH。

最後這個條件形式上是為了避免讓共識層的一個 `uint64` 溢位，但在實務上似乎有點多餘。

[^fn-gwei]: 一個 Gwei 是 $10^9$ Wei，或 $10^{-9}$ ETH，是共識層上的記帳單位。

```solidity
        // Emit `DepositEvent` log
        bytes memory amount = to_little_endian_64(uint64(deposit_amount));
        emit DepositEvent(
            pubkey,
            withdrawal_credentials,
            amount,
            signature,
            to_little_endian_64(uint64(deposit_count))
        );
```

合約現在發出一個事件日誌（收據）。共識層就是透過這些收據撿起關於新存款的資訊。在完成所有檢查之前就發出日誌看起來有點奇怪（我們還有幾個 `require` 要通過），但如果交易回退了，信標鏈也會回退這個事件日誌，所以提早發出它並沒有真正的害處。

關於收據的更多細節見[下文](#deposit-receipts)。

```solidity
        // Compute deposit data root (`DepositData` hash tree root)
        bytes32 pubkey_root = sha256(abi.encodePacked(pubkey, bytes16(0)));
        bytes32 signature_root = sha256(abi.encodePacked(
            sha256(abi.encodePacked(signature[:64])),
            sha256(abi.encodePacked(signature[64:], bytes32(0)))
        ));
        bytes32 node = sha256(abi.encodePacked(
            sha256(abi.encodePacked(pubkey_root, withdrawal_credentials)),
            sha256(abi.encodePacked(amount, bytes24(0), signature_root))
        ));

        // Verify computed and expected deposit data roots match
        require(node == deposit_data_root, "DepositContract: reconstructed DepositData does not match supplied deposit_data_root");
```

這裡我們有一個「手工」實作，為一個共識層的 [`DepositData`](/part3/containers/dependencies/#depositdata) 物件計算[雜湊樹根](/part2/building_blocks/merkleization/)。

```none
class DepositData(Container):
    pubkey: BLSPubkey
    withdrawal_credentials: Bytes32
    amount: Gwei
    signature: BLSSignature  # Signing over DepositMessage
```

沿用 [Merkle 化](/part2/building_blocks/merkleization/)一章的同樣風格，我們可以用下面的示意圖來說明這個過程。稍微傷一下腦筋，要把它對應到程式碼中那一團亂的 `sha256` 呼叫並不太難。

<a id="img_deposits_withdrawals_deposit_data_root"></a>
<figure class="diagram" style="width: 100%">

![一張示意圖，顯示一個 `DepositData` 物件的雜湊樹根如何從它的成員計算出來。](images/diagrams/deposits-withdrawals-deposit-data-root.svg)

<figcaption>

每個方塊是一個 32 位元組的分塊，可能以零填補（在 $S{(Pubkey)}_2$ 與 $S(Amount)$ 的情況下）。Merkle 化就是「以二元樹的形式，反覆地把成對的分塊一起雜湊，直到抵達根部」、從而找出雜湊樹根的過程。

</figcaption>
</figure>

在這裡這麼做的唯一原因，是把它當作一種校驗碼。質押者提供 `deposit_data_root`，那是他們從輸入資料獨立計算出的存款根。合約重新計算它，以確保它與所提供的資料相符。

`deposit_data_root` 就是那個會作為一個新的葉被插入 Merkle 樹的量（`node`），它構成了共識層上「驗證一筆存款」的一部分。

```solidity
        // Avoid overflowing the Merkle tree (and prevent edge case in computing `branch`)
        require(deposit_count < MAX_DEPOSIT_COUNT, "DepositContract: merkle tree full");

        // Add deposit data root to Merkle tree (update a single `branch` node)
        deposit_count += 1;
        uint size = deposit_count;
        for (uint height = 0; height < DEPOSIT_CONTRACT_TREE_DEPTH; height++) {
            if ((size & 1) == 1) {
                branch[height] = node;
                return;
            }
            node = sha256(abi.encodePacked(branch[height], node));
            size /= 2;
        }
        // As the loop should always end prematurely with the `return` statement,
        // this code should be unreachable. We assert `false` just to be safe.
        assert(false);
    }
```

<a id="updating_branch"></a>

最後，我們必須更新 Merkle 樹。

增量式 Merkle 樹一個非常酷的特性是：我們不僅能藉由只維護 `branch` 中的 32 個值來持續維護它的根，而且當我們插入一個新的葉值時，我們只需更新 `branch` 的_單一一個值_。

這並不顯而易見，但我們可以如下推導出來。要看更正式的解釋與分析，請見 Franck Cassez 的論文[《以 Dafny 驗證增量式 Merkle 樹演算法》](https://arxiv.org/pdf/2105.06009)。

考慮從相鄰的葉到根的路徑：從葉 $j - 1$ 出發的路徑 $P$，以及從葉 $j$ 出發的路徑 $Q$，其中 $j$ 是 `deposit_count`。超過某個層級 $i$ 之後，路徑 $P$ 與 $Q$ 會收斂並造訪相同的節點。在層級 $i$，路徑 $P$ 會造訪一個左節點（此前只造訪過右節點），而路徑 $Q$ 會造訪一個右節點（此前只造訪過左節點）[^fn-binary-arithmetic]。

[^fn-binary-arithmetic]: 如果從思考路徑還看不清楚，那就考慮二進位數。如果 $j-1$ 是 `0111`，那麼 $j$ 就是 `1000`。零代表左節點，一代表右節點。

簡言之：

  - 路徑 $P$ 會由 $(i-1)$ 個右節點構成，後面跟著一個左節點，再跟著一段與 $Q$ 共享的尾段。
  - 路徑 $Q$ 會由 $(i-1)$ 個左節點構成，後面跟著一個右節點，再跟著一段與 $P$ 共享的尾段。

路徑 $Q$ 就是 [`get_deposit_root()`](#get_deposit_root) 演算法中將被使用的那條路徑。

現在，依構造，$B_n$（`branch` 值）在樹中永遠代表左節點，而且只有在路徑 $Q$ 造訪一個右節點時才需要它們。

對於大於或等於 $i$ 的層級——路徑 $P$ 與 $Q$ 在此重合——所造訪的節點要嘛是左節點，這種情況下 $B_n$ 值無關緊要；要嘛是右節點，這種情況下 $B_n$ 值不變，因為它是從一棵「葉未曾改變」的子樹計算出來的。所以對於 $n > i$，$B_n$ 不需要更新。

至於 $n < i$ 的層級，所有的 $Q_n$ 都是左節點，因此 $B_n$ 無關緊要。所以唯一需要更新的 $B_n$ 就是 $B_i$。其直覺是：由於二進位遞增的運作方式，每次我們需要一個新的 $B_n$ 時，它都已被前一次的插入「恰好及時地」更新過了。

<a id="img_deposits_withdrawals_update_branch"></a>
<figure class="diagram" style="width: 100%">

![一張示意圖，顯示當一個新的葉被附加時 `branch` 如何被更新。](images/diagrams/deposits-withdrawals-update-branch.svg)

<figcaption>

我們剛在位置 $j$ 插入了一個葉。下次 `get_deposit_root()` 被呼叫時，它會從 $j+1$ 走過路徑 $Q$，而此前它從 $j$ 走過了 $P$。這些路徑在高度 $i + 1$ 處收斂。對於 $n < i$，路徑 $Q$ 完全是左節點，所以 $B_n$ 無關緊要。對於 $n > i$，$B_n$ 要嘛不變、要嘛無關緊要。所以我們只需把 $B_i$ 更新為 $B_i'$。

</figcaption>
</figure>

##### `supportsInterface`

```solidity
    function supportsInterface(bytes4 interfaceId) override external pure returns (bool) {
        return interfaceId == type(ERC165).interfaceId || interfaceId == type(IDepositContract).interfaceId;
    }
```

這是基於 [ERC-165](https://eips.ethereum.org/EIPS/eip-165) 的標準程式碼，它讓呼叫端的應用程式得以根據給定的函式選擇器 `interfaceID`，以程式化的方式偵測該合約是否支援某個函式介面。

例如，根據[以太坊 ABI](https://docs.soliditylang.org/en/develop/abi-spec.html#function-selector)，`get_deposit_count()` 的函式選擇器是 `0x621fd130`。因此，呼叫 `supportsInterface(0x621fd130)` 會回傳 `true`。

我不知道為存款合約實作這個有什麼理由，但我想這麼做被認為是良好的實務做法。

##### `to_little_endian_64`

```solidity
    function to_little_endian_64(uint64 value) internal pure returns (bytes memory ret) {
        ret = new bytes(8);
        bytes8 bytesValue = bytes8(value);
        // Byteswapping during copying to bytes.
        ret[0] = bytesValue[7];
        ret[1] = bytesValue[6];
        ret[2] = bytesValue[5];
        ret[3] = bytesValue[4];
        ret[4] = bytesValue[3];
        ret[5] = bytesValue[2];
        ret[6] = bytesValue[1];
        ret[7] = bytesValue[0];
    }
```

這在 `get_deposit_root()`、`get_deposit_count()` 中，以及發出 `DepositEvent` 日誌時被使用。這些全都會被共識層所消費，而共識層對 SSZ 整數[使用小端](/part3/config/constants/#endianness)編碼。

```solidity
}
```

我們就完成了。

#### 存款收據

對於存款合約所接受的每一筆存款，它都會發出一份收據（也稱為日誌或事件[^fn-receipts-naming]），這份收據是透過一個 EVM `LOG1` 操作碼產生的。

[^fn-receipts-naming]: 這些東西的命名真的一團亂。我相信 Eth1 的日誌、事件與收據全都是同一回事。Etherscan 兩面下注，把它們稱為「交易收據事件日誌」（Transaction Receipt Event Logs）。

這份收據有單一一個主題（topic），即 `DepositEvent` 的簽名：<span class="wrap">`0x649bbc62d0e31342afea4e5cd82d4049e7e1ee912fc0889aa790803be39038c5`</span>，等於 `keccak256("DepositEvent(bytes,`<wbr/>`bytes,`<wbr/>`bytes,`<wbr/>`bytes,`<wbr/>`bytes)")`。

這份收據的資料是 `pubkey`、`withdrawal_credentials`、`amount`、`signature` 與 `deposit_count` 的 576 位元組 ABI 編碼，在需要之處轉換成小端。這裡有[一個範例](https://etherscan.io/tx/0xa41ae80276c837f3855e109c3bbba89bb6078215f86ccc4b981a4930858d3f3a#eventlog)。

<details>
<summary>收據資料範例</summary>

第一欄是第二欄中資料起始處的十六進位位元組位置。

```none
# Pointer to pubkey: 0x0a0
000  00000000000000000000000000000000000000000000000000000000000000a0

# Pointer to withdrawal_credentials: 0x100
020  0000000000000000000000000000000000000000000000000000000000000100

# Pointer to amount: 0x140
040  0000000000000000000000000000000000000000000000000000000000000140

# Pointer to signature: 0x180
060  0000000000000000000000000000000000000000000000000000000000000180

# Pointer to deposit_count: 0x200
080  0000000000000000000000000000000000000000000000000000000000000200

# Length of pubkey: 48 bytes
0a0  0000000000000000000000000000000000000000000000000000000000000030

# Pubkey data, padded with 16 zero bytes
0c0  b73fe99acbf91f0032ae95c3ed0d663ea246d02332373e101ff5c7ed520ce098
0e0  652de3eab056a9889bb3d05d734be21400000000000000000000000000000000

# Length of withdrawal_credentials: 32 bytes
100  0000000000000000000000000000000000000000000000000000000000000020

# Withdrawal credentials (0x01 type)
120  010000000000000000000000e637a2acbc531531700fcb7d2ed7e6d96ed8bbe8

# Length of amount: 8 bytes
140  0000000000000000000000000000000000000000000000000000000000000008

# Amount, little-endian encoded. 0x0773594000 = 32,000,000,000
160  0040597307000000000000000000000000000000000000000000000000000000

# Length of signature: 96 bytes
180  0000000000000000000000000000000000000000000000000000000000000060

# Signature data
1a0  b4a7e1546b13be69d31849b4302d870a04867b9de73a973794f8be88c25dc71f
1c0  c3440141c33cf3fbf2dea328179c89550f4e19cad118dd962b07a7c40a3aa8ac
1e0  eaded660edb6e030df48074ddfbe70b26d0e9db1c3be28afc0b47096aab7a616

# Length of deposit_count: 8 bytes
200  0000000000000000000000000000000000000000000000000000000000000008

# Deposit count, little-endian. 0x0a7b1a = 686,874
220  1a7b0a0000000000000000000000000000000000000000000000000000000000
```

</details>

共識客戶端可以透過標準的 [`eth_getLogs`](https://docs.infura.io/infura/networks/ethereum/json-rpc-methods/eth_getlogs) RPC 方法，向它所連接的執行客戶端索取這些收據，並依存款合約位址、區塊編號與事件主題進行過濾。共識層就是這樣得知新存款的細節的。

在這裡使用事件日誌是一種最佳化。存款合約大可改為儲存 Merkle 樹的所有葉，並透過一個 `eth_call` 方法把它們提供出來。然而，由於日誌不被儲存在鏈的狀態中，只儲存在區塊歷史中，使用它們要比把那些葉儲存在合約的狀態中便宜得多。然而，這對「我們必須留存的歷史量」加上了一個約束——我們現在不能丟棄存款合約部署之前的區塊歷史。一個新啟用的共識客戶端，需要存取完整的收據歷史，才能重建它對 Merkle 樹的內部看法，即使它能夠對它的信標狀態進行檢查點同步。為求方便，某些客戶端現在支援從 Merkle 樹的一份[存款快照](https://github.com/ConsenSys/teku/pull/5954)開始，這份快照可以與其他客戶端共享，方式與[檢查點狀態](https://eth-clients.github.io/checkpoint-sync-endpoints/)大致相同。這讓想這麼做的人得以積極地修剪區塊歷史。

### 存款處理 <!-- /part2/deposits-withdrawals/deposit-processing/ -->

<div class="summary">

  - 共識層在一段 8 小時的延遲之後，以一個 2048 時段的投票期，對存款合約的狀態做出承諾。
  - 這段延遲與投票在合併之後不再有必要，將來可能被移除。
  - 當一個新的存款根經投票被採納時，提議者必須把存款納入區塊。
  - 區塊提議者針對合約的存款根，為該存款做出一份所有節點都能驗證的納入證明。
  - 對新公鑰的存款會建立新的驗證者記錄。
  - 對既有公鑰的存款會為驗證者的餘額加值。

</div>

#### 概觀

前一節談[存款合約](/part2/deposits-withdrawals/contract/)，涵蓋了存款在執行層上如何被處理。現在我們會看它們如何被交接給共識層——質押這檔事實際上就在那裡發生。一筆（有效的）進入執行層存款合約的存款，要嘛在共識層上建立一個新的驗證者，要嘛為一個既有驗證者的餘額加值。

存款資訊從執行層轉移到共識層有兩種方式。一種是投票過程，共識層藉此對「存款合約在某個特定執行層區塊高度的狀態」達成一致。另一種是驗證者直接從它們所連接的 Eth1 客戶端匯入存款收據，它們會把這些收據納入區塊，並用它們來維護自己那一份存款 Merkle 樹的副本。

<a id="img_deposits_withdrawals_eth_calls"></a>
<figure class="diagram" style="width: 90%">

![一張示意圖，顯示區塊提議者如何取得並使用來自存款合約的資料。](images/diagrams/deposits-withdrawals-eth-calls.svg)

<figcaption>

只有區塊提議者直接需要來自存款合約的資訊。它們藉由透過標準 JSON RPC 介面對執行層發出呼叫來取得這些資訊。提議者仰賴存款收據來把存款納入區塊，並仰賴它們來維護一份存款 Merkle 樹副本，以便為那些存款做出證明。提議者也為存款合約近期的某個狀態投下一票。

</figcaption>
</figure>

在合併之後，這兩種機制都算是某種遺留產物，雖然目前仍然存在。有一項提案打算在未來某個時點徹底翻修整個共識層存款處理工作流程，其形式是 [EIP-6110](https://eips.ethereum.org/EIPS/eip-6110)。

#### Eth1 投票與跟隨距離

如上所述，Eth1 投票是共識層合併前時代的遺留產物。它是信標鏈藉以對「以太坊 1.0 鏈的共同看法」、尤其是「存款合約狀態的共同看法」達成一致的途徑。在合併之後，執行酬載被包含在信標區塊中，依定義，所有正確的信標節點現在都對 Eth1 鏈有著共同的看法。

共識層對存款合約的共同看法，是由信標區塊提議者在一個 2048 時段（約 6.8 小時，見 [`EPOCHS_PER_ETH1_VOTING_PERIOD`](/part3/config/preset/#epochs_per_eth1_voting_period)）的重複週期上以多數投票形成的。每個提議者在它的區塊中納入一份 [`Eth1Data`](/part3/containers/dependencies/#eth1data) 投票，如下所示。

```python
class Eth1Data(Container):
    deposit_root: Root
    deposit_count: uint64
    block_hash: Hash32
```

最後一個欄位 `block_hash` 標識執行鏈上一個特定的區塊。`deposit_root` 與 `deposit_count` 欄位是藉由在那個區塊上呼叫存款合約的 [`get_deposit_root()`](/part2/deposits-withdrawals/contract/#get_deposit_root) 方法來設定的。共識客戶端是透過對執行客戶端的一般 JSON RPC [`eth_call`](https://ethereum.org/en/developers/docs/apis/json-rpc/#eth_call) 呼叫來做這件事的。

在區塊處理期間，信標鏈的 [`process_eth1_data()`](/part3/transition/block/#def_process_eth1_data) 函式為當前週期中所見的每一個 Eth1Data 實例的票數加總。第一組獲得超過 1024 個驗證者（超過該週期半數的區塊提議者）支持的 Eth1Data，會被立即更新到 `state.eth1_data` 而被採納。如果在投票期內沒有任何 Eth1Data 投票達到門檻，那麼 `state.eth1_data` 就不會被更新。即使新的 Eth1Data 提早經投票被採納，一個全新的投票期也只有在前一個投票期跑完它完整的 2048 時段歷程之後才會開始。

##### Eth1 投票

區塊提議者選擇它們的 Eth1 投票，方式如[誠實驗證者指南](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#eth1-data)中所描述。以下是這個過程的摘要。我們設 $S$ 為當前投票期開始的牆鐘時間。那 $8\ \text{小時}$ 來自 [`ETH1_FOLLOW_DISTANCE`](/part3/config/configuration/#eth1_follow_distance)（2048 個 Eth1 區塊）乘以 [`SECONDS_PER_ETH1_BLOCK`](/part3/config/configuration/#seconds_per_eth1_block)（在工作量證明下設為 14，作為一個近似的平均值）[^fn-28672-seconds]。

[^fn-28672-seconds]: 這實際上是 28,672 秒，但 8 小時對於說明的目的已夠接近了。朋友之間，差個 128 秒算什麼呢？

1. 首先，向 Eth1 客戶端索取所有時間戳 $t$ 落在區間 $(S - 2\times 8\ \text{小時}) \le t \le (S - 8\ \text{小時})$ 內的 Eth1 區塊。
2. 過濾掉任何存款計數小於 `state.eth1_data.deposit_count` 的區塊：這些我們已經看過了。
3. 提議者的預設投票會是這段期間內最後一個區塊的 Eth1Data，或者如果該清單是空的（因為 Eth1 已停擺），則是前一個投票期的勝出投票。
4. 我們力求盡快達成一致，所以一個誠實的提議者會丟棄任何「在當前週期中尚未被其他提議者投過票」的 Eth1Data。
5. 最後，誠實的提議者會為「在剩下的清單中已獲得最大支持」的那個 Eth1Data 投下一票。如果那份清單是空的（例如，若它是某個投票期中的第一個提議者），它就投下它的預設投票。

這個演算法多年來已經過大幅修整。據傳，多年來 Eth1 資料投票一直是測試網上大量問題的來源。它似乎很難做對，大概是因為它很難測試。把 Eth1Data 投票做對也不受協定激勵。相反地，它還受到些微的反向激勵，因為迎入新的驗證者會稀釋既有驗證者的獎勵。無論如何，看到這整套東西被移除會是件好事。

##### Eth1 跟隨距離

出現在上文中的，是一段 8 小時的延遲，[`ETH1_FOLLOW_DISTANCE`](/part3/config/configuration/#eth1_follow_distance) ` * ` [`SECONDS_PER_ETH1_BLOCK`](/part3/config/configuration/#seconds_per_eth1_block)，共識層在此延遲之後才會去考慮存款合約的狀態。

這段延遲有兩個作用。在工作量證明之下，鏈頂端附近的區塊總是有可能被重組掉。要是信標鏈納入了之後被回退的存款，那會非常糟糕——人們甚至可能試圖對共識層進行「雙重花費」。

就一切實務目的而言，幾個區塊的延遲大概就足以對付這一點，因為工作量證明下的以太坊從未遭受過長於兩三個區塊的回退。把跟隨距離設得長達 8 小時，更多是為了在 Eth1 鏈上發生可能影響存款流程的事件（例如鏈分裂）時，給開發者足夠的時間去回應。無論如何，這段延遲現在是多餘的，因為在合併之後，信標鏈與執行鏈是步調一致地移動的。

這一切的結果是：從把一筆存款送往存款合約，到共識層處理那筆存款，兩者之間的絕對最短時間間隔約為 11.4 小時：8 小時來自跟隨距離，3.4 小時是投票期的一半，即取得多數投票所需的最少時間。假設投票運作良好，平均時間會是 17 小時多一點。這還不包括後續等待存款被納入區塊、驗證者在啟用佇列中等待等等的時間。

關於 Eth1 跟隨距離與 Eth1 投票期長度的深入分析，請見 Mikhail Kalinin 的 Ethresear.ch 文章[《通往 Eth1 最終性之路》](https://ethresear.ch/t/on-the-way-to-eth1-finality/7041?u=benjaminion)。請注意，自那篇文章寫成以來，跟隨距離與投票期的長度都已加倍。

#### 存款的納入

假設新的 Eth1Data 已經投票被採納，信標狀態中的 `deposit_count` $n$ 取代了先前的計數 $m < n$。這意味著後續的區塊提議者有 $n - m$ 筆新的存款要納入區塊。

Eth1Data 中的 `deposit_root` 是 $n$ 筆存款之後存款 Merkle 樹的根。區塊提議者必須構造證明，證明存款 $m + 1$、$m + 2$、$\dots$、$n$ 被包含在那個 Merkle 根中：也就是在 Merkle 樹中的納入證明。

為了做到這一點，每個驗證者根據它從所連接的 Eth1 客戶端下載的存款收據，維護它自己的存款 Merkle 樹。要構造一份「存款 $m + 1$ 被包含在這棵樹中」的證明，我需要已經建好那棵含有全部 $n$ 筆存款的樹。然後我就能輕鬆地提供從葉 $m + 1$ 到已知 `deposit_root` 值的 [Merkle 分支](https://pangea.cloud/docs/audit/merkle-trees)。

信標區塊提議者必須以連續的順序，把所有可取得的存款連同它們的 Merkle 納入證明一起納入，上限為 [`MAX_DEPOSITS`](/part3/config/preset/#max-operations-per-block)。如果一個區塊未能以正確的順序納入所有可取得的存款，那麼整個區塊就是無效的。

為每一筆存款而被納入提議者信標區塊的實際資料，是一個 [`Deposit`](/part3/containers/operations/#deposit) 物件，

```python
class Deposit(Container):
    proof: Vector[Bytes32, DEPOSIT_CONTRACT_TREE_DEPTH + 1]  # Merkle path to deposit root
    data: DepositData
```

其中 [`DepositData`](/part3/containers/dependencies/#depositdata) 如下所示，

```python
class DepositData(Container):
    pubkey: BLSPubkey
    withdrawal_credentials: Bytes32
    amount: Gwei
    signature: BLSSignature
```

每個區塊至多可納入 [`MAX_DEPOSITS`](/part3/config/preset/#max-operations-per-block)（16）個這樣的物件。

#### 存款驗證

存款在區塊處理期間，由所有節點在 [`process_deposit()`](/part3/transition/block/#def_process_deposit) 與 [`apply_deposit()`](/part3/transition/block/#def_apply_deposit) 中驗證。此外，「區塊含有預期數量之存款」（`MAX_DEPOSITS` 與剩餘待處理存款數兩者中較小的那個）的檢查，在 [`process_operations()`](/part3/transition/block/#def_process_operations) 中進行。

對於每一筆存款，第一件要檢查的事是它的 Merkle 納入證明。[驗證是針對](/part3/helper/predicates/#def_is_valid_merkle_branch)經投票被採納之 Eth1Data 中的存款根來進行的。如果一筆存款通過了檢查，它就證明了它被包含在存款合約的樹中相同的葉位置上。如果這項檢查對任何一筆存款失敗，那麼整個區塊就是無效的。

當存款是給一個新的驗證者時——也就是它的公鑰在驗證者集合中尚不存在——那麼這筆存款的簽章就會被驗證。簽章驗證證明了該公鑰屬於一把存款者持有的、真正、已知的祕密金鑰。重要的是，一筆簽章無效的存款並不會使整個區塊無效。它只是被忽略，處理繼續進行下去。這是因為存款合約無法驗證簽章，所以它的 Merkle 樹中有可能存在無效的存款。

#### 新的驗證者

如果存款資料中的公鑰在[驗證者註冊表](/part3/containers/state/#registry)中尚不存在，那麼就會建立一個新的驗證者記錄，並把存款金額記入該驗證者的帳戶。存款金額通常會是啟用一個驗證者所需的完整 32&nbsp;ETH，但不一定。稍後，在紀元結束時，該驗證者的[有效餘額](/part2/incentives/balances/)會被計算——當有效餘額首次變為 32&nbsp;ETH 時，該驗證者就會被排入啟用佇列；否則該帳戶就只會閒置在那裡不活躍，直到其有效餘額透過一筆加值存款被提升到 32&nbsp;ETH。

該驗證者的提領憑證也會在此時被設定。如果它們是 `0x01` 的 Eth1 提領憑證，那麼它們是永久的，將來無法更改。如果它們是 `0x00` 的 BLS 提領憑證，那麼它們之後可以更改一次，改為 `0x01` 憑證。關於這一點的更多內容見[下一節](/part2/deposits-withdrawals/withdrawal-processing/#withdrawal-credentials)。

#### 驗證者加值

也可以為先前已存在的驗證者做出加值存款。任何人都可以為任何驗證者這麼做。加值存款的結構與一般存款完全相同，差別只在於加值存款的 BLS 簽章不會被檢查，提領憑證也會被忽略。

最低加值金額是 1&nbsp;ETH。如果一個驗證者的有效餘額已掉到最大值 32&nbsp;ETH 以下，一個人可能會想送一筆加值。由於大部分獎勵與有效餘額成比例，這樣一個驗證者的表現會偏低。例如，在有效餘額為 31&nbsp;ETH 的情況下，你的預期獎勵會減少約 3%，而加值以維持 32&nbsp;ETH 的有效餘額可能是值得的。迄今做出的加值不多，但有一些[例子](https://etherscan.io/tx/0x3e68702566edee0061344eb99c484b4fac8800db082980bb6027d1dca09f5812)。

如前所述，隨著時間推移逐步累積一個驗證者的質押是有可能的：先做一筆少於 32&nbsp;ETH 的初始存款，再做一筆或多筆加值存款。當該驗證者的有效餘額達到 32&nbsp;ETH 時，它就會變得活躍。然而，如果你打算這麼做，當最後一筆加值是 1&nbsp;ETH 時，要當心一個牽涉遲滯的棘手[邊角案例](/part2/incentives/balances/#an-edge-case)。

#### 另見

如今大多只剩歷史價值，Mikhail Kalinin 的文章[《通往 Eth1 最終性之路》](https://ethresear.ch/t/on-the-way-to-eth1-finality/7041?u=benjaminion)是對「從 Eth1 到 Eth2 的存款橋」的一份典範性分析。

存款相關的規格函式與資料結構如下。

  - [存款合約](/part2/deposits-withdrawals/contract/)。
  - 常數 [`ETH1_FOLLOW_DISTANCE`](/part3/config/configuration/#eth1_follow_distance)、[`SECONDS_PER_ETH1_BLOCK`](/part3/config/configuration/#seconds_per_eth1_block)、[`EPOCHS_PER_ETH1_VOTING_PERIOD`](/part3/config/preset/#epochs_per_eth1_voting_period) 與 [`MAX_DEPOSITS`](/part3/config/preset/#max-operations-per-block)。
  - [`Eth1Data`](/part3/containers/dependencies/#eth1data)、[`DepositData`](/part3/containers/dependencies/#depositdata) 與 [`Deposit`](/part3/containers/operations/#deposit) 容器。
  - 函式 [`process_eth1_data()`](/part3/transition/block/#def_process_eth1_data)、[`process_deposit()`](/part3/transition/block/#def_process_deposit)、[`is_valid_merkle_branch()`](/part3/helper/predicates/#def_is_valid_merkle_branch) 與 [`apply_deposit()`](/part3/transition/block/#def_apply_deposit)，全都是[區塊處理](/part3/transition/block/)的一部分。
  - [誠實驗證者指南](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#eth1-data)中的 Eth1 資料處理。

### 提領 <!-- /part2/deposits-withdrawals/withdrawal-processing/ -->

<div class="summary">

  - 共識層提領在 Capella 升級中被啟用。
  - 一個驗證者必須擁有 Eth1 提領憑證，才能從提領中受益。
  - 從 BLS 憑證到 Eth1 憑證的一次性更新是可行的。
  - 提領是自動且週期性的。
  - 每個區塊至多可處理 16 筆提領。
  - 一筆提領可能是部分的（對活躍的驗證者）或完整的（對已退出的驗證者）。

</div>

#### 背景

從共識層做出提領的能力，在合併之後的第一次升級——[Capella 升級](/part4/history/capella/)——中被啟用。

顯然，一個功能完整的權益證明系統，既需要質押的辦法，也需要解除質押的辦法。然而，在信標鏈生命的前 29 個月裡，只有質押是可行的。所有的質押，以及所有賺得的獎勵，都被鎖在共識層之內。

要在合併之前提供提領，本會需要一座從信標鏈通往以太坊工作量證明鏈的[橋](https://ethresear.ch/t/two-way-bridges-between-eth1-and-eth2/6286?u=benjaminion)，也許是在 Eth1 那一側透過某種信標鏈輕客戶端的實作。這被認為是一個複雜的專案，只會延誤合併。

基於類似的原因，我們在合併當時也沒有啟用提領。合併本身就很複雜，並帶有風險。我們盡力把它簡化、把它的風險降到最低，這包括了再一次延後提領。

最終，為了履行核心開發者對以太坊社群的軟性承諾，提領在合併之後的第一次升級 Capella 中、於 2023 年 4 月 12 日成功被啟用。

對於「讓信標鏈以太幣得以在執行鏈上被取回」，曾考慮過兩種做法。

第一種設計是[拉式提領](https://github.com/ethereum/consensus-specs/pull/2759)（pull withdrawal）。在一個驗證者退出之後，共識層會建立一份收據，質押者可以把它作為一筆一般的以太坊交易手動提交給執行層，以便取回所質押的以太幣與獎勵。以一種對存款的鏡像方式，共識層會維護一棵提領收據的 Merkle 樹，把它的根揭露給執行層，使得提領收據在那裡被提交時能被驗證。部分提領在那項工作中並未真正得到處理。

不過，被採用的設計是[推式提領](https://github.com/ethereum/consensus-specs/pull/2836)（push withdrawal），如下所述。推式提領自動發生，不需要質押者採取任何行動。這種做法提供了更好的使用者體驗，而且幾乎不需要增加信標狀態的大小。它善用了合併之後的 [Engine API](https://github.com/ethereum/execution-apis/blob/main/src/engine/common.md)，作為執行層與共識層之間的橋。

#### 提領憑證

當信標鏈被構思出來時，它原本只是規模大得多的以太坊 2.0 專案的第一階段（Phase&nbsp;0）。當時，既有的以太坊 1.0 鏈會發生什麼事、Eth2.0 中會實作哪種帳戶、會使用哪種簽章方案等等，全都完全不明朗。

有鑑於這些未知數，我們決定把提領憑證實作成一項承諾：將來能夠以某種方式提領，即使我們對那會是什麼樣子幾乎毫無頭緒。質押者會保管一把 BLS 提領金鑰，並能夠透過 BLS 提領憑證證明對該驗證者餘額的所有權。

信標鏈上線時只有 BLS 提領憑證，所有早期的驗證者都使用這種。Eth1 提領憑證在 2021 年 2 月——信標鏈生命才大約三個月——時於規格中[被承諾](https://github.com/ethereum/consensus-specs/pull/2149)。由於做出存款時不會對提領憑證做任何驗證，質押者仍可以自由地使用他們偏好的任一種。在 Capella 升級的時間點，有 322,491 個驗證者（56.9%）擁有 BLS 憑證，244,653 個（43.1%）擁有 Eth1 憑證[^fn-check-your-creds]。

[^fn-check-your-creds]: 你可以透過你的驗證者在 [Beaconcha.in](https://beaconcha.in) 瀏覽器上的頁面，查看它擁有哪種類型的憑證。前往「Deposits」分頁。如果你的憑證以 `0x00` 開頭，那它們就是 BLS；如果以 `0x01` 開頭，那它們就是 Eth1。

##### BLS 提領憑證

BLS 提領憑證由於它們的[前綴](/part3/config/constants/#withdrawal-prefixes)，常被稱為 `0x00` 憑證。你可以把它們想成第零版憑證。一個 BLS 提領憑證，是一把 48 位元組 BLS 公鑰的 32 位元組雜湊值，其第一個位元組被替換為 `0x00`。

這是[零號驗證者](https://beaconcha.in/validator/0#deposits)原本的 BLS 提領憑證。注意開頭的 `0x00` 位元組。

```none
0x00f50428677c60f997aadeab24aabf7fceaef491c96a52b463ae91f95611cf71
```

其構想是：質押者除了他們平常的簽章金鑰之外，還有第二把 BLS 祕密金鑰，即一把提領金鑰。協定開發者所做出的承諾是：這把提領金鑰將來可以用來為一份憑證變更訊息簽章。BLS 提領憑證確保那份訊息上所宣稱的公鑰，與最初做出的存款相符，所以只有原本的存款者能存取質押與獎勵。

把提領金鑰與一般的簽章金鑰分開，有許多好處。最主要的是，它把質押的所有權（由提領金鑰掌控）與質押的管理（由簽章金鑰掌控）分開。這讓「非託管」（non-custodial）質押服務得以出現，在這種服務中，質押服務商用簽章金鑰進行日常運作，但由於個別質押者保有提領金鑰，他們對質押或獎勵並無所有權。它也讓提領金鑰得以離線保管在冷儲存中，而簽章金鑰維持在線上、保持「熱」狀態。

為了便於復原，BLS 提領金鑰可以使用一個略微不同的衍生路徑，從與簽章金鑰相同的助記詞產生出來，如 [ERC-2334](https://eips.ethereum.org/EIPS/eip-2334#validator-keys) 中所描述。這就是 [`staking-deposit-cli` 工具](https://github.com/ethereum/staking-deposit-cli)所做的事。

##### Eth1 提領憑證

除非你出於某種原因想把你的以太幣鎖在共識層上，否則現在每個人都應該使用 Eth1 提領憑證。它們要嘛在質押時設定[^fn-cli-tool-eth1-creds]，要嘛藉由發送一份「BLS 轉執行層」（BLS to execution change）變更訊息來設定。

[^fn-cli-tool-eth1-creds]: 使用 [`staking-deposit-cli`](https://github.com/ethereum/staking-deposit-cli) 做出存款時要小心。除非你指定 `--eth1_withdrawal_address` 命令列參數，否則它會（默默地）預設為 BLS 提領憑證。

一個 Eth1（執行層）提領憑證有[前綴](/part3/config/constants/#withdrawal-prefixes) `0x01`，後面跟著十一個零位元組，再跟著一個一般以太坊位址的 20 個位元組。那個位址就是所有來自提領的以太幣將被送往之處。

這是[零號驗證者](https://beaconcha.in/validator/0#deposits)目前的 Eth1 提領憑證。注意開頭的 `0x01` 位元組。

```none
0x0100000000000000000000000d369bb49efa5100fd3b86a9f828c55da04d2d50
```

提領位址可以是一個一般的以太坊帳戶（一個 EOA）或一個智慧合約。然而，當它是一個智慧合約時，在收到一筆提領給付時不會執行任何程式碼。這與透過轉帳收到以太幣不同，後者可能導致一個後備函式（fallback function）被呼叫。

##### 憑證變更

只有擁有 Eth1 提領憑證的驗證者才有資格進行提領。擁有 BLS 提領憑證的驗證者，需要發送一份提領憑證變更訊息來更新為 Eth1 憑證。在它們這麼做之前，它們的質押與獎勵仍鎖在共識層上。

更改提領憑證是一次性的操作。一個驗證者一旦擁有 Eth1 憑證，就不可能再有進一步的變更。提領給付位址一旦設定，唯一更改它的辦法，就是退出你的驗證者，再用新的憑證重新質押。

###### 做出一次憑證變更

驗證者擁有 BLS 提領憑證、希望改為 Eth1 憑證的質押者，必須向信標鏈發送一份用該驗證者的提領金鑰簽署的訊息。[`staking-deposit-cli`](https://github.com/ethereum/staking-deposit-cli) 與 [`ethdo`](https://github.com/wealdtech/ethdo) 工具都能夠產生這份訊息。這是一個直截了當的過程，需要該驗證者的公鑰、質押時所用的助記詞，以及該驗證者既有的提領憑證作為校驗碼。建議離線進行訊息的產生，因為在憑證變更完成之前，BLS 提領金鑰對駭客而言仍然極具價值。

憑證變更訊息一旦產生，就需要被上傳到一個信標節點，以便被廣播到網路。這可以透過任何信標節點的 [REST API](https://ethereum.github.io/beacon-APIs/#/Beacon/submitPoolBLSToExecutionChange) 來完成，或透過 Beaconcha.in 瀏覽器方便的已簽署訊息[提交服務](https://beaconcha.in/tools/broadcast)。

在訊息被上傳並廣播之後過一段時間，某個區塊提議者應當把這份憑證變更訊息納入一個信標區塊，供共識層處理。每個區塊至多可納入 [`MAX_BLS_TO_EXECUTION_CHANGES`](/part3/config/preset/#max_bls_to_execution_changes)（16）份這樣的訊息。

供參考，一份「BLS 轉 Eth1」憑證變更訊息有[下列內容](/part3/containers/operations/#blstoexecutionchange)。

```python
class BLSToExecutionChange(Container):
    validator_index: ValidatorIndex
    from_bls_pubkey: BLSPubkey
    to_execution_address: ExecutionAddress
```

###### 處理一次憑證變更

憑證變更訊息在區塊處理期間，由 [`process_bls_to_execution_change()`](/part3/transition/block/#def_process_bls_to_execution_change) 函式處理。

它檢查：

1. 該驗證者目前擁有 `0x00` BLS 憑證，
2. （從祕密提領金鑰所產生的）公開提領金鑰的雜湊值，與做出存款時所建立的提領憑證相符，以及
3. 訊息上的簽章針對所提供的公開提領金鑰驗證通過。

一旦確信一切正確，該驗證者的提領憑證就會被不可撤回地更新為 Eth1 提領憑證。該驗證者現在有資格接受自動推式提領，這些提領將被送往 `BLSToExecutionChange` 資料中所提供的 `to_execution_address`。

重申一次，更改提領憑證是一次性的過程。你只能從 BLS 憑證改為 Eth1 憑證。不退出驗證者並重新質押，是不可能更改 Eth1 憑證的。

#### 提領處理

如上所述，我們決定為提領採用一種「推式」機制。推式提領自動發生，不需要質押者的介入。每個區塊至多做出 [`MAX_WITHDRAWALS_PER_PAYLOAD`](/part3/config/preset/#max_withdrawals_per_payload)（16）筆共識層提領。

<!-- Number of validators -->

驗證者提領以輪詢（round-robin）的方式處理。從 Capella 升級時的 0 號驗證者開始，每處理一個區塊，共識層就依驗證者索引順序掃過驗證者集合，直到它找到 16 筆要納入的提領為止。下一個區塊提議者會從前一個提議者在驗證者集合中停下的地方接續，再掃描 16 筆進一步的提領，依此類推。如果每個驗證者都有資格進行提領，而且信標鏈表現完美，那麼掃過 576,000 個驗證者一整輪會花 5 天。也就是說，一個驗證者可以預期每 5 天收到一筆部分提領的給付。

##### 找出提領

為了找出它必須納入的提領，區塊提議者呼叫 [`get_expected_withdrawals()`](/part3/transition/block/#def_get_expected_withdrawals) 函式。這會回傳一份至多 `MAX_WITHDRAWALS_PER_PAYLOAD` 個 [`Withdrawal`](/part3/containers/dependencies/#withdrawal) 物件的清單，每個物件含有下列資訊。

```python
class Withdrawal(Container):
    index: WithdrawalIndex
    validator_index: ValidatorIndex
    address: ExecutionAddress
    amount: Gwei
```

`index` 欄位是迄今曾做出之先前提領的數量。它由 `state.next_withdrawal_index` 填入，每筆提領遞增一。它僅用於在執行層中唯一地索引提領。`validator_index` 當然就是那個「信標鏈餘額將被減少，且其 Eth1 提領位址（此處的 `address` 欄位）餘額將被增加」的驗證者。

提領清單是確定性地產生的。區塊提議者從 `state.next_withdrawal_validator_index` 的當前值開始，依次考慮各個驗證者。如果一個驗證者有資格進行提領，它就被加進清單，否則它就被跳過。當已加入 `MAX_WITHDRAWALS_PER_PAYLOAD` 筆提領，或已考慮過 `MAX_VALIDATORS_PER_WITHDRAWALS_SWEEP` 個驗證者時，清單就被回傳。如果碰到驗證者註冊表的尾端，搜尋就再次繞回到 0 號驗證者。

要有資格進行提領，一個驗證者必須已設定 [Eth1 提領憑證](#eth1-withdrawal-credentials)，並且下列其中一項也必須成立：

  - 該驗證者已退出、已變得可提領，並且有一個非零的餘額。這樣一個驗證者有資格進行[完整提領](#full-withdrawals)。
  - 該驗證者有一個 [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance)（32&nbsp;ETH）的[有效餘額](/part2/incentives/balances/)，以及一個高於它的實際餘額。這樣一個驗證者有資格進行[部分提領](#partial-withdrawals)。

這兩者可能同時為真，在這種情況下，第一項優先，會為該驗證者做出一筆完整提領。

通常會產生一份滿滿 16 筆提領的清單。然而，搜尋以「至多考慮 [`MAX_VALIDATORS_PER_WITHDRAWALS_SWEEP`](/part3/config/preset/#max_validators_per_withdrawals_sweep) 個驗證者」為界。如果碰到這個上限，產生的提領就會少於 16 筆。

[限制搜尋範圍](https://github.com/ethereum/consensus-specs/pull/3095)、而不掃過整個驗證者集合一整輪的原因，是為了對共識節點的計算負載設下界限。存取驗證者註冊表可能相當昂貴；一次無界限的掃描可能成為效能瓶頸。

有兩種情境下這個界限可能變得相關。第一是「驗證者註冊表中有長段區段，其中沒有任何驗證者升級到 Eth1 提領憑證」。這在 Capella 升級的時間點較令人擔憂，當時所有早期的驗證者都必然擁有 BLS 提領憑證。更有意思的是[怠惰洩漏](/part2/incentives/inactivity/)的可能性，它發生在鏈停止及時最終確定時。在一次怠惰洩漏期間，沒有驗證者收到證明獎勵，許多驗證者還收到額外的怠惰懲罰。會有非常少的餘額在增加——也許只有區塊提議者與同步委員會成員。在一次長時間的怠惰洩漏期間，有可能驗證者註冊表中有大段區段都沒有資格進行提領，這時提領掃描的界限就會被強制執行。

##### 執行提領

為了處理一筆提領，共識層與執行層必須仔細協調，這使得完整的往返有點曲折。步驟如下。

1. 信標區塊提議者藉由呼叫如上文所詳述的 [`get_expected_withdrawals()`](/part3/transition/block/#def_get_expected_withdrawals) 來組裝一份提領清單。
2. 信標區塊提議者透過 Engine API 把這份提領清單送往它所連接的執行客戶端。見誠實驗證者規格中的 [`prepare_execution_payload()`](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/capella/validator.md#executionpayload)。相關的 Engine API 資料結構是 [`PayloadAttributesV2`](https://github.com/ethereum/execution-apis/blob/main/src/engine/shanghai.md#payloadattributesv2)。
3. 執行客戶端回傳一個[執行酬載](https://github.com/ethereum/execution-apis/blob/main/src/engine/shanghai.md#executionpayloadv2)，其中包含這份提領清單，以及其他一切。
4. 區塊提議者把這個執行酬載納入它的信標區塊，並把它廣播到網路。
5. 收到這個區塊時，所有共識節點都從[執行酬載](/part3/containers/execution/#executionpayload)中萃取出提領清單，並呼叫 [`process_withdrawals()`](/part3/transition/block/#def_process_withdrawals) 來從驗證者的餘額中扣除提領金額。每個節點都各自獨立呼叫 [`get_expected_withdrawals()`](/part3/transition/block/#def_get_expected_withdrawals)，而只有當該信標區塊的提領清單相符時它才有效。
6. 共識節點把執行酬載送往它所連接的執行客戶端。執行客戶端會把這些提領與酬載中所有其他交易一起處理，並依需要遞增各 Eth1 提領位址。

提領處理在執行層的運作機制，在 [EIP-4895](https://eips.ethereum.org/EIPS/eip-4895) 中有所描述。提領交易在區塊中所有一般交易之後被處理。

如上所述，當 Eth1 帳戶餘額被遞增時，提領交易不會觸發智慧合約處理。這主要是為了避免會使整個過程複雜化的失敗（EVM 交易回退）。它也避免了對執行客戶端施加未知的負載。這麼做的好處是，提領是無 Gas 的，因此是免費的。接收帳戶的餘額會精確地增加與「從該驗證者的信標鏈餘額中扣除」等額的 ETH。

##### 部分提領與完整提領

一個驗證者可能有資格進行部分提領或完整提領。兩種類型誰也不比誰優先；在提領掃描期間考慮各驗證者時，它們是並行發生的。如果一個驗證者對兩者都有資格，就會執行一筆完整提領。

在這兩種情況下，都沒有最低提領金額——它可以是單一一個 Gwei，即信標鏈最小的記帳單位。不會為零金額建立提領。

###### 部分提領

部分提領構成了所處理之提領的大部分。隨著驗證者賺得獎勵，部分提領週期性地把驗證者多餘的餘額撇出來。

要有資格進行部分提領，下列各項全都必須為真。第二與第三項準則在 [`is_partially_withdrawable_validator()`](/part3/helper/predicates/#is_partially_withdrawable_validator) 述詞中被檢查。

  - 該驗證者擁有 [Eth1 提領憑證](#eth1-withdrawal-credentials)。
  - 該驗證者的有效餘額是 [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance)（32&nbsp;ETH）。
  - 該驗證者的實際餘額超過 `MAX_EFFECTIVE_BALANCE`。

部分提領的金額會是該驗證者超出 `MAX_EFFECTIVE_BALANCE` 的那部分餘額。

對驗證者有效餘額的這個條件，消除了一個邊角案例：一個驗證者有效餘額為 31&nbsp;ETH，但實際餘額超過 32&nbsp;ETH，這可能由於[遲滯](/part2/incentives/balances/#hysteresis)而產生。如果不套用這個有效餘額的條件，一個驗證者可能會由於其餘額不斷被撇出，而變得永遠無法（在沒有加值存款的情況下）重新獲得 32 ETH 的完整有效餘額。

###### 完整提領

完整提領發生在一個驗證者已退出驗證者集合、隨後變得可提領之後。一個驗證者通常在通過退出佇列之後約 [27 小時](/part3/config/configuration/#min_validator_withdrawability_delay)變得可提領，但一個被罰沒的驗證者要花[久得多](/part3/config/preset/#epochs_per_slashings_vector)的時間。

精確的準則在 [`is_fully_withdrawable_validator()`](/part3/helper/predicates/#is_fully_withdrawable_validator) 述詞中。下列各項全都必須成立。

  - 該驗證者擁有 [Eth1 提領憑證](#eth1-withdrawal-credentials)。
  - 該驗證者是可提領的（當前紀元大於或等於它的可提領紀元）。
  - 該驗證者有一個非零的餘額。

完整提領的金額會是該驗證者的全部餘額。

請注意，[並沒有旗標](https://github.com/ethereum/consensus-specs/pull/2836#discussion_r817657925)用以指出一個驗證者已被提領。這在原則上允許在一筆完整提領發生之後，為一個驗證者做出一筆加值存款，在這種情況下，另一筆完整提領就會發生，而那筆加值金額會被退回執行層。

#### 另見

Ethereum.org 的頁面有一個關於[提領的章節](https://ethereum.org/en/staking/withdrawals/)，另外還有一份獨立的[提領常見問答](https://notes.ethereum.org/@launchpad/withdrawals-faq)。兩者都有大量通往進一步資源的連結。

提領相關的規格函式與資料結構如下。

  - 常數 [`MAX_WITHDRAWALS_PER_PAYLOAD`](/part3/config/preset/#max_withdrawals_per_payload)、[`MAX_VALIDATORS_PER_WITHDRAWALS_SWEEP`](/part3/config/preset/#max_validators_per_withdrawals_sweep) 與 [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance)。
  - [信標狀態](/part3/containers/state/#withdrawals)中的 `next_withdrawal_index` 與 `next_withdrawal_validator_index`。
  - [`Withdrawal`](/part3/containers/dependencies/#withdrawal) 容器，以及 [`ExecutionPayload`](/part3/containers/execution/#executionpayload) 容器中的 `withdrawals` 清單。
  - [區塊處理](/part3/transition/block/)中的 [`get_expected_withdrawals()`](/part3/transition/block/#def_get_expected_withdrawals)、[`process_withdrawals()`](/part3/transition/block/#def_process_withdrawals)。
  - [述詞](/part3/helper/predicates/)中的 [`is_fully_withdrawable_validator()`](/part3/helper/predicates/#def_is_fully_withdrawable_validator)、[`is_partially_withdrawable_validator()`](/part3/helper/predicates/#def_is_partially_withdrawable_validator)。
  - 在 Capella [誠實驗證者指南](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/capella/validator.md#executionpayload)中準備 `ExecutionPayload`，以及 [Execution API](https://github.com/ethereum/execution-apis/blob/main/src/engine/shanghai.md#payloadattributesv2) 中的 `PayloadAttributesV2`。
  - [EIP-4895](https://eips.ethereum.org/EIPS/eip-4895)「以操作形式進行的信標鏈推式提領」涵蓋了執行層那一側。

以及憑證變更方面。

  - [常數](/part3/config/constants/)中的[提領前綴](/part3/config/constants/#withdrawal-prefixes)。
  - [`BLSToExecutionChange`](/part3/containers/operations/#blstoexecutionchange) 與 [`SignedBLSToExecutionChange`](/part3/containers/envelopes/#signedblstoexecutionchange) 容器。
  - [區塊處理](/part3/transition/block/)中的 [`process_bls_to_execution_change()`](/part3/transition/block/#def_process_bls_to_execution_change)。
  - [Beacon API](https://ethereum.github.io/beacon-APIs/#/Beacon/submitPoolBLSToExecutionChange) 的 `submitPoolBLSToExecutionChange` 方法。

## 激勵層 <!-- /part2/incentives/ -->

### 胡蘿蔔、棍子與猝死

無須許可的區塊鏈是加密經濟系統：密碼學在可能之處強制正確的行為；經濟學則在無法強制之處激勵正確的行為。我們所尋求的正確行為，大致對應到可用性與安全性。我們希望鏈持續取得進展，也希望鏈在一切合理的情況下都給出可靠、不自相矛盾的結果。

本章描述信標鏈用以激勵其參與者的經濟工具；密碼學那一面則在別處涵蓋。廣義地說，能幫助我們達成這些目標的工具有：(1) 對「有助於協定之行為」的獎勵，(2) 對「妨礙協定之行為」的懲罰，以及 (3) 對「看起來像是對協定發動攻擊之行為」的處罰。

工作量證明少數吸引人的面向之一，是它經濟模型的簡潔。礦工因為建立了被納入鏈上的區塊而收到區塊獎勵，並因為在它們的區塊中納入交易而收到費用。區塊獎勵來自新建立的代幣（發行），而交易費用來自先前已發行的代幣。並沒有明示的協定內懲罰或處罰。與「最重鏈」分叉選擇規則結合起來，這個簡單的模型已被證明極其穩健。以太坊&nbsp;1 用礦工的叔塊獎勵與 EIP-1559 費用燒毀機制增添了一點複雜性，但它在根本上仍然簡單，相當容易推理。

相比之下，以太坊&nbsp;2.0 權益證明協定運用了一整套不同的經濟激勵。我們會在接下來幾節把事情拆解成下列幾個要素。

1. 最根本的經濟組成部分是[質押](/part2/incentives/staking/)本身。
2. 在協定內，質押以驗證者的[餘額](/part2/incentives/balances/)來表示，尤其是一個稱為「有效餘額」的量，它才是「某個特定驗證者對協定有多少影響力」的實際量度。
3. 與工作量證明類似，協定發行新的代幣來提供我們正在討論的這些激勵。我們會在[發行](/part2/incentives/issuance/)一節看這一點。
4. 一整套[獎勵](/part2/incentives/rewards/)被用來激勵所期望的行為，例如發布信標區塊與及時的證明。
5. [懲罰](/part2/incentives/penalties/)被用來反向激勵不可取的行為，例如未能做出證明、或做出遲到或不正確的證明。
6. [怠惰洩漏](/part2/incentives/inactivity/)是信標鏈可能進入的一種特殊狀態，其中獎勵與懲罰會被修改，以遠遠更嚴厲地懲罰不參與。
7. [罰沒](/part2/incentives/slashing/)是對「以非常特定、看起來像攻擊的方式違反協定規則」的處罰。
8. 最後，我們以一則註記作結，談這些激勵的各個面向如何結合起來，使「信標鏈基礎設施的部署多樣化（[多樣性](/part2/incentives/diversity/)）」成為最安全的策略。

請注意，這幾節中的討論是孤立地考慮共識層。既然我們已在合併之後，這就不再是完整的全貌了。除了協定產生的獎勵之外，以太坊質押者現在還能從交易費小費，以及 [MEV](https://ethereum.org/en/developers/docs/mev/)（最大可萃取價值）中獲利。將來，他們也許能夠從[再質押](https://docs.eigenlayer.xyz/overview/readme)（restaking）中獲利。這一切都可能修改協定的激勵。例如，曾有一個驗證者讓自己[被罰沒](https://beaconcha.in/validator/552061)（代價是 1&nbsp;ETH），以[獲得約 2000 萬美元](https://collective.flashbots.net/t/post-mortem-april-3rd-2023-mev-boost-relay-incident-and-related-timing-issue/1540)的 MEV 收入，這在經濟上是理性的行為，儘管它這麼做時依協定規則而言是不誠實地行事。這些事物的影響是眾多討論、開發與辯論的主題，自成一本書都當之無愧。儘管如此，就本作的目的而言，我只聚焦於共識層的加密經濟堆疊。

#### 另見

Vlad Zamfir 關於 Casper 協定發展的回憶錄，不僅是極佳的讀物，也是對「設計一個權益證明協定的種種難題」的好引介。它們討論了許多設計決定的背景，這些決定最終導向我們今天所見的協定。[第 1 部](https://medium.com/@Vlad_Zamfir/the-history-of-casper-part-1-59233819c9a9)、[第 2 部](https://medium.com/@Vlad_Zamfir/the-history-of-casper-chapter-2-8e09b9d3b780)、[第 3 部](https://medium.com/@Vlad_Zamfir/the-history-of-casper-chapter-3-70fefb1182fc)、[第 4 部](https://medium.com/@Vlad_Zamfir/the-history-of-casper-chapter-4-3855638b5f0e)、[第 5 部](https://medium.com/@Vlad_Zamfir/the-history-of-casper-chapter-5-8652959cef58)。

接下來幾節中的許多素材，也涵蓋在 Chorus One 的 Umberto Natale 較近期的報告[《分析以太坊加密經濟學：驗證者的觀點》](https://docs.google.com/document/d/1r640UQOm2z-Q9nsJzqBq3BVgCtTL1_Yc7WnPp4jEBgk/edit)中。

### 質押 <!-- /part2/incentives/staking/ -->

<div class="summary">

  - 權益證明中的質押提供三樣東西：一個反女巫攻擊機制、一個問責機制，以及一個激勵對齊機制。
  - 32&nbsp;ETH 的質押規模，是網路開銷、驗證者數量與最終確定時間三者之間的取捨。
  - 與 Casper FFG 規則結合起來，質押提供了經濟性最終性：一個可量化的鏈安全性量度。

</div>

#### 引言

質押是以太坊&nbsp;2 協定的完整參與者所必須鎖定的存款。質押被永久地存放在以太坊鏈上的[存款合約](/part2/deposits-withdrawals/contract/)中，並反映於信標鏈上該驗證者記錄中的一個餘額。質押賦予一個驗證者提議區塊、為區塊與檢查點做出證明、以及參與同步委員會的權利，這一切都換取累積到它信標鏈餘額的獎勵。

在以太坊&nbsp;2 中，質押有三個關鍵的角色。

第一，質押是一個反女巫攻擊機制。以太坊&nbsp;2 是一個任何人都可以參與的無須許可系統。無須許可的系統必須找到某種方式來在其參與者之間分配影響力。在協定中建立一個身分必須有某種成本，否則個人就能廉價地建立大量的重複身分並壓垮鏈。在工作量證明鏈中，一個參與者的影響力與它的雜湊算力成比例，那是一種有限的資源[^fn-one-cpu-one-vote]。在權益證明鏈中，參與者必須質押一些鏈的代幣，那同樣是一種有限的資源。協定中每個質押者的影響力，與他們所鎖定的質押成比例。

[^fn-one-cpu-one-vote]: 在比特幣白皮書中，中本聰寫道：「工作量證明本質上是一 CPU 一票」，雖然 ASIC 與礦場早已顛覆了這一點。權益證明則是一質押一票。

第二，質押提供問責。在以太坊&nbsp;2 中，以有害的方式行事有直接的代價。特定類型的有害行為可以被唯一地歸因於做出它們的質押者，而他們的質押可以在一個稱為[罰沒](/part2/incentives/slashing/)的過程中被減少或整個取走。這讓我們得以用「攻擊者要做某件有害的事得花多少代價」來量化協定的[經濟性安全](#economic-finality)。

第三，質押對齊激勵。質押者必然擁有他們所守護之物的一部分，因而受到激勵去好好守護它。

#### 質押規模

以太坊&nbsp;2 中質押的規模是每個驗證者 32&nbsp;ETH。

這個數值是一種折衷。它試圖盡可能小，以容許廣泛的參與，同時又維持得夠大，使我們最終不會有太多驗證者。簡言之，如果我們降低質押額，我們可能就會迫使質押者在更高頻寬的網路上運行更昂貴的硬體，從而增強中心化的力量。

對於一條單體式（monolithic）[^fn-monolithic] L1 區塊鏈，驗證者數量在實務上的主要約束，是達成最終性所需的訊息傳遞開銷。如同其他 [PBFT](https://pmg.csail.mit.edu/papers/osdi99.pdf) 風格的共識演算法，Casper&nbsp;FFG 需要兩輪的全體對全體（all-to-all）通訊來達成最終性。也就是要讓所有節點對一個將永不被回退的區塊達成一致。

<!-- markdownlint-disable code-block-style ul-indent -->
[^fn-monolithic]: 單體式區塊鏈是指所有節點都處理所有資訊的區塊鏈，不論是交易還是共識相關的資訊。迄今幾乎所有區塊鏈，包括以太坊，都是單體式的。逃離可擴展性三難（scalability trilemma）的一種辦法是走向「模組化」（modular）。這正是以太坊[以 Rollup 為中心的路線圖](https://ethereum-magicians.org/t/a-rollup-centric-ethereum-roadmap/4698)背後的用意。

    - 關於一般性可擴展性三難的更多內容：Vitalik 的[《為何分片很棒》](https://web.archive.org/web/20231102071831/https://vitalik.ca/general/2021/04/07/sharding.html)。
    - 關於模組化的更多內容：Volt Capital 的 Alec Chen 所寫的[《模組化區塊鏈：深入探討》](https://volt.capital/blog/modular-blockchains)。
    - 非常值得一讀：Polynya 那篇生動有趣（雖然有點暴躁）的[《單體式區塊鏈駭人的低效率》](https://polynya.mirror.xyz/3-omFNK3uU0iAaYSpFz0f9rCvrDBjx0H3XOSDGXU8hY)。
<!-- markdownlint-enable code-block-style ul-indent -->

沿用 Vitalik 的[符號](https://notes.ethereum.org/@vbuterin/rkhCgQteN#Why-32-ETH-validator-sizes)，如果我們能容忍每秒 $\omega$ 則訊息的網路開銷，並且我們想要的最終確定時間為 $f$，那麼我們最多能有 $n$ 個驗證者的參與，其中

$$
n \le \frac{\omega f}{2}
$$

我們希望讓 $\omega$ 維持得小，以容許驗證者盡可能廣泛的參與，包括那些網路較慢的驗證者。而我們希望 $f$ 盡可能短，因為較短的最終確定時間比較長的時間有用得多[^fn-finality-utility]。綜合起來，這些要求意味著對 $n$（驗證者總數）有一個上限。

<!-- markdownlint-disable code-block-style -->
[^fn-finality-utility]: 在一篇[未完成的論文](https://github.com/ethereum/research/blob/master/papers/casper-economics/casper_economics_basic.pdf)中，Vitalik 嘗試量化不同最終確定時間所對應的「協定效用」。

    > ……一條有著某個最終確定時間 $f$ 的區塊鏈，其效用大約是 $-\log(f)$，換句話說，把一條區塊鏈的最終確定時間增加一個固定的倍數，會造成固定量的效用損失。1 分鐘與 2 分鐘最終性之間的效用差，和 1 小時與 2 小時最終性之間的效用差是一樣的。

    他接著為這一點做了一番論證（第 10 頁）。
<!-- markdownlint-enable code-block-style -->

這是一個典型的可擴展性三難。我個人並不覺得這些三角形的圖很直觀，但它們已成為表示這些取捨的正典方式。

<a id="img_incentives_scalability_trilemma"></a>
<figure class="diagram" style="width: 60%">

![可擴展性三難的一個版本。](images/diagrams/incentives-scalability_trilemma.svg)

<figcaption>

可擴展性三難的一個版本：任選其二。

</figcaption>
</figure>

1. 我們的理想或許是在低開銷（低 $\omega$）下有高參與（大 $n$）——許多質押者跑在低規格的機器上——但最終確定會花很長時間，因為訊息交換會很慢。
2. 我們可以有非常快的最終確定與高參與，但會需要強制規定質押者必須在高頻寬網路上運行高規格的機器才能參與。
3. 或者我們可以藉由嚴格限制參與者數量，在相當普通的機器上做到快速的最終確定。

要怎麼把以太坊&nbsp;2 精確地放在這樣一張圖上並不清楚，但我們肯定偏好參與更甚於最終確定時間：也許「x」標出了那個位置。一個複雜之處是，參與與開銷並非完全獨立：我們可以降低質押額來鼓勵參與，但那會增加硬體與網路需求（開銷），而這往往會減少有能力或願意參與的人數。[^fn-exercise-triangle]

[^fn-exercise-triangle]: 給讀者的練習：試著把其他幾條單體式 L1 區塊鏈放進這個取捨空間裡。

把這講得具體一點，驗證者數量的硬上限，是以太幣總供給量除以質押規模。在 32&nbsp;ETH 質押下，如今那是約 360 萬個驗證者，這與 768 秒（兩個紀元）的最終確定時間、以及每秒 9375 則訊息的訊息開銷一致[^fn-message-overhead]。每秒要處理的訊息量相當可觀。然而，我們從不預期_所有_以太幣都會被質押，大概在 10-20% 左右。此外，由於使用了 [BLS 聚合簽章](/part2/building_blocks/signatures/)，訊息被高度壓縮到漸近上每個驗證者 1 位元。

[^fn-message-overhead]: Vitalik 的[估計值](https://notes.ethereum.org/@vbuterin/rkhCgQteN#Why-32-ETH-validator-sizes) 5461 太低了，因為他在計算中省略了那個 2 的因子。

以目前 p2p 網路的容量而言，在兩個紀元內交付最終性的同時，每筆質押 32&nbsp;ETH 大約已是我們所能降到的最低點。據我個人經驗，我的質押節點持續消耗約 3.5mb/s 的上下行頻寬。那大約是我家用 ADSL 上行頻寬的 30%。如果這個協定再更聒噪一點，許多人就無法在家質押了。

另一種做法或許是[對任一時刻活躍的驗證者數量設下上限](https://github.com/ethereum/consensus-specs/issues/2137)，以對所交換的訊息數量設下一個上界。有了那樣的東西到位，我們就可以探索把質押額降到 32&nbsp;ETH 以下，容許多得多的驗證者參與，但每一個都只以兼職的方式參與。

請注意，這個分析忽略了節點（實際上必須處理訊息的是它們）與驗證者（其中大量可由單一一個節點託管）之間的區別。以太坊&nbsp;2 協定的一個設計目標，是盡量縮小任何規模經濟，讓獨立質押者與質押池盡可能站在平等的立足點上。因此，我們應當小心地把我們的分析套用到最分散的情況，即每個節點一個驗證者的情況。

有趣的事實：最初的混合式 Casper FFG PoS 提案（[EIP-1011](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1011.md)）要求最低存款規模為 1500&nbsp;ETH，因為那個系統設計最多只能處理約 900 個活躍的驗證者。雖然 32&nbsp;ETH 如今對大多數人而言代表一大筆錢，但能接受少於 32&nbsp;ETH 的去中心化質押池現在正逐漸出現。

#### 經濟性最終性

「要求驗證者鎖定質押」這項要求，以及罰沒條件的引入，讓我們得以在某種意義上量化信標鏈的安全性。

我們希望防止的主要攻擊，是一種改寫鏈歷史的攻擊。這樣一場攻擊的代價，為鏈的安全性提供了參數化的量度。在工作量證明中，這是「在一段期間內取得壓倒性（51%）雜湊算力」的代價。有意思的是，工作量證明中一場成功的 51% 攻擊本質上不花任何代價，因為攻擊者在被改寫的鏈上把所有區塊獎勵都據為己有。

在以太坊的權益證明協定中，我們可以用_經濟性最終性_來衡量安全性。也就是說，如果一個攻擊者想回退鏈上一個已最終確定的區塊，代價會是多少？

結果這很容易量化。引用 Vitalik 的[《為 Casper 參數化》](https://medium.com/@VitalikButerin/parametrizing-casper-the-decentralization-finality-time-overhead-tradeoff-3f2011672735)：

> 如果有足夠多的驗證者簽署一則為 $H_1$ 做出證明的訊息，狀態 $H_1$ 就在經濟上被最終確定了，這帶有一個性質：如果 $H_1$ 與一個相衝突的 $H_2$ 都被最終確定，那麼就存在可用來證明「至少 $\frac{1}{3}$ 的驗證者是惡意的」的證據，因而摧毀他們的全部存款。

以太坊的權益證明協定具有這個性質。為了最終確定一個檢查點（$H_1$），三分之二的驗證者必須曾為它做出證明。要最終確定一個相衝突的檢查點（$H_2$），需要三分之二的驗證者也為那個做出證明。因此，至少三分之一的驗證者必定曾為這兩個檢查點都做出證明。由於個別驗證者為它們的證明簽章，這既是可偵測的，也是可歸因的：要把「那些驗證者自相矛盾」的證據提交上鏈很容易，而它們可以被協定懲罰。

如果三分之一的驗證者同時被罰沒，它們的全部有效餘額都會被燒毀（每個最多 32&nbsp;ETH）。在那個時點，假設總共質押了一千五百萬 ETH，回退一個已最終確定區塊的代價，就會是攻擊者五百萬 ETH 被永久燒毀，並且攻擊者被逐出網路。

此時引用（或意譯）Vlad Zamfir 的話是免不了的：把權益證明與工作量證明相比，「就好比你若參與了一次 51% 攻擊，你的 ASIC 礦場就燒個精光」。

關於經濟性最終性運作機制的更多內容，見下文[罰沒](/part2/incentives/slashing/)；關於其原理與論證的更多內容，見 [Casper FFG](/part2/consensus/casper_ffg/) 一節。

#### 另見

  - [《為 Casper 參數化：去中心化／最終確定時間／開銷的取捨》](https://medium.com/@VitalikButerin/parametrizing-casper-the-decentralization-finality-time-overhead-tradeoff-3f2011672735)呈現了關於不同質押規模之取捨的一些早期推理。自那時以來情況已有所推進，最值得一提的是 BLS 聚合簽章的出現。
  - 出自 Vitalik《Serenity 設計原理》的[《為何是 32&nbsp;ETH 的驗證者規模？》](https://notes.ethereum.org/@vbuterin/rkhCgQteN#Why-32-ETH-validator-sizes)。

Vitalik 圍繞達成[單時段最終性](https://notes.ethereum.org/@vbuterin/single_slot_finality)的討論文件，從一個不同的視角審視「參與／開銷／最終性」的取捨空間。

### 餘額 <!-- /part2/incentives/balances/ -->

<div class="summary">

  - 每個驗證者除了它的實際餘額之外，還維護一個_有效餘額_。
  - 驗證者在協定中的影響力與它的有效餘額成比例，它的獎勵與懲罰也是。
  - 有效餘額追蹤驗證者的實際餘額，但被設計成變動得罕見得多。這是一種最佳化。
  - 一個驗證者的有效餘額上限為 32&nbsp;ETH。

</div>

#### 引言

信標鏈為每個驗證者的餘額維護兩份分開的記錄：它的實際餘額與它的有效餘額。

一個驗證者的實際餘額很直截了當。它是「透過存款合約為它做出的任何存款，加上累積的信標鏈獎勵，減去累積的懲罰與提領」的總和。實際餘額快速地變動，對所有活躍的驗證者而言至少每個紀元更新一次，對同步委員會參與者而言則每個時段更新一次。它也是細粒度的：實際餘額的單位是 Gwei，亦即 $10^{-9}$&nbsp;ETH。

一個驗證者的有效餘額由它的實際餘額衍生而來，衍生方式使得它變動得慢得多。為了做到這一點，有效餘額的單位是整數的 ETH（見 [`EFFECTIVE_BALANCE_INCREMENT`](/part3/config/preset/#effective_balance_increment)），而對有效餘額的更動受到[遲滯](#hysteresis)的約束。

使用有效餘額達成兩個目標，一個與經濟學有關，另一個純粹是工程上的。

#### 有效餘額的經濟面向

有效餘額最初被引入，是為了代表一個驗證者「[處於風險中的最大餘額](https://github.com/ethereum/consensus-specs/pull/162#issuecomment-441759461)」，上限為 32&nbsp;ETH。一個驗證者的實際餘額可能高得多；例如，如果不小心做了一筆雙重存款，一個驗證者的實際餘額會是 64&nbsp;ETH，但有效餘額只有 32&nbsp;ETH。我們大可設想一個協定，其中每個驗證者的影響力與它無上限的實際餘額成比例，但那會使委員會的成員資格等等變得複雜。我們改為對有效餘額設上限，並要求質押者若想質押更多，就為更多驗證者做出存款。[^fn-eip-7251]

[^fn-eip-7251]: 事實上，有一項提案打算把[最大有效餘額提高](https://notes.ethereum.org/@mikeneuder/eip-7251-faq)到 2048 ETH。

有效餘額的適用範圍很快就擴大了，現在它完整地代表一個驗證者在共識協定中的權重。

下列所有共識相關的量都與一個驗證者的有效餘額成比例：

  - 被[選為](/part3/helper/misc/#def_compute_proposer_index)信標區塊提議者的機率；
  - 該驗證者在 LMD-GHOST [分叉選擇規則](/part3/forkchoice/phase0/#get_weight)中的權重；
  - 該驗證者在證成與最終確定[計算](/part3/transition/epoch/#def_weigh_justification_and_finalization)中的權重；以及
  - 被[納入](/part3/helper/accessors/#def_get_next_sync_committee_indices)同步委員會的機率。

對應地，下列獎勵、懲罰與處罰也都依有效餘額加權：

  - 一個驗證者的[基礎獎勵](/part3/transition/epoch/#def_get_base_reward)，證明的獎勵與懲罰是以它為基準來計算的；
  - 作為怠惰洩漏之後果而套用於一個驗證者的[怠惰懲罰](/part2/incentives/inactivity/)；以及
  - [初始](/part2/incentives/slashing/#the-initial-penalty)罰沒懲罰與[關聯](/part2/incentives/slashing/#the-correlation-penalty)罰沒懲罰兩者。

然而，區塊提議者獎勵並不依提議者的有效餘額成比例縮放。由於一個驗證者被選來提議的機率與它的有效餘額成比例，「獎勵隨有效餘額縮放」這件事就已經被處理掉了。基於同樣的原因，同步委員會獎勵也不與參與者的有效餘額成比例。

#### 有效餘額的工程面向

我們大可以單純地用驗證者上限為 32&nbsp;ETH 的實際餘額作為它們的權重，來達成以上的一切。然而，把一切改以有效餘額為基礎，我們可以獲得顯著的效能好處。

首先，有效餘額每個紀元才[更新](/part3/transition/epoch/#def_process_effective_balance_updates)一次，這意味著像[每增量基礎獎勵](/part2/incentives/issuance/#the-base-reward-per-increment)這樣的東西我們只需計算一次，然後把結果為整個紀元快取起來，不論實際餘額有任何變動。

但有效餘額的主要特性是，它們被設計成變動得比那還要罕見得多。這是藉由把它們做得非常[粗顆粒](#increments)、並對任何更新套用[遲滯](#hysteresis)來達成的。

計算信標鏈狀態轉換時，一大效能挑戰是產生整個狀態的雜湊樹根。[Merkle 化](/part2/building_blocks/merkleization/)過程允許狀態中未曾改變的部分被快取起來，提供了顯著的效能提升。

狀態中的驗證者記錄清單是一個龐大的資料結構。要是我們把驗證者的實際餘額儲存在那些記錄之內，它們就會頻繁地變動，整個資料結構就需要至少每個紀元重新雜湊一次。

[解決這個問題的第一次嘗試](https://github.com/ethereum/consensus-specs/pull/317/files)，單純地把驗證者的餘額從驗證者記錄中移出，放進狀態中一個專用的清單。這減少了所需的重新雜湊量，因為當只有驗證者的餘額改變時，整個驗證者清單並不需要重新雜湊。

然而，那種做法在別處導致了效能問題。需要驗證者餘額資訊的輕客戶端，現在會需要從狀態的兩個不同部分取得資料——既要驗證者記錄、又要驗證者餘額清單。這需要兩份 Merkle 證明而非一份，顯著增加了它們的頻寬成本。

繞過這一點的一個辦法，是把一個變動緩慢的餘額版本儲存在驗證者的記錄中——意味著它們不常需要重新雜湊——並把快速變動的實際餘額儲存在一個分開的清單中，那是個小得多、重新雜湊起來容易得多的結構。

引用某種有效餘額實作的[早期嘗試](https://github.com/ethereum/consensus-specs/issues/685)的筆記：

> 〔有效餘額是一個〕「近似餘額」，輕客戶端可以在 `validator_registry` 中使用它，把它們每個驗證者需要下載的 Merkle 分支數量從 3 減為 2（實際上往往是從約 2.01 減為約 1.01，因為取得一個委員會時，active_index_roots 中的 Merkle 分支大多是共享的），達成輕客戶端頻寬成本非常顯著的降低。

重點在於，輕客戶端不會需要存取那份分開儲存在狀態中的實際餘額清單，只需要它們反正都要下載的驗證者記錄。

總而言之，把有效餘額加進驗證者的記錄中，讓我們得以同時達成兩個效能目標：既避免了頻繁重新雜湊狀態中驗證者清單的工作量，又不增加輕客戶端的工作量。

##### 增量

雖然有效餘額以 Gwei 為單位，它們卻只能是 [`EFFECTIVE_BALANCE_INCREMENT`](/part3/config/preset/#effective_balance_increment)（即 1&nbsp;ETH，$10^9$&nbsp;Gwei）的整數倍。實際餘額則可以是任意數量的 Gwei。

這個倍數在規格中以「增量」（increment）為人所知，它出現在像計算[基礎獎勵](/part3/transition/epoch/#def_get_base_reward_per_increment)，以及其他獎勵與懲罰計算這類地方。由於它方便地恰為 1&nbsp;ETH，要在心裡把「增量」代換成「以太幣」來獲得一些直覺很容易。

把有效餘額以增量、而非 Gwei 為單位來儲存，大概會比較乾淨。那肯定會減少對 `EFFECTIVE_BALANCE_INCREMENT` 進行除法與乘法的次數，以及相關的[算術溢位](https://github.com/ethereum/consensus-specs/pull/1286)危險。但目前的版本是隨時間演化而來的，現在回頭去改動東西會具侵入性又有風險。

##### 遲滯

藉由在有效餘額的計算中加入[遲滯](https://en.wikipedia.org/wiki/Hysteresis)（hysteresis），有效餘額被保證會比實際餘額變動得慢得多。

在我們的情境中，遲滯意味著：如果有效餘額是 31&nbsp;ETH，實際餘額必須上升到 32.25&nbsp;ETH，才會觸發一次把有效餘額更新為 32&nbsp;ETH。同樣地，如果有效餘額是 31&nbsp;ETH，那麼實際餘額必須下降到 30.75&nbsp;ETH，才會觸發一次把有效餘額更新為 30&nbsp;ETH。

下面這張圖表說明了這個行為。

  - 實際餘額與有效餘額都從 32&nbsp;ETH 開始。
  - 一開始實際餘額上升。有效餘額上限為 32&nbsp;ETH，所以它不會被更新。
  - 只有當實際餘額掉到 31.75&nbsp;ETH 以下時，有效餘額才會被降為 31&nbsp;ETH。
  - 雖然實際餘額上升並在 32&nbsp;ETH 附近振盪，但沒有觸發任何有效餘額更新，它維持在 31&nbsp;ETH。
  - 最終實際餘額上升到 32.25&nbsp;ETH 以上，有效餘額就被更新為 32&nbsp;ETH。
  - 儘管實際餘額再次下降，它並未掉到 31.75&nbsp;ETH 以下，所以有效餘額維持在 32&nbsp;ETH。

<a id="img_hysteresis"></a>
<figure class="chart">

![一張圖，說明實際餘額與有效餘額的對比。](images/charts/hysteresis.svg)

<figcaption>

一個驗證者實際餘額（實線）與有效餘額（虛線）之間關係的圖示。點線是有效餘額被更新的門檻——也就是遲滯。

</figcaption>
</figure>

遲滯的水準由規格中的[遲滯參數](/part3/config/preset/#hysteresis-parameters)所控制：

| 名稱 | 值 |
| - | - |
| `HYSTERESIS_QUOTIENT` | `uint64(4)` |
| `HYSTERESIS_DOWNWARD_MULTIPLIER` | `uint64(1)` |
| `HYSTERESIS_UPWARD_MULTIPLIER` | `uint64(5)` |

這些在每個紀元結束時、於[有效餘額更新](/part3/transition/epoch/#effective-balances-updates)期間被套用。狀態中的每個驗證者（不論活躍與否）的有效餘額都如下被更新：

  - 如果實際餘額小於有效餘額減 0.25（`=` `HYSTERESIS_DOWNWARD_MULTIPLIER` `/` `HYSTERESIS_QUOTIENT`）個增量（ETH），那麼就把有效餘額減少整數個增量。
  - 如果實際餘額大於有效餘額加 1.25（`=` `HYSTERESIS_UPWARD_MULTIPLIER` `/` `HYSTERESIS_QUOTIENT`）個增量（ETH），那麼就把有效餘額增加整數個增量。

遲滯的效果是：有效餘額變動的頻率，不可能高於「一個驗證者的實際餘額變動 0.5&nbsp;ETH 所需的時間」，而那通常要花好幾個星期或好幾個月。

###### 一個邊角案例

遲滯的設計在存款處理中衍生出一個有意思的[邊角案例](https://github.com/ethereum/consensus-specs/issues/3049)。[存款合約](https://github.com/ethereum/consensus-specs/blob/v1.3.0/solidity_deposit_contract/deposit_contract.sol)允許質押者存入任何大於或等於 1&nbsp;ETH 的金額；一筆存款不一定要是完整的 32&nbsp;ETH。這允許從多筆存款累積出一筆質押。例如，一筆 24&nbsp;ETH 的存款後面跟著一筆獨立的 8&nbsp;ETH 存款，就湊成一筆完整的質押，並會在第二筆存款被處理之後啟用該驗證者。

這個邊角案例發生在「一個驗證者的最後一筆存款把它的實際餘額帶到 32&nbsp;ETH 或更多，但由於遲滯，不足以把它的有效餘額更新為 32&nbsp;ETH」之時。例如，在一筆 31&nbsp;ETH 的存款之後，該驗證者的實際與有效餘額都會是 31&nbsp;ETH。一筆進一步的 1&nbsp;ETH 存款會把該驗證者的實際餘額帶到 32&nbsp;ETH——這使它在技術上有資格被啟用——但由於遲滯計算，會讓它的有效餘額停留在 31&nbsp;ETH。因此，它不會被啟用。

驗證者 [418408](https://beaconcha.in/validator/b6c1531b7896e3493806a8dd72fa9c3387f4f7a2fdc565bf1e8e66becb0666f8c3938270a757703e3865619dcc34bf7c#deposits) 就是這在主網上發生的一個例子。倒數第二筆 1&nbsp;ETH 的存款把該驗證者的總餘額帶到 32&nbsp;ETH，但它直到又做出一筆進一步的 1&nbsp;ETH 存款、以強制觸發一次有效餘額更新之後，才被啟用。

[TODO: link to deposit contract section when written]::

###### 一則歷史註記

遲滯最初的實作實際上[採用了](https://github.com/ethereum/consensus-specs/pull/1627#discussion_r387294528) `QUOTIENT = 2`、`DOWNWARD_MULTIPLIER = 0`、`UPWARD_MULTIPLIER = 3`。這意味著一個以 32&nbsp;ETH 實際餘額起步、卻遭受一次小小的初期斷線的驗證者，會立即掉到 31&nbsp;ETH 的有效餘額。要回到 32&nbsp;ETH 的有效餘額，它會需要達到 32.5&nbsp;ETH 的實際餘額，而在此期間，由於有效餘額降低，該驗證者的獎勵會低 3.1%。這[看起來不公平](https://github.com/ethereum/consensus-specs/issues/1609)，並激勵質押者「過度存款」以太幣，以避免初期有效餘額下降的風險，因此才有了採用當前參數的[變更](https://github.com/ethereum/consensus-specs/pull/1627)。

#### 另見

出自規格：

  - 約束有效餘額的預設值 [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance) 與 [`EFFECTIVE_BALANCE_INCREMENT`](/part3/config/preset/#effective_balance_increment)。
  - [控制遲滯的參數](/part3/config/preset/#hysteresis-parameters)。
  - 用於遲滯之實際計算與套用的函式 [`process_effective_balance_updates()`](/part3/transition/epoch/#def_process_effective_balance_updates)。
  - [`Validator`](/part3/containers/dependencies/#validator) 物件儲存有效餘額。信標狀態中的[註冊表](/part3/containers/state/#registry)含有驗證者清單，旁邊還有一份分開的實際餘額清單。

### 發行 <!-- /part2/incentives/issuance/ -->

<div class="summary">

  - 發行（issuance）是協定為了激勵其參與者而建立的新以太幣數量。
  - 一條理想運作的信標鏈每個紀元發行一個固定數量的以太幣，它是每增量基礎獎勵的一個倍數。
  - 總發行量與驗證者數量的平方根成比例。這並不是一個完全任意的選擇。

</div>

#### 引言

對於「為激勵驗證者正確地參與協定而給予它們的獎勵」，我們可以採取三種看法。

第一是「發行」，也就是協定為支付獎勵而產生的新以太幣的總量。第二是一個驗證者長期下來可能賺得的預期獎勵。第三是任何特定驗證者實際賺得的獎勵。

在本節中我們會看發行，並在[下一節](/part2/incentives/rewards/)看獎勵。不過，這兩者之間有著緊密的關係，所以這個區分並不是完全乾淨利落的。

首先我們必須定義獎勵的基本單位，也就是「每增量基礎獎勵」。

#### 每增量基礎獎勵

所有獎勵都是以一個「每增量基礎獎勵」為基準來計算的。這又被[計算](/part3/transition/epoch/#def_get_base_reward_per_increment)為

```none
Gwei(EFFECTIVE_BALANCE_INCREMENT * BASE_REWARD_FACTOR // integer_squareroot(get_total_active_balance(state)))
```

為求簡潔，我們把每增量基礎獎勵稱為 $b$。一個增量是一單位的有效餘額，亦即 1&nbsp;ETH（[`EFFECTIVE_BALANCE_INCREMENT`](/part3/config/preset/#effective_balance_increment)），所以活躍的驗證者最多有 32 個增量。

[`BASE_REWARD_FACTOR`](/part3/config/preset/#base_reward_factor) 是那個「我們若想改變信標鏈上以太幣的發行率，就能轉動」的大旋鈕。到目前為止它一直被設為 64，這產生了我們在下面所見的發行圖。這似乎運作得非常好，沒有計畫要更改它。

#### 獎勵來自發行

發行是協定為了激勵其參與者而建立的新以太幣數量。在把懲罰、燒毀的交易費等等都計入之後的淨發行量，有時被稱為通膨，或供給成長。

在合併之前，Eth1 鏈以區塊獎勵與叔塊獎勵的形式發行新以太幣。自從 London 升級以來，這個發行量已部分被——甚至有時被超過——由 [EIP-1559](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1559.md) 所造成的交易基礎費用燒毀所抵銷。

在合併之後，Eth1 鏈上不再發行任何區塊或叔塊獎勵。但基礎費用燒毀仍然存在。淨發行量有可能變成負的——使得被摧毀的以太幣多於被建立的[^fn-ultrasound-money]——至少在短期到中期是如此。在較長期，Anders Elowsson 論證會出現[一個流通供給均衡](https://ethresear.ch/t/circulating-supply-equilibrium-for-ethereum-and-minimum-viable-issuance-during-the-proof-of-stake-era/10954?u=benjaminion)，由「權益證明發行以太幣」與「EIP-1559 摧毀以太幣」共同產生。

[^fn-ultrasound-money]: 你可以在 [ultrasound.money](https://ultrasound.money/) 看到以太坊當前的發行量，並擺弄各種情境。

在接下來的內容中，我們會假設信標鏈正以最佳狀態運作，也就是所有驗證者都完美地履行它們的職責。在現實中，這在一個無須許可、全球分散的點對點網路上是不可能達成的，不過信標鏈在它歷史的大部分時間裡，表現都在最佳狀態的幾個百分點以內。實際的驗證者獎勵與淨發行量肯定會稍低或低得多，視網路的參與率而定。

#### 整體發行

在我們所假設的理想條件下，信標鏈被設計成每個紀元恰好發行總計 $Tb$ Gwei 的獎勵。此處的 $T$ 是活躍驗證者所持有的增量總數，換句話說就是他們全部有效餘額以 ETH 計的總和。這是信標鏈所能產生的最大發行量——最大量的新以太幣。如果全部 $N$ 個驗證者都有最大的 32&nbsp;ETH 有效餘額，那麼這算出來總共是每個紀元 $32Nb$ Gwei。

一年有 $365.25 \times 225 = 82181.25$ 個紀元，且 [`BASE_REWARD_FACTOR`](/part3/config/preset/#base_reward_factor) $= 64$，

$$
\begin{aligned}
\text{Max issuance per year} &= 82181.25 \times \frac{32 \times 64 \times N}{\sqrt{32 \times 10^9 \times N}} \text{ETH} \\
                             &= 940.8659 \sqrt{N} \\
\end{aligned}
$$

<!-- Number of validators -->

在有 500,000 個驗證者的情況下，這相當於每年 665,292&nbsp;ETH 多一點。作為對照，在工作量證明之下，以太坊的區塊與叔塊獎勵每年達到將近五百萬 ETH。

我們可以把最大發行量畫成驗證者數量的函數。它就是一條經縮放的平方根曲線。

<a id="img_issuance_curve"></a>
<figure class="chart">

![一張圖，呈現信標鏈上每年協定最大發行量作為活躍驗證者數量的函數。](images/charts/issuance_curve.svg)

<figcaption>

信標鏈上每年協定最大發行量作為活躍驗證者數量的函數。

</figcaption>
</figure>

#### 驗證者獎勵

目標是把這些獎勵平均地分配給各驗證者（繼續假設一切都以最佳狀態運作），使得長期平均下來，每個驗證者 $i$ 每個紀元賺得 $n_{i}b$ Gwei，其中 $n_i$ 是它所擁有的增量數量，等價於它以 ETH 計的有效餘額。以這些術語來說，$T = \sum^{N-1}_{i=0}{n_i}$。

有鑑於此，一個表現良好、有著 32&nbsp;ETH 有效餘額的驗證者，可以預期長期平均每個紀元賺得 $32b$ Gwei。當然，$b$ 隨著總活躍餘額的變化而隨時間改變，但在沒有大規模罰沒事件的情況下，那個變化會是緩慢的。

與發行量的計算類似，我們可以計算一個驗證者因為參與信標鏈協定而獲得的預期年化百分比獎勵：

$$
\begin{aligned}
\text{APR} &= 100 \times 82181.25 \times \frac{64}{\sqrt{32 \times 10^9 \times N}} \% \\
           &= \frac{2940.21}{\sqrt{N}} \% \\
\end{aligned}
$$

<!-- Number of validators -->

舉例來說，在有 500,000 個驗證者參與的情況下，這相當於驗證者有效餘額 4.16% 的預期報酬。

把這畫成圖，我們得到一條反平方根曲線。

<a id="img_rewards_curve"></a>
<figure class="chart">

![一張圖，呈現質押者的預期年化百分比獎勵作為活躍驗證者數量的函數。](images/charts/rewards_curve.svg)

<figcaption>

質押者的預期年化百分比獎勵作為活躍驗證者數量的函數。

</figcaption>
</figure>

#### 反平方根縮放

「讓每驗證者預期獎勵以 $\frac{1}{\sqrt{N}}$ 縮放」這個選擇並不顯而易見，我們可以設想不同的情境。

如果我們把每驗證者獎勵建模為 $r \propto N^{-p}$，那麼一些選項如下。

1. $p = 0$：每個驗證者賺得固定的報酬，與驗證者總數無關。發行量與 $N$ 成比例。
2. $p = \frac{1}{2}$：發行量以 $\sqrt{N}$ 的方式縮放，這就是我們所使用的公式。
3. $p = 1$：每個驗證者的預期獎勵與驗證者總數成反比。發行量與驗證者總數無關。

採用一個凹函數很有吸引力，因為它讓「一個均衡的驗證者數量」得以被發現，而不必不斷地擺弄參數。理想情況下，如果有更多驗證者加入，我們希望每驗證者獎勵下降，以反向激勵進一步的加入者；如果有驗證者退出，我們希望每驗證者獎勵上升，以鼓勵新的加入者。最終，會找到一個均衡的驗證者數量，它在質押獎勵與「質押所被認知的風險與機會成本」之間取得平衡。假設協定對驗證者總數不過度敏感，這似乎是一個不錯的特性。

那會排除第一個選項 $p=0$。$p = 0$ 的風險在於：如果獎勵率被設得低於所被認知的風險，那麼所有理性的驗證者都會退出。如果我們把它設得太高，那麼我們最終就會為超過所需的安全性付費（太多被過度激勵的驗證者）。可能需要透過硬分叉頻繁地手動調校來調整這個率。

選擇 $p = \frac{1}{2}$ 而非 $p = 1$ 的論證相當微妙，並與[勸退攻擊](/part2/incentives/rewards/#discouragement-attacks)（discouragement attack）有關。在 $p \ne 0$ 時，一組驗證者可能藉由審查其他驗證者、或進行其他類型的阻斷服務，來對付那些驗證者，以說服它們退出系統，從而增加它們自己的獎勵。在各種假設與模型下，我們發現要讓某些類型的攻擊無利可圖，我們需要 $p \le \frac{1}{2}$。本質上，我們不想為「成功使其他驗證者退出信標鏈」的驗證者把獎勵增加太多。

請注意，自合併以來，驗證者的收入可能包含來自交易優先費與 MEV 的一個顯著成分。這有把 $p$ 推向更接近 $1$ 的效果，使上述大部分的推理變得無關緊要。在這種狀態下的勸退攻擊是一個未解的問題。

#### 另見

關於 $\frac{1}{\sqrt{N}}$ 獎勵曲線的更多背景，見

  - [《Casper：固定收益的做法》](https://ethresear.ch/t/casper-the-fixed-income-approach/218?u=benjaminion)，
  - Vitalik 的[《Serenity 設計原理》](https://notes.ethereum.org/@vbuterin/rkhCgQteN#Base-rewards)，以及
  - [《勸退攻擊》](https://github.com/ethereum/research/blob/master/papers/discouragement/discouragement.pdf)論文。

Anders Elowsson 關於以太坊流通供給均衡與最低可行發行量的研究，更深入地審視了質押發行量與以太幣總供給量之間的關係。見他在 Ethresear.ch 上的[貼文與留言](https://ethresear.ch/t/circulating-supply-equilibrium-for-ethereum-and-minimum-viable-issuance-during-the-proof-of-stake-era/10954?u=benjaminion)，以及在 Devconnect 2022 的 [ETHconomics 演講](https://www.youtube.com/watch?v=LtEMabS0Oas)。

### 獎勵 <!-- /part2/incentives/rewards/ -->

<div class="summary">

  - 驗證者因為依其對鏈的看法做出證明、提議區塊、以及參與同步委員會，而以不同的比例收到獎勵。
  - 構成證明的各票必須既正確又及時，才會獲得獎勵。
  - 提議者的獎勵，是它納入其區塊的所有職責之總獎勵的一個固定比例 $\frac{1}{7}$。
  - 一個驗證者的預期長期獎勵是每個紀元 $nb$（增量數乘以每增量基礎獎勵），但由於提議者與同步委員會指派的隨機性，存在顯著的變異。
  - 獎勵既隨一個驗證者的有效餘額縮放，也隨驗證者集合的總參與率縮放。
  - 防禦勸退攻擊的需要，形塑了協定的各個面向。

</div>

#### 引言

在本節中我們只考慮獎勵。我們會在[下一節](/part2/incentives/penalties/)涵蓋懲罰。

信標鏈協定藉由為下列三種活動提供獎勵，來激勵每個驗證者好好行事。

1. 作為共識協定的一部分，為它對鏈的看法做出證明：
   - 為 Casper FFG 投票支持一個來源檢查點；
   - 為 Casper FFG 投票支持一個目標檢查點；以及
   - 為 LMD-GHOST 投票支持一個鏈頭區塊。
2. 提議信標鏈區塊。
3. 在支援輕客戶端的同步委員會中為區塊背書。

這當中的第一項——做出證明——每個紀元規律地發生，並佔了一個驗證者預期總獎勵的大部分。

然而，驗證者是被隨機選來提議區塊或參與同步委員會的，所以後兩種獎勵有著天然的變異。長期下來，每種活動所賺得獎勵的預期比例，分解如下面這張圖所示。

<a id="img_incentives_weights"></a>
<figure class="diagram" style="width:50%">

![一張圓餅圖，呈現一個驗證者總獎勵中來自每種活動的比例。](images/diagrams/incentives-weights.svg)

<figcaption>

一個驗證者總獎勵中來自每種活動的比例。

</figcaption>
</figure>

這些比例由規格中的[激勵權重](/part3/config/constants/#incentivization-weights)所設定。為求方便，我在最後一欄為每個權重指派了一個符號。

| 名稱 | 值 | 百分比 | 符號 |
| - | - | - | - |
| `TIMELY_SOURCE_WEIGHT` | `uint64(14)` | 21.9% | $W_s$ |
| `TIMELY_TARGET_WEIGHT` | `uint64(26)` | 40.6% | $W_t$ |
| `TIMELY_HEAD_WEIGHT`   | `uint64(14)` | 21.9% | $W_h$ |
| `SYNC_REWARD_WEIGHT`   | `uint64(2)`  | 3.1%  | $W_y$ |
| `PROPOSER_WEIGHT`      | `uint64(8)`  | 12.5% | $W_p$ |
| `WEIGHT_DENOMINATOR`   | `uint64(64)` | 100%  | $W_{\Sigma}$ |

還有一項進一步的獎勵可供區塊提議者因為舉報違反罰沒規則而獲得，但這應當非常罕見，我們在本節會忽略它（關於這一點的更多內容見[罰沒](/part2/incentives/slashing/)）。

獎勵是新建立的以太幣，單純地被加到信標鏈上驗證者的餘額中。

#### 獲得獎勵的資格

一個驗證者的生命週期中有三個相關的里程碑：它的啟用紀元、它的退出紀元，以及它的可提領紀元。獲得獎勵、懲罰與罰沒的資格，依這些里程碑而異。

<a id="img_incentives_rewards_eligibility"></a>
<figure class="diagram" style="width:80%">

![一張驗證者獲得獎勵之資格的時間軸。](images/diagrams/incentives-rewards_eligibility.svg)

<figcaption>

驗證者獲得獎勵之資格的時間軸

</figcaption>
</figure>

驗證者只有在它們的啟用紀元與退出紀元之間才能收到獎勵。請注意，在提交一份自願退出之後，當驗證者通過退出佇列、直到它的退出紀元過去之前，可能會有一段延遲。在這段期間，驗證者被期望像平常一樣參與。

同樣地，驗證者只有在它們的啟用紀元與退出紀元之間才收到懲罰。這一點的例外是被罰沒的驗證者。作為一個[特例](/part2/incentives/slashing/#other-penalties)，被罰沒的驗證者會繼續收到懲罰，直到它們抵達它們的可提領紀元，那可能在它們的退出紀元之後很久。

所有處於啟用紀元與可提領紀元之間、未被罰沒的驗證者，都有被罰沒的可能。

[TODO: link to validator lifecycle when done]::

#### 獎勵隨有效餘額縮放

如[前文所述](/part2/incentives/balances/#economic-aspects-of-effective-balance)，所有獎勵都依一個驗證者的有效餘額成比例縮放。這反映了「一個驗證者在協定中的影響力（權重）與它的有效餘額成比例」這個事實。

如果一個驗證者有 $n$ 個增量（也就是 $n \times$ `EFFECTIVE_BALANCE_INCREMENT` 的有效餘額，換句話說即 $n$&nbsp;ETH），那麼它每個紀元的預期[^fn-expected-value]收入就是 $nb$，其中 $b$ 是[每增量基礎獎勵](/part2/incentives/issuance/#the-base-reward-per-increment)。

[^fn-expected-value]: 我在這裡用「預期」這個詞是取它的[技術意義](https://en.wikipedia.org/wiki/Expected_value)。由於[隨機性](#individual-validator-rewards-vary)，有些驗證者有可能賺得較少，有些有可能賺得較多。運氣平平的驗證者可以預期，長期下來它們的獎勵會平均成每個紀元 $nb$ Gwei。

對於每個紀元發生的規律證明，這是藉由在 [`get_base_reward()`](/part3/transition/epoch/#def_get_base_reward) 中把基礎獎勵乘以增量數而明示地達成的。

對於隨機的元素——區塊提議與同步委員會參與——這個縮放是藉由把「一個驗證者被選來執勤的機率」修改為與 $\frac{n}{T}$ 成比例而隱含地達成的，其中 $T$ 是活躍驗證者集合的增量總數。所以，如果你的有效餘額是 24&nbsp;ETH，那麼你被選來提議一個區塊或加入一個同步委員會的機率，會比一個有 32&nbsp;ETH 的驗證者低 25%。細節見 [`compute_proposer_index()`](/part3/helper/misc/#def_compute_proposer_index) 與 [`get_next_sync_committee_indices()`](/part3/helper/accessors/#def_get_next_sync_committee_indices)。

#### 證明獎勵

驗證者獎勵最大的一部分，84.4%，來自做出證明。雖然證明的委員會與時段指派是隨機化的，每個活躍的驗證者每個紀元都恰好會被選來做出一份證明。

證明只有在被納入信標鏈區塊中時才會收到獎勵。一份證明含有三票。每一票都在符合條件的前提下有資格獲得獎勵。

| 有效性 | 時效性 | 獎勵 |
| - | - | - |
| 來源正確                  | 5 個時段內  | $\frac{W_s}{W_{\Sigma}}nb$ |
| 來源與目標正確       | 32 個時段內 | $\frac{W_t}{W_{\Sigma}}nb$ |
| 來源、目標與鏈頭正確 | 1 個時段內   | $\frac{W_h}{W_{\Sigma}}nb$ |

這些是可累加的，所以每個紀元最大的證明獎勵（三票全對、並讓證明在下一個區塊被納入）是 $\frac{W_s + W_t + W_h}{W_{\Sigma}}nb$，或 $0.84375nb$。

一份證明獎勵之可能權重的完整矩陣如下。在每種情況中，我們都需要乘以 $\frac{nb}{W_{\Sigma}}$ 才能得到實際的獎勵。

<a id="rewards-table"></a>

| 時效性 | 1 個時段 | <= 5 個時段 | <= 32 個時段 | > 32 個時段（缺失） |
| - | - | - | - | - |
| 來源錯誤                    | 0                 | 0           | 0     | 0 |
| 來源正確                  | $W_s$             | $W_s$       | 0     | 0 |
| 來源與目標正確       | $W_s + W_t$       | $W_s + W_t$ | $W_t$ | 0 |
| 來源、目標與鏈頭正確 | $W_s + W_t + W_h$ | $W_s + W_t$ | $W_t$ | 0 |

但這並不是完整的全貌：我們還需要把不正確或遲到之證明的[懲罰](/part2/incentives/penalties/)計入。

所有驗證者每個紀元的最大總發行量是

$$
I_A = \frac{W_s + W_t + W_h}{W_{\Sigma}}Tb
$$

其中，再一次，$T$ 是活躍驗證者的增量總數（他們以 ETH 計的有效餘額總和）。

##### 正確性

上文中的「正確」意味著該證明與當前區塊提議者所擁有的對區塊鏈之看法一致。如果做出證明的驗證者為不同的檢查點或鏈頭區塊投票，那麼它就在一個不同的分叉上，那一票對我們而言就沒有用處。例如，如果來源檢查點投票與我們身為提議者所認為它應該是的不同，那麼我們對鏈歷史的看法就與證明者的根本不同，所以我們必須忽略它們的證明。這份證明會改在另一個分叉上的區塊中收到獎勵，而最終要嘛這個分叉、要嘛那個分叉會勝出。為了反向激勵攻擊，重要的是只有勝出之鏈的參與者才收到獎勵。

##### 時效性

Altair 帶來的變更之一，是收緊了對證明的時效性要求。先前，有針對正確性的獎勵，以及一個分開的、針對及時納入的獎勵，後者以 $\frac{1}{d}$ 的方式遞減，其中 $d$ 是以時段計的納入距離，上限為 32 個時段。這導致了一些怪事，例如多等一下子以確保把鏈頭投票投對是值得的，因為那比「因納入遲到而造成的任何損失」更有價值，即使一張遲到的鏈頭投票其實幾乎毫無用處。

新的時效性獎勵更好地反映了各票的相對重要性。一張比一個時段更舊的鏈頭投票沒有用處，所以它不獲得獎勵。

Target votes are always useful, but we only want to track attestations pertaining to the current and previous epochs, so we ignore them if they are older than 32 slots. The number 32 was chosen for reasons of fairness: whichever slot in an epoch validators attest, their attestations are valid for the same length of time.[^fn-eip7045-notes]

[^fn-eip7045-notes]: [EIP-7045](https://eips.ethereum.org/EIPS/eip-7045) proposes to change this in the [Deneb upgrade](/part4/history/deneb/) to accept and reward target votes for the whole of the current and previous epochs. Danny Ryan made an insightful presentation on the reasons for changing this, and a defence of why the changes remain fair to validators, in the [PEEPanEIP 114 session](https://www.youtube.com/watch?v=Z4tMgrreCN8).

納入來源投票所用的距離選擇很有意思。它被選為 $\lfloor \sqrt{\tt SLOTS\_PER\_EPOCH} \rfloor = \lfloor \sqrt{32} \rfloor = 5$，這是 1 與 32（鏈頭值與目標值）的幾何平均。這是個有點任意的選擇，但用意是讓一份完全正確的證明，在時效性方面落在一條指數遞減的曲線上：（淨）獎勵的每一階下降，都在以指數方式增加的時段數之後發生。[^fn-five-slots]

<a id="img_reward_timeliness"></a>
<figure class="chart">

![一張圖，將一份完全正確之證明隨著它變舊的淨獎勵，與一條指數曲線並列對照。](images/charts/reward_timeliness.svg)

<figcaption>

把「來源正確」的納入距離設為 5，似乎合理地給出了一種獎勵隨時間呈指數遞減的效果。這張圖顯示一份完全正確之證明隨著它變舊的淨獎勵（獎勵 + 懲罰），並與一條指數曲線並列以作對照。

</figcaption>
</figure>

<!-- markdownlint-disable code-block-style -->
[^fn-five-slots]: This is taken from a [conversation](https://discord.com/channels/595666850260713488/595701173944713277/871340571107655700) on the Ethereum R&D Discord server:

    > vbuterin:<br/>
    > The rationale for the number 5 is just that 5 is geometrically halfway in between 1 and 32<br/>
    > And so we get the closest that makes sense to a smooth curve in terms of rewarding earlier inclusion<br/>
    > ...<br/>
    > ah I mean on an exponential curve, not quadratic<br/>
    > To me exponential feels more logical<br/>
    > What's a bigger improvement in quality, 4 slot delay vs 6 slot delay, or 20 slot delay vs 23 slot delay?
<!-- markdownlint-enable code-block-style -->

##### 評註

請注意，證明者對於它是否收到獎勵並沒有完全的掌控。一個證明者可能行為完美，但如果下一個區塊因為提議者離線而被跳過，那麼它就不會收到「鏈頭區塊正確」的獎勵。或者如果下一個提議者剛好在一個少數分叉上，證明者又會放棄獎勵。或者如果下一個提議者的區塊遲到並被孤立——後續的提議者理應撿起那些被孤立的證明，但如果區塊空間緊張，可能會有相當大的延遲。有著數不清的、在證明者掌控之外的失敗模式。

當質押者的驗證者就一切意圖與目的而言看似運作得完美無瑕、卻仍然錯失獎勵或收到懲罰時，這往往令他們困惑。但這就是無須許可、全球性、點對點網路的本質。迄今信標鏈上錯失的獎勵出奇地罕見，這正是協定與各個客戶端實作品質的明證。

#### 提議者因證明而獲得的獎勵

如果一個區塊中的證明對證明者而言總計值 $R$ 的獎勵，那麼把那些證明納入一個區塊的提議者就會收到一份獎勵，為

$$
R_{A_P} = \frac{W_p}{W_{\Sigma} - W_p}R
$$

因此，在一個紀元中，因提議者證明獎勵而產生的最大總發行量是

$$
I_{A_P} = \frac{W_p}{W_{\Sigma} - W_p}I_A
$$

其中 $I_A$ 是如上文所述、每個紀元給證明者的最大發行量。

因此，提議者受到強烈的激勵去納入高價值的證明，這基本上意味著快速地納入它們，並納入打包良好、盡可能正確的聚合。

#### 同步委員會獎勵

<!-- Number of validators -->

每隔 [256](/part3/config/preset/#epochs_per_sync_committee_period) 個紀元（27.3 小時），就選出 [512](/part3/config/preset/#sync_committee_size) 個驗證者參與同步委員會。對任何給定的驗證者而言，這很罕見才發生；在有 500,000 個驗證者的情況下，被選來執行同步委員會職責之間的預期間隔約為 37 個月。然而，在那 27 小時的參與期間，獎勵相對而言非常大。

[TODO: link to explanation of sync committees when done]::

同步委員會參與者每正確履行其職責的一個時段，就收到一份獎勵。委員會有 512 個成員，每個紀元有 32 個時段，因此正確參與時每個驗證者每個時段的獎勵是

$$
R_Y = \frac{W_y}{32 \times 512 \times W_{\Sigma}}Tb
$$

這裡的 $T$ 是整個活躍驗證者集合的增量總數，所以這是一個很大的數。每紀元每驗證者獎勵是這個的 32 倍。

於是，因同步貢獻而每個紀元給同步委員會成員的最大發行量是

$$
I_Y = \frac{W_y}{W_{\Sigma}}Tb
$$

#### 提議者因同步委員會而獲得的獎勵

與證明一樣，納入同步委員會輸出的區塊提議者，會收到一份與整個委員會的獎勵成比例的獎勵：

$$
R_{Y_P} = 512\frac{W_p}{W_{\Sigma} - W_p}R_Y
$$

所以因納入同步委員會貢獻而每個紀元給提議者的最大發行量是

$$
I_{Y_P} = \frac{W_p}{W_{\Sigma} - W_p}I_Y
$$

#### 關於提議者獎勵的評註

你會注意到，對於證明與同步委員會兩者，「把它們納入一個區塊」的提議者獎勵，都是驗證者獎勵的一個固定比例。如果 $R$ 是某項職責的驗證者獎勵，那麼提議者獎勵就是 $\frac{W_p}{W_{\Sigma} - W_p}R$。以 [Vitalik 的話](https://github.com/ethereum/annotated-spec/blob/master/altair/beacon-chain.md#aside-proposer-rewards-in-altair)來說：「某項職責的提議者獎勵，是那項職責的證明者獎勵，乘以_提議者獎勵佔『除提議者獎勵以外的一切』的比例_」（強調為他所加）。

這個因子算出來是 $\frac{8}{56} = \frac{1}{7}$，這意味著 $\frac{7}{8}$ 的獎勵歸給履行職責的驗證者，$\frac{1}{8}$ 歸給把證據納入區塊的提議者。

在下面的圖表中，我把驗證者獎勵與提議者獎勵分開來，我們可以看到它們在各職責間有著完全相同的劃分。為了真正的準確，右邊那張圖大概應該是左邊那張的七分之一大。

<a id="img_incentives_reward_split"></a>
<figure class="diagram">

![圓餅圖，顯示提議者與驗證者獎勵在各職責間以相同的比例分配。](images/diagrams/incentives-reward_split.svg)

<figcaption>

左邊是驗證者因履行職責而獲得的預期獎勵分解。右邊是提議者因納入那些職責之證據而獲得的獎勵分解。

</figcaption>
</figure>

這種等價性確保了證明者與提議者的利益是對齊的。

#### 總發行量

為了檢查上述計算與我們的[主張](/part2/incentives/issuance/#overall-issuance)——信標鏈每個紀元的最大發行量是 $Tb$ Gwei——一致，讓我們把四種獎勵所造成的發行量加總起來：證明者獎勵、因納入證明而給的提議者獎勵、同步委員會獎勵，以及因納入同步委員會而給的提議者獎勵。每個紀元的總最大發行量是

$$
\begin{aligned}
I &= I_A + I_{A_P} + I_Y + I_{Y_P} \\
  &= \left(1 + \frac{W_p}{W_{\Sigma} - W_p}\right)\left(I_A + I_Y\right) \\
  &= \left(1 + \frac{W_p}{W_{\Sigma} - W_p}\right)\left(\frac{W_s + W_t + W_h + W_y}{W_{\Sigma}}\right)Tb \\
  &= \left(\frac{W_{\Sigma}}{W_{\Sigma} - W_p}\right)\left(\frac{W_{\Sigma} - W_p}{W_{\Sigma}}\right)Tb \\
  &= Tb
\end{aligned}
$$

如預期。

#### 以數字看獎勵

<!-- Number of validators -->

下面的計算基於 50 萬個活躍的驗證者，全都表現完美，且全都有 32&nbsp;ETH 的有效餘額。

  - [每增量基礎獎勵](/part2/incentives/issuance/#the-base-reward-per-increment)
    - $b = \frac{1{,}000{,}000{,}000 \times 64}{\sqrt{32{,}000{,}000{,}000 \times 500{,}000}} = 505$ Gwei
  - 單一一份證明的價值
    - $R_A = \frac{14 + 26 + 14}{64}32b = 13{,}635$ Gwei
  - 單一一份同步委員會貢獻的價值
    - $R_Y = \frac{2}{32 \times 512 \times 64}500{,}000 \times 32b = 15{,}411$ Gwei
  - 因證明而來的一次區塊提議的價值
    - $R_{A_P} = \frac{500{,}000}{32}\frac{8}{64-8}R_A = 30{,}435{,}267$ Gwei
    - 註：如果鏈表現得不完美，這實際上可能更高，因為在一個被跳過的時段之後，提議者可以納入來自那個被錯失時段的高價值證明。
  - 因同步委員會貢獻而來的一次區塊提議的價值
    - $R_{Y_P} = 512\frac{8}{64-8}R_Y = 1{,}127{,}204$ Gwei

把這一切湊在一起，所有驗證者每個紀元可得的總獎勵是 $500{,}000R_A + 32(512R_Y + R_{A_P} + R_{Y_P}) = 8{,}080{,}000{,}000$ Gwei（取 5 個有效數字）。

最後，作為一個校驗和，$Tb = 500{,}000 \times 32b = 8{,}080{,}000{,}000 \text{ Gwei} = 8.080 \text{ ETH}$，即每個紀元所發行的量。

#### 個別驗證者的獎勵會有變異

實際的個別驗證者報酬，即使在一條以最佳狀態運作的信標鏈上，也會在預期金額之上下變動，因為區塊提議與同步委員會職責是隨機指派的。這導致獎勵的變異，有些驗證者賺得較多，有些賺得較少。儘管如此，一個平均的驗證者長期下來可以預期賺得與每個紀元 $nb$ 一致的報酬。

<!-- Number of validators -->

下面這張圖顯示 500,000 個驗證者——全都完美參與，每個都有 32&nbsp;ETH 的有效餘額——年度獎勵的預期分布。平均獎勵是 1.3302&nbsp;ETH／年（[前文](/part2/incentives/issuance/#validator-rewards)的 4.16% 那個數字），中位數是 1.3123&nbsp;ETH／年，但由於被選來提議區塊或參與同步委員會的隨機性，有一個很大的標準差 0.1037。事實上，純粹由於指派職責的隨機性，10% 的驗證者一年下來獎勵會少於 1.2175&nbsp;ETH，另有 10% 會多於 1.4704&nbsp;ETH。

<a id="img_reward_variance"></a>
<figure class="chart">

<!-- Number of validators -->

![一張長條圖，呈現 500,000 個質押 32&nbsp;ETH 之驗證者的年度獎勵分布。](images/charts/reward_variance.svg)

<figcaption>

500,000 個表現完美、質押 32&nbsp;ETH 之驗證者的年度信標鏈獎勵分布。變異來自不同數量區塊提議或同步委員會指派的機率。在這個理想化的模型中，某些值是無法達到的。

</figcaption>
</figure>

關於這一點的幾則評註。

第一，Altair 升級並未改變每個驗證者的預期獎勵，但它確實大幅改變了變異。這是由於區塊獎勵增加了四倍、並引入了同步委員會，伴隨著證明獎勵相應的減少。由於區塊提議與同步委員會參與是隨機指派的，而證明獎勵是穩定的，Altair 大幅增加了實際獎勵的變異。關於這項變更的分析，見 [Pintail 的文章](https://pintail.xyz/posts/modelling-the-impact-of-altair/)。

第二，還有上述分析未計入的進一步的變異來源。例如，如果我的驗證者剛好在一個「沒有區塊的被跳過時段」之後提議一個區塊，那麼我的區塊提議可能值得比一次正常的區塊提議多達 71.4%。這是因為我可以納入來自那個被跳過時段以及我自己時段的證明，並從額外的來源與目標投票中受益（但不包括額外的鏈頭投票，那會太遲，也不包括額外的同步委員會納入）。

第三（也最重要），在合併之後，驗證者另外還收到來自執行酬載的交易優先費，可能還有 MEV 相關的收入。這些能大幅增加質押者的百分比收益與收益的變異，但不會影響信標鏈上的整體發行量，因為它們來自被回收的以太幣，而非新發行。

#### 獎勵隨參與率縮放

到目前為止尚未提到的、證明獎勵一個令人意外的面向是：它們依參與率成比例縮放。也就是說，對每一項職責（來源、目標、鏈頭投票），證明者的獎勵都依「做出相同投票的總質押比例」來縮放。

例如，如果我做出了一張正確的鏈頭投票，而擁有總有效餘額增量 75% 的驗證者做出了相同的鏈頭投票，那麼我就會為那一票收到 $0.75 \times \frac{W_h}{W_{\Sigma}}nb$ 的獎勵。

這件事的一個含糊的理由是：這種縮放使得「幫助其他驗證者讓它們的證明被納入」對我有利。協定的好幾個面向並未被明示地激勵、卻多少有點昂貴，例如轉發流言訊息與證明聚合職責。這種縮放給了我一份隱含的獎勵，獎勵我藉由提供這些服務來幫助其他驗證者：如果它們表現更好，那麼我也表現更好。

要看更量化的分析，見下文[勸退攻擊](#discouragement-attacks)。

這件事一個有意思的副作用是：如果參與率下降 10%（比方說由於 10% 的驗證者離線），那麼因證明而來的總獎勵發行量會下降 19%，此外還有來自懲罰的進一步減少。

我們可以計算「因證明而來的淨發行量轉為負」的那個參與率。在參與率為 $p$ 時，一份完全正確之證明的獎勵是 $0.844nbp$，而一份錯失之證明的懲罰是 $0.625Tb$。這給了我們一個淨發行量 $p^2(0.844Tb) - (1-p)(0.625Tb)$。它的正根是 $p = 56.7\%$。但由於這低於最終確定所需的 2/3 參與率，[怠惰洩漏](/part2/incentives/inactivity/)會在我們抵達這個水準之前就啟動，並完全改變獎勵與懲罰的樣貌，所以這個計算只有理論上的趣味。

請注意，提議者獎勵並不像這樣縮放——提議者已經受到充分的激勵去納入所有相關的證明——同步委員會獎勵也不縮放。懲罰同樣不隨參與率縮放。

#### 勸退攻擊

引用 Vitalik 的[《勸退攻擊》論文](https://github.com/ethereum/research/blob/master/papers/discouragement/discouragement.pdf)：

> 勸退攻擊（discouragement attack）由「攻擊者在一個共識機制內部惡意行事，以減少其他驗證者的收益，即使對自己也有些代價」所構成，目的是促使受害者退出該機制。

攻擊者這麼做，可能是為了在系統參與者較少的情況下獲得更多獎勵。或者它們這麼做是作為對鏈發動攻擊的準備：藉由減少驗證者的數量，它們降低自己的攻擊代價。

該論文對不同種類的勸退攻擊做了一些量化分析。我會鼓勵你讀它，並把這些事情想過一遍。如其結論所言：

> 一般而言，這仍是一個活躍的研究領域，需要更多關於反制策略的研究。

信標鏈設計中已經受到「想避免勸退攻擊」這份願望影響的一些部分是：

  - 驗證者獎勵的[反平方根縮放](/part2/incentives/issuance/#inverse-square-root-scaling)；
  - 獎勵[隨參與率的縮放](#rewards-scale-with-participation)；
  - 在[怠惰洩漏](/part2/incentives/inactivity/)期間把證明獎勵歸零；以及
  - 對驗證者退出的速率限制，這意味著攻擊者需要把一場攻擊維持更久，才能以更大的代價達成相同的目的。

#### 另見

詳細的獎勵計算在規格中的這些函式裡定義：

  - 證明的驗證者獎勵在 [`get_flag_index_deltas()`](/part3/helper/accessors/#def_get_flag_index_deltas) 中作為[紀元處理](/part3/transition/epoch/)的一部分而計算。
  - 證明的提議者獎勵在 [`process_attestation()`](/part3/transition/block/#def_process_attestation) 中作為[區塊處理](/part3/transition/block/#block-processing)的一部分而計算。
  - 同步委員會參與的驗證者與提議者獎勵兩者，都在 [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate) 中作為[區塊處理](/part3/transition/block/#block-processing)的一部分而計算。

關於獎勵變異的討論，是基於 [Pintail 對 Altair 的分析](https://pintail.xyz/posts/modelling-the-impact-of-altair/)。我用來產生統計數據與圖表的程式碼，是基於那篇文章中的程式碼。

勸退攻擊在 Vitalik 的一篇[論文](https://github.com/ethereum/research/blob/master/papers/discouragement/discouragement.pdf)中有所分析。

### 懲罰 <!-- /part2/incentives/penalties/ -->

<div class="summary">

  - 未能履行其所指派之職責的驗證者，會因為失去少量質押而受到懲罰。
  - 收到一筆懲罰跟被罰沒不是同一回事！
  - 一個驗證者的損益兩平在線時間約為 43%。

</div>

#### 引言

信標鏈上對驗證者的激勵，是胡蘿蔔與棍子的結合。驗證者因為為鏈的安全做出貢獻而獲得獎勵，並因為未能做出貢獻而受到懲罰。如我們將見，懲罰相當溫和。儘管如此，它們為質押者提供了良好的動機，去確保他們的驗證者部署運作良好。

常常會聽到有人把「離線的懲罰」稱為「被罰沒」（getting slashed）。這是不正確的。被[罰沒](/part2/incentives/slashing/)是對非常特定的不當行為的嚴厲處罰，會導致驗證者被逐出協定，此外其部分或全部質押被扣除。

懲罰會從信標鏈上驗證者的餘額中扣除並實質燒毀，所以它們會減少信標鏈的淨發行量。

#### 證明懲罰

證明會因為缺失、遲到或不正確而受到懲罰。為求簡潔，我們把這些統稱為「錯失」。

證明者會因為錯失的 Casper FFG 投票——也就是錯失的來源或目標投票——而受到懲罰。但錯失的鏈頭投票並沒有懲罰。如果一張來源投票不正確，那麼目標投票就算錯失；如果來源或目標投票不正確，那麼鏈頭投票就算錯失。

讓我們更新我們的[獎勵矩陣](/part2/incentives/rewards/#rewards-table)，給出證明的懲罰與獎勵的完整全貌。回想一下，這顯示的是權重；我們需要乘以 $\frac{nb}{W_{\Sigma}}$ 才能得到實際的獎勵。

<a id="penalties-rewards-table"></a>

| 時效性 | 1 個時段 | <= 5 個時段 | <= 32 個時段 | > 32 個時段（缺失） |
| - | - | - | - | - |
| 來源錯誤                    | $-W_s-W_t$    | $-W_s-W_t$ | $-W_s-W_t$ | $-W_s-W_t$ |
| 僅來源正確             | $W_s-W_t$     | $W_s-W_t$  | $-W_s-W_t$ | $-W_s-W_t$ |
| 僅來源與目標正確  | $W_s+W_t$     | $W_s+W_t$  | $-W_s+W_t$ | $-W_s-W_t$ |
| 來源、目標與鏈頭正確 | $W_s+W_t+W_h$ | $W_s+W_t$  | $-W_s+W_t$ | $-W_s-W_t$ |

為了更多直覺，我們可以代入數字 $W_s = 14$、$W_t = 26$、$W_h = 14$，並以 $W_{\Sigma} = 64$ 正規化：

| 時效性 | 1 個時段 | <= 5 個時段 | <= 32 個時段 | > 32 個時段（缺失） |
| - | - | - | - | - |
| 來源錯誤                    | $-0.625$ | $-0.625$ | $-0.625$ | $-0.625$ |
| 僅來源正確             | $-0.188$ | $-0.188$ | $-0.625$ | $-0.625$ |
| 僅來源與目標正確  | $+0.625$ | $+0.625$ | $+0.188$ | $-0.625$ |
| 來源、目標與鏈頭正確 | $+0.844$ | $+0.625$ | $+0.188$ | $-0.625$ |

##### 損益兩平在線時間

質押者有時擔心停機會非常昂貴。為了檢視這一點，我們可以估算損益兩平在線時間。我們會忽略同步委員會參與，因為那太罕見了，所以這個計算只與證明相關。

我們會假設：在線時，該驗證者的表現完美，而其餘的驗證者也表現良好（這兩者都相當接近信標鏈第一年的實際表現）。

如果 $p$ 是該驗證者在線的時間比例，那麼它的淨收入就是 $0.844p - 0.625(1-p) = 1.469p - 0.625$。這在 $p > 42.5\%$ 時為正。所以，如果你的驗證者在線時間超過 42.5%，你就會賺得正的報酬。

一個有用的經驗法則是：要從一天的停機中恢復，大約要花一天的在線時間。

#### 同步委員會懲罰

目前在執行同步委員會職責的那一小群驗證者，每為一個正確的鏈頭區塊（從提議者的角度而言正確）背書的時段，就收到一份[獎勵](/part2/incentives/rewards/#sync-committee-rewards)。

不參與（為錯誤的鏈頭區塊簽章、或根本沒出現）的驗證者，會收到一筆「恰好等於它們本可因為正確而賺得之獎勵」的懲罰。而區塊提議者對於那份缺失的貢獻不會收到任何東西。

歷史註記：由於對任何給定的驗證者而言，同步委員會參與都很罕見，而且獎勵相當可觀，較早期的設計曾有[疑慮](https://github.com/ethereum/consensus-specs/issues/2448)，擔心由此產生的驗證者[獎勵變異](/part2/incentives/rewards/#individual-validator-rewards-vary)會相當不公平。小型質押者為了把變異抹平，可能會偏好加入質押池而非獨立質押，類似於工作量證明礦池之所以興起的原因。

降低變異的一個[建議做法](https://github.com/ethereum/consensus-specs/pull/2450)，是完全不獎勵同步委員會參與，而是提高每個人的整體獎勵水準，並在同步委員會驗證者不參與時懲罰它們。最終[被採用的做法](https://github.com/ethereum/consensus-specs/pull/2453)，是縮短同步委員會的長度（意味著獎勵較低，但較頻繁）、減少參與所佔總獎勵的比例，並引入一項對不參與的懲罰——算是走到另一個提案的一半路。

不採用前一個提案——儘管它很優雅——的主要原因[^fn-sync-penalties]，似乎圍繞著「被明示地懲罰、卻從不被明示地獎勵」的心理。一個紀元下來，不參與同步委員會的懲罰會大幅大於證明獎勵。此外，參與並不完全操之在驗證者自己手中：它取決於下一個區塊提議者是否在正確的分叉上。也有疑慮擔心會改變提議者獎勵與「它們納入區塊之職責的價值」之間那種[乾淨的關係](/part2/incentives/rewards/#remarks-on-proposer-rewards)。

[^fn-sync-penalties]: 這場相當有意思的討論仍留在 [Ethereum R&D Discord](https://discord.com/channels/595666850260713488/595701319793377299/847063172174577744) 上。

#### 關於懲罰的評註

並沒有與區塊提議者相關的明示懲罰。

尤其，對於「未能納入來自 Eth1 鏈的存款」並沒有明示的懲罰，對於納入它們也沒有任何直接的誘因。然而，如果一個區塊提議者沒有納入網路其餘部分所知道的存款，那麼它的區塊就是無效的。這提供了一個強而有力的誘因去納入尚未處理的存款。

另請注意，懲罰並不像[獎勵那樣](/part2/incentives/rewards/#rewards-scale-with-participation)隨參與率縮放。

#### 另見

詳細的懲罰計算在規格中的這些函式裡定義：

  - 錯失證明的懲罰在 [`get_flag_index_deltas()`](/part3/helper/accessors/#def_get_flag_index_deltas) 中作為[紀元處理](/part3/transition/epoch/)的一部分而計算。
  - 錯失同步委員會參與的懲罰在 [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate) 中作為[區塊處理](/part3/transition/block/#block-processing)的一部分而計算。

### 怠惰洩漏 <!-- /part2/incentives/inactivity/ -->

<div class="summary">

  - 當信標鏈未在最終確定時，它會進入一種特殊的「怠惰洩漏」模式。
  - 證明者不收到任何獎勵。不參與的驗證者會根據它們的過往記錄收到越來越大的懲罰。
  - 這是被設計來在大量驗證者永久故障的情況下恢復最終性的。

</div>

#### 引言

如果信標鏈未最終確定一個檢查點的時間超過 [`MIN_EPOCHS_TO_INACTIVITY_PENALTY`](/part3/config/preset/#min_epochs_to_inactivity_penalty)（4）個紀元，那麼它就進入「怠惰洩漏」模式[^fn-inactivity-leak-mainnet]。

[^fn-inactivity-leak-mainnet]: 以太坊主網在 2023 年 5 月 12 日，從紀元 200,750 到 200,758 經歷了連續九個紀元的延遲最終確定。這是主網上第一段足夠長、足以觸發怠惰洩漏的延遲最終確定期間。

怠惰洩漏是一種緊急狀態，其中獎勵與懲罰被修改如下。

  - 證明者不收到任何證明獎勵，而證明懲罰維持不變。
  - 任何被判定為不活躍的驗證者，其怠惰分數會被提高，導致一項額外的怠惰懲罰，這項懲罰有可能隨時間以平方方式成長。這就是怠惰洩漏，有時稱為平方洩漏（quadratic leak）。
  - 提議者與同步委員會獎勵維持不變。

怠惰洩漏的構想在最初的 [Casper FFG 論文](https://arxiv.org/abs/1710.09437)中被提出。它所處理的問題，是「當超過三分之一的驗證者離線時，如何恢復最終性（在某種意義上即活躍性）」。最終性需要代表總質押 2/3 的驗證者投出多數票。

這個機制的運作如下。當偵測到最終性喪失時，怠惰洩漏會逐步減少未做出證明之驗證者的質押，直到最終，參與的驗證者掌控了剩餘質押的 2/3。屆時它們就能再次開始最終確定檢查點。

這個怠惰懲罰機制，是被設計來在面對災難性事件時長期保護鏈的（有時被稱為「在第三次世界大戰中存活的能力」）。其結果可能是信標鏈在一個網路分區的兩側永久地分裂成兩條獨立的鏈，而對於任何無法在幾週內修復的問題，這被假定為一個合理的結果。在這個意義上，信標鏈在形式上把可用性置於一致性之上的優先位置。（你[兩者不可兼得](https://en.wikipedia.org/wiki/CAP_theorem)。）

無論如何，它為質押者提供了一個強而有力的誘因，去修復他們所有的問題並重新上線。

在怠惰洩漏期間沒有驗證者收到證明獎勵的原因，再一次是由於[勸退攻擊](/part2/incentives/rewards/#discouragement-attacks)的可能性。一個攻擊者可能刻意把信標鏈逼進怠惰洩漏，或許藉由對其他驗證者結合審查與阻斷服務攻擊。這會使不參與者遭受洩漏之苦，而攻擊者卻繼續正常地做出證明。我們需要在這種情境下增加攻擊者的代價，而我們是藉由在怠惰洩漏期間完全不獎勵證明來做到這一點的。

如同懲罰一樣，因怠惰洩漏而從驗證者的信標鏈帳戶中扣除的金額會實質燒毀，減少信標鏈整體的淨發行量。

#### 數學

讓我們研究洩漏對單一一個驗證者餘額的影響，假設在怠惰洩漏（未最終確定）的期間，該驗證者完全離線。

在每個紀元，離線的驗證者會被處以一筆與 $tB / \alpha$ 成比例的懲罰，其中 $t$ 是自鏈上次最終確定以來的紀元數，$B$ 是該驗證者的有效餘額，而 $\alpha$ 是當時通行的[怠惰懲罰商](/part3/config/preset/#rewards-and-penalties)（目前是 `INACTIVITY_PENALTY_QUOTIENT_BELLATRIX`）。

有效餘額 $B$ 依設計會維持恆定一陣子，在這段時間內，$t$ 個紀元之後的懲罰總額會是 $t(t+1)B / 2\alpha$：著名的「平方洩漏」。如果 $B$ 是連續可變的，那麼這項懲罰會滿足 $\frac{dB}{dt}=-\frac{tB}{\alpha}$，解之可得指數式 $B(t)=B_0e^{-t^2/2\alpha}$。實際的行為介於這兩者之間（分段平方），因為有效餘額既非恆定、也非連續可變，而是以階梯式的方式遞減。

在連續近似中，怠惰懲罰商 $\alpha$ 是「把一個不參與驗證者的餘額減到 $1 / \sqrt{e}$（即其初始值約 60.7%）所需時間」的平方。`INACTIVITY_PENALTY_QUOTIENT_BELLATRIX` 的值為 $2^{24}$，這相當於 4096 個紀元，或 18.2 天。

對於信標鏈的 Phase&nbsp;0，`INACTIVITY_PENALTY_QUOTIENT` 的值[被增加](https://github.com/ethereum/consensus-specs/commit/157f7e8ef4be3675543980e68581eb4b73284763)了四倍，從 $2^{24}$ 增為 $2^{26}$，使得萬一在早期由於實作問題而發生未最終確定，驗證者所受的懲罰會較不嚴厲。事實上，信標鏈 Phase&nbsp;0 整整十一個月期間，並沒有任何未最終確定的情形。

這個值在 Altair 升級中被減少了四分之一，從 $2^{26}$（`INACTIVITY_PENALTY_QUOTIENT`）減為 $3 \cdot 2^{24}$（`INACTIVITY_PENALTY_QUOTIENT_ALTAIR`），並在 [Bellatrix 升級](/part4/history/bellatrix/)中減為它的最終值 $2^{24}$（`INACTIVITY_PENALTY_QUOTIENT_BELLATRIX`）。降低怠惰懲罰商，會在發生怠惰洩漏時加快最終確定的恢復。

#### 怠惰分數

在 Phase&nbsp;0 期間，怠惰懲罰是一個遞增的全域金額，套用於所有未在某個紀元參與的驗證者，不論它們各自的參與過往記錄如何。所以一個能夠在相當大一部分時間裡參與的驗證者，仍然可能由於怠惰懲罰的成長而受到相當嚴厲的懲罰。Vitalik 給了一個簡化的[例子](https://github.com/ethereum/consensus-specs/issues/2125#issue-737768917)：「如果完全離線的驗證者被洩漏而失去其餘額的 40%，那麼一個一直努力維持在線、並成功完成其職責 90% 的人，仍然會失去其餘額的 4%。可以說這並不公平。」我們在 [Medalla 測試網事件](https://hackmd.io/@benjaminion/wnie2_200822#Medalla-Meltdown-redux)期間發現，在你周遭一片混亂時要讓一個驗證者維持在線並不容易。我們不想懲罰那些誠實地盡力而為的質押者。

為了改善這一點，Altair 升級引入了儲存在狀態中的「個別驗證者怠惰分數」。驗證者的分數每個紀元如下被更新。

  - 在紀元 $N$ 結束時，不論是否處於怠惰洩漏，
    - 當一個驗證者在紀元 $N-1$ 做出了一張正確且及時的目標投票時，把它的分數減一，並
    - 否則，把該驗證者的分數增加 `INACTIVITY_SCORE_BIAS`（四）。
  - 當_不_處於怠惰洩漏時，
    - 把每個驗證者的分數減少 `INACTIVITY_SCORE_RECOVERY_RATE`（十六）。

以圖形來看，這個流程圖看起來像這樣。

<a id="img_incentives_inactivity_scores_flow"></a>
<figure class="diagram">

![一張流程圖，顯示怠惰分數更新如何計算。](images/diagrams/incentives-inactivity_scores_flow.svg)

<figcaption>

每個驗證者的怠惰分數如何被更新。順利的流程正好走過中間。在紀元 $N$ 結束時更新分數時，「活躍」意味著在紀元 $N-1$ 做出了一張正確且及時的目標投票。

</figcaption>
</figure>

請注意，分數有一個零的下限。

當不處於怠惰洩漏時，當驗證者做出一張及時的目標投票時，它們的怠惰分數每個紀元被減少 `INACTIVITY_SCORE_RECOVERY_RATE` ` + ` `1`，當它們沒有時，被減少 `INACTIVITY_SCORE_RECOVERY_RATE` ` - ` `INACTIVITY_SCORE_BIAS`。所以，即使是表現不佳的驗證者，在洩漏之外分數也會下降。

當處於洩漏時，如果 $p$ 是介於 $0$ 與 $1$ 之間的參與率，而 $\lambda$ 是 `INACTIVITY_SCORE_BIAS`，那麼 $N$ 個紀元之後的預期分數是 $\max (0, N((1-p)\lambda - p))$。對於 $\lambda = 4$，這是 $\max (0, N(4 - 5p))$。所以一個參與時間達 80% 或以上的驗證者，能維持一個有界、接近零的分數。在平均參與率低於 80% 時，它的分數會無界地增加。

這很不錯，因為如果許多驗證者能夠斷斷續續地參與，這表示降臨到鏈上的那個事件——不論是什麼——是有可能恢復的，不像例如一個永久的網路分區、或一個超級多數的網路分叉。怠惰洩漏的用意是為無法恢復的情況帶來最終性，所以如果情況是可恢復的，延長最終確定的時間很可能是件好事。

下面這張圖說明了一些情境。我們有一個從零開始、在 100 個紀元後結束的怠惰洩漏，在那之後最終性恢復，我們不再處於洩漏中。有五個驗證者。從最低的那條線往上算，它們是：

1. 始終在線：在每個紀元都正確地登錄一張及時的目標投票。怠惰分數維持在零。
2. 90% 在線：怠惰分數維持有界、接近零。由上述分析，預期任何優於 80% 在線的情況都會把分數約束在接近零。
3. 70% 在線：怠惰分數隨時間緩慢成長。
4. 大致在線，但在紀元 50 與 75 之間離線：在最初的在線期間怠惰分數為零；在洩漏期間離線時線性且相當快速地成長；在洩漏期間重新上線時緩慢下降；洩漏一結束就快速下降。
5. 始終離線：怠惰分數在洩漏期間快速增加，洩漏一結束就更快速地下降。

<a id="img_inactivity_scores"></a>
<figure class="chart">

![一張圖，說明怠惰分數的種種情境。](images/charts/inactivity_scores.svg)

<figcaption>

五種不同驗證者人物在一個「從零開始、在紀元 100 結束」之怠惰洩漏中的怠惰分數（標記為「End」並以虛線顯示）。標記為「A」與「B」的點線標出了第四個驗證者離線期間的開始與結束。

</figcaption>
</figure>

#### 怠惰懲罰

怠惰懲罰在每個紀元根據驗證者各自的怠惰分數套用於所有驗證者，不論是否有洩漏正在進行。當沒有洩漏時，分數會回到零（對活躍的驗證者快速地，對不活躍的驗證者較不快速地），所以大部分時候這是一個空操作。

驗證者 $i$ 的懲罰被計算為

$$
\begin{split}
s_{i}B_{i} / (\tt{INACTIVITY\_SCORE\_BIAS} \times \tt{INACTIVITY\_PENALTY\_QUOTIENT\_BELLATRIX}) \\
= \frac{s_{i}B_{i}}{4 \times 16{,}777{,}216}
\end{split}
$$

其中 $s_i$ 是該驗證者的怠惰分數，而 $B_i$ 是該驗證者的有效餘額。

這項懲罰在每個紀元被套用，所以（對於恆定的 $B_i$）總懲罰與上方怠惰分數曲線下方的面積成比例。用同樣的五種驗證者人物，我們可以在下面這張圖中量化這些懲罰。

1. 始終在線：沒有因洩漏而來的懲罰。
2. 90% 在線：因洩漏而來的懲罰可忽略不計。
3. 70% 在線：總懲罰在洩漏期間以平方方式但緩慢地成長，並在洩漏結束後快速停止。
4. 大致在線，但在紀元 50 與 75 之間離線：在洩漏期間有一個成長的懲罰，在洩漏結束時快速停止。
5. 始終離線：我們可以從曲線最初的拋物線形狀清楚地看到這項懲罰的平方本質。在洩漏結束之後，懲罰要花約 35 個紀元才回到零。

<a id="img_inactivity_balances"></a>
<figure class="chart">

![一張圖，顯示怠惰洩漏在五種不同情境中的效果。](images/charts/inactivity_balances.svg)

<figcaption>

在怠惰洩漏懲罰被套用之後，五種驗證者人物各自所保有的餘額。情境與上方的圖表完全相同。

</figcaption>
</figure>

我們可以看到，新的計分系統意味著某些驗證者在最終確定再次開始之後，仍會繼續因洩漏而受到懲罰。這是[刻意的](https://github.com/ethereum/consensus-specs/issues/2098)。當洩漏使信標鏈最終確定時，在那個時點我們只有三分之二的質押在線。如果我們立即停止洩漏（像我們從前那樣），那麼在線的質押量就會維持在接近三分之二，鏈就會易受「隨著少量驗證者來來去去而在最終性中進進出出」之害。我們在上線之前的一些測試網上看過這種行為。在最終確定之後繼續洩漏，能把參與驗證者的餘額提升到大於三分之二，提供一個應能緩和這種行為的緩衝。

#### 逐出

要讓怠惰洩漏有效地重新取得最終性，並不需要把不參與的驗證者從活躍驗證者集合中逐出。減少那些不參與驗證者所持有的總質押比例就足夠了。

儘管如此，當一個驗證者的有效餘額掉到 [`EJECTION_BALANCE`](/part3/config/configuration/#ejection_balance) 時，它就會被退出。這在紀元結束的[註冊表更新](/part3/transition/epoch/#registry-updates)中處理。請注意，由於有效餘額的計算方式，逐出會在實際餘額掉到 16.75&nbsp;ETH 以下時發生。

我們可以模擬一個完全離線的驗證者，純粹由於怠惰洩漏而被逐出要花多久。實際上由於還有錯失證明的額外懲罰，會稍微早一點。

對於一個以 32&nbsp;ETH 實際餘額起步進入洩漏期的驗證者，模擬顯示它要花 4686 個紀元（將近 3 週）才會被逐出。我們也可以把這當成「不論有多少驗證者離線，信標鏈要花多久才能恢復最終性」的一個粗略上界[^fn-ejection-queue]。

[^fn-ejection-queue]: 這因為「驗證者需要被排入退出佇列、以及處理那個佇列的速率限制」而變得複雜。要瞬間大規模退出驗證者是不可能的。退出中的驗證者在它們排在佇列裡時仍受怠惰洩漏的約束，所以它們的有效餘額可能掉到低於 16&nbsp;ETH。

<details>
<summary>逐出模擬程式碼</summary>

```python
GWEI = 10 ** 9
EJECTION_BALANCE = 16 * GWEI
MAX_EFFECTIVE_BALANCE = 32 * GWEI
HYSTERESIS_QUOTIENT = 4
INACTIVITY_SCORE_BIAS = 4
INACTIVITY_PENALTY_QUOTIENT = 2 ** 24

# Simplified hysteresis for monotonically decreasing balance
def calc_effective_balance(balance):
    return min(MAX_EFFECTIVE_BALANCE, (balance + GWEI // HYSTERESIS_QUOTIENT) // GWEI * GWEI)

epoch = 0
score = 0
balance = 32 * GWEI
effective_balance = calc_effective_balance(balance)

while effective_balance > EJECTION_BALANCE:
    balance -= effective_balance * score // (INACTIVITY_SCORE_BIAS * INACTIVITY_PENALTY_QUOTIENT)
    effective_balance = calc_effective_balance(balance)
    score += INACTIVITY_SCORE_BIAS
    epoch += 1

print(balance / GWEI)
print(effective_balance // GWEI)
print(epoch)
```

</details>

#### 另見

出自規格：

  - 怠惰分數在紀元處理期間於 [`process_inactivity_updates()`](/part3/transition/epoch/#def_process_inactivity_updates) 中被更新。
  - 怠惰懲罰在 [`get_inactivity_penalty_deltas()`](/part3/transition/epoch/#def_get_inactivity_penalty_deltas) 中被計算。

關於怠惰洩漏運作機制的原始描述，見 [Casper 論文](https://arxiv.org/abs/1710.09437)第 4.2 節。

### 罰沒 <!-- /part2/incentives/slashing/ -->

<div class="summary">

  - 驗證者會因為違反非常特定、可能是對鏈攻擊一部分的協定規則而被罰沒。
  - 被罰沒的驗證者會被退出信標鏈，並收到三種類型的懲罰。
  - 關聯懲罰意味著對於孤立的事件處罰很輕，但當許多驗證者在短時間內被罰沒時則很嚴厲。
  - 區塊提議者因為舉報可罰沒過錯的證據而收到獎勵。

</div>

#### 引言

罰沒發生在驗證者做出違反非常特定協定規則的證明或區塊提議之時。它適用於有可能是對鏈攻擊一部分的行為。被罰沒意味著失去一筆可觀的質押，並被逐出協定。它比較像「處罰」而非「懲罰」[^fn-slashing-punitive]。好消息是，質押者可以採取簡單的預防措施，以保護自己永遠不被罰沒。

[^fn-slashing-punitive]: 罰沒的概念，其根源在於 Vitalik 2014 年初的 [Slasher](https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm) 演算法。我們目前的設計看起來相當不同，但有些東西保留了下來。尤其，他說「我們把〔它〕稱為 Slasher，以表達它嚴厲懲罰的本質」，而我們基於同樣的原因沿用「罰沒」（slashing）這個名稱。

導致罰沒的行為如下。

1. 與 Casper FFG 共識相關的，
    - 為同一個目標檢查點做出兩份相異的證明，或
    - 做出一份「其來源與目標投票『包圍』同一驗證者另一份證明中的來源與目標投票」的證明。
2. 與 LMD GHOST 共識相關的，
    - 在同一個高度提議多於一個相異的區塊，或
    - 以相同的來源與目標檢查點，為不同的鏈頭區塊做出證明[^fn-slash-different-heads]。

[TODO: Link to Casper FFG and LMD GHOST sections when done]::

[^fn-slash-different-heads]: 這個條件在[程式碼](/part3/helper/predicates/#is_slashable_attestation_data)中不太明顯。它之所以成立，是因為兩份有著相同來源與目標投票、但鏈頭投票不同的證明，彼此是相異的。它們因此被算作對同一個目標的相衝突投票，並在第一條 Casper FFG 規則下被罰沒。

所有這些可罰沒的行為都與「含糊其辭」（equivocation）有關，也就是當一個驗證者與它先前向網路宣告的某件事相矛盾之時。[^fn-avoid-slashing]

[^fn-avoid-slashing]: 要避免被罰沒，只要確保不含糊其辭就行了。任何正常運作的客戶端（在沒有臭蟲的情況下）永遠不會這麼做。就所能查明的範圍而言，迄今每一次以太坊罰沒，都是由於某個節點營運者同時在兩個不同的節點上運行相同的驗證者金鑰，或許是一種被誤導的、想改善在線時間的做法。別這麼做。（更新：[有一次罰沒](https://beaconcha.in/slot/6142320#proposer-slashings)是由於一個提議者[攻擊一個 MEV Relay](https://collective.flashbots.net/t/post-mortem-april-3rd-2023-mev-boost-relay-incident-and-related-timing-issue/1540)。）

與 Casper FFG 相關的罰沒條件，支撐著以太坊&nbsp;2.0 的[經濟性最終性](/part2/incentives/staking/#economic-finality)保證。它們實質上為「回退最終性」加上了一個明確界定的代價。

與 LMD GHOST 相關的罰沒條件，是被設計來對抗[無利害關係](https://ethereum.stackexchange.com/questions/2402/what-exactly-is-the-nothing-at-stake-problem)問題的，與經濟性最終性沒有直接關係。它們懲罰可能導致諸如[平衡攻擊](https://ethresear.ch/t/a-balancing-attack-on-gasper-the-current-candidate-for-eth2s-beacon-chain/8079?u=benjaminion)（balancing attack）這類嚴重問題的壞行為。由於我們已經有了可供 Casper FFG 使用的罰沒機制，把它擴充到 LMD GHOST 夠簡單的。

如同懲罰一樣，任何因罰沒而從驗證者信標鏈帳戶中扣除的金額都會實質燒毀，減少信標鏈整體的淨發行量。

#### 被罰沒的代價

說到被罰沒的處罰，違反的是哪一條規則並不重要。所有罰沒都以相同的方式處理。

##### 初始懲罰

罰沒是由「過錯的證據被納入一個信標鏈區塊」所觸發的。一旦證據被網路確認，犯規的驗證者（或多個驗證者）就被罰沒。

犯規者的有效餘額會立即有 $\frac{1}{32}$（[`MIN_SLASHING_PENALTY_QUOTIENT_BELLATRIX`](/part3/config/preset/#min_slashing_penalty_quotient)）從它的實際餘額中被扣除。由於有效餘額有上限，這最多是 1&nbsp;ETH。

這項初始懲罰[被引入](https://github.com/ethereum/consensus-specs/pull/624)，是為了讓驗證者出於任何原因自我罰沒都多少有點代價[^fn-initial-penalty]。

[^fn-initial-penalty]: 我不清楚在信標鏈目前的設計下，自我罰沒在什麼情況下會帶來任何好處。迄今，這項初始懲罰唯一的效果，就是懲罰那些把質押設定弄錯（在不止一個地方運行金鑰）的小型質押者，這在我看來過於嚴厲。我曾主張它應該被完全移除。儘管如此，它仍然存在。

連同這項初始懲罰，該驗證者會被排入退出佇列，並把它的可提領紀元設定到大約 36 天（[`EPOCHS_PER_SLASHINGS_VECTOR`](/part3/config/preset/#epochs_per_slashings_vector)，即 8192 個紀元）之後的未來。

在 Phase&nbsp;0 期間，初始懲罰是犯規者有效餘額的 $\frac{1}{128}$，在 Altair 期間是 $\frac{1}{64}$。它在合併前的 [Bellatrix 升級](/part4/history/bellatrix/)中被提升到它的完整值，即被罰沒驗證者有效餘額的 $\frac{1}{32}$，最多 1&nbsp;ETH。

##### 關聯懲罰

在它可提領期的中點（被罰沒之後 18 天），被罰沒的驗證者預定要收到第二筆懲罰。

這第二筆懲罰是基於「在我們的驗證者被罰沒之前與之後的 18 天內被罰沒的質押總量」。其構想是縮放這項處罰，使得「一個對鏈幾乎不構成威脅的一次性事件」只受到輕微的處罰，而「一個有可能是試圖最終確定相衝突區塊之結果的大規模罰沒事件」則受到盡可能最大程度的處罰。

為了能夠計算這一點，信標鏈為「在最近 8192 個紀元（約 36 天）內被罰沒的所有驗證者」維護一份有效餘額的記錄。

關聯懲罰如下被計算。

 1. 計算「前 36 天內被罰沒的所有驗證者」之有效餘額（在那些驗證者被罰沒時的有效餘額）的總和。也就是我們的驗證者被罰沒之前的 18 天與之後的 18 天。
 2. 把這個總和乘以 [`PROPORTIONAL_SLASHING_MULTIPLIER_BELLATRIX`](/part3/config/preset/#proportional_slashing_multiplier)，但把結果上限封在 `total_balance`，即所有驗證者的總活躍餘額。
 3. 把被罰沒驗證者的有效餘額乘以第 2 步的結果，然後除以 `total_balance`。這得出一個介於零與「被罰沒驗證者完整有效餘額」之間的金額。那個金額被從它的實際餘額中扣除作為懲罰。請注意，在奇怪的角落案例中，有效餘額可能超過實際餘額，但 [`decrease_balance()`](/part3/helper/mutators/#def_decrease_balance) 確保餘額不會變成負的。

自 Bellatrix 以來，罰沒乘數被設為 3。設 $S$ 為過去 36 天被罰沒驗證者清單中的增量總和，$B$ 為我的有效餘額，$T$ 為總增量，這個計算看起來如下。

$$
\text{關聯懲罰} = \min(B, \frac{3SB}{T})
$$

有意思的是，[由於](https://github.com/ethereum/consensus-specs/issues/1322)[實作](/part3/transition/epoch/#def_process_slashings)中整數算術的建構方式，如果 $3SB < T$，這個計算的結果會是零。實際上，這項懲罰被向下捨入到最接近的整數量的以太幣。其後果是，當罰沒很少時，根本沒有額外的關聯罰沒懲罰，這大概是件好事。

比例罰沒乘數在信標鏈的早期部署過程中逐步增加。在創世時，它被設為一（`PROPORTIONAL_SLASHING_MULTIPLIER`），在 Altair 時被增為二（`PROPORTIONAL_SLASHING_MULTIPLIER_ALTAIR`），在 Bellatrix 時被設為它的最終值三（`PROPORTIONAL_SLASHING_MULTIPLIER_BELLATRIX`）。這原本的用意是在我們逐漸習慣運行信標鏈的同時，較不嚴厲地處罰被罰沒的驗證者。事實上，在這個機制下並沒有發生招致大於零之懲罰的關聯罰沒。

##### 其他懲罰

正常退出（藉由發送一份自願退出訊息）的驗證者，被期望只參與到它們的退出紀元為止，那通常只是幾個紀元之後。

一個被罰沒的驗證者會繼續收到證明懲罰，直到它的可提領紀元——那被設定到罰沒之後 8192 個紀元（36 天）——而在這段時間內它們無法收到任何證明獎勵。它們在這整段期間也受制於任何可能正在運作中的[怠惰洩漏](/part2/incentives/inactivity/)。不論被罰沒的驗證者做什麼，它都被處罰得彷彿它正未能參與一樣。[^fn-slashed-validators]

[^fn-slashed-validators]: 被罰沒後有這麼長一段「驗證者繼續收到懲罰」的延宕期，看起來像是「落井下石」，尤其因為被罰沒的驗證者被鎖定的時間，是計算關聯懲罰所需時間的兩倍。Vitalik [說](https://notes.ethereum.org/@vbuterin/Sys3GLJbD#Aside-note-on-a-validators-life-cycle)，這項措施「被納入，是為了防止自我罰沒成為逃避怠惰洩漏的一種辦法」。但驗證者並不需要自我罰沒來避開這一點；它們大可以做一次正常的自願退出。

<!-- Number of validators -->

所以，除了初始罰沒懲罰與關聯懲罰之外，還有一筆進一步的懲罰，最多可達 $8192\frac{14 + 26}{64}32b = 82{,}739{,}200 \text{ Gwei} = 0.0827 \text{ ETH}$（以 50 萬個驗證者為基礎），其中 $b$ 是[每增量基礎獎勵](/part2/incentives/issuance/#the-base-reward-per-increment)。這假設鏈不處於怠惰洩漏中；如果它處於其中，這些懲罰會高得多。

被罰沒的驗證者直到抵達它們的退出紀元之前，都有資格被選來提議區塊，但那些區塊會被視為無效，所以它們沒有可得的提議者獎勵。這樣做是為了不立即重新計算職責指派——那會破壞它們所擁有的前瞻保證。（提議者選擇演算法大可以被輕易修改成[跳過被罰沒的驗證者](https://github.com/ethereum/consensus-specs/pull/3175)，但目前不是那樣實作的。）

然而，在一個有意思的邊角案例中，被罰沒的驗證者直到抵達它們的退出紀元之前，都有資格被選來執行同步委員會職責，並收到同步委員會參與的獎勵。不過，在沒有大規模罰沒事件的情況下，這發生的機率相當微小。

#### 舉報一次罰沒的價值

為了讓信標鏈能驗證罰沒並對犯規者採取行動，證據需要被納入一個信標區塊。為了激勵驗證者付出這份心力，對於「納入罰沒的區塊」的提議者有一項特定的獎勵。

##### 提議者獎勵

在初始罰沒舉報被納入一個區塊的時點，該區塊的提議者收到一份獎勵，為 `validator.effective_balance` / [`WHISTLEBLOWER_REWARD_QUOTIENT`](/part3/config/preset/#whistleblower_reward_quotient)，如果 $B$ 是被罰沒驗證者的有效餘額，這就是 $B / 512$。

一份提議者罰沒違規的舉報只能罰沒一個驗證者，但一份證明罰沒違規的舉報可以同時罰沒多達一整個委員會，那可能是數百個驗證者。這對納入這些舉報的提議者而言可能非常有利可圖。單一一個區塊最多可包含 16 份提議者罰沒舉報，以及最多 2 份證明者罰沒舉報。

請注意，支付這份獎勵並不需要新的發行。提議者獎勵遠少於套用於該驗證者的初始罰沒，所以一次罰沒事件所造成的淨發行量永遠是負的。

##### 吹哨者獎勵

在實作「舉報罰沒證據之獎勵」的[程式碼](/part3/helper/mutators/#def_slash_validator)中，有為一份「吹哨者獎勵」所做的安排，吹哨者收到上述獎勵的 $\frac{7}{8}$，提議者收到 $\frac{1}{8}$。

其構想是激勵那些搜尋並發現可罰沒行為之證據的節點，那可能是一個密集的過程。

然而，這項功能目前在信標鏈上並未被使用，提議者如上文所述同時收到吹哨者獎勵與提議者獎勵。難題在於，提議者要直接竊取一份罰沒舉報太容易了，所以分開激勵它們沒有意義。這不是一個理想的狀況，但到目前為止，信標鏈上似乎有足夠多利他的罰沒偵測器在運行，足以讓罰沒被迅速舉報。實務上只需要有一個。

這項功能在未來的升級中可能會變得有用。

#### 另見

出自規格：

  - 初始罰沒懲罰與提議者獎勵在區塊處理期間於 [`slash_validator()`](/part3/helper/mutators/#def_slash_validator) 中被套用。
  - 關聯罰沒懲罰在紀元處理期間於 [`process_slashings()`](/part3/transition/epoch/#def_process_slashings) 中被套用。

在《Serenity 設計原理》中，Vitalik 就「以太坊&nbsp;2.0 為何[納入提議者罰沒](https://notes.ethereum.org/@vbuterin/rkhCgQteN#Slashing)」給了一些進一步的背景。它特別是為了勸阻質押者同時運行主要節點與備援節點。

### 多樣性 <!-- /part2/incentives/diversity/ -->

<div class="summary">

  - 信標鏈的激勵強烈鼓勵客戶端部署、託管基礎設施與質押池之間的多樣性。
  - 缺乏多樣性會危及鏈本身，也危及所有運行多數客戶端的人。
  - 由單一一個客戶端實作所託管的驗證者份額越大，風險就越大。
  - 當沒有單一一種客戶端類型管理超過三分之一（33%）的驗證者時，信標鏈最為穩健、最能容錯。

</div>

#### 多樣性使我們所有人更強

正如生物生態系中的多樣性使它們更有韌性，而單一栽培（monoculture）使它們非常脆弱——是的，我一直在看 David Attenborough（的紀錄片）——以太坊質押也是如此。

[怠惰洩漏](/part2/incentives/inactivity/)與罰沒的[關聯懲罰](/part2/incentives/slashing/#the-correlation-penalty)兩者都強烈鼓勵盡可能讓網路多樣化，這並非無心之舉。

例如，怠惰洩漏在以下這樣的網路上發生的可能性大得多：單一一個客戶端實作運行超過 33% 的驗證者，或單一一個質押營運者控制超過 33% 的驗證者，或超過 33% 的驗證者被部署到同一個託管基礎設施上。所有這些情境都構成了單一故障點，可能阻止信標鏈最終確定，並導致一場最嚴厲懲罰「運行多數（已離線）客戶端者」的洩漏。

#### 情境

讓我們考慮一些情境。為了這個練習，假設你正在運行信標鏈客戶端 X。在每個情境中，你以及其他使用客戶端 X 的人，託管著管理總質押某一比例的驗證者。我們會考慮如果客戶端 X 有一個使它癱瘓的臭蟲會發生什麼事。它可能是一個共識臭蟲，或另一種使該客戶端離開網路的臭蟲：我們在上線前的測試網上都看過這兩者的例子。

##### 1. 客戶端 X 擁有少於三分之一的質押

當一個管理少於三分之一總質押的客戶端癱瘓時，後果微乎其微。信標鏈可以照常繼續最終確定。客戶端 X 的使用者在臭蟲被修復之前只會遭受正常的離線懲罰，不過其他驗證者的獎勵也會全面降低。但這並不是災難性的，而且有時間在不恐慌的情況下復原，方法是修復臭蟲，或換用一個不同的客戶端。

_當沒有單一一種客戶端類型管理超過三分之一（33%）的驗證者時，信標鏈最為穩健、最能容錯。_

##### 2. 客戶端 X 擁有超過三分之一的質押

如果客戶端 X 在管理超過三分之一總質押時癱瘓，那麼信標鏈將無法最終確定，並進入[怠惰洩漏](/part2/incentives/inactivity/)。

在這種情況下，沒有驗證者會收到證明的獎勵。非 X 客戶端的使用者不會失去質押，但客戶端 X 的使用者由於以平方方式增加的怠惰洩漏，會遭受比平常大得多的損失。有著強烈的時間壓力，要透過修復臭蟲或換用一個不同的客戶端來把客戶端 X 的問題解決掉。

##### 3. 客戶端 X 擁有大約一半的質押

當 X 託管大約一半的驗證者時，情況有可能變得糟糕得多。如果 X 有一個共識臭蟲、但在其他方面持續運行，信標鏈就會分裂成兩條大小相近的鏈。每條鏈都會看到一半的驗證者缺失，並開始洩漏掉那些驗證者的質押。在三到四週內，每條鏈都會洩漏掉夠多缺失驗證者的質押，使得在場的驗證者控制了剩餘質押的三分之二，意味著這些鏈各自都能分別最終確定。要再次重新統一這些鏈會極其困難——實際上是不可能的——因為它們會含有相衝突的已最終確定檢查點。信標鏈會被永久分區。

但願 3-4 週對客戶端 X 修復它的臭蟲、或對 X 的使用者遷移到其他客戶端是足夠的時間。在此期間，如情境 2 所述，X 的使用者在正確的鏈上遭受著巨大的怠惰懲罰。

##### 4. 客戶端 X 接近或超過三分之二的質押

單一一個客戶端接近[^fn-approaches-67]託管三分之二（66%）驗證者的情境，有可能是災難性的。那個客戶端中的一個共識臭蟲，會非常快速地——可能在 13 分鐘內——最終確定一個壞掉版本的鏈，而沒有介入的機會。

那會讓以太坊社群陷入一個可怕的兩難。

一種可能的回應，是修改其他客戶端（以及規格）來重現那個臭蟲，並允許它們加入 X 的鏈。這一點的可行性取決於那個共識臭蟲的本質。對一個微不足道的臭蟲來說也許可行，但那會對非 X 客戶端非常不公平，因為它們儘管行為完全正確，卻會遭受懲罰。無論如何，許多類型的共識臭蟲會使這變得不可行：不管怎樣，X 的鏈都壞了，現在與整個生態系的其餘部分不相容。

正確——但屬於核選項——的選擇，是修復客戶端 X 中的臭蟲。然而不幸的是，在不正確的 X 鏈上的質押者沒有辦法重新加入正確的鏈。任何試圖這麼做的人都會被罰沒，因為他們先前在不正確的鏈上最終確定了一個檢查點。對客戶端 X 的（前）使用者而言，唯一合理的策略是停止驗證，並自願退出他們的質押。由於佇列機制，退出可能要花很長時間，導致來自怠惰洩漏的巨大懲罰。許多受影響的質押者很可能會試圖重新開始驗證，而那肯定會被罰沒。

這裡沒有好的結果，這就是為什麼至關重要的是：我們絕不能有一個擁有三分之二或以上超級多數的客戶端。[^fn-client-diversity-220112]

[^fn-approaches-67]: 如果份額少於 67%，不正確的鏈不會立即最終確定，但很快地，怠惰洩漏就會把那條鏈上的比例提升到 67% 以上，於是它就會最終確定。

[^fn-client-diversity-220112]: 截至 2022-01-12，Prysm 客戶端[似乎擁有](https://web.archive.org/web/20230630135447/https://nitter.it/sproulM_/status/1481109509544513539) 68.1% 的驗證者。

#### 罰沒

至於罰沒，再一次，運行多數客戶端可能是一種自我傷害的行為。在「一個客戶端實作有一個導致其驗證者大規模被罰沒之臭蟲」這個不太可能的情況下，[關聯罰沒懲罰](/part2/incentives/slashing/#the-correlation-penalty)會比同樣的事發生在運行少數客戶端者身上時嚴厲得多。

#### 另一種觀點

Danny Ryan 對客戶端多樣性提出了一個略微[不同的角度](https://blog.ethereum.org/2022/01/31/finalized-no-33/)，很有啟發性：

> 如果單一一個客戶端：
>
>   - 不超過 66.6%，那麼單一一個客戶端中的故障／臭蟲就不可能被最終確定。
>   - 不超過 50%，那麼單一一個客戶端分叉選擇中的故障／臭蟲就不可能主宰鏈頭。
>   - 不超過 33.3%，那麼單一一個客戶端中的故障／臭蟲就不可能擾亂最終性。

#### 尾聲

容我強調，_這些情境遠非理論性的_。對以太坊網路而言，質押者留意客戶端軟體的分布、並避免增添多數客戶端的份額，具有攸關存亡的重要性。

重溫 Medalla 測試網上發生的那場[重大事件](https://hackmd.io/@benjaminion/wnie2_200822#Medalla-Meltdown-redux)很有教育意義，當時多數客戶端中的一個問題造成了高度的混亂，並導致大量的罰沒。要是那個客戶端管理的網路比例較小，每個人的後果都會輕微得多。

#### 另見

  - Dankrad Feist 的[《運行多數客戶端，後果自負！》](https://dankradfeist.de/ethereum/2022/03/24/run-the-majority-client-at-your-own-peril.html)。
  - Adrian Sutton 的[《如果信標鏈共識失敗會怎樣？》](https://www.symphonious.net/2021/09/23/what-happens-if-beacon-chain-consensus-fails/)。

## 構成要素 <!-- /part2/building_blocks/ -->

### 引言

在本章中，我們會探索一些使以太坊&nbsp;2 協定變得實際可行的根本性創新，也就是構築出較高層次協定的那些構成要素。

這些構成要素沒有一個是絕對全新的——它們全都在某種程度上依賴既有的技術——但在每一種情況中，應用到 Eth2 的某個面向都是新穎的。以太坊基金會的研發團隊在這些進展背後的研究與洞見，值得極大的讚譽。

在你閱讀時，要對支撐著這些設計選擇的種種取捨保持警覺。深刻理解的門徑，永遠在於取捨之中。

其中一些取捨相當有意思。例如，[洗牌](/part2/building_blocks/shuffling/)演算法與[狀態根](/part2/building_blocks/merkleization/)計算演算法，至少就純粹的速度而言，都不是我們本可選擇的最有效率者。在這兩種情況中，我們都偏好「能使輕客戶端生態系成為可能」的演算法，更甚於「對全節點而言可能效能更高」的演算法。

我在本章中歸整在一起的構成要素，是那些屬於協定規格本身一部分的要素。客戶端實作往往採用其他並非規格一部分的最佳化。我們稍後會在[實作](/part2/implementation/)一章中考慮其中一些。

以下是我挑出來特別關注的主題。

  - [BLS 簽章](/part2/building_blocks/signatures/)促成了以太坊權益證明協定的徹底重新設計，並支撐著以太坊 2 的規模與企圖心。
  - [隨機性](/part2/building_blocks/randomness/)是安全性的一個關鍵面向，但在一個確定性的系統中難以產生。信標鏈用 BLS 簽章來達成它。
  - [洗牌](/part2/building_blocks/shuffling/)使用隨機性來填充委員會。但為了輕客戶端著想，我們使用一種「不經意」（oblivious）的洗牌，而非標準的 Fisher–Yates 洗牌。
  - [委員會](/part2/building_blocks/committees/)把信標鏈的工作負載分散開來。
  - [聚合者選擇](/part2/building_blocks/aggregator/)祕密地選出委員會的小子集，去做聚合證明的工作。
  - [SSZ：簡易序列化](/part2/building_blocks/ssz/)是一種新穎的序列化技術，它在協定中無處不在。它體現了優雅與效率。
  - [雜湊樹根與 Merkle 化](/part2/building_blocks/merkleization/)是 SSZ 的應用。除了別的之外，它們使輕客戶端變得實際可行。
  - 廣義索引與 Merkle 證明（TODO）。
  - 同步委員會（TODO）。

### BLS 簽章 <!-- /part2/building_blocks/signatures/ -->

<div class="summary">

  - 權益證明協定使用數位簽章來辨識其參與者並追究他們的責任。
  - BLS 簽章可以被聚合在一起，使它們在大規模下驗證起來有效率。
  - 簽章聚合讓信標鏈得以擴展到數十萬個驗證者。
  - 執行（Eth1）層上的以太坊交易簽章維持原狀。

</div>

#### 數位簽章

[數位簽章](https://en.wikipedia.org/wiki/Digital_signature)在區塊鏈技術中被大量使用。一份數位簽章被套用在一則訊息上，以確保兩件事：(1) 該訊息未曾以任何方式遭到竄改；以及 (2) 該訊息的發送者就是它所宣稱的那個人。數位簽章並不新鮮，它真正的發展是在 1980 年代，作為[非對稱密碼學](https://en.wikipedia.org/wiki/Public-key_cryptography)發明的結果。然而，較近期涉及橢圓曲線、以配對為基礎的密碼學的發展，大力影響了以太坊&nbsp;2 的設計。

每次你發送一筆以太坊交易，你都在使用一份數位簽章；所有以太坊使用者都熟悉這套簽章工作流程。但那是在交易的層級。在共識協定的層級，以太坊&nbsp;1 完全不使用數位簽章——在工作量證明之下，一個區塊只需要有一個正確的 `mixHash` 來證明它是被正確挖出的，沒有人在意究竟是誰挖出了那個區塊，所以不需要簽章。

然而，在以太坊&nbsp;2 中，驗證者有身分，並要為它們的行為負責。為了強制執行 Casper FFG 規則，並為了能夠為 LMD GHOST 分叉選擇數票，我們需要能夠唯一地辨識出做出個別證明與區塊的驗證者。

#### 數位簽章的用途

數位簽章的主要功能，是把一則訊息的發送者與該訊息的內容不可撤回地連結起來。舉例來說，這可以用來確鑿地證明某個驗證者發布了相衝突的投票、因而面臨被罰沒的處置。

「把訊息綁定到驗證者」的能力，在協定之外也很有用。例如，在流言層，簽章在被轉發之前會被節點驗證，作為一種反垃圾訊息的機制。

除了它們辨識訊息發送者的一般功能之外，數位簽章在以太坊&nbsp;2 協定中還有幾個相當新穎的用途。它們被用於為 [RANDAO](/part2/building_blocks/randomness/) 貢獻隨機性，也被用於選出[委員會的子集](/part2/building_blocks/aggregator/)來執行聚合職責。我們會在各自的章節討論那些用途，並在本節聚焦於協定訊息的簽章。

#### 背景

<!-- Number of validators -->

權益證明協定的特性之一，是需要處理的協定訊息數量之龐大。在有 500,000 個活躍驗證者的情況下，當前的信標鏈設計要求每秒有超過 1,300 份證明在網路上被流言傳播。那是一個持續的平均值，實務上有高得多的爆量。這些訊息不僅需要在網路上傳遞，而且每一份個別的數位簽章都需要被每個節點驗證，那是一項耗 CPU 的操作。更別提還得把所有那些已簽章的訊息儲存在區塊歷史中。這些具挑戰性的要求，通常限制了權益證明或權威證明網路中的驗證者數量。純粹以 PBFT 為基礎的共識協定，其驗證者集合的數量往往是數十個、而非數千個。

2018 年初，以太坊（部分）轉向權益證明的主流進行中設計 [EIP-1011](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1011.md)，估計協定由於這種訊息開銷最多只能處理約 900 個驗證者，並據此設定了每個驗證者 1500&nbsp;ETH 這個沉重的質押規模。

轉捩點出現在 2018 年 5 月，Justin Drake 在 Ethresear.ch 論壇上發表了一篇題為[《以 BLS 進行務實的簽章聚合》](https://ethresear.ch/t/pragmatic-signature-aggregation-with-bls/2105?u=benjaminion)的文章。那篇文章提議使用一種新的簽章方案，它能夠把許多數位簽章_聚合_成一份，同時保留每個簽署者的個別問責性。聚合提供了一種方式，大幅減少「必須在網路上被流言傳播的個別訊息數量」，以及「驗證那些訊息完整性的成本」。它因此讓我們得以擴展到數十萬個共識參與者。[^fn-dfinity-credit]

[^fn-dfinity-credit]: 為了把功勞歸於應得之人，Dfinity 的區塊鏈研究人員早幾個月就發表了[一份白皮書](https://dfinity.org/pdf-viewer/pdfs/viewer?file=../library/dfinity-consensus.pdf)，提議在一個門檻方案中使用 BLS 簽章。然而，他們使用門檻簽章使鏈易受活躍性失敗之害，並且還需要一個棘手的分散式金鑰產生協定。以太坊以聚合為基礎的做法兩個問題都沒有。儘管如此，我們今天仍在使用的「信標鏈」（beacon chain）這個名稱，正源自該論文中所描述的 Dfinity 的「隨機性信標」（randomness beacon）。

這種簽章聚合能力，是促使我們完全放棄 EIP-1011 鏈上 PoS 管理機制、轉向我們今天所擁有之「信標鏈」模型的主要突破[^fn-killing-of-hybrid-casper]。

[^fn-killing-of-hybrid-casper]: EIP-1011 最後一次重大更新是在 [2018 年 5 月 16 日](https://github.com/ethereum/EIPs/commit/46927c516f6dda913cbabb0beb44a3f19f02c0bb)做出的。Justin Drake 關於簽章聚合的貼文，僅僅在[兩週後](https://ethresear.ch/t/pragmatic-signature-aggregation-with-bls/2105?u=benjaminion)發表。

#### BLS 數位簽章

區塊鏈世界中的數位簽章通常以橢圓曲線群為基礎。為了簽署使用者的交易，以太坊使用搭配 [secp256k1](https://en.bitcoin.it/wiki/Secp256k1) 橢圓曲線的 [ECDSA](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm) 簽章。然而，信標鏈協定使用搭配 [BLS12-381](/part2/building_blocks/bls12-381/) 橢圓曲線的 [BLS](https://en.wikipedia.org/wiki/BLS_digital_signature) 簽章[^fn-bls-bls]。雖然在用途上相似，ECDSA 與 BLS 簽章在數學上相當不同，後者仰賴某些橢圓曲線的一個特殊性質，稱為「[配對](/part2/building_blocks/bls12-381/#pairings)」（pairing）。雖然 ECDSA 簽章比 BLS 簽章[快得多](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-bls-signature-04#section-1.1)，但配對性質允許 BLS 簽章被聚合，使整個信標鏈共識協定變得實際可行。

[^fn-bls-bls]: 這裡有一個奇特的命名衝突。「BLS 簽章」中的 BLS 三人是 Boneh、Lynn、Shacham，而「BLS12-381」橢圓曲線中的 BLS 三人則是 Barreto、Lynn、Scott。Ben Lynn 是兩者之間唯一共同的名字。

還有好幾個其他的區塊鏈協定已採用或將採用 BLS12-381 曲線上的 BLS 簽章，而在我們對 Eth2 的整個實作中，我們一直留意要遵循任何既有的標準，並在可能之處參與那些標準的制定。這既有助於互通性，也支援共同函式庫與工具的開發。

建立並驗證一份 BLS 簽章的高層次工作流程相對直截了當。在接下來的各節中，我會用一些文字、一些圖畫、一些數學來描述這一切如何運作。如果你願意，儘管跳過數學，它不是強制的，結尾也沒有測驗。不過它頗為優雅。

##### 組成部分

在 BLS 數位簽章的過程中有四個組成部分的資料片段。

1. _祕密金鑰_。在協定內行動的每一個實體（在 Eth2 的情境中即一個驗證者）都有一把祕密金鑰，有時稱為私鑰。祕密金鑰被用來為訊息簽章，並且必須保持祕密，一如其名所示。
2. _公鑰_。公鑰由祕密金鑰唯一地衍生而來，但無法從它逆向工程出祕密金鑰（除非投入大到不可能的工作量）。一個驗證者的公鑰代表它在協定內的身分，並為所有人所知。
3. _訊息_。我們稍後會看 Eth2 協定中所使用的訊息種類，以及它們如何構成。目前，訊息就只是一串位元組。
4. _簽章_，即簽章過程的輸出。簽章是藉由把訊息與祕密金鑰結合而建立的。給定一則訊息、一份對該訊息的簽章、以及一把公鑰，我們可以驗證：擁有那把公鑰的驗證者恰恰簽署了那則訊息。換句話說，沒有別人能簽署那則訊息，而且該訊息自簽署以來未曾被改動。

更數學一點地說，事情看起來像這樣。我們使用 [BLS12-381 橢圓曲線](/part2/building_blocks/bls12-381/)的兩個子群：定義在基域 $F_q$ 上的 $G_1$，以及定義在域擴張 $F_{q^2}$ 上的 $G_2$。這兩個子群的階都是 $r$，一個 77 位數的質數。子群 $G_1$ 與 $G_2$ 的（任意選定的）生成元，分別是點 $g_1$ 與 $g_2$。

1. 祕密金鑰 $sk$ 是一個介於 $1$ 與 $r$ 之間的數（技術上這個範圍包含 $1$、但不包含 $r$。然而，使用非常小的 $sk$ 值會毫無希望地不安全）。
2. 公鑰 $pk$ 是 $[sk]g_1$，其中方括號代表橢圓曲線群點的純量乘法。因此公鑰是 $G_1$ 群的一個成員。
3. 訊息 $m$ 是一串位元組序列。在簽章過程中，這會被對應到某個身為 $G_2$ 群成員的點 $H(m)$。
4. 簽章 $\sigma$ 也是 $G_2$ 群的一個成員，即 $[sk]H(m)$。

<a id="img_bls_key"></a>
<figure class="diagram" style="width:80%">

![一張示意圖，顯示我們會如何在下面的圖中描繪各個組成部分。](images/diagrams/bls-key.svg)

<figcaption>

理解各把金鑰的鑰匙。這就是我們會如何在下面的圖中描繪各個組成部分。同一個物件的變體以不同的斜線填滿。祕密金鑰在數學上是一個純量；公鑰是 $G_1$ 群成員；訊息根被對應到 $G_2$ 群成員；簽章是 $G_2$ 群成員。

</figcaption>
</figure>

##### 金鑰對

一個金鑰對是一把祕密金鑰連同它的公鑰。這兩者一起把每個驗證者與它的行為無可辯駁地連結起來。

信標鏈上每個驗證者都至少有一個金鑰對，即用於日常運作（做出證明、產生區塊等等）的「簽章金鑰」。視該驗證者使用哪個版本的[提領憑證](/part3/config/constants/#withdrawal-prefixes)而定，它可能還有第二個 BLS 金鑰對，即離線保管的「提領金鑰」。

祕密金鑰理應在範圍 $[1,r)$ 內均勻隨機地產生。[EIP-2333](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-2333.md) 基於 IRTF BLS 簽章標準草案的 [`KeyGen`](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-bls-signature-04#section-2.3) 方法，定義了做這件事的一套標準方式。使用這個方法並非強制——你不用，也永遠不會有人知道——但你最好別不用。實務上，許多質押者用以太坊基金會所建立的 [`eth2.0-deposit-cli`](https://github.com/ethereum/eth2.0-deposit-cli) 工具來產生他們的金鑰。在運作上，金鑰對往往被儲存在密碼保護的 [EIP-2335](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-2335.md) 金鑰庫檔案中。

祕密金鑰 $sk$ 是一個 32 位元組的無號整數。公鑰 $pk$ 是 $G_1$ 曲線上的一個點，它在協定內以其[壓縮過](/part2/building_blocks/bls12-381/#point-compression)的序列化形式表示，為一串 48 位元組。

<a id="img_bls_setup"></a>
<figure class="diagram" style="width:50%">

![公鑰產生過程的示意圖。](images/diagrams/bls-setup.svg)

<figcaption>

一個驗證者隨機產生它的祕密金鑰。它的公鑰接著由那把金鑰衍生而來。

</figcaption>
</figure>

##### 簽章

在信標鏈協定中，唯一會被簽章的訊息，是物件的[雜湊樹根](/part2/building_blocks/merkleization/)：也就是它們所謂的簽章根（signing root），那是 32 位元組的字串。[`compute_signing_root()`](/part3/helper/misc/#compute_signing_root) 函式總是把一個物件的雜湊樹根與一個「網域」（domain）結合起來，如[下文](#domain-separation-and-forks)所述。

一旦我們有了簽章根，它就需要被對應到 $G_2$ 群中的一個橢圓曲線點。如果訊息的簽章根是 $m$，那麼那個點就是 $H(m)$，其中 $H()$ 是一個[把位元組對應到 $G_2$](/part2/building_blocks/bls12-381/#hashing-to-the-curve) 的函式。這個對應很難做得好，甚至有一整個標準 [RFC 9380](https://www.rfc-editor.org/rfc/rfc9380.html) 存在來定義這個過程。所幸，我們可以完全忽略細節，把它們留給我們的密碼學函式庫[^fn-implement-h2g2]。

[^fn-implement-h2g2]: 除非你不得不實作這玩意兒，就像我[最後](https://github.com/ConsenSys/teku/commit/e927d9be89b64fe8297b74405f37aa0e6378024)用 Java 所做的那樣。

既然我們有了 $H(m)$，簽章過程本身就很簡單，只是把那個 $G_2$ 點以祕密金鑰做一次純量乘法：

$$
\sigma = [sk]H(m)
$$

顯然，簽章 $\sigma$ 也是 $G_2$ 群的一個成員，它以[壓縮形式](/part2/building_blocks/bls12-381/#point-compression)序列化成一串 96 位元組的字串。

<a id="img_bls_signing"></a>
<figure class="diagram" style="width:65%">

![為一則訊息簽章的示意圖。](images/diagrams/bls-signing.svg)

<figcaption>

一個驗證者把它的祕密金鑰套用在一則訊息上，以產生一份獨一無二的數位簽章。

</figcaption>
</figure>

##### 驗證

要驗證一份簽章，我們需要知道簽署它的驗證者的公鑰。每個驗證者的公鑰都儲存在信標狀態中，並可以單純地透過該驗證者的索引來查找，而依設計，那個索引在需要時總是能以某種方式取得。

簽章驗證可以被當成一個黑箱來看待：我們把訊息、公鑰、簽章送給驗證器；如果在一些密碼學魔法之後，簽章與公鑰、訊息兩者都相符，那麼我們就宣告它有效。否則，要嘛簽章損壞、要嘛使用了不正確的祕密金鑰、要嘛訊息不是被簽署的那一個。

更正式地說，簽章是用橢圓曲線配對來驗證的。

如 BLS12-381 一章所討論，可以定義一種[配對操作](/part2/building_blocks/bls12-381/#pairings)，作為配對之雙線性的結果，下列恆等式對它成立。

$$
e([a]P,[b]Q)={e(P,[b]Q)}^a={e(P,Q)}^{ab}={e(P,[a]Q)}^b=e([b]P,[a]Q)
$$

在這套符號中，配對單純地取一個點 $P \in G_1$、一個點 $Q \in G_2$，並輸出一個來自群 $G_T \subset F_{q^{12}}$ 的點。也就是說，對於一個配對 $e$，$e:G_1\times G_2\rightarrow G_T$。$G_1$ 與 $G_2$ 中點的純量乘法分別記為 $[n]P$ 與 $[n]Q$。[^fn-notation-discussion]

[^fn-notation-discussion]: 關於[這套符號](/part2/building_blocks/bls12-381/#pairings)與雙線性的討論，見 BLS12-381 一章。

有了這個，驗證一份簽章就很直截了當。簽章有效，若且唯若

$$
e(g_1,\sigma)=e(pk,H(m))
$$

也就是說，給定訊息 $m$、公鑰 $pk$、簽章 $\sigma$、以及固定的公開值 $g_1$（$G_1$ 群的生成元），我們可以驗證該訊息是被祕密金鑰 $sk$ 所簽署的。

這個恆等式直接來自上文所述的配對性質。

$$
e(pk,H(m)) = e([sk]g_1,H(m)) = {e(g_1,H(m))}^{(sk)} = e(g_1,[sk]H(m)) = e(g_1,\sigma)
$$

請注意，支援這樣一種配對函式的橢圓曲線非常罕見。這樣的曲線可以被構造出來，[BLS12-381 就是](/part2/building_blocks/bls12-381/#history)，但一般的橢圓曲線——例如更常用的 secp256k1 曲線——並不支援配對，無法用於 BLS 簽章。

<a id="img_bls_verifying"></a>
<figure class="diagram" style="width:80%">

![驗證一份簽章的示意圖。](images/diagrams/bls-verifying.svg)

<figcaption>

要驗證某個特定的驗證者簽署了某則特定的訊息，我們使用該驗證者的公鑰、原始訊息、以及簽章。如果簽章正確，驗證操作輸出真，否則輸出假。

</figcaption>
</figure>

驗證會回傳 `True`，若且唯若簽章與公鑰相符（也就是簽章與公鑰都是從同一把祕密金鑰產生的）、並且與訊息相符（也就是訊息與原本被簽署的那一個完全相同）。否則，它會回傳 `False`。

#### 聚合

到目前為止，我們看了 BLS 簽章的基本布置。就功能而言，我們所看到的與任何其他數位簽章方案非常相似。魔法發生之處在於_聚合_。

聚合意味著對同一則訊息的多份簽章——有可能是數千份簽章——可以用單一一次驗證操作來檢查。此外，聚合簽章與一份一般簽章有相同的大小，96 位元組。這在可擴展性上是一項巨大的收穫，正是這份收穫從根本上使以太坊&nbsp;2 共識協定變得可行。

這如何運作？回想一下，公鑰與簽章都是橢圓曲線點。由於配對函式 $e()$ 的雙線性性質，結果證明我們可以對同一則訊息的公鑰與簽章形成線性組合，而驗證仍如預期般運作。

這個陳述有點晦澀；讓我們一步一步來。

##### 聚合簽章

在接下來的內容中，我們只考慮對同一則訊息之簽章的聚合[^fn-aggregation-terminology]。

[^fn-aggregation-terminology]: 一則關於術語的註記。描述這個方案的[原始論文](https://eprint.iacr.org/2018/483.pdf)，在結合對同一則訊息的簽章時使用「多重簽章」（multi-signature）一詞，在結合對不同訊息的簽章時使用「聚合簽章」（aggregate signature）一詞。在 Eth2 中我們只做前者，並就稱之為聚合。

這個過程在概念上非常簡單：我們單純地把簽章「加起來」。確切的操作並不像我們所熟悉的一般數字加法，但這個操作是完全類比的。橢圓曲線上點的加法是 $G_2$ 群的群運算，而每份簽章都是這個群中的一個點，所以結果也是這個群中的一個點。一份聚合簽章在數學上與一份非聚合簽章無法區分，並有著相同的 96 位元組大小。

<a id="img_bls_signature_aggregation"></a>
<figure class="diagram" style="width:60%">

![顯示簽章聚合的示意圖。](images/diagrams/bls-signature_aggregation.svg)

<figcaption>

簽章的聚合單純地就是 $G_2$ 群中的群加法。

</figcaption>
</figure>

##### 聚合公鑰

要驗證一份聚合簽章，我們需要一把聚合公鑰。只要我們確切地知道是哪些驗證者簽署了原始訊息，這同樣容易構造。再一次，我們單純地把簽署者的公鑰「加起來」。這次加法是 $G_1$ 橢圓曲線群的群運算，結果也會是 $G_1$ 群的一個成員，所以它在數學上與一把非聚合公鑰無法區分，並有著相同的 48 位元組大小。

<a id="img_bls_pubkey_aggregation"></a>
<figure class="diagram" style="width:60%">

![公鑰聚合的示意圖。](images/diagrams/bls-pubkey_aggregation.svg)

<figcaption>

公鑰的聚合單純地就是 $G_1$ 群中的群加法。

</figcaption>
</figure>

##### 驗證聚合簽章

由於聚合簽章與一般簽章無法區分，聚合公鑰與一般公鑰也無法區分，我們可以單純地把它們餵進我們一般的驗證演算法。

<a id="img_bls_aggregate_verify"></a>
<figure class="diagram" style="width:70%">

![驗證一份聚合簽章的示意圖。](images/diagrams/bls-aggregate_verify.svg)

<figcaption>

只要我們使用對應的聚合公鑰，驗證一份聚合簽章就與驗證一份一般簽章完全相同。

</figcaption>
</figure>

這個奇蹟歸因於配對操作的雙線性。有了一份聚合簽章 $\sigma_{agg}$、一把對應的聚合公鑰 $pk_{agg}$、以及共同的訊息 $m$，我們有下列恆等式，它與單一一份簽章與公鑰的驗證恆等式完全相同。

$$
\begin{aligned}
e(pk_{agg},H(m)) &= e(pk_1 + pk_2 + \cdots + pk_n,H(m)) \\
                 &= e([sk_1 + sk_2 + \cdots + sk_n]g_1,H(m)) \\
                 &= {e(g_1,H(m))}^{(sk_1 + sk_2 + \cdots + sk_n)} \\
                 &= e(g_1,[sk_1 + sk_2 + \cdots + sk_n]H(m)) \\
                 &= e(g_1,\sigma_1 + \sigma_2 + \cdots + \sigma_n) \\
                 &= e(g_1,\sigma_{agg})
\end{aligned}
$$

##### 聚合的好處

與驗證一份 ECDSA 簽章相比，驗證一份 BLS 簽章是昂貴的（耗資源的）——由於配對操作而慢上一個數量級以上——那麼我們獲得了什麼好處？

當我們能夠聚合可觀數量的簽章時，好處就累積起來。這正是我們在信標鏈證明委員會中所擁有的。理想情況下，委員會中所有的驗證者都為相同的證明資料背書，所以它們所有的簽章都可以被聚合。實務上，委員會成員之間對鏈狀態可能有意見分歧，導致兩三份不同的證明，但即便如此，聚合的數量也會遠少於委員會成員的總數。

###### 速度上的好處

那麼，作為第一近似，我們可以用單一一次簽章驗證操作，驗證一整個委員會的所有證明——有可能是數百份。

這是第一近似，因為我們還需要把聚合公鑰與聚合簽章的成本計入。但這些聚合操作只涉及它們各自橢圓曲線群中的點加法，與驗證相比那非常便宜。

總而言之：

  - 我們可以用兩次配對驗證單一一份簽章。
  - 我們可以樸素地用 $2N$ 次配對驗證 $N$ 份簽章。
  - 或者我們可以透過聚合，僅用兩次配對、$N-1$ 次 $G_1$ 中的加法、以及 $N-1$ 次 $G_2$ 中的加法，來驗證 $N$ 份簽章。每一次橢圓曲線點加法都比一次配對便宜得多得多。

###### 空間上的好處

當我們聚合簽章時，還有一項巨大的空間節省。

一份聚合簽章像所有 BLS 簽章一樣有 96 位元組。所以，作為第一近似，$N$ 份簽章的一份聚合，佔用的空間是未聚合簽章的 $\frac{1}{N}$。

再一次，這只是第一近似。這裡的微妙之處在於，為了構造對應的聚合公鑰，我們需要以某種方式追蹤是哪些驗證者簽署了訊息。我們不能假設整個委員會都參與了，而且我們需要小心不要把任何驗證者納入超過一次。

如果我們事先知道委員會的成員是誰、以及他們如何排序，那麼這項追蹤可以用每個驗證者一位元的邊際成本來完成：如果該驗證者對聚合有所貢獻就是真，否則就是假。

##### 完整的全貌

這張圖說明了從簽章、經過聚合、到驗證的完整流程。在這個例子中有三個驗證者，雖然可能有多得多個，而每一個都在簽署相同的訊息內容。每個驗證者都有它自己獨一無二的祕密金鑰與公鑰對。這個工作流程完全是非互動式的，驗證之前的任何行動都可以獨立發生。甚至聚合也可以增量地進行。

<a id="img_bls_aggregation"></a>
<figure class="diagram" style="width:80%">

![顯示端到端聚合簽章工作流程的示意圖。](images/diagrams/bls-aggregation.svg)

<figcaption>

端到端的聚合簽章工作流程。驗證單一一份聚合簽章，比分別驗證原始的各份簽章快得多。

</figcaption>
</figure>

##### 聚合範例

聚合簽章在實務上如何被使用的兩個有用範例，是聚合證明與同步委員會聚合。

###### 聚合證明

聚合證明是一種非常精簡的方式，用以儲存並證明是哪些驗證者做出了某份特定的證明。

在每個時段的每個信標鏈委員會內，個別的驗證者為它們對鏈的看法做出證明，如[驗證者規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#attesting)中所描述。

一個 [`Attestation`](/part3/containers/operations/#attestation) 物件看起來像這樣：

```python
class Attestation(Container):
    aggregation_bits: Bitlist[MAX_VALIDATORS_PER_COMMITTEE]
    data: AttestationData
    signature: BLSSignature
```

在做出它的證明時，驗證者在 `aggregation_bits` 欄位中設定單一一個位元，以指出它是委員會的哪一個成員。連同時段編號與委員會索引，那就足以在全域驗證者集合中唯一地辨識出做出證明的驗證者。

`signature` 欄位是該驗證者對 `data` 欄位中 `AttestationData` 所做的[簽章](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#aggregate-signature)。

這份證明稍後會與委員會中其他含有相同 `data` 的證明[聚合](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#attestation-aggregation)在一起。一份證明被加進一份聚合的方式，是把它在 `aggregation_bits` 欄位中的位元複製過去，並把它的簽章（以橢圓曲線加法的意義）加進 `signature` 欄位。聚合證明可以用相同的方式聚合在一起，但只有在它們的 `aggregation_bits` 清單不相交時：我們不能把一個驗證者納入超過一次。（原則上我們可以把個別的驗證者納入多次，但那樣我們就需要不止單一一個位元來追蹤多少次，而那種冗餘並無用處。）

這份聚合證明會在網路上被流言傳播，並最終被納入一個區塊。在每一步，聚合簽章都會被驗證。

要驗證簽章，一個節點需要重建委員會中的驗證者清單，它可以從 [`AttestationData`](/part3/containers/dependencies/#attestationdata) 中的資訊做到這一點：

```python
class AttestationData(Container):
    slot: Slot
    index: CommitteeIndex
    beacon_block_root: Root
...
```

給定重建後的委員會成員清單，驗證的節點會依該證明中哪些 `aggregation_bits` 被設定來過濾這份清單。現在它有了「對這份證明有所貢獻的所有驗證者」的索引。該節點從信標狀態取得那些驗證者的公鑰，並把那些金鑰聚合在一起（藉由橢圓曲線加法）。

最後，把聚合簽章、聚合公鑰、以及 `data` 的簽章根餵進標準的 BLS 簽章驗證函式。如果一切順利，這會回傳 `True`，否則這份聚合證明就是無效的。

###### 同步聚合

[`SyncAggregate`](/part3/containers/operations/#syncaggregate) 由一個 512 名成員的同步委員會所產生。

```python
class SyncAggregate(Container):
    sync_committee_bits: Bitvector[SYNC_COMMITTEE_SIZE]
    sync_committee_signature: BLSSignature
```

[`SyncCommittee`](/part3/containers/dependencies/#synccommittee) 當前的成員以下列形式儲存在信標狀態中：

```python
class SyncCommittee(Container):
    pubkeys: Vector[BLSPubkey, SYNC_COMMITTEE_SIZE]
    aggregate_pubkey: BLSPubkey
```

同步委員會訊息的產生與聚合與證明[略有不同](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/validator.md#sync-committees)，但相似到我在此略過不談。

主要值得注意的幾點是：`SyncCommittee` 物件含有所有成員實際的公鑰（可能有重複），而非驗證者索引。它還含有一個預先計算好的 `aggregate_pubkey` 欄位，那是委員會中所有公鑰的聚合。

這麼做的構想是減少輕客戶端的計算負載，因為將會是它們需要驗證 `SyncAggregate` 簽章。同步委員會被預期有高參與率，比方說 90% 的驗證者有所貢獻。要驗證聚合簽章，我們需要聚合所有貢獻者的公鑰。從一個空集合開始，那會意味著 461 次橢圓曲線點加法（512 的 90%）。然而，如果我們從_完整_的集合 `aggregate_pubkey` 開始，那麼我們就可以藉由_減去_未參與的那 10% 來達成同樣的事。那是 51 次橢圓曲線減法（與加法有相同的成本），工作量少了九倍。

#### 各種主題

##### 網域分離與分叉

Eth2 協定中所使用的每一份簽章，在簽章之前都有一個 `domain` 值被混進訊息中。這由 [`compute_signing_root()`](/part3/helper/misc/#def_compute_signing_root) 函式處理，它既計算待簽章物件的 SSZ [雜湊樹根](/part2/building_blocks/merkleization/)，也混入給定的網域。

```python
def compute_signing_root(ssz_object: SSZObject, domain: Domain) -> Root:
    return hash_tree_root(SigningData(
        object_root=hash_tree_root(ssz_object),
        domain=domain,
    ))
```

網域接著由 [`compute_domain()`](/part3/helper/misc/#def_compute_domain) 函式計算，它把十種[網域類型](/part3/config/constants/#domain-types)之一，與[分叉版本](/part3/config/types/#version)和[創世驗證者根](/part3/containers/state/#genesis_validators_root)的混合物結合起來。

被捲進訊息中的每一個額外的量都有特定的目的。

  - 網域類型確保「為一個目的而做的簽章，無法被重複用於一個不同的目的」。不同 SSZ 類型的物件並不保證有唯一的雜湊樹根，而我們頗希望能夠分辨它們之間的差別。這十種[網域類型](/part3/config/constants/#domain-types)就是簽章在協定中被使用的所有不同方式。
  - 創世驗證者根唯一地辨識出這條特定的信標鏈，把它與任何其他測試網或替代鏈區分開來。這確保來自不同鏈的簽章永遠互不相容。
  - 分叉版本辨識出對信標鏈刻意進行的共識升級。把分叉版本混進訊息中，確保來自尚未升級之驗證者的訊息是無效的。它們在共識之外，沒有對我們有用的資訊，所以這提供了一種方便的方式來忽略它們的訊息。或者，一個驗證者可能希望在一個有爭議的分叉的兩側都運作，而分叉版本為它們提供了一種安全這麼做的方式。

混入分叉版本的唯一例外，是存款上的簽章。不論信標鏈如何被升級，存款永遠有效。

##### 群的選擇

BLS 簽章以兩個橢圓曲線群 $G_1$ 與 $G_2$ 為基礎。$G_1$ 的元素小（序列化後 48 位元組），它們的群算術較快；$G_2$ 的元素大（序列化後 96 位元組），它們的群算術較慢，也許慢三倍。

我們可以選擇用任一個群作為公鑰，只要我們用另一個群作為簽章：配對函式不在乎；如果我們把兩個群對調，一切仍然運作。描述 BLS 聚合簽章的[原始論文](https://eprint.iacr.org/2018/483.pdf)把公鑰放在 $G_2$、簽章放在 $G_1$，而對於以太坊&nbsp;2，我們做了相反的選擇。

這麼做的主要原因，是我們希望公鑰聚合盡可能快。簽章被驗證的頻率遠高於它們被聚合的頻率——目前信標鏈客戶端到目前為止的主要負載就是簽章驗證——而驗證需要公鑰聚合。所以我們選擇把我們的公鑰放在較快的 $G_1$ 群。這還有減少信標狀態大小的好處，因為公鑰被儲存在驗證者記錄中。要是我們用 $G_2$ 群作為公鑰，信標狀態就會大約大 35%。

代價是，由於簽章大小較大，協定訊息與信標鏈區塊都較大。

從根本上說，聚合簽章的驗證是一項我們希望盡可能輕的「鏈上」活動，而簽章聚合是「鏈下」的，所以可以較為笨重。

##### 持有證明

對 BLS 簽章方案有一種我們希望避免的可能攻擊，即「流氓公鑰」攻擊。

假設你的公鑰是 $pk_1$，而我有一把祕密金鑰 $sk_2$。但我不發布我真正的公鑰，而是發布 $pk'_2=[sk_2]g_1-pk_1$（也就是我真正的公鑰加上你公鑰的反元素）。我可以用我的祕密金鑰為一則訊息 $H(m)$ 簽章，做出 $\sigma=[sk_2]H(m)$。然後我發布這個，宣稱它是一份你和我都簽署過的聚合簽章。

現在，當用我的流氓公鑰與你實際的公鑰驗證時，這個宣稱通過了檢查：看起來你簽署了那則訊息，而其實你沒有：$e(g1,\sigma)=e(g_1,[sk_2]H(m))=e([sk_2]g_1,H(m))=e(pk_1+pk'_2,H(m))$。

對此一個相對簡單的防禦——我們在以太坊&nbsp;2 中所使用的那個——是強制驗證者登錄一份「持有證明」，證明它持有與它所宣稱之公鑰對應的祕密金鑰。你看，攻擊者並沒有、也無法計算出與 $pk'_2$ 對應的 $sk'_2$。持有證明可以單純地藉由讓所有驗證者在登錄時——也就是它們在存款合約中存入它們的質押時——為它們的公鑰簽章來完成。如果實際的簽章與所宣稱的公鑰驗證通過，那就一切順利。

##### 門檻簽章

除了聚合之外，BLS 方案也支援[門檻簽章](https://alinush.github.io/threshold-bls)（threshold signature）。這是把一把祕密金鑰分割給 $N$ 個驗證者。對於一個預先定義的值 $M \le N$，如果其中 $M$ 個驗證者簽署一則訊息，那麼就可以用所有驗證者單一一把聯合公鑰來驗證該簽章。

門檻簽章目前並未在以太坊&nbsp;2 核心協定內使用。然而，它們在基礎設施的層級很有用。例如，為了安全與韌性，把一個驗證者的祕密金鑰分割到多個地點可能是可取的。如果一個攻擊者取得少於 $M$ 份金鑰份額，那麼該金鑰仍然安全；如果多達 $N-M$ 個金鑰庫不可用，該驗證者仍能正確地簽章。這方面一個運作中的例子是 Attestant 的 [Dirk](https://www.attestant.io/posts/introducing-dirk/) 金鑰管理器。

門檻簽章在分散式驗證者技術（Distributed Validator Technology）中也佔有一席之地，我會在另一章中寫到它。

[TODO - link to DVT when done]::

##### 批次驗證

配對函式的雙線性允許一些相當別緻的最佳化。例如，Vitalik 制定了一種[同時驗證一批](https://ethresear.ch/t/fast-verification-of-multiple-bls-signatures/5407?u=benjaminion)簽章——例如一個區塊中所含的所有簽章——的方法，它顯著減少所需的配對操作數量。由於這項技術構成一種客戶端的最佳化、而非協定的根本部分，我會在「實作」一章中適切地描述它。

[TODO - link to batch verification when done]::

##### 量子安全性

BLS 簽章的安全性（不可偽造性）除了別的之外，仰賴一個稱為橢圓曲線離散對數問題（ECDLP）之物的困難度。基本上，給定公鑰 $[sk]g_1$，要算出祕密金鑰 $sk$ 是什麼，在計算上不可行。

ECDLP 被認為易受[量子電腦](https://en.wikipedia.org/wiki/Elliptic-curve_cryptography#Quantum_computing_attacks)的攻擊，因此我們的簽章方案可能有著有限的保存期限。

抗量子的替代方案——例如 [zkSTARK](https://eprint.iacr.org/2018/046.pdf)——是已知的，但目前不如 BLS 方案實際可行。預期是在某個時點，我們會遷移到這樣一種方案，作為 BLS 簽章的就地替換（drop-in replacement）。

萬一有人一夜之間揭曉一台足夠強大的量子電腦，[EIP-2333](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-2333.md)（它是以太坊中 BLS 金鑰產生的一套標準）描述了一種產生 [Lamport 簽章](https://en.wikipedia.org/wiki/Lamport_signature)階層的方式。Lamport 簽章被認為是量子安全的，但帶有它們自己的限制。原則上，我們可以緊急切換到這些，以在實作 STARK 期間幫我們撐過難關。但這在實務上會極具挑戰性。

#### BLS 函式庫函式

作為參考，以下是以太坊&nbsp;2 [規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/beacon-chain.md#bls-signatures)中所使用的 BLS 函式庫函式。它們的命名與定義依據 [BLS 簽章標準](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-bls-signature-04)草案。函式名稱連結到標準中的定義。由於我們使用標準中所定義的[持有證明](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-bls-signature-04#section-3.3)方案，我們的 `Sign`、`Verify`、`AggregateVerify` 函式分別對應到 `CoreSign`、`CoreVerify`、`CoreAggregateVerify`。

  - `def` [`Sign`](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-bls-signature-04#section-2.6)`(privkey: int, message: Bytes) -> BLSSignature`
    - 用驗證者的祕密（私）金鑰為一則訊息簽章。
  - `def` [`Verify`](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-bls-signature-04#section-2.7)`(pubkey: BLSPubkey, message: Bytes, signature: BLSSignature) -> bool`
    - 給定公鑰與訊息，驗證一份簽章。
  - `def` [`Aggregate`](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-bls-signature-04#section-2.8)`(signatures: Sequence[BLSSignature]) -> BLSSignature`
    - 聚合一份簽章清單。
  - `def` [`FastAggregateVerify`](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-bls-signature-04#section-3.3.4)`(pubkeys: Sequence[BLSPubkey], message: Bytes, signature: BLSSignature) - bool`
    - 給定訊息、以及與「對聚合簽章有所貢獻之驗證者」對應的公鑰清單，驗證一份聚合簽章。
  - `def` [`AggregateVerify`](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-bls-signature-04#section-2.9)`(pubkeys: Sequence[BLSPubkey], messages: Sequence[Bytes], signature: BLSSignature) -> bool`
    - 這在目前的規格中並未使用，但出現在未來的[保管證明規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/_features/custody_game/beacon-chain.md)中。它取由 $n$ 個驗證者所簽署的 $n$ 則訊息，並驗證它們的聚合簽章。其數學與上文的相似，但需要 $n+1$ 次配對操作、而非只有兩次。但這比驗證未聚合簽章所需的 $2n$ 次配對來得好。
  - `def` [`KeyValidate`](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-bls-signature-04#section-2.5)`(pubkey: BLSPubkey) -> bool`
    - 檢查一把公鑰是否有效。也就是：它落在橢圓曲線上；它不是該群的單位元點（對應於零祕密金鑰）；並且它是該曲線 $G_1$ 子群的成員。所有這些檢查對於避免某些攻擊都很重要。群成員資格檢查相當昂貴，但對於儲存在信標狀態中的每一把公鑰，它只需做一次。

Eth2 規格還定義了兩個進一步的 BLS 工具函式 `eth_aggregate_pubkeys()` 與 `eth_fast_aggregate_verify()`，我在[註解規格](/part3/helper/crypto/#bls-signatures)中描述它們。

#### 另見

關於橢圓曲線配對之妙處的深入得多的探討，以及通往更多參考文獻的連結，見[曲線 BLS12-381](/part2/building_blocks/bls12-381/) 一章。

[《給較小型區塊鏈的精簡多重簽章》](https://eprint.iacr.org/2018/483.pdf)（Boneh、Drijvers、Neven）是描述高效率 BLS 多重簽章的原始論文。而[《以 BLS 進行務實的簽章聚合》](https://ethresear.ch/t/pragmatic-signature-aggregation-with-bls/2105?u=benjaminion)是 Justin Drake 提議在以太坊&nbsp;2 情境中使用這些簽章的提案。

有三項 EIP 意在規範金鑰在實務上的產生與儲存：

  - [EIP-2333](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-2333.md) 提供一種基於熵種子衍生 BLS12-381 金鑰樹階層的方法。
  - [EIP-2334](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-2334.md) 定義一個確定性帳戶階層，用以指定金鑰的用途。
  - [EIP-2335](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-2335.md) 規定一個標準的金鑰庫格式，用於 BLS12-381 金鑰的儲存與交換。

### 曲線 BLS12-381 <!-- /part2/building_blocks/bls12-381/ -->

<div class="summary">

  - BLS12-381 是一條密碼學上安全、對配對友善的橢圓曲線。
  - 雙線性配對使諸如簽章聚合與多項式承諾這類重要特性成為可能。

</div>

本章是我原本那篇[向曲線 BLS12-381 致敬](https://hackmd.io/@benjaminion/bls12-381)的文章的修訂更新版。它並非必讀——把橢圓曲線實作當成一個黑箱是沒問題的——但我把它收錄進來，是給那些樂於深入挖掘的人。雖然曲線 BLS12-381 是主要焦點，接下來的許多內容涵蓋的是關於橢圓曲線與配對的較廣泛的一般性背景素材。身為一個非數學家[^fn-non-mathematician]，這一切在我初次接觸時都非常神祕；我花了好一陣子才覺得自己對到底是怎麼回事有了一些掌握。

[^fn-non-mathematician]: 雖然我很多很多年前確實學過數學，我盡心盡力地逃避任何聞起來像純數學的東西，例如群論。我現在後悔了。

#### 引言

橢圓曲線從第一天起就是區塊鏈工具箱的一部分。例如，比特幣與以太坊都使用名為 [secp256k1](https://en.bitcoin.it/wiki/Secp256k1) 的曲線，以 [ECDSA](https://en.bitcoin.it/wiki/Elliptic_Curve_Digital_Signature_Algorithm)（「橢圓曲線數位簽章演算法」）來簽署使用者的交易。

然而，secp256k1 曲線並未用於以太坊的共識層。我們改為使用一條名為 BLS12-381 的曲線，因為它支援一種稱為雙線性配對的數學操作——它是一條「對配對友善」的橢圓曲線。配對非常酷，因為除了別的之外，它們讓我們得以做[簽章聚合](/part2/building_blocks/signatures/)與多項式承諾，這些操作已成為以太坊共識的基礎，但大多數橢圓曲線並不支援它們。

對配對友善的橢圓曲線，是同時具有「有利的嵌入度」（embedding degree，會在[下文](#embedding-degree)解釋）與「一個大的質數階子群」（也見[下文](#the-subgroups)）的曲線。這些很罕見。如果你隨機建立一條橢圓曲線，它對配對友善的機會微乎其微。儘管如此，它們可以被構造出來，而除了 BLS 曲線之外，還有好幾個對配對友善曲線的族系[是已知的](https://eprint.iacr.org/2006/372.pdf)。

如果你想多了解一些以配對為基礎的密碼學，一些不錯的讀物：

  - Vitalik 有一份很棒的[橢圓曲線配對](https://web.archive.org/web/20231102064237/https://vitalik.ca/general/2017/01/14/exploring_ecp.html)的一般性引介。
  - Alin Tomescu 在一篇部落格文章[《配對，或雙線性映射》](https://alinush.github.io/pairings)中，對以配對為基礎的密碼學的發展史及其一些應用，做了生動有趣的回顧[^fn-mathematicians-in-jail]。
  - [NIST 關於以配對為基礎之密碼學的報告](https://pmc.ncbi.nlm.nih.gov/articles/PMC4730686/pdf/jres.120.002.pdf)頗為易讀。我推薦第 2 節與附錄。
  - 對配對友善曲線的 [IETF 標準草案](https://www.ietf.org/archive/id/draft-irtf-cfrg-pairing-friendly-curves-11.html)也是不錯的背景。

[^fn-mathematicians-in-jail]: 請務必點進去看 Dan Boneh 解釋「為何所有數學家都應該在牢裡待一段時間」的[短片](https://www.youtube.com/watch?v=1RwkqZ6JNeo)。

如果你真的想_理解_這玩意兒，那麼[《給初學者的配對》](https://www.craigcostello.com.au/s/PairingsForBeginners.pdf)無與倫比。如果你仔細地把它做過一遍、邊讀邊研究範例，它結果遠沒有看起來那麼嚇人。

#### 以太坊中的 BLS12-381

簽章聚合的可能性，是使以太坊信標鏈成為可能的[關鍵突破](https://ethresear.ch/t/pragmatic-signature-aggregation-with-bls/2105?u=benjaminion)。它讓我們得以在 2018 年中放棄先前那不切實際的權益證明計畫，全力投入信標鏈的做法。

要進行簽章聚合，我們需要使用一條密碼學上安全、對配對友善的橢圓曲線。如前所述，這些相當罕見。

為信標鏈選擇 BLS12-381 的主要原因，是它在可用的對配對友善曲線之中，就安全性（原本認為約 128 位元，但[見下文](#security-level)）、[配對操作的速度](https://github.com/zcash/zcash/issues/2502)、以及公鑰（48 位元組）與簽章（96 位元組）的大小而言，是一個甜蜜點。在其他候選者中，BN128/BN254 曲線有較小的簽章，但較低的安全性（[約 100 位元](https://github.com/zcash/zcash/issues/714#issuecomment-295813446)）。其他對配對友善的曲線（例如 BW、MNT、KSS 族系）在類似的安全等級下，往往有較大的簽章或較慢的配對。

其他有影響力的因素如下。

  - BLS12-381 是為 Zcash 設計的，並且已被諸如 Chia 等其他鏈所採用。人多有保障（更多審視、更好的函式庫），而鏈與鏈之間的互通性在當時是一條指導原則，雖然那份企圖心自那時起已然消退。
  - 關於區塊鏈簽章聚合的[原始論文](https://eprint.iacr.org/2018/483.pdf)[^fn-compact-multi]在其分析中使用了 BLS12-381。
  - BLS 曲線被納入 IETF 對配對友善曲線的[標準化過程](https://www.ietf.org/archive/id/draft-irtf-cfrg-pairing-friendly-curves-11.html)。標準化讓一切都更容易[^fn-keccak-sha3]。

[^fn-compact-multi]: [《給較小型區塊鏈的精簡多重簽章》](https://link.springer.com/chapter/10.1007/978-3-030-03329-3_15)，Boneh、Drijvers、Neven，2018。

[^fn-keccak-sha3]: 以太坊的執行層使用「幾乎、[但不完全是標準](https://crypto.stackexchange.com/questions/15727/what-are-the-key-differences-between-the-draft-sha-3-standard-and-the-keccak-sub)」的 Keccak 雜湊、而非 SHA-3 標準，這一點至今仍是內褲裡的一根芒刺。

值得一提的是，BLS12-381 也被設計成對 ZK-SNARK 證明高效率（那是 Zcash 用它的主要目的），但這在以太坊最初採用它時並不是一項主要的考量。

總而言之，我不記得關於採用曲線 BLS12-381 有過任何重大的辯論；它在當時就只是顯而易見的選擇。

#### 關於曲線 BLS12-381

##### 歷史

曲線 BLS12-381 由 [Sean Bowe](https://twitter.com/ebfull) 在 2017 年初[設計](https://web.archive.org/web/20190605200224/https://electriccoin.co/blog/new-snark-curve/)，作為 Zcash 協定一次升級的基礎。它既對配對友善（使它對數位簽章高效率），又對構造 ZK-SNARK 有效。

以太坊 2.0 是這條曲線相當早期的採用者。其他一些區塊鏈（Zcash、Chia、Dfinity、Filecoin、Algorand）也使用 BLS12-381，並有好幾個密碼學函式庫支援它。以太坊客戶端所使用的主要函式庫是 [Blst](https://github.com/supranational/blst)，它是以太坊基金會為此目的而委託開發的；其他實作這條曲線的函式庫有 [Gnark](https://github.com/Consensys/gnark-crypto)、[Noble](https://github.com/paulmillr/noble-curves)、[Herumi/mcl](https://github.com/herumi/mcl)、[Constantine](https://github.com/mratsim/constantine)。

至於標準化，BLS12-381 [被納入](https://www.ietf.org/archive/id/draft-irtf-cfrg-pairing-friendly-curves-11.html#section-4.2.1)新興的 IETF [對配對友善曲線](https://datatracker.ietf.org/doc/draft-irtf-cfrg-pairing-friendly-curves/)標準。它也出現在[雜湊至橢圓曲線](https://www.ietf.org/archive/id/draft-irtf-cfrg-hash-to-curve-10.html#section-8.8)與 [BLS 簽章](https://www.ietf.org/archive/id/draft-irtf-cfrg-bls-signature-05.html#section-4.2)的標準草案中[^fn-ietf-irtf-0]。

[^fn-ietf-irtf-0]: 這份文件並不具有 IETF 標準的完整效力。一方面，它仍然是一份草案（如今已過期），另一方面它是一份 IRTF 文件，意味著它來自一個研究群組，而非在 IETF 標準軌道上。前 IETF 主席 Brian Carpenter 提供了[一些背景](https://mailarchive.ietf.org/arch/msg/ietf/A8MaBwNpbWf_DJoWj0sRROIml3Y/)：
    > 我猜你指的是 draft-irtf-cfrg-bls-signature-04 中的一個議題。那甚至不是一份 IETF 草案；它是一份 IRTF 草案，顯然正在一個 IRTF 研究群組中被討論。所以它連「被考慮成為一個 IETF 標準」都遠遠談不上……

##### 命名

BLS12-381 是 [Barreto、Lynn、Scott](https://eprint.iacr.org/2002/088.pdf) 所描述的一個曲線族系的一部分（他們就是此處所說的 B、L、S——在與 [BLS 簽章](/part2/building_blocks/signatures/)相關之處出現的是大致不同的 BLS 三人組）。

12 是這條曲線的嵌入度：既不太低，也不太高。我們會[稍後一會兒](#embedding-degree)討論嵌入度。

381 是表示曲線上座標所需的位元數：即域模數 $q$。一個點的座標來自一個有質數階的有限域，而那個質數 $q$ 寬 381 位元。381 是一個相當方便的數，因為我們可以每個域元素用 48 位元組，剩下 3 位元用於有用的旗標或算術最佳化。這個數的大小，既受[安全性需求](#security-level)、也受實作效率所指引。

##### 域擴張

域擴張對橢圓曲線配對至關重要。BLS12-381 中的「12」不只是嵌入度，它（相關地）也是我們計算配對時需要使用的域擴張的次數。

域 $F_q$ 可以被想成就只是模 $q$ 的整數：$0,1,\ldots,q-1$。但 $F_{q^{12}}$（$F_q$ 的十二次擴張）是什麼樣的怪獸呢？

我一直找不到任何對域擴張直截了當的解說，所以這是我的嘗試。

讓我們構造 $F_{q^2}$，即 $F_q$ 的二次擴張。在 $F_{q^2}$ 中，我們會把域元素表示成像 $a_0 + a_1x$ 這樣的一次多項式，如果我們願意，可以更簡潔地寫成 $(a_0, a_1)$。

把兩個元素相加很容易：${(a, b) + (c, d)} = {a + bx + c + dx} = {(a+c) + (b+d)x} = {(a+c, b+d)}$。我們只需確保把 $a+c$ 與 $b+d$ 模 $q$ 約化。

那相乘呢？${(a, b) \times (c, d)} = {(a + bx)(c + dx)} = {ac + (ad+bc)x+ bdx^2} = {\tt ???}$。糟了——出現的那個 $x^2$ 我們該拿它怎麼辦？

我們需要一條約化多項式的規則，好讓它們的次數小於二。在這個例子中，我們會取 ${x^2 + 1} = 0$ 作為我們的規則，但我們也可以做其他選擇。關於我們的規則只有兩條規則[^fn-efmr]：

  1. 它必須是一個 $k$ 次多項式，其中 $k$ 是我們的擴張次數，在這個例子中是 $2$；以及
  2. 它在我們所擴張的域中必須是[不可約的](https://en.wikipedia.org/wiki/Irreducible_polynomial)。那意味著不可能把它分解成兩個或更多個較低次的多項式。

[^fn-efmr]: 我們的規則是一個「擴張域模約化」（extension field modular reduction，術語出自[此處](https://web.archive.org/web/20250618101639/https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=0a0f5c189957ef6b78bb2a96b275599f7426e1ac)第 4.4 節）。我們可以把它想成類比於一般算術中的取模操作：它把多項式的次數保持在一個給定的界限之內，正如取模操作把數字的大小保持在一個給定的界限之內。不可約性的要求類似於該多項式是「質的」，也就是沒有非平凡的因式。

套用我們的規則，藉由代入 $x^2 = -1$ 來消除不想要的 $x^2$ 項，得出最終結果 ${(a, b) \times (c, d)} = {ac + (ad+bc)x + bdx^2} = {(ac-bd) + (ad+bc)x} = {(ac-bd, ad+bc)}$。這從複數算術看起來可能有點眼熟：${(a+ib) \times (c+id)} = {(ac-bd) + (ad+bc)i}$。這不是巧合！複數是實數的一個二次擴張。

複數無法再被進一步擴張，因為[複數上沒有不可約多項式](https://en.wikipedia.org/wiki/Fundamental_theorem_of_algebra)。但對於有限域，如果我們能在我們的域 $F_q$ 中找到一個不可約的 $k$ 次多項式——而我們常常能——那麼我們就能把該域擴張到 $F_{q^k}$，並把擴張域的元素表示成 $k-1$ 次多項式 $a_0 + a_1x + \cdots + a_{k-1}x^{k-1}$。我們可以把這緊湊地寫成 $(a_0,\ldots,a_{k-1})$，只要我們記得其中可能進行著一些非常別緻的算術。

也值得一提的是，像這樣的模約化（我們的約化規則）可以被選得與[扭曲](#twists)（twisting）操作配合良好。

實務上，像 $F_{q^{12}}$ 這樣的大擴張域，是以較小擴張的塔（tower）來實作的。那是一個實作面向，所以我把它放在[下文](#extension-towers)較實務的部分。

##### 那些曲線

關於 BLS12-381，一件起初不明顯的事是：我們其實在處理的是兩條曲線，而非一條。這兩條曲線共享或多或少相同的曲線方程式，但定義在不同的域上。

##### Curve equation and parameters

The basic equation of the BLS12-381 curve is $y^2=x^3+4$.[^fn-bls12381-refs]

[^fn-bls12381-refs]: This [now deleted page](https://github.com/zkcrypto/pairing/blob/34aa52b0f7bef705917252ea63e5a13fa01af551/src/bls12_381/README.md) is the reference for much of this section. Lots of curve data is also in the [IETF specification](https://www.ietf.org/archive/id/draft-irtf-cfrg-pairing-friendly-curves-11.html#name-bls-curves-for-the-128-bit-).

The key parameters for a BLS curve are set using a single parameter $\tt x$ (different from the $x$ in the curve equation!) that can be selected to give the curve nice properties for implementation. BLS12-381 is derived from the $k\equiv0\,\text{(mod 6)}$ case of Construction 6.6 in the [taxonomy](https://eprint.iacr.org/2006/372.pdf).

Specific design goals for BLS12-381 are:

  - $\tt x$ has "low hamming weight", meaning that it has very few bits set to 1. This is particularly important for the efficiency of the algorithm that calculates pairings (the Miller loop).
  - The field modulus $q$ mentioned above is prime and has 383 bits or fewer, which makes 64-bit or 32-bit arithmetic on it more efficient.
  - The order $r$ of the subgroups we use is prime and has 255 bits or fewer, which is good for the same reason as above.
  - The security target is 128 bits - see [below](#security-level).
  - To support ZK-SNARK schemes, we want to have a large power of two [root of unity](#roots-of-unity) in the field $F_r$. This means we want $2^n$ to be a factor of $r-1$, for some biggish $n$. Making $\tt x$ a multiple of $2^\frac{n}{2}$ will achieve this. This property is key to being able to use fast Fourier transforms for interesting things like polynomial multiplication.

The value ${\tt x}=$&nbsp;`-0xd201000000010000` (hexadecimal, note that it is negative) gives the largest $q$ and the lowest Hamming weight meeting these criteria. With this $\tt x$ value we have,

| Parameter | &nbsp; | Equation | Value | Comments |
| ---- | - | ---- | ---------------- | ---- |
| Field modulus | $q$ | $\frac{1}{3}{({\tt x}-1)}^2\allowbreak {({\tt x}^4-{\tt x}^2+1)}\allowbreak +{\tt x}$ | Hex: <span class="wrap">`0x1a0111ea397fe69a4b1ba7b6434bacd764774b84f38512bf6730d2a0f6b0f6241eabfffeb153ffffb9feffffffffaaab`</span><br/>Dec: <span class="wrap">4002409555221667393417789825735904156556882819939007885332058136124031650490837864442687629129015664037894272559787</span> | 381 bits, prime |
| Subgroup size | $r$ | ${({\tt x}^4-{\tt x}^2+1)}$ | Hex: <span class="wrap">`0x73eda753299d7d483339d80809a1d80553bda402fffe5bfeffffffff00000001`</span><br/>Dec: <span class="wrap">52435875175126190479447740508185965837690552500527637822603658699938581184513</span> | 255 bits,  prime |

較簡單的那條是在有限域 $F_q$ 上，而 $F_q$ 就只是模 $q$ 的整數。所以這條曲線只在「方程式 $y^2=x^3+4$ 有著 $x$ 與 $y$ 皆為小於 $q$ 之整數的解」之處有點。舉例來說，$(0,2)$ 就是這樣一個點[^fn-another-point]。我們會把這條曲線稱為 $E(F_q)$。

[^fn-another-point]: $E(F_q)$ 上的另一個點是 <span class="wrap">`(0x04,0x0a989badd40d6212b33cffc3f3763e9bc760f988c9926b26da9dd85e928483446346b8ed00e1de5d5ea93e354abe706c)`</span>。平均而言，約有一半的 $x$ 值會得出曲線上的一個點，而其中大多數的 $(x,y)$ 與 $(x,-y)$ 都在曲線上（對某些則 $y=0$）。你很快就會習慣這些大到荒謬的數字。

另一條曲線定義在 $F_q$ 對 $F_{q^2}$ 的[擴張](https://en.wikipedia.org/wiki/Field_extension)上（想想複數）。在這種情況下，曲線方程式被略微修改為 $y^2=x^3+4(1+i)$[^fn-i-or-u]，我們會把這條曲線稱為 $E'(F_{q^2})$[^fn-point-on-e-prime]。我們會在[扭曲](#twists)一節解釋這是從何而來的。

[^fn-i-or-u]: 這裡有時用 $u$ 而非 $i$，且 $u^2+1=0$。我用 $i$。

[^fn-point-on-e-prime]: 這是 $E'$ 曲線上的一個點：<span class="wrap">`(1+i, 0x17faa6201231304f270b858dad9462089f2a5b83388e4b10773abc1eef6d193b9fce4e8ea2d9d28e3c3a315aa7de14ca + i * 0xcc12449be6ac4e7f367e7242250427c4fb4c39325d3164ad397c1837a90f0ea1a534757df374dd6569345eb41ed76e)`</span>

順帶一提，$E'(F_{q^2})$ 的曲線階（曲線上點的數量）遠遠大於 $E(F_q)$ 的；當定義域被擴張到複數時，曲線方程式有著多得多的解。事實上，$E$ 的階接近 $q$，而 $E'$ 的階接近 $q^2$。這不是巧合，而是 [Hasse 界](https://en.wikipedia.org/wiki/Hasse%27s_theorem_on_elliptic_curves)的結果。這些數字的實際值見[參考一節](#bls12-381-reference)。

##### 子群

在本節與下一節，我會試著解釋 BLS12-381 何以最終有著兩個曲線方程式、而非一個。

一個配對是一個雙線性映射。這意味著它取兩個點作為輸入，每個點都來自一個有相同階 $r$ 的群。這個 $r$ 必須是質數，而為了安全需要很大。此外，基於相當技術性的原因[^fn-distinct-subgroups]，這兩個群需要是相異的。我們把它們稱為 $G_1$ 與 $G_2$。

[^fn-distinct-subgroups]: 關於我們為何偏好讓 $G_1$ 與 $G_2$ 是相異子群的更多內容，見[《以配對為基礎之密碼學中的子群安全性》](https://eprint.iacr.org/2015/247.pdf)引言中的「非對稱配對」段落。簡言之，非對稱配對比對稱配對更安全、計算上更有效率，因為後者只存在於超奇異曲線上。

不幸的是，我們那條簡單的曲線 $E(F_q)$ 只有單一一個大子群，所以我們無法單憑 $E(F_q)$ 定義出一個有用的配對。

[然而](https://web.archive.org/web/20131203082655/https://www.computing.dcu.ie/~mike/tate.html)，如果我們持續擴張 $E$ 所定義於其上的域，可以證明我們最終會找到一條有著不止一個 $r$ 階子群（事實上有 $r+1$ 個）的曲線。也就是說，對某個 $k$，$E(F_{q^k})$[^fn-lost-prime] 含有其他我們可以使用的 $r$ 階子群。這些子群中有一個只含跡為零的點[^fn-trace-zero]，我們選那個子群作為 $G_2$。

[^fn-lost-prime]: 請注意，我們這裡把 $E$ 上的 $'$ 弄丟了——這是原本的曲線 $y^2=x^3+4$，但現在定義在 $F_{q^k}$ 上。

[^fn-trace-zero]: 基本上，一個點的跡是 $\sum_{i=0}^{k-1}(x^{q^i},y^{q^i})$，在我們的情況中 k=12。理解這個牽涉到諸如 Frobenius 自同態這類東西，而那個兔子洞挖得很深。

這個數 $k$，也就是我們為了找到新群所需擴張基域的量，稱為該曲線的_嵌入度_（embedding degree），在我們的情況中就是 BLS12-381 中的「12」。我們稍後一會兒會更多地討論嵌入度。

為求完整，請注意 $G_1$ 與 $G_2$ 每一個都與它所在的曲線共享「無窮遠點」。這是橢圓曲線算術群的單位元，常記為 $\mathcal{O}$。對任何點 $P$，$P+\mathcal{O}=\mathcal{O}+P=P$。

總結我們進展到的地方，我們現在在 $E(F_q)$ 中有一個 $r$ 階的群 $G_1$，並在 $E(F_{q^{12}})$ 中有一個相異的 $r$ 階群 $G_2$。耶——我們可以做配對了！

##### 扭曲

但還有另一個難題。如前所討論，在 $F_{q^{12}}$ 中做算術複雜且低效率得可怕，而曲線運算需要大量的算術。但有一個辦法可以繞開這一點。

一個[扭曲](https://web.archive.org/web/20241006125924/http://indigo.ie/~mscott/twists.pdf)（twist）有點像是一個座標變換。相當奇妙地，這可以被用來把我們的 $E(F_{q^{12}})$ 曲線變換成一條定義在較低次域上、卻仍有一個 $r$ 階子群的曲線。此外，這個子群與我們的 $G_2$ 群之間有一個簡單的雙向映射[^fn-trace-zero-again]。

[^fn-trace-zero-again]: 因為我們先前選了跡為零的子群。[《給初學者的配對》](https://www.craigcostello.com.au/s/PairingsForBeginners.pdf)深入探討了這方面的細節。

曲線 BLS12-381 使用一個「六次扭曲」（sextic twist）。這意味著它把擴張域的次數減少六倍。所以扭曲曲線上的 $G_2$ 可以定義在 $F_{q^2}$、而非 $F_{q^{12}}$ 上，這是複雜度上一項巨大的節省。

如果我們能找到一個 $u$ 使得 $u^6=(1+i)^{-1}$，那麼我們就可以把我們的扭曲變換定義為 $(x,y)\rightarrow(x/u^2,y/u^3)$[^fn-twisting-transformation]。這把我們原本的曲線 $E:y^2=x^3+4$ 變換成曲線 $E':y^2 = {x^3 + 4/u^6} = {x^3 + 4(1+i)}$。$E$ 與 $E'$ 看起來不同，但實際上是同一個物件、相對於不同基域中的係數所呈現的[^fn-ack-olivier]。

[^fn-twisting-transformation]: 這似乎在任何地方都沒有記載，但我是藉由試著解讀 Barreto 與 Naehrig 的[《質數階的對配對友善橢圓曲線》](https://eprint.iacr.org/2005/133.pdf)第 3 節而得到這個的。

[^fn-ack-olivier]: 我為這個洞見感謝 Olivier Bégassat。

當扭曲被[正確地完成](https://web.archive.org/web/20241006125924/http://indigo.ie/~mscott/twists.pdf)時，所得到的 $E'$ 有一個 $r$ 階子群，它映射到我們的 $G_2$ 群，反之亦然。所以，結果是我們大部分目的都可以在 $F_{q^2}$ 上的 $E'$ 中作業，只在需要時（也就是只在實際計算配對時）才把 $G_2$ 映射回 $E(F_{q^{12}})$。

所以這就是我們將使用的兩個群：

  - $G_1$ $\subset E(F_q)$，其中 $E: y^2 = x^3 + 4$
  - $G_2$ $\subset E'(F_{q^2})$，其中 $E': y^2 = x^3 + 4(1+i)$

這就是 BLS12-381 為何看起來像兩條曲線、而非一條的故事。$E'(F_{q^2})$ 被稱為 $E(F_q)$ 的扭曲，或與 $E(F_q)$ 對應的扭曲曲線。

請注意，$G_1$ 群中點的座標是成對的整數，而 $G_2$ 群中點的座標是成對的複整數，所以 $G_2$ 的點佔用兩倍的儲存量，作業起來也較昂貴。這導致了有意思的[實作取捨](#swapping-g1-and-g2)。

##### 配對

那麼，配對這玩意兒究竟是怎麼回事？

就 BLS12-381 而言，一個配對是一個函式，它單純地取一個點 $P\in G_1\subset E(F_q)$、一個點 $Q\in G_2\subset E'(F_{q^2})$，並輸出一個來自群 $G_T\subset F_{q^{12}}$ 的點。也就是說，一個配對 $e$ 是一個映射 $e:G_1\times G_2\rightarrow G_T$。

橢圓曲線配對通常記為 $e(\cdot,\cdot)$（它們取一對運算元，因而得名），並有某些性質。

1. $e(\cdot,\cdot)$ 是[雙線性](#bilinearity)的。
2. $e(\cdot,\cdot)$ 是可有效率地計算的。對任何 $P$ 與 $Q$，我們都必須有一個多項式時間的演算法來計算 $e(P,Q)$。
3. $e(\cdot,\cdot)$ 是非退化的。也就是說，對一個非零的 $P \in G_1$，必定存在某個 $Q \in G_2$ 使得 $e(P,Q) \neq 1$（$G_T$ 中的單位元），反之亦然。這確保了配對是「非平凡的」、並且實際上有用。

###### 雙線性

配對的性質中我們最感興趣的，是它們是_雙線性_的。也就是說，$e(P,Q)$ 對它的兩個引數都是線性的。

任何會做乘法的人都熟悉雙線性：設 $f(a,b) \equiv a \times b$，那麼 ${f(a_1 + a_2, b)} = {f(a_1, b) + f(a_2, b)}$，且 ${f(a, b_1 + b_2)} = {f(a, b_1) + f(a, b_2)}$——乘法對它的兩個引數都是線性的。

我們可以為橢圓曲線點構造一個類似的雙線性函式，方法是把兩個輸入點的離散對數相乘。如果 $g$ 是一個橢圓曲線群的生成元，那麼一個點 $P$ 依定義就是那個生成元的一個倍數 $P=[p]g$，而 $p$ 被稱為 $P$ 的離散對數[^dl-rant]。所以，給定點 $P=[p]g$ 與 $Q=[q]g$，我們可以找出 $p$ 與 $q$，並定義 $e(P,Q) = [pq]g$——這歸結為整數乘法，因此是雙線性的。然而，這的缺陷在於：在我們的橢圓曲線上取離散對數，依設計被假定是非常、非常昂貴的。它基本上需要暴力計算，成本與曲線階成比例，而這正是讓我們的簽章方案保持安全的東西。這就是為什麼配對操作需要它的第二項性質：它必須是可_有效率地_計算的。

[^dl-rant]: 此處輪到我照例抱怨：在以加法寫成的群中，為何它仍被稱為離散對數、而非離散除法。

###### 雙線性配對

我不會深入「可有效率地計算的配對函式 $e(\cdot,\cdot)$ 如何構造」的所有細節——我們大致可以把它當成一個黑箱——儘管如此，[Vitalik 的文章](https://web.archive.org/web/20231102064237/https://vitalik.ca/general/2017/01/14/exploring_ecp.html)是一份很棒的引介，而要看所有精彩的細節，容我再次推薦[《給初學者的配對》](https://www.craigcostello.com.au/s/PairingsForBeginners.pdf)。

Recall that $e$ is a mapping, $e:G_1\times G_2\rightarrow G_T$. Since $e(\cdot,\cdot)$ is linear in both its arguments, it behaves as follows.

  - $e(P, Q + R) = e(P, Q) \cdot e(P, R)$, and
  - $e(P + S, R) = e(P, R) \cdot e(S, R)$

From this, we can deduce that all of the following identities hold:

  - ${e([a]P,[b]Q)} = {e(P,[b]Q)^a} = {e(P,Q)^{ab}} = {e(P,[a]Q)^b} = {e([b]P,[a]Q)}$

Note that, traditionally, the group operation in $G_1$ and $G_2$ is written additively, and the group operation in $G_T$ is written multiplicatively[^fn-notational-weirdness] - I've used a "$\cdot$" to show that above. So we write $[n]P$ or $[n]Q$ for applying the group operation $n$ times on $P \in G_1$ or on $Q \in G_2$, but we write $e(P,Q)^n$ (rather than $[n]e(P,Q)$) because $e(P,Q) \in G_T$.

[^fn-notational-weirdness]: It is natural to write elliptic curve groups (like $G_1$ and $G_2$) additively due to the way that elliptic curve point addition is constructed geometrically. $G_T$ is not an elliptic curve group, but rather a finite field subgroup, in which multiplication is the more intuitive group operation.

If we look past this notational weirdness, then we can loosely think of a pairing as being a way to "multiply" a point in $G_1$ by a point in $G_2$, an operation that cryptographically secure elliptic curves don't normally support in any practical way.

In any case, bilinearity is just what we need when [verifying BLS digital signatures](/part2/building_blocks/signatures/#verifying).

##### Embedding degree

We've mentioned the embedding degree several times, and it is significant enough to appear in the name of the curve.

The embedding degree, $k$, is calculated as the smallest positive integer such that $r$ divides $(q^k − 1)$. So, in the case of BLS12-381, $r$ is a factor of $(q^{12}-1)$[^fn12], but not of any lower power.

[^fn12]: Numbers in this world are truly enormous. The number of times $r$ divides $(q^{12}-1)$ is 1299 digits long in decimal. This number is actually used in the final exponentiation when computing pairings (a multiplicative version of cofactor clearing).

It turns out that this number, $k$, gives the smallest field extension $F_{q^k}$ that satisfies the two equivalent conditions:

  - $F_{q^k}$ contains more than one subgroup of order $r$ (used for constructing $G_2$, see [above](#the-subgroups));
  - $F_{q^k}$ contains all the $r$th roots of unity (used for constructing $G_T$, see [below](#roots-of-unity))

These are the conditions we need to satisfy for pairings to be possible.

嵌入度的選擇（一如既往地）是安全性與效率之間的一個平衡。在[安全性](#security-level)這一面，嵌入度也被稱為安全乘數：較高的嵌入度使離散對數問題在 $G_T$ 中更難求解。然而，高嵌入度意味著我們必須在高次擴張（例如 $F_{q^{12}}$）中做域運算，那既笨重又低效率。（即使在使用[扭曲](#twists)時也是如此：可用的最大扭曲是六次，所以我們所能做到最好的，就是把域擴張次數減少六倍。而且無論如何，配對都必須在那個大擴張域中進行。）

12 或 24 的嵌入度，對許多應用而言似乎是當前的一個甜蜜點。再一次，BLS12-381 的嵌入度是 12——它就在名稱裡。

##### 安全等級

密碼系統的安全性以[位元來衡量](https://en.wikipedia.org/wiki/Security_level)。非正式地說，我把 $n$ 位元安全理解成像「要破解它需要約 $2^n$ 次操作」這樣的意思。

對於橢圓曲線密碼學，安全性的全部關鍵在於使離散對數問題變得困難。也就是說，給定一個點 $g$ 與一個點 $g^k$（用乘法群符號），在沒有先備知識的情況下找出 $k$ 必須不可行，意思是以今天的標準而言，我們希望對 $n>100$ 左右它至少要花 $2^n$ 次操作。

對於對配對友善的曲線，離散對數問題在我們所使用的三個群 $G_1$、$G_2$、$G_T$ 的每一個中都必須困難。因此，要瞄準 $n$ 位元安全，

  - 質數群階 $r$ 必須至少 $2n$ 位元長，因為存在像 [Pollard's rho 演算法](https://en.wikipedia.org/wiki/Pollard%27s_rho_algorithm_for_logarithms)這樣成本為 $O(\sqrt{r})$ 的演算法。
  - 我們的擴張域 $F_{q^k}$ 必須夠大，才不會易受像[數域篩法](https://en.wikipedia.org/wiki/General_number_field_sieve)這類方法之害。

基於這些準則，BLS12-381 原本意在提供約 128 位元的安全等級，而初步的分析支持這一點。例如見[《分類》](https://eprint.iacr.org/2006/372.pdf)中的表 1.1。

然而，更仔細地檢查之後，鑑於上述第二項準則，似乎「大小為 3072 = 12 × 256 位元的有限擴張域不夠大」（引用[此處](https://eprint.iacr.org/2019/077.pdf)第 2 節）。

根據一份 [NCC Group 的報告](https://www.nccgroup.com/media/v1kkxeae/_ncc_group_zcash2018_public_report_2019-01-30_v13.pdf)（引用了其他來源），實際的安全等級大概介於 117 與 120 位元之間（見第 8、9 頁）。他們認為這是一個完全充足的安全水準：「達到『128 位元』的價值〔大多是〕心理上的」。Sean Bowe 也鑑於[原本的設計目標](https://github.com/zcash/zcash/issues/4065#issuecomment-572202467)對安全等級發表了評論。BLS12-381 的 IETF 規格草案比 NCC Group 較不悲觀，並[引用](https://www.ietf.org/archive/id/draft-irtf-cfrg-pairing-friendly-curves-11.html#section-4.2.1-8)了 126 位元的安全等級。

##### 餘因子

一個子群的餘因子（cofactor），是整個群的大小與該子群的大小之比。一般的橢圓曲線密碼學要求餘因子非常小，[通常是一](https://crypto.stackexchange.com/questions/2881/why-would-anyone-use-an-elliptic-curve-with-a-cofactor-1)，以避免對離散對數的小子群攻擊。然而，在以配對為基礎的密碼學中，情況並非如此，$G_1$ 與 $G_2$ 群的餘因子可以真的非常龐大。

結果是，只要小心，我們可以有大的餘因子卻仍然安全。也就是說，當 $G_1$、$G_2$、$G_T$ 的餘因子不含小於 $r$ 的質因數時。[這篇論文](https://eprint.iacr.org/2015/247.pdf)的第 3.2 節詳細討論了這一點。然而，對 BLS12-381 來說情況_並非_如此，$G_1$ 與 $G_2$ 的餘因子都有好幾個小因數。因此，我們[在我們的實作中](#subgroup-membership-checks)必須留意小子群攻擊。

我已在[參考一節](#bls12-381-reference)列出了曲線階的質因數，以及餘因子本身。$G_1$ 餘因子含有像 3、11、10177 這樣的小質因數；$G_2$ 餘因子含有像 13、23、2713 這樣的小質因數。

不過，說到餘因子並不全是壞消息。結果是，乘以群的餘因子，是把橢圓曲線上任何任意的點映射進各自子群 $G_1$ 或 $G_2$ 的一種直截了當的方式[^fn13]。這在做「雜湊至曲線」這類操作時很重要：我們先造出曲線上的一個點，然後藉由乘以餘因子把它映射進適當的群，這就是所謂的[餘因子清除](#cofactor-clearing)。

[^fn13]: 這很容易看出。子群 $G$ 的階是 $r$，它的餘因子是 $h$，使得 $hr = n$，即整個橢圓曲線群的階。考慮橢圓曲線群的一個任意元素 $P$。我們有 $\mathcal{O} = [n]P = [r] ([h]P)$。因此 $[h]P\in G$。或者，對每一個不是 $G$ 的子群，$h$ 都是它的階的倍數，所以乘以 $h$ 就「殺掉」了 $P$ 中所有不在 $G$ 中的成分。雖然並非 BLS12-381 所特有，這裡有一篇關於餘因子清除的[出色文章](https://loup-vaillant.fr/tutorials/cofactor)。

##### 單位根

只是一則關於單位根（root of unity）的註記，因為它們出現在兩個完全不同、互不相關的情境中，這可能令人困惑。

第一，我們說過，為了用這條曲線支援 ZK-SNARK 方案，對某個相當大的 $n$，我們想在域 $F_r$（注意，不是 $F_q$）中有一個 $2^n$ 次單位根。這是為了便於高效率的快速傅立葉變換，用以操作純量域 $F_r$ 上非常大的多項式。從 $r-1$ 的十六進位表示，它顯然是 $2^{32}$ 的倍數，所以有一個 $2^{32}$ 次單位根（事實上有 $2^{32}$ 個）。

第二，且完全無關，配對的效果是把來自 $G_1$ 與 $G_2$ 的兩個點映射到 $F_{q^{12}}$ 中的一個 $r$ 次單位根上。這些 $r$ 次單位根實際上在 $F_{q^{12}}$ 中構成一個 $r$ 階的子群[^fn-roots-of-unity]，那就是我們稱為 $G_T$ 的群。

[^fn-roots-of-unity]: 這是乘法群中單位根的一個一般性質，並非橢圓曲線或配對所特有。例如，$F_{q^2}$ 中四次單位根的集合 $\{1, -i, -1, i\}$，在乘法下構成一個四階的群。

讓我們簡短地回顧[我們先前的討論](#the-subgroups)——把 $E$ 的基域擴張到 $F_{q^{12}}$，我們這麼做是為了找到另一個 $r$ 階的子群。結果還有一點是：$F_{q^{12}}$ 被當成一個乘法群來看時，是「含有該域中 $r$ 次單位根」的最小域擴張，那個 12 再一次來自嵌入度。這就是為什麼 $G_T$ 定義在 $F_{q^{12}}$ 上。

#### 使用曲線 BLS12-381

本節是與「在實務上使用 BLS12-381」相關的雜項。

##### BLS 數位簽章

現在該介紹另一組 BLS 了：Boneh、Lynn、Shacham。（這個 L 與 BLS12-381 中的 L 是同一個 L；B 和 S 則不同。）

BLS 簽章[早在 2001 年](https://www.iacr.org/archive/asiacrypt2001/22480516.pdf)被提出，比 2002 年發表的 [BLS 曲線族系](https://eprint.iacr.org/2002/088.pdf)略早一點。令人愉快的是，它們攜手並進。（BLS 簽章可以使用其他曲線；BLS 曲線也有簽章以外的用途。但當它們湊在一起時很不錯。）

BLS 簽章方案在下面簡短地描述。關於我們如何在以太坊 2 中實作它們的更完整探討，見 [BLS 簽章](/part2/building_blocks/signatures/)一章。你可以在 [IETF 標準草案](https://www.ietf.org/archive/id/draft-irtf-cfrg-bls-signature-05.html)中找到對 BLS 簽章方案相當簡潔但清晰的描述。

###### 私鑰與公鑰

私鑰／祕密金鑰（用於簽章）就只是一個在 $1$ 與 $r-1$（含）之間隨機選出的數。我們把它稱為 $sk$。

對應的公鑰（如果我們[用 $G_1$ 作為公鑰](#swapping-g1-and-g2)）是 $pk = [sk]g_1$，其中 $g_1$ 是 $G_1$ 所選定的[生成元](#generators)。也就是 $g_1$ 乘以 $sk$，即 $g_1$ 與自己相加 $sk$ 次。

離散對數問題意味著：給定公鑰 $pk$，要復原 $sk$ 是不可行的。

###### 簽章

要簽署一則訊息 $m$，我們首先需要把 $m$ 映射到群 $G_2$ 中的一個點上（如果我們[用 $G_2$ 作為簽章](#swapping-g1-and-g2)）。關於做這件事的方法的討論，見[下文](#hashing-to-the-curve)的「雜湊至曲線」。無論如何，讓我們假設我們能做到這一點，並把所得的 $G_2$ 點稱為 $H(m)$。

我們藉由計算簽章 $\sigma = [sk]H(m)$ 來簽署訊息。也就是把那個雜湊點乘以我們的祕密金鑰。

###### 驗證

給定一則訊息 $m$、一份簽章 $\sigma$、一把公鑰 $pk$，我們想驗證它是被與 $pk$ 對應的 $sk$ 所簽署的。

這就是[配對](#pairings)登場之處。簽章有效，若且唯若 $e(g_1,\sigma) = e(pk,H(m))$。

我們可以用配對的性質來確認這一點：${e(pk,H(m))} = {e([sk]g_1,H(m))} = {e(g_1,H(m))^{(sk)}} = {e(g_1,[sk]H(m))} = {e(g_1,\sigma)}$。

###### 聚合

BLS 簽章一個真正俐落的性質，是它們可以被[聚合](https://eprint.iacr.org/2018/483.pdf)（另見[原始論文](https://crypto.stanford.edu/~dabo/pubs/papers/aggreg.pdf)），使得我們只需兩次配對就能驗證一則由 $n$ 方所簽署的單一訊息，或只需 $n+1$ 次配對就能驗證由 $n$ 方所簽署的 $n$ 則不同訊息，而非你樸素地以為會需要的 $2n$ 次配對。配對計算起來昂貴，所以這非常有吸引力。

可以聚合對不同訊息的簽章，也可以聚合對同一則訊息的簽章。在以太坊 2.0 的情況中，我們聚合對同一則訊息的簽章，所以為求簡潔，我只會考慮那種。

要聚合簽章，我們只需把它們所對應的 $G_2$ 點加起來：$\sigma_{agg} = \sigma_1+\sigma_2+\cdots+\sigma_n$。我們也聚合對應的 $G_1$ 公鑰點 $pk_{agg} = pk_1+pk_2+\cdots+pk_n$。

現在，配對的魔法意味著，我們只需驗證 $e(g_1,\sigma_{agg}) = e(pk_{agg},H(m))$，就能僅用兩次配對一起驗證所有的簽章。

##### 對調 G1 與 G2

就許多目的而言，$G_1$ 與 $G_2$ 群是可互換的。例如，在 BLS 簽章方案中，我們可以選擇讓我們的公鑰是 $G_1$ 的成員、讓我們的簽章是 $G_2$ 的成員，也可以反過來做——配對函式不在乎；如果我們把兩個群對調，一切仍然運作。

取捨在於執行速度與儲存大小。$G_1$ 有小的點，而且快；$G_2$ 有大的點，而且慢。BLS12-381 最初是為實作 Zcash 而設計的，出於效能的原因，他們選擇用 $G_1$ 來表示簽章、用 $G_2$ 來表示公鑰。

相對於 Zcash，大多數其他的實作是「反過來」的。在以太坊 2.0 中，我們[用 $G_1$ 作為公鑰](/part2/building_blocks/signatures/#choice-of-groups)：一方面，公鑰的聚合發生的頻率遠高於簽章的聚合；另一方面，驗證者的公鑰需要被儲存在狀態中，所以讓表示保持小很重要。那麼，簽章就是 $G_2$ 點。

##### 點壓縮

（請注意，有時[扭曲](#twists)操作被稱為點壓縮——那是與我們在這裡所討論的完全不同的東西。）

為了儲存與傳輸橢圓曲線點，常見的做法是丟掉 $y$ 座標。這把資料量減半。對於 BLS12-381，$G_1$ 點從 96 位元組（2 × 381 位元、捨入到位元組）減為 48 位元組，$G_2$ 點從 192 位元組減為 96 位元組。

任何橢圓曲線點都可以用相關的曲線方程式 $E$ 或 $E'$，從 $x$ 座標重新產生。對於曲線上任何有效的 $x$ 座標，$y$ 要嘛是零，要嘛有兩個互為相反數的可能值：對 $G_1$ 是 $y=\pm\sqrt{x^3+4}$，對 $G_2$ 則類似。

由於域元素是 381 位元，而 48 位元組是 384 位元，我們有一些多餘的位元可用於旗標。最重要的是一個旗標，用以顯示該點對應到哪一個 $y$ 值（正或負）。另一個位元被用來標示這是否為無窮遠點（它有許多可能的表示）。第三個位元單純地用以指出這是壓縮過還是未壓縮的表示，雖然實務上情境應能處理這一點。

對 $G_1$ 與 $G_2$ 兩者而言，約有一半的 $x$ 值不在曲線上。在這種情況下，依慣例該點被解碼為無窮遠點。但除非無窮遠旗標被設定——在那種情況下我們本不會嘗試解碼該點——否則這是一個錯誤狀況。

關於旗標位元與 $x$ 值如何編碼的具體細節在[此處](https://github.com/zcash/librustzcash/blob/6e0364cd42a2b3d2b958a54771ef51a8db79dd29/pairing/src/bls12_381/README.md#serialization)。

##### 子群成員資格檢查

在處理任何來歷不明的點時，無論它是壓縮過還是未壓縮地來到我們手中，重要的是我們要檢查它落在正確的子群中。上述的點解壓縮只得出曲線上的一個點；我們不知道它是否落在適當的 $G_1$ 或 $G_2$ 中。

主要的問題似乎是 $E(F_{q})$ 與 $E'(F_{q^2})$ 兩者都含有小子群（你可以藉由分解餘因子[^fn-factoring]看到這一點——實際的因數見[參考一節](#bls12-381-reference)）。無意中在這些小子群中處理點，可能導致弱點，如[這篇論文](https://eprint.iacr.org/2015/247.pdf)所討論。

[^fn-factoring]: 分解巨大數字的幾個線上工具有 [dCode](https://www.dcode.fr/prime-factors-decomposition)，以及 [Dario Alpern](https://www.alpertron.com.ar/ECM.HTM) 的工具。

子群檢查在原則上很容易：只要把我們的點乘以 $r$。對於 $G_1$ 或 $G_2$ 中的點，這會得出各自的無窮遠點；對於群之外的點，則不會。

不幸的是，這在實務上很慢，尤其對 $G_2$ 而言，因為 $r$ 如此之大。作為替代，有[新的技術](https://eprint.iacr.org/2019/814.pdf)利用自同態來執行較快的子群檢查。

##### 生成元

$G_1$ 與 $G_2$ 是質數階的循環群，所以任何點（除了單位元／無窮遠點）都是一個生成元。因此，挑選生成元只是一個慣例的問題。

$G_1$ 與 $G_2$ 的生成元點以十進位表示在[此處](https://github.com/zcash/librustzcash/blob/6e0364cd42a2b3d2b958a54771ef51a8db79dd29/pairing/src/bls12_381/README.md#generators)指定，相同的點以十六進位表示在[此處](https://www.ietf.org/archive/id/draft-irtf-cfrg-pairing-friendly-curves-11.html#section-4.2.1)。

它們是[如下](https://github.com/zcash/librustzcash/blob/6e0364cd42a2b3d2b958a54771ef51a8db79dd29/pairing/src/bls12_381/README.md#generators)被選定的：

> $G_1$ 與 $G_2$ 的生成元，是藉由找出字典序最小的有效 x 座標、以及其字典序最小的 y 座標，並把它以餘因子縮放、使結果不是無窮遠點而計算出來的。

依我的計算，以 $h_1$ 與 $h_2$ 為各自的群[餘因子](#cofactor)，這使得 $G_1$ 生成元為 $g_1=[h_1]p_1$，其中 $p_1$ 如下，

  - $p_1 =$ <span class="wrap">`(0x04, 0x0a989badd40d6212b33cffc3f3763e9bc760f988c9926b26da9dd85e928483446346b8ed00e1de5d5ea93e354abe706c)`</span>

而 $G_2$ 生成元為 $g_2=[h_2]p_2$，其中 $p_2$ 如下，

  - $p_2 =$ <span class="wrap">`([0x02, 0x00],[0x013a59858b6809fca4d9a3b6539246a70051a3c88899964a42bc9a69cf9acdd9dd387cfa9086b894185b9a46a402be73,0x02d27e0ec3356299a346a09ad7dc4ef68a483c3aed53f9139d2f929a3eecebf72082e5e58c6da24ee32e03040c406d4f])`</span>

（我認為「字典序最小」意味著把基域中所有的數都當成非負，並就取較小的那個，且實部優先於虛部。）

##### 最終冪運算

一個配對的計算有兩個部分：Miller 迴圈與最終冪運算（final exponentiation）。這兩個部分都相當昂貴，但有一個不錯的小技巧可以做，以減少最終冪運算的影響。

通常，為了執行簽章驗證，我們計算兩個完整的配對，以檢查 $e(g_1,\sigma)=e(pk,H(m))$ 是否成立。

如果我們把不含最終冪運算的配對記為 $e'(\cdot,\cdot)$，那麼對某個 $x$，我們是在檢查 $e'(g_1,\sigma)^x=e'(pk,H(m))^x$ 是否成立。（$x$ 剛好是 $(q^{12} − 1)/r$，它很巨大[^fn-final-exponentiation]。）

[^fn-final-exponentiation]: $(q^{12} − 1)/r$ 實際上是 $G_T$ 群在 $F^*_{q^{12}}$ 中的餘因子。執行冪運算把 Miller 迴圈所產生的元素映射進 $G_T$，即 $r$ 次單位根的群。當我們把加法群與乘法群之間的符號差異納入考量時，這類比於本節別處所討論的 $G_1$ 與 $G_2$ 的餘因子清除。

我們知道如何在群 $G_T$ 中相乘，所以我們可以把這重新組織成一項檢查：$(e'(-g_1,\sigma)e'(pk,H(m)))^x=1$ 是否成立。（我們可以把其中任一個點取負：配對的魔法使這等價於在 $G_T$ 中取反元素。）

所以，要驗證一份簽章，我們做那兩個 Miller 迴圈，其中一個帶有一個取負的輸入值，把結果相乘，然後做單一一次最終冪運算。如果結果在 $G_T$ 中是單位元，那麼我們的配對就相符。這應當會帶來值得的加速。

##### 雜湊至曲線

要計算對一則訊息的數位簽章，我們首先需要把一則任意的訊息（位元組字串）變換成 $G_2$ 曲線上的一個點（如果我們用 $G_2$ 作為簽章）。做這件事有許多方法，效率與安全性程度各異。

###### 雜湊並檢查

Eth2 中[最初的實作](https://github.com/ethereum/consensus-specs/pull/141/files)是「雜湊並檢查」（hash-and-check）。這非常簡單。

1. 把你的訊息雜湊成一個模 $q$ 的整數。
2. 檢查曲線上是否有一個帶有這個 $x$ 座標（實部 $x$、虛部 $0$）的點。如果沒有，把 $x$ 加一並重複這一步。
3. 我們有了曲線上的一個點！乘以 $G_2$ 餘因子，把它轉換成 $G_2$ 中的一個點（[餘因子清除](#cofactor-clearing)）。

我們所嘗試的點約有一半會得出曲線上的一個點，所以這不是定時的（constant time）：我們不知道找到一個會花多少次迭代。在某種意義上這無關緊要：所有的資訊都是公開的，所以我們沒有洩漏任何東西。然而，它確實開啟了一種惡作劇攻擊（griefing attack）。攻擊者可以預先計算出「要花非常久才能找到一個點」的訊息（例如，一百萬則訊息中有 1 則會花 20 次嘗試），並大幅拖慢我們。

###### 簡化 SWU 映射

我們現在已採用一種較好的做法，它在[這篇論文](https://eprint.iacr.org/2019/403.pdf)中描述，並在 [RFC 9380](https://www.rfc-editor.org/rfc/rfc9380#name-bls12-381-g2)（雜湊至曲線的 IETF 標準）中定義。如同之前（但稍有不同，以確保輸出點的均勻分布），我們首先藉由把訊息模 $q$ 雜湊來造出一個域點（「擴展訊息」步驟）。

接著我們使用一個特殊的映射（SWU 映射），它保證把那個域點轉換成某條橢圓曲線上一個有效的點。基於技術上的原因，這_不_是曲線 $E'(F_{q^2})$，而是一條與它[同源](https://www.johndcook.com/blog/2019/04/21/what-is-an-isogeny/)（isogenous，即有相同數量的點）的曲線。然後我們使用另一個映射（3-同源）把這轉移到 $E'(F_{q^2})$ 上的一個點。最後我們使用[餘因子清除](#cofactor-clearing)，最終得到 $G_2$ 中的一個點。

你可以看看我[用 Java 對這的實作](https://github.com/PegaSysEng/artemis/pull/898)，它是基於 [Python 中的參考程式碼](https://github.com/algorand/bls_sigs_ref/tree/master/python-impl)。其構想是讓這種做法被普遍採用，以增進區塊鏈的互通性。

##### 餘因子清除

我們討論過乘以[餘因子](#cofactor)，作為把 $E$ 或 $E'$ 上一個任意的點，分別變成 $G_1$ 或 $G_2$ 中一個點的辦法。舉例來說，這在[雜湊至曲線](#hashing-to-the-curve)時很有用。

$G_2$ 餘因子[_非常龐大_](#subgroup-g_2)，所以乘以它很慢。然而，有[較快的方式](https://eprint.iacr.org/2017/419.pdf)可以用一個自同態（endomorphism，群到它自身的一個映射）把曲線點映射進 $G_2$。這出現在 [RFC 9380](https://www.rfc-editor.org/rfc/rfc9380#name-clearing-the-cofactor) 標準中。

我們所使用的這個自同態，直到不久前還受到[一項專利](https://patents.google.com/patent/US7110538B2/en)的約束，但截至 2020 年，這項專利已在世界各地到期。

作為這項專利到期前的一個變通辦法，標準建議不要乘以 $G_2$ 餘因子，而是乘以一個有效餘因子 $h_{eff}$（其值見 RFC 9380 的[第 8.8.2 節](https://www.rfc-editor.org/rfc/rfc9380#name-bls12-381-g2)），它給出與該自同態相同的結果。這個有效餘因子比 $G_2$ 餘因子_甚至更大_，但這個乘法可以用一條[加法鏈](https://github.com/PegaSysEng/teku/blob/55d04f87b422112312f79c1b4d662b3d58e3ca74/bls/src/main/java/tech/pegasys/teku/bls/impl/mikuli/hash2g2/Chains.java#L569)作為一種最佳化來實作。

既然這項專利已經到期，那個自同態就可以直接被當成有效餘因子乘法的替換而就地放入。

##### 擴張塔

還記得我們對[域擴張](#field-extensions)的討論嗎？實務上，與其直接實作一個龐大的 12 次擴張，從較小的擴張一層層建起來會更有效率：[一座擴張之塔](https://eprint.iacr.org/2009/556.pdf)。

對於 BLS12-381，$F_{q^{12}}$ 域被實作成一個二次（二次方）擴張，疊在一個三次（三次方）擴張之上，再疊在 $F_q$ 的一個二次擴張之上。

只要在每一階段，模約化多項式（我們的約化規則）在被擴張的域中是不可約的（無法被分解的），那麼這一切都行得通。

[具體而言](https://github.com/zcash/librustzcash/blob/6e0364cd42a2b3d2b958a54771ef51a8db79dd29/pairing/src/bls12_381/README.md)：

  1. $F_{q^2}$ 被構造為 $F_q(u) / (u^2 - \beta)$，其中 $\beta = -1$。
  2. $F_{q^6}$ 被構造為 $F_{q^2}(v) / (v^3 - \xi)$，其中 $\xi = u + 1$。
  3. $F_{q^{12}}$ 被構造為 $F_{q^6}(w) / (w^2 - \gamma)$，其中 $\gamma = v$。

以我們先前的解釋來詮釋這些：

  1. 我們把 $F_{q^2}$ 域的元素寫成 $u$ 的一次多項式，係數來自 $F_q$，並套用約化規則 $u^2 + 1 = 0$，它在 $F_q$ 中是不可約的。
      - $F_{q^2}$ 的一個元素看起來像 $a_0 + a_1u$，其中 $a_j \in F_q$。
  2. 我們把 $F_{q^6}$ 域的元素寫成 $v$ 的二次多項式，係數來自我們剛構造的 $F_{q^2}$ 域，並套用約化規則 $v^3 - (u + 1) = 0$，它在 $F_{q^2}$ 中是不可約的。
      - $F_{q^6}$ 的一個元素看起來像 $b_0 + b_1v + b_2v^2$，其中 $b_j \in F_{q^2}$。
  3. 我們把 $F_{q^{12}}$ 域的元素寫成 $w$ 的一次多項式，係數來自我們剛構造的 $F_{q^6}$ 域，並套用約化規則 $w^2 - v = 0$，它在 $F_{q^6}$ 中是不可約的。
      - $F_{q^{12}}$ 的一個元素看起來像 $c_0 + c_1w$，其中 $c_j \in F_{q^6}$。

這座塔式擴張可以取代直接擴張，作為配對的基礎，而若實作良好，在相乘 $F_{q^{12}}$ 點時能省下龐大的算術量。關於這些優點的完整討論，見[《給初學者的配對》](https://www.craigcostello.com.au/s/PairingsForBeginners.pdf)第 7.3 節。

##### 座標系統

求一個域元素的反元素（即除法）是一項昂貴的操作，所以橢圓曲線算術的實作試圖盡可能避免它。如果我們為表示我們的點選擇正確的座標系統，會有所幫助。

###### 仿射座標

仿射座標（Affine coordinate）是點的傳統表示，只用一對 $(x,y)$ 座標，其中 $x$ 與 $y$ 滿足曲線方程式。這是我們在儲存與傳輸點時通常所使用的。

然而，在實際處理點時，它並不總是最有效率的形式，而就我所知，還有另外兩種用於 BLS12-381 的方案。

基本構想是用概念性的分數來表示座標，減少所需的實際除法操作數量。要做到這一點，引入了第三個座標，我們用 $(X, Y, Z)$ 作為一個點的內部表示。如同我們熟悉的分數，同一個值有許多表示，全都對應到單一一個實際的值（$\frac{1}{2}$、$\frac{3}{6}$、$\frac{197}{394}$ 全都是同一個數）。

就我所知，用於 BLS12-381 的兩種系統是標準射影座標與 Jacobian 座標。

###### 標準射影座標

[標準射影座標](https://en.wikibooks.org/wiki/Cryptography/Prime_Curve/Standard_Projective_Coordinates)點 $(X, Y, Z)$ 表示仿射座標點 $(X/Z, Y/Z)$。

這些也被稱為齊次射影座標，因為曲線方程式採用了齊次形式 $Y^2Z=X^3+4Z^3$。在 $(X, Y, Z)$ 空間中，點變成通過原點的直線，而仿射點是該直線與平面 $Z=1$ 的交點。[《給初學者的配對》](https://www.craigcostello.com.au/s/PairingsForBeginners.pdf)中的圖 2.10 給了一個不錯的圖示。

標準射影座標被 [Apache Milagro](https://milagro.apache.org/) BLS12-381 函式庫所使用，也被 [noble-curves](https://github.com/paulmillr/noble-curves/tree/main) 實作所使用。

###### Jacobian 座標

一種不同的射影座標是 [Jacobian 座標](https://en.wikibooks.org/wiki/Cryptography/Prime_Curve/Jacobian_Coordinates)。在這個方案中，Jacobian 點 $(X, Y, Z)$ 表示仿射點 $(X/Z^2, Y/Z^3)$。曲線方程式變成 $Y^2=X^3+4Z^6$。

定時雜湊至曲線的[範例程式碼](https://github.com/algorand/bls_sigs_ref/tree/master/python-impl)使用 Jacobian 座標，[gnark-crypto](https://github.com/Consensys/gnark-crypto) 函式庫也是。

請注意，在這兩種方案中，匯入仿射點 $(x, y)$ 最容易的方式，都是把它映射到 $(x, y, 1)$。

#### BLS12-381 參考

##### 一般

| 參數 | &nbsp; | 方程式 | 值 | 備註 |
| ---- | - | ---- | ---------------- | ---- |
| 曲線參數| ${\tt x}$ | &nbsp; | `-0xd201000000010000` | |
| 域模數 | $q$ | $\frac{1}{3}{({\tt x}-1)}^2\allowbreak {({\tt x}^4-{\tt x}^2+1)}\allowbreak +{\tt x}$ | 十六進位：<span class="wrap">`0x1a0111ea397fe69a4b1ba7b6434bacd764774b84f38512bf6730d2a0f6b0f6241eabfffeb153ffffb9feffffffffaaab`</span><br/>十進位：<span class="wrap">4002409555221667393417789825735904156556882819939007885332058136124031650490837864442687629129015664037894272559787</span> | 381 位元，質數 |
| 子群大小：$\vert G_1\vert$、$\vert G_2\vert$、$\vert G_T\vert$ | $r$ | ${({\tt x}^4-{\tt x}^2+1)}$ | 十六進位：<span class="wrap">`0x73eda753299d7d483339d80809a1d80553bda402fffe5bfeffffffff00000001`</span><br/>十進位：<span class="wrap">52435875175126190479447740508185965837690552500527637822603658699938581184513</span> | 255 位元，質數 |

##### 曲線 E(F_q)

|||
| - | ----- |
| 方程式 | $y^2=x^3+4$ |
| 階 $\vert E(F_q)\vert$ | <span class="wrap">`0x1a0111ea397fe69a4b1ba7b6434bacd764774b84f38512bf6730d2a0f6b0f6241eabfffeb15400008c0000000000aaab`</span> |
| 階（十進位） | <span class="wrap">4002409555221667393417789825735904156556882819939007885332058136124031650490837864442687629129030796414117214202539</span> |
| 質因數分解 | 3 $\times$ 11$^2$ $\times$ 10177$^2$ $\times$ 859267$^2$ $\times$ 52437899$^2$ $\times$ $r$ |

群階各因數中（排除 $r$）的乘積，依定義就是「階為 $r$ 之子群」（此處即 $G_1$）的餘因子。

請觀察，曲線 $E$ 上點的數量、它的階 $|E(F_q)|$，（在某種意義上）非常接近域模數 $q$。這是 [Hasse 界](https://en.wikipedia.org/wiki/Hasse%27s_theorem_on_elliptic_curves)的結果。

##### 子群 G_1

|||
| - | ------- |
| 階 | $r$ |
| 生成元 | <span class="wrap">`(0x17f1d3a73197d7942695638c4fa9ac0fc3688c4f9774b905a14e3a3f171bac586c55e83ff97a1aeffb3af00adb22c6bb,`</span><br/><span class="wrap">`0x08b3f481e3aaa0f1a09e30ed741d8ae4fcf5e095d5d00af600db18cb2c04b3edd03cc744a2888ae40caa232946c5e7e1)`</span> |
| 餘因子 | <span class="wrap">`0x396c8c005555e1568c00aaab0000aaab`</span> |

$G_1$ 餘因子就是曲線階 $|E(F_q)|$ 的因數分解中、排除 $r$ 項之後的部分。

##### 曲線 E'(F_q^2)

|||
| - | ----- |
| 方程式 | $y^2=x^3+4(1+i)$ |
| 階 $\vert E'(F_{q^2})\vert$ | <span class="wrap">`0x2a437a4b8c35fc74bd278eaa22f25e9e2dc90e50e7046b466e59e49349e8bd050a62cfd16ddca6ef53149330978ef0137697386bf984315744a2d5eb3dd4d213f2484c55b94474ab096de2c62640b2643116b1e2788e6a8b2a9fffe1c7238e5`</span> |
| 階（十進位） | <span class="wrap">16019282247729705411943748644318972617695120099330552659862384536985976748491357143400656079302193429974954385540174732940659106207100323726025938325193045129788127168347624263893040187112659960846674086295148469572963088890738917</span> |
| 質因數分解 | 13$^2$ $\times$ 23$^2$ $\times$ 2713 $\times$ 11953 $\times$ 262069 $\times$ <span class="wrap">402096035359507321594726366720466575392706800671181159425656785868777272553337714697862511267018014931937703598282857976535744623203249</span> $\times$ $r$ |

曲線 $E'$ 的階 $|E'(F_{q^2})|$ 接近域模數的平方 $q^2$。

##### 子群 G_2

|||
| - | ------- |
| 階 | $r$ |
| 生成元 | <span class="wrap">`([0x024aa2b2f08f0a91260805272dc51051c6e47ad4fa403b02b4510b647ae3d1770bac0326a805bbefd48056c8c121bdb8, 0x13e02b6052719f607dacd3a088274f65596bd0d09920b61ab5da61bbdc7f5049334cf11213945d57e5ac7d055d042b7e],`</span><br/><span class="wrap">`[0x0ce5d527727d6e118cc9cdc6da2e351aadfd9baa8cbdd3a76d429a695160d12c923ac9cc3baca289e193548608b82801, 0x0606c4a02ea734cc32acd2b02bc28b99cb3e287e85a763af267492ab572e99ab3f370d275cec1da1aaa9075ff05f79be])`</span> |
| 餘因子 | <span class="wrap">`0x5d543a95414e7f1091d50792876a202cd91de4547085abaa68a205b2e5a7ddfa628f1cb4d9e82ef21537e293a6691ae1616ec6e786f0c70cf1c38e31c7238e5`</span> |

$G_2$ 餘因子就是曲線階 $|E'(F_{q^2})|$ 的因數分解中、排除 $r$ 項之後的部分。

#### 資源與延伸閱讀

上文中連結了_大量_的參考文獻，我不會在此重複許多。我只會挑出幾樣特別有用或有意思的東西。

有用的參考材料：

  - [最初的](https://web.archive.org/web/20190605200224/https://electriccoin.co/blog/new-snark-curve/) BLS12-381 公告
  - 對參數與序列化的[簡潔](https://github.com/zcash/librustzcash/blob/6e0364cd42a2b3d2b958a54771ef51a8db79dd29/pairing/src/bls12_381/README.md)描述
  - [IETF 標準](https://www.ietf.org/archive/id/draft-irtf-cfrg-pairing-friendly-curves-11.html#name-bls-curves-for-the-128-bit-)草案

一般而言，配對函式庫的實作往往高度最佳化且／或非常通用（支援許多曲線），這使得它們相當難以從中學習。Paul Miller 用 JavaScript/TypeScript 寫的 [Noble BLS12-381](https://github.com/paulmillr/noble-bls12-381) 函式庫，是較容易跟得上的之一。

[`blsh`](https://github.com/one-hundred-proof/blsh) REPL（BLST 函式庫的一個包裝）對於探索曲線本身極為出色。完整的功能見[文法](https://github.com/one-hundred-proof/blsh/blob/main/src/blsh.pest)——光是 `info` 命令就值得了。如果你願意，你可以[手動驗證](https://x.com/1_00_proof/status/1930535556049424817) BLS 簽章。

最後，幾篇隨意但有趣、有意思的讀物：

  - 這份關於 [Curve9769](https://github.com/pornin/curve9767/raw/master/doc/curve9767.pdf) 的白皮書與 BLS12-381 沒有直接關係，但是一篇文筆優美、對「設計與實作一條橢圓曲線（在這個例子中不是對配對友善的曲線）的甘苦」的精彩探索。
  - [《配對沒死，只是在休息》](https://ecc2017.cs.ru.nl/slides/ecc2017-aranha.pdf)。一份很棒的概觀簡報。有一些 BLS12-381 的東西。

### 隨機性 <!-- /part2/building_blocks/randomness/ -->

<div class="summary">

  - 以不可預測的方式指派信標鏈職責，是對某些攻擊的一項重要防禦。
  - 信標鏈維護一個 RANDAO 來累積隨機性。
  - 諸如提議區塊、委員會指派、同步委員會參與這類職責，都基於 RANDAO 來指派，並有一段有限的前瞻期。
  - 區塊提議者透過對紀元編號所做的 BLS 簽章，可被驗證地為 RANDAO 貢獻隨機性。
  - 驗證者能夠在小幅度上偏置 RANDAO，但這在實務上並非顯著的問題。

</div>

#### 引言

隨機性這個要素，是一個無須許可之區塊鏈協定的重要部分，無論就安全性或就公平性而言。

一個完全可預測的協定，在良性的環境中可能運作良好。但我們必須假設我們的協定會遭受攻擊，而可預測性給了攻擊者機會——正如犯罪驚悚片裡的壞人常常利用受害者可預測的作息。

一個事先知道哪些驗證者會以不同角色活躍的攻擊者，在發動攻擊上有著一個重要的立足點。例如，去選擇性地對未來的提議者發動阻斷服務攻擊、去賄賂某個特定委員會的成員、去為自己登錄特別有利的驗證者編號使他們得以接管某個未來的委員會，或單純去審查交易。[^fn-initial-shuffling]

[^fn-initial-shuffling]: 關於「不可預測性不足之危險」的一個可愛的例證，見規格儲存庫上的[議題 1446](https://github.com/ethereum/consensus-specs/issues/1446)：操縱存款合約以取得早期的多數。要感謝 [Paul Hauner](https://web.archive.org/web/20230630135550/https://nitter.it/paulhauner/status/1509677010448121856)。

引用 Brown-Cohen 等人的一篇[論文](https://arxiv.org/abs/1809.06528)[^fn-unpredictability-paper]：

> 直觀地說，協定具有不可預測性是好事，意思是礦工直到一個區塊應被挖出之前不久，才得知他們有資格挖那個區塊。許多攻擊，例如雙重花費或自私挖礦，如果礦工事先知道他們何時變得有資格挖礦，就可能變得有利可圖得多。

[^fn-unpredictability-paper]: [《最長鏈權益證明協定的形式化障礙》](https://arxiv.org/abs/1809.06528)，Jonah Brown-Cohen、Arvind Narayanan、Christos-Alexandros Psomas、S. Matthew Weinberg（2018）。引文出自第 3.1 節。

源自隨機性的不可預測性，是對抗許多攻擊的一道絕佳的第一道防線。

工作量證明中的不可預測性，來自用以挖區塊的過程。一個區塊只有在它滿足[某個條件](https://ethereum.org/en/developers/docs/consensus-mechanisms/pow/)時才有效，而滿足那個條件的唯一辦法是反覆試誤。礦工做出一個隨機的猜測、測試它，如果不對就再試——這就是工作量證明中的「工作」。只有當猜測正確時，區塊才有效，礦工才得以延伸該鏈。在我撰寫本文時，以太坊 PoW 鏈的難度約為 12.5 Peta 雜湊。那意味著挖出一個以太坊區塊平均需要 $1.25 \times 10^{16}$ 次猜測。這類似於「擲 21 顆骰子、直到它們在同一次擲出時全部都是六」的機率。它出奇地不可能，然而以太坊網路上某處每隔約 13 秒就有人設法做到。由於這個過程是均勻的——沒有人比別人更擅長猜測（擲骰子）——它提供了公平性。每一個每秒 Giga 雜湊都等同於其他每一個每秒 Giga 雜湊（雖然工作量證明中還有其他不公平的來源）。而由於猜測是隨機的，它提供了不可預測性，這緩和了上述的攻擊。

以太坊權益證明協定中的隨機性[^fn-pseudo-random]，被用來為「區塊提議者的選擇」、以及「為區塊做出證明並簽署同步資料之委員會的成員資格」帶來不可預測性。

[^fn-pseudo-random]: 在本節中，我不會去區分隨機性與偽隨機性的細微之處。我們實際上是用偽隨機性，並以（假定的）真正隨機性為種子。事情必定如此，因為要對真正的隨機性達成共識是不可能的。然而，我通篇就把它稱為「隨機性」。

在本節中，我們會看隨機性被引入信標鏈的方式、它被使用的一些方式，最後再看當前方案的一些問題。

#### RANDAO

信標鏈的設計一直使用一個 RANDAO[^fn-randao-naming] 機制來提供它的協定內隨機性。一個 RANDAO 就只是一個累加器，它增量地從貢獻者那裡蒐集隨機性。所以，每處理一個區塊，提議者就把一份隨機的貢獻混入既有的 RANDAO 值。

[^fn-randao-naming]: 我不確定 RANDAO 這個名稱從何而來，但它被塑造成一個經營隨機性的 DAO（去中心化自治組織）。2016 年以太坊的 [randao 專案](https://github.com/randao/randao)可能是這個名稱的起源。

把這稍微展開一點，信標鏈維護一個 RANDAO 值。鏈中所納入的每個區塊，都含有一個由提議它的驗證者所提供的可驗證隨機值，即它的 [`randao_reveal`](/part3/containers/blocks/#beaconblockbody)。每處理一個區塊，信標鏈的 RANDAO 值就與該區塊的 `randao_reveal` 混合。於是，隨著時間推移，RANDAO 累積了來自所有區塊提議者的隨機性。

如果 $R_n$ 是 $n$ 次貢獻之後的 RANDAO 值，而 $r_n$ 是第 $n$ 個 `randao_reveal`，那麼下式成立。此處我們用 `xor` 函式 $\oplus$ 來混入新的貢獻。替代方案可能是用求和或雜湊，但 `xor` 簡單，並有著有用的性質。

$$
R_n = r_n \oplus R_{n-1}
$$

我們可以把 RANDAO 想成像一副在桌邊傳來傳去的撲克牌，每個人輪流洗它：這副牌被反覆地重新隨機化。即使其中一個貢獻者的隨機性很弱，累積的結果仍有著高水準的熵。

<a id="img_randomness_shuffle"></a>
<figure class="diagram" style="width:80%">

![一張示意圖，說明反覆地洗一副撲克牌。](images/diagrams/randomness-shuffle.svg)

<figcaption>

我們可以把 RANDAO 想像成一副撲克牌，隨著每個參與者輪流洗牌，它隨時間累積隨機性。

</figcaption>
</figure>

當前與過去的 RANDAO 值，儲存在[信標狀態](/part3/containers/state/#beaconstate)的 `randao_mixes` 欄位中。信標鏈每處理一個區塊，當前值就由 [`process_randao`](/part3/transition/block/#def_process_randao) 更新。如果一個時段中沒有區塊，那麼 RANDAO 就不被更新。除了 RANDAO 的當前值之外，[`EPOCHS_PER_HISTORICAL_VECTOR`](/part3/config/preset/#epochs_per_historical_vector)（減一）個「過去各紀元結束時的 RANDAO 值」也被儲存在狀態中。這些可以用來重新計算過去的委員會指派，使得歷史的證明即使在數個月後也能被罰沒。

#### 隨機性的來源

每個[區塊](/part3/containers/blocks/#beaconblockbody)都包含一個 `randao_reveal` 欄位，它是該區塊提議者要被混入 RANDAO 的貢獻。

這份貢獻需要滿足兩個性質：它應當無法被任何其他節點預測，卻應當能被所有節點驗證。

「可驗證」意味著：RANDAO 貢獻值雖然是隨機的（讀作偽隨機的），卻不能是任意的。提議者不能隨意挑選它的貢獻，否則它就會直接挑一個給它自己某種優勢的值。在任何給定的區塊中，提議者能做出的有效貢獻必須是單一一個，而所有其他節點都必須能夠驗證那份貢獻。

##### 舊的：雜湊洋蔥

對可驗證隨機性的[早期構想](https://github.com/ethereum/consensus-specs/pull/33/files#diff-d74f72ec8cd401e342e5e5f6939647b860dd98518a6618d3a7f5256edbaf4b69R480)，是讓每個驗證者預先承諾一個「雜湊洋蔥」（hash onion）。在加入信標鏈之前，一個驗證者會產生一個隨機數。在登錄它的初始存款時，該驗證者會把「反覆地對那個數做密碼學雜湊大量（數千）次」的結果作為一個承諾納入。然後在提議一個區塊時，`randao_reveal` 就會是那個承諾的原像（pre-image）：一層會被「從洋蔥上剝下來」。由於密碼學雜湊不可逆，只有提議者能計算出這個值，但每個人都能輕易驗證它。然後這個揭露值就被儲存為新的承諾，依此類推。

這個方案可行，但有著一些複雜性與邊角案例——例如，如果一個區塊被孤立，那麼（除信標鏈之外的）每個人現在都能看到提議者的揭露值——這些使它在實務上實作起來笨重。

##### 新的：BLS 簽章

當我們轉而在協定中使用 [BLS 簽章](/part2/building_blocks/signatures/)時，雜湊洋蔥的一個替代方案就變得可用了。有了 BLS 方案，每個驗證者都已經有一個嚴密守護的隨機值：它用來簽署區塊與證明的祕密金鑰。就所有人所知，所產生的簽章是均勻隨機的。

對一則經一致同意之訊息的簽章，很好地滿足了我們對 RANDAO 貢獻所期望的兩個性質。它對其他驗證者是不可預測的，因為它們不知道提議者的私鑰，但它可被輕易驗證，因為所有驗證者都知道提議者的公鑰。

為 RANDAO 重複使用 BLS 金鑰基礎設施，其優雅與簡潔，使它相對於原本的雜湊洋蔥設計是一項相當大的改進。

使用 BLS 簽章還有一個或許不明顯的不錯的好處。簽章的[聚合性質](/part2/building_blocks/signatures/#aggregation)允許這份貢獻透過一個多方計算來導出。也就是說，來自多個驗證者的簽章可以被結合成一份門檻簽章，使得它們能實際上作為單一一個驗證者行動。我們並未在 Eth2 核心協定內使用這個性質，但它使[分散式驗證者技術](https://docs.obol.tech/docs/int/key-concepts)成為可能，而用舊的雜湊洋蔥做法那會非常困難。

[TODO: add link to DVT when done]::

基於所有這些原因，[我們現在使用](https://github.com/ethereum/consensus-specs/pull/483)一份 BLS 簽章作為對 RANDAO 的熵貢獻，也就是 `randao_reveal`。

##### 熵從何而來？

顯然，以太坊 2 協定中隨機性的主要來源，是驗證者的祕密金鑰。如果每把驗證者金鑰都是均勻隨機且獨立地產生的，那麼每一把都為整體的池貢獻 256 位元的熵。然而，金鑰有時並非獨立產生[^fn-vasily]。[EIP-2333](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-2333.md) 提供了一種從單一一個熵種子衍生多把驗證者金鑰的方式，而大型質押者很可能這麼做了。因此，來自 $N$ 把驗證者金鑰的總熵會少於 $N \times 256$ 位元，但我們不知道少多少。

[^fn-vasily]: 我感謝 Vasiliy Shapovalov 提醒我這一點。

RANDAO 的一些其他的熵來源在 [EIP-4399](https://eips.ethereum.org/EIPS/eip-4399) 中有所提及。

  - 錯失或被孤立的區塊提議直接影響 RANDAO 的輸出。網路條件、節點故障、或維護停機，都可能導致帶有某種程度隨機性的錯失區塊提議。
  - 一個紀元中活躍驗證者的總數，影響提議者的選擇，這又進而影響對 RANDAO 的參與。因此，存款與退出（自願與被迫兩者）都貢獻熵。
  - 一個驗證者的[有效餘額](/part2/incentives/balances/)影響它被選來提議一個區塊的可能性。因此，有效餘額的變化（或許由於一個或多個驗證者離線一段時間）增添熵。

#### 更新 RANDAO

當一個驗證者提議[一個區塊](/part3/containers/blocks/#beaconblockbody)時，它包含一個 `randao_reveal` 欄位，它有著 `BLSSignature` 型別。這是提議者用它一般的簽章祕密金鑰，對[紀元編號](https://github.com/ethereum/consensus-specs/pull/498)所做的簽章。

`randao_reveal` 由提議者如下[計算](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#randao-reveal)，`privkey` 輸入即該驗證者的隨機祕密金鑰。

```python
def get_epoch_signature(state: BeaconState, block: BeaconBlock, privkey: int) -> BLSSignature:
    domain = get_domain(state, DOMAIN_RANDAO, compute_epoch_at_slot(block.slot))
    signing_root = compute_signing_root(compute_epoch_at_slot(block.slot), domain)
    return bls.Sign(privkey, signing_root)
```

When a block is processed, the `randao_reveal` is mixed into the RANDAO [like this](/part3/transition/block/#def_process_randao):

```python
def process_randao(state: BeaconState, body: BeaconBlockBody) -> None:
    epoch = get_current_epoch(state)
    # Verify RANDAO reveal
    proposer = state.validators[get_beacon_proposer_index(state)]
    signing_root = compute_signing_root(epoch, get_domain(state, DOMAIN_RANDAO))
    assert bls.Verify(proposer.pubkey, signing_root, body.randao_reveal)
    # Mix in RANDAO reveal
    mix = xor(get_randao_mix(state, epoch), hash(body.randao_reveal))
    state.randao_mixes[epoch % EPOCHS_PER_HISTORICAL_VECTOR] = mix
```

在 `randao_reveal` 簽章的處理中，有兩件事在進行。

第一，在被混入之前，該簽章會用提議者的公鑰被驗證。這意味著提議者對於它向 RANDAO 貢獻什麼幾乎沒有選擇：它要嘛貢獻單一一個可驗證的值——對紀元編號的正確簽章——要嘛扣住它的區塊不發、什麼都不貢獻。（等價地說，一個帶有不正確揭露值的區塊是無效的。）

第二，該簽章的雜湊值用一個 `xor` 操作被混入信標狀態的 RANDAO。我們套用雜湊操作，是為了把 RANDAO 累加器的長度，從約 762 位元——一份壓縮 BLS 簽章的長度，一個處理起來不方便的位元數——減為 256 位元。雜湊函式輸出的均勻性，相較於 BLS 簽章的也較為被確立。

<a id="img_randomness_reveal"></a>
<figure class="diagram" style="width:80%">

![一張示意圖，說明更新 RANDAO。](images/diagrams/randomness-reveal.svg)

<figcaption>

當 RANDAO 被洗牌時，真正發生的是什麼。對紀元編號的簽章就是提議者納入它區塊的 RANDAO 揭露值。這被雜湊，然後用一個 `xor` 操作混入既有的 RANDAO。

</figcaption>
</figure>

<a id="randao_xor"></a>
我們本可藉由把揭露值直接與 RANDAO 累加器一起雜湊來混入它，然而我們選擇透過一個 `xor` 操作來混入它。「用紀元編號作為被簽署的量」與「用 `xor` 來混入它」這兩者的結合，導致 RANDAO 的抗攻擊性有一個微妙、儘管微小的[改進](https://github.com/ethereum/consensus-specs/pull/496#issuecomment-457449830)。Justin Drake 在他的[筆記](https://notes.ethereum.org/@JustinDrake/rkPjB1_xr)中解釋：

> 在 `process_randao` 中使用 `xor`，比使用 `hash`（稍微）更安全。為了說明原因，想像一個攻擊者能在當前紀元研磨隨機性，使得他的兩個驗證者是最後的提議者，並在所得的兩種下一紀元的取樣中以不同的順序出現。`xor` 的交換律使那兩種取樣等價，從而相對於 `hash`（它不可交換）減少了攻擊者對下一紀元的研磨機會。這項嚴格的安全性改進，可能簡化 RANDAO 安全性形式化下界的推導。

我們會[很快](#randao-biasability)看到，掌控一個紀元的最後幾個時段對攻擊者可能有利。Justin 的[要點](https://github.com/ethereum/consensus-specs/pull/496#issuecomment-457546253)是：在當前的方案下，就 `randao_reveal` 而言，攻擊者在一個紀元的最後兩個時段擁有驗證者 $V_0, V_1$，等價於它擁有 $V_1, V_0$。當涉及到影響 RANDAO 時，這微幅地減少了攻擊者的選擇。如果我們用 `hash` 而非 `xor`，或如果我們對時段編號、而非紀元編號簽章，這些排序就會彼此導致不同的結果，給攻擊者更多的選擇、因而更多的權力。

#### 前瞻

我們以對不可預測性的討論開始本節。理想情況下，在任何區塊提議者或委員會成員變得活躍之前的那一刻，都不應能預測他們的職責。然而，實務上，提議者與委員會成員需要對他們的職責有一點提前的通知，以讓他們得以加入正確的 p2p 網路子網、並做他們需要做的任何其他準備。

紀元 $N$ 結束時的 RANDAO 種子，被用來計算整個紀元 $N+2$ 的驗證者職責。這個間隔透過 [`get_seed()`](/part3/helper/accessors/#def_get_seed) 函式由 [`MIN_SEED_LOOKAHEAD`](/part3/config/preset/#min_seed_lookahead) 所控制。因此，驗證者至少有一整個紀元來為任何職責做準備，但不超過兩個。

那麼，在正常的情況下，攻擊者無法提前超過兩個紀元預測職責指派。然而，如果攻擊者擁有一大部分的質押，或者例如能夠對區塊提議者發動一陣子的 DoS 攻擊，那麼攻擊者就有可能比 `MIN_SEED_LOOKAHEAD` 通常所容許的更往前地預測 RANDAO 的輸出。攻擊者接著就可能利用這份先見之明，策略性地退出驗證者或做出存款[^fn-instant-activations]，以取得對一個委員會、或大量區塊提議時段的掌控。

[^fn-instant-activations]: 在當前的協定中，由於 [`ETH1_FOLLOW_DISTANCE`](/part3/config/configuration/#eth1_follow_distance) 與 [`EPOCHS_PER_ETH1_VOTING_PERIOD`](/part3/config/preset/#epochs_per_eth1_voting_period)，你會需要往前預測約 16 小時的 RANDAO，存款才會對操縱它有用。然而，在合併之後的某個時點，可能就能或多或少立即地迎入存款。

這當然不是一個容易的攻擊。儘管如此，它容易防禦，所以我們不妨就這麼做。

為了防止這一點，我們假設一個攻擊者可能達到的最大可行前瞻 [`MAX_SEED_LOOKAHEAD`](/part3/config/preset/#max_seed_lookahead)，並把所有的啟用與退出都延遲這麼多，這讓新的隨機性有時間透過誠實驗證者的區塊提議進來，使得進入或退出之驗證者的任何操縱都變得無關緊要。在 `MAX_SEED_LOOKAHEAD` 設為 4 的情況下，如果只有 10% 的驗證者在線且誠實，那麼攻擊者能成功預測超過（`MAX_SEED_LOOKAHEAD` ` - ` `MIN_SEED_LOOKAHEAD`）= 3 個紀元之種子的機會是 $0.9^{3\times 32}$，那約為兩萬五千分之一。

<a id="img_randomness_lookahead"></a>
<figure class="diagram" style="width:90%">

![一張示意圖，顯示最小與最大前瞻。](images/diagrams/randomness-lookahead.svg)

<figcaption>

紀元 $N$ 結束時的 RANDAO 值，被用來設定紀元 $N+2$ 的職責，這由 `MIN_SEED_LOOKAHEAD` 所控制。一個在紀元 $N+1$ 退出的驗證者，至少維持活躍到紀元 $N+5$ 結束（視退出佇列而定）。這由 `MAX_SEED_LOOKAHEAD` 所控制。

</figcaption>
</figure>

##### 單一祕密領導人選舉

以目前的實作而言，最小與最大前瞻兩者都有點工程拼湊的味道。在一個完美的設計中，只有區塊提議者本身會提前知道它已被選來在那個時段提議。一旦它的區塊被揭露，網路的其餘部分就能驗證：是的，這的確是那個被選出的提議者。這個特性稱為[單一祕密領導人選舉](https://eprint.iacr.org/2020/025)（Single Secret Leader Election）。我們在以太坊協定中還沒有它，我會在別處寫到它。在此期間，朝著使它實際可行已有一些[不錯的進展](https://ethresear.ch/t/simplified-ssle/12315?u=benjaminion)。

[TODO: link to SSLE when done]::

#### RANDAO 的可偏置性

一個紀元的 RANDAO 值在前一個紀元結束時被設定，而整個紀元的職責指派（提議與委員會成員資格）都取決於那個值。（實際上——由於 [`MIN_SEED_LOOKAHEAD`](/part3/config/preset/#min_seed_lookahead)——取決於倒數第二個紀元結束時的 RANDAO 值，但在接下來的內容中我們會略過這一點。）

<a id="img_randomness_assignments"></a>
<figure class="diagram" style="width:80%">

![一張示意圖，說明基於 RANDAO 計算職責。](images/diagrams/randomness-assignments.svg)

<figcaption>

驗證者未來的職責指派——區塊提議者、委員會成員、同步委員會職責——是基於每個紀元結束時 RANDAO 的狀態而計算的。

</figcaption>
</figure>

因此，當一個驗證者剛好被指派在一個紀元的最後一個時段提議一個區塊時，它就獲得了對下一個紀元之指派的少量掌控。這是因為它可以選擇揭露它的區塊（這會混入它的 RANDAO 揭露值），或它可以（以一個代價）選擇扣住它的區塊、保留既有的 RANDAO 值，因為它知道在職責被計算之前不會有後續的 RANDAO 變動。如此一來，一個驗證者就能對下一個紀元的提議者與委員會指派施加一點影響。由於該驗證者有兩種結果可選，這被稱為對 RANDAO 「一位元的影響」。

<a id="img_randomness_biasing"></a>
<figure class="diagram" style="width:80%">

![一張示意圖，說明偏置 RANDAO。](images/diagrams/randomness-biasing.svg)

<figcaption>

一個紀元中最後的提議者有一個選擇。它可以照常提議它的區塊，更新 RANDAO，得出一組職責指派 $A$。或它可以扣住它的區塊，讓 RANDAO 維持原狀，得出一組職責指派 $B$。如果結果 $B$ 給該驗證者的擁有者足夠的優勢，足以補償錯失一次提議，那麼這就是一個「作弊」的機會。

</figcaption>
</figure>

如果攻擊者在一個紀元的結尾得到一連串的提議，那麼它就有更多的權力。在一個紀元的結尾擁有 $k$ 個連續的提議，給了攻擊者 $2^k$ 種選擇，用以決定那個「將被用來計算未來驗證者職責」的 RANDAO 的最終值。在這個情境中，攻擊者對 RANDAO 有「$k$ 位元的影響」。

#### 可偏置性分析

本節完全是選讀的。我有點被數學沖昏了頭；直接跳到[下一節](#verifiable-delay-functions)是沒問題的。這些範例僅意在作為例證。它們不是學術研究，而且有許多未盡之處。一些更新、更嚴謹的討論的連結，見下面的[延伸閱讀](#see-also)一節。

為了讓對 RANDAO 可偏置性的討論更具體，我會用幾個範例試著量化它在實務上意味著什麼。在每個範例中，「作弊」或「攻擊」的實體都掌控著質押的某個比例 $r$，無論是直接掌控還是透過某種勾結，而我們會假設其餘的驗證者全都獨立且正確地行事。我們當然也會假設個別的 `randao_reveal` 是均勻隨機的。

在第一個範例中，我會試圖藉由永久取得一個紀元最後幾個時段的提議，來取得對 RANDAO 的掌控。在第二個範例中，我會試圖在我得到機會時藉由偏置 RANDAO，來改善我的預期區塊提議數。在這兩種情況中，我都會在計算出最佳結果之後，選擇性地做出與扣住提議：這是一個「研磨」（grinding）RANDAO 的過程。

##### RANDAO 接管

如果我掌控總質押的一個比例 $r$，我藉由操縱 RANDAO 能把我對協定的影響力提升多少？

影響 RANDAO 的能力，取決於掌控一個紀元結尾一連串連續的區塊提議。我們會把這個性質稱為「擁有一條尾巴」，而這條尾巴會有一個長度 $k$，從 0 到最大的 32（一整個紀元）。

我們的問題可以這樣框定：如果我在一個紀元中有一條長度為 $k$ 的尾巴，我在下一個紀元的預期尾巴長度是多少？有了一條長度為 $k$ 的尾巴，我就有 $2^k$ 個機會藉由選擇性地做出或扣住區塊提議來重新洗牌 RANDAO。我能不能研磨過這些可能性，以增加我下一次的尾巴長度，並最終接管整個紀元？

在沒有任何操縱的情況下，我在任何給定紀元中擁有恰好長度為 $k$ 之尾巴的機率，對 $k < 32$ 而言是 $(1-r)r^k$，而當 $k = 32$ 時是 $r^{32}$。這是「我在尾巴位置做出 $k$ 個提議、且其前面有一個並非由我做出的提議」的機會。

$$
q_k =
\begin{cases}
(1-r)r^k & 0 \leq k < 32 \\
r^k      & k = 32
\end{cases}
$$

所以對於一個掌控比例 $r$ 質押的人，預期尾巴長度是，

$$
E(r) = \sum_{n=1}^{32} n q_n = \sum_{n=1}^{31} n (1-r) r^n + 32 r^{32}
$$

<a id="img_randao_tail"></a>
<figure class="chart" style="width:100%">

![預期 RANDAO 尾巴的圖。](images/charts/randao_tail.svg)

<figcaption>

底軸是 $r$，側軸是我假設沒有 RANDAO 操縱時的預期提議尾巴長度 $E(r)$。

</figcaption>
</figure>

現在我們會計算 $E^{(k)}(r)$，即我藉由用我先前長度為 $k$ 的尾巴來研磨各選項，能在下一個紀元達到的預期尾巴長度。

考慮我在某個紀元有一條長度為 $k = 1$ 之尾巴的情況。這給我兩個選項：我可以發布我的 RANDAO 貢獻，或我可以扣住我的 RANDAO 貢獻（藉由扣住我的區塊）。我的策略是選出我能透過這兩個選項之任一個獲得的、下一個紀元最長的尾巴。

由於擁有一條長度為 1 的尾巴，而獲得恰好長度為 $j$ 之尾巴的機率 $p^{(1)}_j$ 是，

$$
p^{(1)}_j =  2\sum_{i=0}^{j-1}q_{j}q_{i} + q_{j}q_{j} = q_j \left( 2\sum_{i=0}^{j-1}q_i + q_j \right)
$$

我們可以這樣想。在 $k = 1$ 時我們得到兩次嘗試，因此 $q$ 在每個乘積中出現兩次。要計算 $p^{(1)}_j$，我們需要對所有組合求和：「獲得恰好長度為 $j$ 之尾巴的機率」（即 $q_j$）乘以「獲得 $j$ 或更短之尾巴的機率」（也就是沒獲得比 $j$ 更長的尾巴，否則我們本會選那個長度而非 $j$）。

從視覺上看，計算 $p^{(1)}_2$ 看起來就像下一張圖陰影區域中各值的總和。

<a id="img_randomness_tail_probabilities"></a>
<figure class="diagram" style="width:40%">

![尾巴長度機率的矩陣。](images/diagrams/randomness-tail_probabilities.svg)

<figcaption>

我們以兩次嘗試獲得恰好為二之最大尾巴長度的機率，是各陰影區域中各項的總和。儘管有重疊，每一項都只被計入一次。

</figcaption>
</figure>

這個尾巴長度 $k = 1$ 的範例得出一個二維的正方形，因為我們有兩種可能性可試。計算 $p^{(1)}_j$ 的一種方式，是取「邊長為 $j + 1$ 之正方形中所有乘積的總和」與「邊長為 $j$ 之正方形中所有乘積的總和」之差。

像這樣思考，有助於我們推廣到 $k > 1$ 的情況。在那些情況中，我們處理的是一個維度為 $2^k$ 的超立方體；每個元素都是 $2^k$ 個 $q$ 值的乘積。要計算 $p^{(k)}_j$，我們可以找出「邊長為 $j + 1$ 之 $2^k$ 維立方體中所有乘積的總和」與「邊長為 $j$ 之 $2^k$ 維立方體中所有乘積的總和」之差。這寫下來很繁瑣，而且即使對相當小的 $k$ 也涉及令人瞠目結舌的計算量，但有效率地計算它的一種方式見我的[範例程式碼](#tail-extension-code)。

現在，終於，給定我們在這個紀元有一條長度為 $k$ 的尾巴，我們可以計算下一個紀元的預期尾巴長度。

$$
E^{(k)}(r) = \sum_{n=1}^{32} n p^{(k)}_n
$$

把這對各種 $k$ 值畫成圖，我們得到下圖。請注意，那條實線、$k = 0$ 的線，與上方的 $E(r)$ 相同——也就是沒有操縱時的預期尾巴。也就是說，如你所料，$E^{(0)}(r) = E(r)$。

<a id="img_randao_extend_0"></a>
<figure class="chart" style="width:100%">

![預期 RANDAO 尾巴的圖。](images/charts/randao_extend_0.svg)

<figcaption>

底軸是 $r$，側軸是給定我可以擺弄的各種尾巴長度 $k$ 值時，我後續的預期提議尾巴長度 $E^{(k)}(r)$。請注意，$E^{(0)}(r) = E(r)$，即上方圖中的那條線。

</figcaption>
</figure>

我們看到，如果我在一個紀元中最終得到任何長度的尾巴，相較於不研磨 RANDAO，我總是可以研磨我的 RANDAO 貢獻，以改善我在下一個紀元的預期尾巴長度。而且我的尾巴越長，我能預期在下一個紀元有的尾巴就越好。這些結果並不令人意外。

重要的問題是：在什麼情況下，我能利用這項能力來無限期地增加我的預期尾巴長度，使我最終得以取得對 RANDAO 的完全掌控？

為了探究這一點，考慮下面這張圖。此處，對每一條 $k$ 線，我們畫的是 $E^{(k)}(r) - k$。這讓我們能看出我們在下一個紀元的預期尾巴是大於還是小於我們當前的尾巴。如果 $E^{(k)}(r) - k$ 是負的，那麼我就可以預期在下一個紀元的提議數比這一個少。

<a id="img_randao_extend_1"></a>
<figure class="chart" style="width:100%">

![RANDAO 尾巴預期變化的圖。](images/charts/randao_extend_1.svg)

<figcaption>

底軸是 $r$，側軸是對各種 $k$ 值而言，我後續的預期提議尾巴長度減去我當前的尾巴長度 $E^{(k)}(r) - k$。

</figcaption>
</figure>

我們可以看到，對於小於約 0.5 的 $r$，尤其隨著 $k$ 增長，儘管我們盡了最大的 RANDAO 研磨努力，我們仍預期我們的尾巴長度會縮短而非增長。然而，對於大於 0.5 的 $r$，無論我們以什麼尾巴長度起步，我們都預期我們的尾巴長度會因為我們的研磨而增長。

為求完整，我們不該只看期望值，也該看機率。下面這張圖顯示「如果我有一條長度為 $k$ 的尾巴，那麼我在下一個紀元會有一條長度小於 $k$ 之尾巴」的機率。隨著 $k$ 增加，你可以看到一個階梯函數正在形成：對於小於約 50% 的質押比例，儘管我盡最大努力想讓尾巴增長，「我的尾巴從一個紀元到下一個紀元會縮短」實際上變成了確定的事；反過來，對於大於略高於 50% 的質押比例，「我能維持或增長我的區塊提議尾巴」實際上變成了確定的事。

<a id="img_randao_extend_2"></a>
<figure class="chart" style="width:100%">

![我的尾巴會縮短之機率的圖。](images/charts/randao_extend_2.svg)

<figcaption>

底軸是 $r$，側軸是對各種尾巴長度 $k$ 值而言，「我在下一個紀元的最佳尾巴長度小於我當前的尾巴長度」的機率。

</figcaption>
</figure>

###### RANDAO 接管的討論

我們能從這得出什麼結論？如果我掌控的質押少於約一半，那麼我就無法指望能爬上「尾巴長度遞增」的階梯：我所擁有的尾巴長度極有可能會縮短而非增加。反之，如果我擁有超過一半的質押，我的預期尾巴長度每個紀元都會增加，所以我很可能最終得以完全接管 RANDAO。在 $r$ 夠高的情況下，我研磨 RANDAO 所擁有的 $2^k$ 個選項，壓過了損失尾巴提議的機率。對於大的 $k$ 值，要研磨過所有這些選項並不實際可行。然而，我們只需抵達一個好的組合就能成功，所以我們可能不需要做完整的計算。

好消息是，如果攻擊者掌控超過一半的質押，他們有更有意思的攻擊可用，例如接管 LMD 分叉選擇規則。所以我們在協定中一般假設任何攻擊者擁有的質押少於一半，在那種情況下，RANDAO 接管攻擊看來不可行。

作為最後一個觀察，我們忽略了「尾巴提議中有兩個或更多來自同一個驗證者」的情況。如[上文](#randao_xor)所討論，這些提議每一個都會得出相同的 RANDAO 貢獻，並減少我的研磨選項。然而，在系統中有大量驗證者的情況下，這是一個合理的近似。

<a id="tail-extension-code"></a>
<details>
<summary>計算作弊時尾巴長度的程式碼</summary>

這是產生上方圖表資料的程式碼。尾巴長度上至 $k = 12$。儘管增加它，雖然它會變得相當耗計算。十二足以看出大致的圖像了。

```python
def prob_tail_eq(r, k):
    return (1 - r) * r**k if k < N else r**k

# The sum of the products of all the q_i in the hypercube of side j and dim k
# Recursive is cooler, but written iteratively so that python doesn't run out of stack
def hyper(q, j, k):
    h = 1
    for n in range(1, k + 1):
        h = sum([q[i] * h for i in range(j)])
    return h

# Smoke test.
assert abs(hyper([0.9, 0.09, 0.009, 0.0009, 0.00009, 0.00001], 6, 32) - 1.0) < 1e-12

N    = 32 # The number of slots per epoch
KMAX = 12 # The maximum length of prior tail we will consider
NINT = 20 # The number of intervals of r between 0 and 1 to generate

expected = [[] for i in range(KMAX + 1)]
prob_dec = [[] for i in range(KMAX + 1)]
rs = [i / NINT for i in range(1, NINT)]
for r in rs:
    # q[j] = the probability of having a tail of exactly j in one attempt
    q = [prob_tail_eq(r, j) for j in range(N + 1)]
    for k in range(KMAX + 1):
        h = [hyper(q, j, 2**k) for j in range(N + 2)]
        # p[j] = the probability that with a tail of k I can achieve a tail of j in the next epoch
        p = [h[j + 1] - h[j] for j in range(N + 1)]
        # The expected length of tail in the next epoch given r and k
        expected[k].append(sum([j * p[j] for j in range(N + 1)]))
        # The probability of a decrease in tail length to < k
        prob_dec[k].append(h[k])
print(rs)
print(expected)
print(prob_dec)
```

</details>

##### 區塊提議的加成

對於第二個工作範例，我會試圖改善我的驗證者整體所得到的提議數量。與第一個範例不同，我不會試圖不計代價地最大化我的優勢。我只會在「能不付出任何淨成本」的情況下操縱 RANDAO。

再一次，我掌控比例 $r$ 的質押。我只會考慮長度為零或長度為一的尾巴——超出這個就變得相當混亂，而我的直覺是，對於小於約一半的 $r$ 值，它造成的差別不大。

設 $q_j$ 為「我在一個紀元中、沒有任何 RANDAO 操縱的情況下，得到恰好 $j$ 個提議」的機率（與第一個範例中的 $q$ 不同，但相關）：

$$
q_j = r^j{(1-r)}^{32-j}{32 \choose j}
$$

我誠實行事時每個紀元的預期提議數計算起來很簡單，

$$
E = \sum_{n=1}^{32} n q_n = 32 r
$$

現在，每當我擁有一個紀元的最後一個時段時，我都會試圖偏置 RANDAO 來給自己更多提議，而這會以機率 $r$ 發生。這麼做時，我在下一個紀元的預期提議數如下。那個撇號是為了顯示我正試圖最大化我的優勢（作弊），而那個下標是為了顯示我們是往前看一個紀元。

$$
E'_1 = \sum_{n=1}^{32} n ((1 - r) q_n + r p_n)
$$

把這展開，加法中的第一項是「我在前一個紀元沒有最後一個時段（所以我無法做任何偏置）」的機率 $1 - r$，乘以「在一個紀元中有 $n$ 個提議」的一般機率 $q_n$。

第二項是「我在前一個紀元_確實_有最後一個時段」的機率 $r$，乘以「我藉由提議我的區塊得到 $n$ 個提議、或藉由扣住我的區塊得到 $n + 1$ 個提議」的機率 $p_n$。我們需要那個加一，來補上「為了得到這個結果，我會在前一個紀元結尾所扣住的那個區塊」。

$$
p_j =
\begin{cases}
\sum_{i=0}^{j} q_i (q_j + q_{j+1}) & 0 \leq j < 32 \\
\sum_{i=0}^{j} q_i q_j            & j = 32
\end{cases}
$$

如同之前，我們可以藉由考慮機率的矩陣來說明這一點。有了一條長度為一的尾巴，我有兩個選擇：提議或扣住。要達到淨數量恰好為 $j$ 的提議，我們尋找的是下列任一者成立的組合。

 1. 提議給我恰好 $j$ 個提議，而扣住給我不超過 $j+1$ 個（即 $\sum_{i=0}^{j+1}q_{i}q_{j}$）。這些是下圖中水平長條中的元素。
 2. 提議給我不超過 $j$ 個提議，而扣住給我恰好 $j + 1$ 個（即 $\sum_{i=0}^{j}q_{j+1}q_i$）[^fn-hyper-hurts-head]。這些是下圖中垂直長條中的元素。

請注意，$q_{j+1}q_j$ 這個元素出現在兩種結果中，但必須只被計入一次。

[^fn-hyper-hurts-head]: 你可以看出我為什麼把這個範例限制在長度僅為零或一的尾巴：我不想去想這在一個 $2^k$ 維空間中看起來是什麼樣子。

<a id="img_randomness_propose_probabilities"></a>
<figure class="diagram" style="width:40%">

![提議數量機率的矩陣。](images/diagrams/randomness-propose_probabilities.svg)

<figcaption>

我們以兩次嘗試得到淨數量恰好為二之提議的機率，是各陰影區域中各項的總和。儘管有重疊，每一項都只被計入一次。

</figcaption>
</figure>

我們可以逐紀元迭代這個，來計算我預期提議數在長期下最大的改善。我得到紀元 $N$ 最後一個時段的機率是 $E'_N / 32$。

$$
E'_{N+1} = \sum_{n=1}^{32} n \left((1 - \frac{E'_N}{32}) q_n + \frac{E'_N}{32} p_n\right)
$$

<a id="img_randao_proposals"></a>
<figure class="chart" style="width:100%">

![一張圖，顯示偏置與不偏置 RANDAO 時每個紀元的預期提議數。](images/charts/randao_proposals.svg)

<figcaption>

實線是 $E$，即一個不尋求偏置 RANDAO 的質押比例每個紀元的預期區塊提議數。虛線是 $E'$，即一個協同合作以偏置 RANDAO 對自己有利的質押比例，長期每個紀元的預期區塊提議數。

</figcaption>
</figure>

我能取得的區塊提議最大百分比增益顯示在下面這張圖中。

<a id="img_randao_proposals_percent"></a>
<figure class="chart" style="width:100%">

![一張圖，顯示偏置 RANDAO 時每個紀元提議數的百分比增加。](images/charts/randao_proposals_percent.svg)

<figcaption>

一個協同合作以偏置 RANDAO 的質押比例，在長期下能取得的每個紀元預期提議數的百分比增加。一個擁有 25% 質押的實體，在假設其餘質押者未協同合作的情況下，可以多得 2.99% 的提議（每個紀元 8.24 個、而非恰好 8 個）。

</figcaption>
</figure>

<details>
<summary>計算作弊時預期提議數的程式碼</summary>

下面的 Python 程式碼把 $E'_N$ 計算到收斂。

```python
def fac(n):
    return n * fac(n - 1) if n else 1

def choose(n, k):
    return fac(n) / fac(k) / fac(n - k)

def prob(n, k, r):
    return r**k * (1 - r)**(n - k) * choose(n, k)

nintervals = 20
for idx in range(1, nintervals + 1):
    r = r0 = idx / nintervals
    q = [prob(32, j, r0) for j in range(33)]

    p = []
    for j in range(33):
        p.append(sum([q[i] * q[j] + (q[j + 1] * q[i] if (j < 32) else 0) for i in range(j + 1)]))

    # Iterate to convergence
    e = 0
    while (e == 0 or abs(e - e_old) > 0.000001):
        e_old = e
        e = sum([i * (q[i] * (1 - r) + p[i] * r) for i in range(33)])
        r = e / 32

    print(r0, r0 * 32, e, 100 * (e / (r0 * 32) - 1))
```

</details>

###### 提議加成的討論

在上述分析中，我們只考慮了「使用一個紀元的最後一個時段來偏置 RANDAO」的效果，並看到在假設其他每個人都誠實行事的情況下，一個擁有任何質押量的實體都能微幅改善它整體的預期區塊提議數。

如果我們考慮使用最後兩個時段、或最後 $k$ 個時段，預期的增益可能更高，尤其若與先前的尾巴延伸攻擊結合。但我預期，對於小於約一半的 $r$，任何進一步的改善都會非常小。

#### 可驗證延遲函式

我們已看到，雖然 RANDAO 可被偏置，它卻沒有可偏置到足以破壞協定的地步：就我們的目的而言，這份隨機性「夠好了」。

儘管如此，探索它可能如何被改善是很有意思的，尤其因為隨著「合併」，RANDAO 值現在對以太坊的智慧合約層也可用了。舉例來說，一個大型樂透合約中的隨機性可偏置性，可能比共識協定中的可偏置性更成問題。

可偏置性的長期解方，是使用一個可驗證延遲函式（verifiable delay function，VDF）。一個 VDF 被保證計算其輸出很慢，但那個輸出可以被快速地驗證。實務上，VDF 是一項在一台專用硬體裝置上運行的計算，並假設該裝置的效能在理論最大效能的一個小倍數之內。所以，一個 VDF 可能在比方說 20 秒內輸出一個結果，並假設任何其他裝置所能做到最好的，是在比方說 5 秒內取得該結果。

其構想是 RANDAO 的更新會來自 VDF 的輸出。提議者會必須在「它有可能計算出實際的貢獻（VDF 未來的輸出）」之前，就決定是否提交它的 `randao_reveal`。這消除了對 RANDAO 任何投機性的偏置。

網路上在任何時候都只需要有一個 VDF 是活躍的，因為它可以發布它的結果，供所有其他節點快速驗證。

雖然在設計與規定 VDF 上已下了[許多工夫](https://www.vdfalliance.org/)，目前並沒有在以太坊中實作一個的活躍計畫。如果說有什麼的話，關於[構造 VDF 函式之困難度](https://ethresear.ch/t/statement-regarding-the-public-report-on-the-analysis-of-minroot/16670?u=benjaminion)的近期結果，暗示協定內 VDF 的前景在此時正在消退。

#### 另見

Vitalik 在他的[《以太坊 2.0 註解規格》](https://notes.ethereum.org/@vbuterin/SkeyEI3xv#Aside-RANDAO-seeds-and-committee-generation)中有一些關於隨機性的筆記。他的文章[《PoS 中的驗證者排序與隨機性》](https://web.archive.org/web/20160723105229/https://vitalik.ca/files/randomness.html)總結了一些關於「權益證明中隨機驗證者選擇之選項」的早期思考[^fn-paddy-randomness]。

[^fn-paddy-randomness]: 這篇文章如今似乎只能在網際網路檔案館取得。我感謝 Patrick McCorry 把它找了出來。

關於 RANDAO 的可偏置性，Runtime Verification 在 2018 年做了一份分析，它既補充、也比我在本節所呈現的概略更深入。他們的工作有一個[統計模型](https://github.com/runtimeverification/rdao-smc)以及一份徹底的[記述](https://github.com/runtimeverification/rdao-smc/blob/master/report/rdao-analysis.pdf)。

在 ethresear.ch 上[搜尋 RANDAO](https://ethresear.ch/search?q=RANDAO%20in%3Atitle%20order%3Alatest) 會得到好幾篇文章，討論它的各種議題、並提出一些解決方案（我們一個也沒採用）。尤其，Toni Wahrstätter 的[《自私混合與 RANDAO 操縱》](https://ethresear.ch/t/selfish-mixing-and-randao-manipulation/16081?u=benjaminion)做了一些與上文相似的分析，然後考慮了實際網路的一些資料與模擬。此外，István András Seres 一篇關於[《分叉 RANDAO》](https://ethresear.ch/t/forking-the-randao-manipulating-ethereums-distributed-randomness-beacon/21414?u=benjaminion)的文章及其[相關論文](https://eprint.iacr.org/2025/037.pdf)，提出了一種不同的做法，它仰賴選擇性地把一個誠實提議者的區塊分叉出去，以操縱 RANDAO。

開始探索可驗證延遲函式的一個好地方，是 [VDF Alliance 網站](https://www.vdfalliance.org/)。

### 洗牌 <!-- /part2/building_blocks/shuffling/ -->

<div class="summary">

  - 洗牌被用來隨機地把驗證者指派到委員會，並選出區塊提議者。
  - 以太坊&nbsp;2 使用一種「交換或不交換」（swap-or-not）洗牌。
  - 交換或不交換是一種不經意洗牌（oblivious shuffle）：它可以被套用在單一的清單元素與子集上。
  - 這使它對於支援輕客戶端而言是理想的。

</div>

#### 引言

洗牌被用來隨機地把驗證者指派到委員會，包括證明委員會與同步委員會兩者。它也被用來在每個時段選出區塊提議者。

雖然有一些[陷阱](https://web.archive.org/web/20230208135555/https://www.developer.com/guides/how-we-learned-to-cheat-at-online-poker-a-study-in-software-security/)要留意，洗牌在電腦科學中是一個被充分理解的問題。黃金標準大概是 [Fisher–Yates 洗牌](https://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle)。那麼我們為什麼不在 Eth2 用那個？簡言之：輕客戶端。

其他的洗牌仰賴處理整份元素清單來找出最終的排序。我們希望讓輕客戶端免於這項負擔。理想情況下，它們應當只處理它們所感興趣之清單的子集。因此，我們使用的不是 Fisher–Yates，而是一種稱為「交換或不交換」洗牌的構造。交換或不交換洗牌可以告訴你單一一個清單元素的目的地索引（或反過來，起源索引），所以在處理整個驗證者集合的子集時是理想的。

舉例來說，正式地說，委員會是藉由洗牌完整的驗證者清單、然後取所得排列的連續切片來指派的。如果我只需要知道委員會 $k$ 的成員，那麼這非常沒有效率。我可以改為只對切片 $k$ 中的索引反向運行交換或不交換洗牌，以找出整個驗證者集合中的哪些會被洗進 $k$。這有效率得多。

#### 交換或不交換規格

[規格中](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/beacon-chain.md#compute_shuffled_index)的洗牌演算法一次只處理單一一個索引。

```python
def compute_shuffled_index(index: uint64, index_count: uint64, seed: Bytes32) -> uint64:
    """
    Return the shuffled index corresponding to ``seed`` (and ``index_count``).
    """
    assert index < index_count

    # Swap or not (https://link.springer.com/content/pdf/10.1007%2F978-3-642-32009-5_1.pdf)
    # See the 'generalized domain' algorithm on page 3
    for current_round in range(SHUFFLE_ROUND_COUNT):
        pivot = bytes_to_uint64(hash(seed + uint_to_bytes(uint8(current_round)))[0:8]) % index_count
        flip = (pivot + index_count - index) % index_count
        position = max(index, flip)
        source = hash(
            seed
            + uint_to_bytes(uint8(current_round))
            + uint_to_bytes(uint32(position // 256))
        )
        byte = uint8(source[(position % 256) // 8])
        bit = (byte >> (position % 8)) % 2
        index = flip if bit else index

    return index
```

提供的是待洗牌清單中的一個索引位置 `index`，連同索引的總數 `index_count` 與一個 `seed` 值。輸出是初始索引被洗牌到的那個索引。

用以計算 `pivot` 與 `source` 的雜湊函式是確定性的，用以從輸入產生偽隨機的輸出：給定相同的輸入，它們會產生相同的輸出。所以我們可以看出，對於給定的 `index`、`index_count`、`seed` 值，這個常式總是會回傳相同的輸出。

洗牌以輪為單位進行。在每一輪，一個 `pivot`（樞紐）索引被偽隨機地選在清單中的某處，僅基於 `seed` 值與輪號。

接著，找出一個索引 `flip`，它是 `pivot - index`，並把模函式所造成的環繞納入考量之後。重要的幾點是：給定 `pivot`，每個 `index` 都映射到一個唯一的 `flip`，並且這項計算是對稱的，所以 `flip` 也映射到 `index`。

  - 在 `index_count = 100`、`pivot = 70`、`index = 45` 時，我們得到 `flip = 25`。
  - 在 `index_count = 100`、`pivot = 70`、`index = 82` 時，我們得到 `flip = 88`。

作為這一輪的最後一步，做出一個決定：要把索引維持原樣，還是要把它更新為 `flip`。這個決定是基於 `seed` 的值、輪號、以及 `index` 與 `flip` 中較大者，偽隨機地做出的。

請注意，把交換或不交換的決定基於 `index` 與 `flip` 中較大者，為這個演算法帶來一種對稱性。不論我們考慮的是 `index` 處的元素還是 `flip` 處的元素，「是否交換這些元素」的決定都會是相同的。這就是看出「完整的演算法交付了對原始集合的一次洗牌（排列）」的關鍵。

演算法基於更新後的索引繼續進行下一次迭代。

這可能不會立即顯而易見，但由於我們僅基於輪號確定性地計算 `flip`，這個洗牌可以單純地藉由從 `SHUFFLE_ROUND_COUNT - 1` 跑到 `0` 來反向運行。相同的交換或不交換決定會被反向做出。如上所述，這個反向洗牌對於找出哪些驗證者最終落入某個特定委員會而言是完美的。

#### 一次完整的洗牌

為了對「這個單一索引的洗牌如何能交付對一份索引清單的完整洗牌」獲得一些直覺，我們可以考慮在一次洗牌整份清單時，這個演算法通常如何[在客戶端中被實作](https://github.com/ConsenSys/teku/blob/04294427f2622c86326db68f3b88ed20d1e6cdc1/ethereum/spec/src/main/java/tech/pegasys/teku/spec/logic/common/helpers/MiscHelpers.java#L154)。

作為一種最佳化，「遍歷待洗牌索引」的迴圈被搬進「遍歷各輪」的迴圈之內。這大幅減少了所需的雜湊量，因為樞紐在這一輪中是固定的（它不取決於索引），而且由於雜湊有 256 位元的輸出，`source` 的各位元可以被重複用於 256 個連續的索引。

對每一輪，我們做下列事情。

##### 1. 選擇一個樞紐並找出第一個鏡像索引

首先，我們挑選一個樞紐索引 $p$。這是基於輪號與某些其他種子資料偽隨機地選出的。樞紐在這一輪剩下的部分是固定的。

有了這個樞紐，我們接著挑選位於 $p$ 與 $0$ 之間中點的鏡像索引 $m_1$。也就是 $m_1 = p / 2$。（為了這個解釋的目的，我們會簡化，忽略差一的捨入問題。）

<a id="img_shuffling_0"></a>
<figure class="diagram" style="width:80%">

![一張示意圖，顯示樞紐與第一個鏡像索引。](images/diagrams/shuffling-0.svg)

<figcaption>

樞紐與第一個鏡像索引。

</figcaption>
</figure>

##### 2. 從第一個鏡像遍歷到樞紐，交換或不交換

對於鏡像索引 $m_1$ 與樞紐索引 $p$ 之間的每一個索引，我們決定我們是否要交換那個元素。

考慮索引 $i$ 處的元素。如果我們選擇不交換它，我們就直接前進去考慮下一個索引。

如果我們確實決定交換，那麼我們就把 $i$ 處的清單元素，與它在鏡像索引中的影像 $i'$ 處的清單元素對調。也就是說，$i$ 與 $i' = m_1 - (i - m_1)$ 對調，使得 $i$ 與 $i'$ 與 $m_1$ 等距。實務上，我們此時並不對調元素，我們只是更新索引 $i \rightarrow i'$、以及 $i' \rightarrow i$。

對於 $m_1$ 與 $p$ 之間的每一個索引，我們都做出相同的交換或不交換決定。

<a id="img_shuffling_1"></a>
<figure class="diagram" style="width:80%">

![一張示意圖，顯示從第一個鏡像往上到樞紐的交換或不交換。](images/diagrams/shuffling-1.svg)

<figcaption>

從第一個鏡像往上到樞紐的交換或不交換。

</figcaption>
</figure>

是否交換的決定，是基於把隨機種子、輪號、以及某些位置資料一起雜湊。對每個索引，從這個雜湊中萃取出單一一個位元，並依這個位元是一還是零來決定交換與否。

##### 3. 計算第二個鏡像索引

在考慮過從 $m_1$ 到 $p$、以 $m_1$ 為鏡的所有索引 $i$ 之後，我們現在找出第二個鏡像索引，位於 $m_2$，它是 $p$ 與清單尾端之間等距的那一點：$m_2 = m_1 + n / 2$。

<a id="img_shuffling_2"></a>
<figure class="diagram" style="width:80%">

![一張示意圖，顯示第二個鏡像索引。](images/diagrams/shuffling-2.svg)

<figcaption>

第二個鏡像索引。

</figcaption>
</figure>

##### 4. 從樞紐遍歷到第二個鏡像，交換或不交換

最後，我們重複交換或不交換的過程，考慮從樞紐 $p$ 到第二個鏡像 $m_2$ 的所有點 $j$。如果我們選擇不交換，我們就直接前進。如果我們選擇交換，那麼我們就把 $j$ 處的元素與它在鏡像索引 $m_2$ 中的影像 $j'$ 處的元素對調。此處 $j' = m_2 + (m_2 - j)$。

<a id="img_shuffling_3"></a>
<figure class="diagram" style="width:80%">

![一張示意圖，顯示從樞紐到第二個鏡像的交換或不交換。](images/diagrams/shuffling-3.svg)

<figcaption>

從樞紐到第二個鏡像的交換或不交換。

</figcaption>
</figure>

##### 把這一切湊在一起

在這一輪結束時，我們已考慮了 $m_1$ 與 $m_2$ 之間的所有索引，依構造，那是全部索引的一半。對於所考慮的每個索引，我們要嘛把元素留在原處，要嘛把它與另一半中一個相異索引處的元素對調。因此，所有的索引都恰好被考慮交換過一次。

下一輪藉由把輪號遞增（反向洗牌則遞減）來開始，這給了我們一個新的樞紐索引，於是我們又上路了。

<a id="img_shuffling_4"></a>
<figure class="diagram" style="width:80%">

![一張示意圖，顯示在單一一輪中從一個鏡像跑到另一個鏡像的整個過程。](images/diagrams/shuffling-4.svg)

<figcaption>

在單一一輪中從一個鏡像跑到另一個鏡像的整個過程。

</figcaption>
</figure>

#### 討論

##### 一個關鍵洞見

在為每個索引決定是否交換時，演算法巧妙地把它的決定基於「候選索引或它在鏡中的影像」中較大的那一個。也就是說（在樞紐下方時）是 $i$ 而非 $i'$，而（在樞紐上方時）是 $j'$ 而非 $j$。這意味著我們在遍歷清單的索引時有彈性：我們可以把 $0$ 到 $m_1$ 與 $p$ 到 $m_2$ 做成兩個分開的迴圈，或如我上文所概述，用一個從 $m_1$ 到 $m_2$ 的單一迴圈來做。結果會是相同的：我們考慮的是 $i$ 還是它的影像 $i'$ 都無關緊要；是否交換的決定有著相同的結果。

##### 輪數

在以太坊&nbsp;2.0 中，我們每次洗牌做 90 輪演算法，由常數 [`SHUFFLE_ROUND_COUNT`](/part3/config/preset/#misc) 所設定。這項技術所基於的[原始論文](https://link.springer.com/content/pdf/10.1007%2F978-3-642-32009-5_1.pdf)建議「要開始看到對 CCA 安全性的良好界限」需要 $6\lg{N}$ 輪，其中 $N$ 是清單長度。Vitalik 在他的[註解規格](https://github.com/ethereum/annotated-spec/blob/master/phase0/beacon-chain.md)中說「專家密碼學家的建議告訴我們 ~$4\log_2{N}$ 對安全而言已足夠」。Eth2 中驗證者的絕對最大數量、因而我們可能需要洗牌之清單的最大大小，約為 $2^{22}$（420 萬）。以 Vitalik 的估計，那給我們所需的 88 輪；以該論文的估計則是 92 輪（假設 $\lg$ 是自然對數）。所以我們在正確的範圍內，尤其因為我們極為極為不可能最終會有那麼多活躍的驗證者。

讓輪數依清單長度自適應，可能會很有意思。但我們不那麼做；那大概是一項過頭的最佳化。

有趣的事實：當 Least Authority 稽核信標鏈規格時，他們起初在「用於選擇區塊提議者的洗牌」中發現了偏置（見[他們報告](https://leastauthority.wpengine.com/static/publications/LeastAuthority-Ethereum-2.0-Specifications-Audit-Report.pdf)中的議題 F）。這結果是由於誤用了一個只有 10 輪洗牌的設定。當他們把它增加到我們用於主網的 90 輪時，偏置就不再出現了。

##### （偽）隨機性

這個演算法要求我們在每一輪隨機地選擇一個樞紐點，並在每一輪隨機地選擇是否交換每個元素。

在 Eth2 中，我們從一個種子值確定性地產生「隨機性」，使得相同的種子總是會產生相同的洗牌。

樞紐索引是從「種子與輪號串接」的 SHA256 雜湊的八個位元組產生的，所以它通常每輪都改變。

用以決定是否交換元素的決定位元，是從「種子、輪號、以及元素在清單中之索引」的 SHA256 雜湊中取出的位元。

##### 效率

這個洗牌演算法比 Fisher–Yates 慢得多。那個演算法需要 $N$ 次交換。我們的演算法平均需要 $90N/4$ 次交換來洗牌 $N$ 個元素。

我們也應該考慮偽隨機性的產生，那是這個演算法最昂貴的部分。Fisher–Yates 需要約 $N\log_2{N}$ 位元的隨機性，而我們需要 $90(\log_2{N} + N/2)$ 位元，對於我們在 Eth2 中所需的 $N$ 範圍而言，那是多得多的位元（當 $N$ 是一百萬時約為兩倍）。

#### 為何用交換或不交換？

我們為什麼會用這麼沒有效率的實作？

##### 洗牌單一元素

其精妙之處在於：如果我們只對少數幾個索引感興趣，我們就不需要計算整份清單的洗牌。事實上，我們可以把演算法套用在單一一個索引上，以找出它將與哪個索引交換。

所以，如果我們想知道索引為 217 的元素被洗牌到哪裡，我們可以只用那個索引運行演算法；我們不需要洗牌整份清單。此外，如果我們想知道相反的問題，也就是哪個元素被洗進索引 217，我們只需為元素 217 反向運行演算法（反向意味著把輪號從高跑到低、而非從低跑到高）。

總而言之，我們可以用 $O(1)$ 次操作計算出元素 $i$ 的目的地，並用同樣的 $O(1)$ 計算出元素 $i'$ 的來源（逆操作），不取決於清單的長度。像 Fisher–Yates 洗牌這樣的洗牌並沒有這個性質，無法處理單一索引，它們總是需要遍歷整份清單。一個洗牌具有這個性質的技術術語，是說它是_不經意的_（oblivious，對清單中所有其他元素而言）。

##### 讓輕客戶端維持輕巧

這個性質對輕客戶端很重要。輕客戶端是 Eth2 信標鏈的觀察者，它們不儲存整個狀態，卻確實希望能夠安全地存取鏈的資料。作為「驗證它們擁有正確的資料——沒有人對它們撒謊」的一部分，有必要計算「為那份資料做出證明的委員會」。這意味著洗牌，而我們不希望輕客戶端必須持有並洗牌整份驗證者清單。藉由使用交換或不交換洗牌，輕客戶端只需考慮它們所感興趣之驗證者的那一小部分子集，整體而言這有效率得多。

#### 另見

  - 關於「尋找一個好的洗牌演算法」的最初討論，是規格儲存庫上的[議題 323](https://github.com/ethereum/consensus-specs/issues/323)。
  - 勝出的演算法在[議題 563](https://github.com/ethereum/consensus-specs/issues/563)中公布。
  - 描述交換或不交換洗牌的原始論文是 Hoang、Morris、Rogaway 2012 年的[《一個基於洗撲克牌的加密方案》](https://link.springer.com/content/pdf/10.1007%2F978-3-642-32009-5_1.pdf)。見第 3 頁的「廣義定義域」演算法。

### 委員會 <!-- /part2/building_blocks/committees/ -->

<div class="summary">

  - 委員會是完整活躍驗證者集合的子集，被用來分散整體的工作負載。
  - 信標委員會為共識協定管理證明；同步委員會在[別處](/part2/building_blocks/sync_committees/)討論。
  - 每個時段有 64 個信標委員會，是以往 Eth2 設計的遺跡。
  - 儘管如此，每個時段有多個委員會，讓我們得以把證明聚合平行化。
  - 信標委員會的成員資格是隨機且短暫的。
  - 一個 128 的目標最低委員會大小，保護它們不被攻佔。

</div>

#### 引言

打造一個高度可擴展之共識協定的難題之一，是組織所涉及的工作，以免壓垮網路或個別節點。

以太坊&nbsp;2 權益證明協定的一個目標，是達成經濟性最終性。在當前的設計中（不過關於單時段最終性的討論見[下文](#see-also)），這要求我們蒐集至少三分之二驗證者集合的票，而我們必須做這件事兩次：一次去證成一個紀元，再一次去最終確定它。

如果整個驗證者集合同時做出證明，網路上的訊息數量會極為龐大，而信標節點所需的工作量對於普通的硬體而言也太多。這就是委員會幫得上忙之處。做出證明的工作被分給驗證者集合的子集（委員會），並分散在一個紀元（6.4 分鐘）內。每個驗證者只參與其中一個委員會。

Altair 規格引入了兩種類型的委員會——信標委員會與同步委員會——每一種都有著相當不同的功能。我們會在本節聚焦於信標委員會，並在[後面的一節](/part2/building_blocks/sync_committees/)處理同步委員會。

當前的信標委員會結構，深受一個曾包含協定內資料分片的以往路線圖所影響。那個設計[現已被棄用](https://github.com/ethereum/consensus-specs/pull/1428)，然而它的一個殘餘留在我們每個時段 64 個信標委員會中。這些委員會原本意在作為「交叉連結委員會」（crosslink committee）直接映射到 64 個分片，但不再有那個功能。儘管如此，信標委員會在把證明的聚合平行化上仍發揮著有用的作用。就我所知，64 是否仍是每個時段委員會的正確數量並未被分析過。其取捨是：較少的信標委員會會減少聚合證明所需的區塊空間量，但會增加[聚合者](/part2/building_blocks/aggregator/)做它們的工作所需的時間。

無論如何，在邏輯上，一個時段中所有的委員會現在都作為單一一個大型超級委員會行動，全都對相同的資訊投票。

#### 委員會指派

信標委員會被召集起來恰好投一次票，然後立即被解散——它們完全是短暫的。相比之下，一個同步委員會持續 256 個紀元（27 小時多一點），並在那段期間投票 8192 次。

在一個紀元期間，每個活躍的驗證者都恰好是一個委員會的成員，所以該紀元的所有委員會都不相交。在下一個紀元的開頭，所有既有的委員會都被解散，活躍驗證者集合被劃分成一組全新的委員會。

一個紀元各委員會的組成，在紀元開頭由 (1) 該紀元的活躍驗證者集合、以及 (2) 前一個紀元開頭的 [RANDAO 種子](/part2/building_blocks/randomness/#lookahead)值，完整地決定。

<a id="img_committees_random"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示圓形與三角形被隨機地劃分進各委員會。](images/diagrams/committees-random.svg)

<figcaption>

此處我們把三十個圓形與十五個三角形隨機地劃分進五個委員會。攻擊的三角形在任何委員會中都沒有多數。

</figcaption>
</figure>

我們隨機地把驗證者指派到委員會，是為了防禦「一個少數攻擊者能夠攻佔任何單一一個委員會」。如果委員會指派不是隨機的、或可在很久以前就被計算出來，那麼一個擁有少數驗證者的攻擊者，就有可能把它們組織起來，使它們在某些委員會中成為超級多數。舉例來說，它們可能藉由操縱它們驗證者的進入與退出來這麼做。

<a id="img_committees_organised"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，顯示在一個攻擊者的影響下，圓形與三角形被劃分進各委員會。](images/diagrams/committees-organised.svg)

<figcaption>

三角形純粹靠機運在一個委員會中取得 2/3 超級多數是不太可能的。但如果攻擊者能夠操縱指派，那麼它們就可能在某些委員會中取得超級多數，例如此處的前兩個。

</figcaption>
</figure>

Eth2 協定中所使用的委員會大小，被選來使「一個少數攻擊者攻佔一個委員會」極為不可能。關於這一點的進一步分析，見下文的[目標委員會大小](#target-committee-size)。

#### 委員會的數量

協定根據活躍驗證者的數量，調整每個紀元委員會的總數。目標是：

1. 在整個紀元中每個時段有相同數量的委員會（所以一個紀元中委員會的數量總是 `SLOTS_PER_EPOCH` 的倍數），
2. 在「確保每個委員會至少有 `TARGET_COMMITTEE_SIZE` 個成員」的前提下有最多數量的委員會，以及
3. 每個時段至多有 `MAX_COMMITTEES_PER_SLOT` 個委員會。

顯然，如果驗證者少於 `SLOTS_PER_EPOCH` 個，第一個目標就無法達成——一個沒人在裡頭的委員會還算委員會嗎？——而如果驗證者少於 `SLOTS_PER_EPOCH` `*` `TARGET_COMMITTEE_SIZE`（4096）個，第二個目標就無法達成。一個驗證者少於 4096 個的協定很難被認為安全，所以這在實務上不是一個顯著的議題。

<a id="img_committees_all"></a>
<figure class="diagram" style="width: 90%">

![一張示意圖，顯示每個時段有 N 個委員會、每個紀元有 32 個時段。](images/diagrams/committees-all.svg)

<figcaption>

一個紀元中每個時段都有相同數量的委員會 $N$，至多 `MAX_COMMITTEES_PER_SLOT` 個。該紀元中每個活躍的驗證者都恰好出現在一個委員會中，所以這些委員會全都不相交。

</figcaption>
</figure>

每個時段的委員會數量由規格函式 [`get_committee_count_per_slot()`](/part3/helper/accessors/#get_committee_count_per_slot) 計算。為了說明的目的，給定該紀元中活躍驗證者的數量 $n$，這可以被簡化為

```code
MAX_COMMITTEES_PER_SLOT = 64
SLOTS_PER_EPOCH = 32
TARGET_COMMITTEE_SIZE = 128
def committees_per_slot(n):
    return max(1, min(MAX_COMMITTEES_PER_SLOT, n // SLOTS_PER_EPOCH // TARGET_COMMITTEE_SIZE))
```

這產生一個委員會結構，隨著驗證者數量的增長或縮減，依下表演變。

| $n$ 最小 | $n$ 最大 | 委員會／時段 | 每個委員會的成員數 | 最小 | 最大 |
| - | - | -- | ----- | - | - |
| $0$ | $31$ | $1$ | 某些委員會有零個成員 | 0 | 1 |
| $32$ | $4095$ | $1$ | ${\lceil n / 32 \rceil}$ 或 ${\lfloor n / 32 \rfloor}$，它低於 `TARGET_COMMITTEE_SIZE` | 1 | 128 |
| $4096$ | $262\,143$ | ${N = \lfloor n / 4096 \rfloor}$ | ${\lceil n / (32N) \rceil}$ 或 ${\lfloor n / (32N) \rfloor}$ | 128 | 256 |
| $262\,144$ | $4\,194\,304$ | 64 | ${\lceil n / 2048 \rceil}$ 或 ${\lfloor n / 2048 \rfloor}$ | 128 | 2048 |
| $4\,194\,305$ | - | 64 | [東西會壞掉](https://consensys.net/blog/news/formal-verification-of-ethereum-2-0-part-1-fixing-the-array-out-of-bound-runtime-error/)。請注意，這在實務上[永遠不會發生](/part3/config/preset/#max_validators_per_committee)。 | - | - |

這張表中各個門檻處的數字，是從規格常數計算出來的：

  - 32 是 [`SLOTS_PER_EPOCH`](/part3/config/preset/#slots_per_epoch)。
  - 4096 是 `SLOTS_PER_EPOCH` `*` [`TARGET_COMMITTEE_SIZE`](/part3/config/preset/#target_committee_size)。這是所有委員會都達到它們目標最低大小的那一點。
  - 262,144 是 `SLOTS_PER_EPOCH` `*` `TARGET_COMMITTEE_SIZE` `*` [`MAX_COMMITTEES_PER_SLOT`](/part3/config/preset/#max_committees_per_slot)。我們已達到每個時段委員會的最大數量（64）。隨著驗證者集合增長，我們不再加入新的委員會，我們只是把委員會變大。
  - 4,194,304 是 `SLOTS_PER_EPOCH` `*` [`MAX_VALIDATORS_PER_COMMITTEE`](/part3/config/preset/#max_validators_per_committee) `*` `MAX_COMMITTEES_PER_SLOT`。現存的以太幣不足以讓我們達到這個活躍驗證者數量。這個上限存在於協定中，是為了讓我們得以為證明中的 [`aggregation_bits`](/part3/containers/operations/#attestation) SSZ [`Bitlist`](/part2/building_blocks/ssz/#bitlists) 型別指定一個最大大小。

##### 委員會索引

一個時段內 $N$ 個委員會的每一個，都有一個從 $0$ 到 $N-1$ 的委員會索引。在接下來的內容中，我會把它稱為 $i$，並稱它為以時段為基礎的索引。這個[以時段為基礎的索引](/part3/config/types/#committeeindex)透過 [`AttestationData`](/part3/containers/dependencies/#attestationdata) 物件被納入委員會的證明中，

```code
class AttestationData(Container):
    slot: Slot
    index: CommitteeIndex
    # LMD GHOST vote
    beacon_block_root: Root
    # FFG vote
    source: Checkpoint
    target: Checkpoint
```

`slot` 與該時段內的委員會 `index`，一起唯一地辨識出一個委員會，而再連同 RANDAO 值，則辨識出它的成員資格。

由於一個時段中所有的委員會都對完全相同的資訊（來源、目標、鏈頭區塊）投票，`index` 是「該時段各委員會所產生之聚合證明」之間唯一會變動的東西（假設大多數驗證者對網路有著相同的看法）。這阻止了該時段各委員會的證明被進一步聚合，所以我們一般會最終得到每個時段 $N$ 份聚合證明，必須把它們儲存在一個信標區塊中。

若不是因為 `index`，所有這 $N$ 份聚合證明本可被進一步聚合成單一一份聚合證明，結合來自所有在該時段投票之驗證者的票。

作為一個思想實驗，我們可以計算這麼做潛在的空間節省。給定一個委員會大小 $k$ 與每個時段 $N$ 個委員會，$N$ 個聚合 `Attestation` 物件當前所需的空間是 $N * (229 + \lfloor k / 8 \rfloor)$ 位元組。如果我們能從被簽署的資料中移除委員會索引、並把所有這些結合成單一一份聚合 `Attestation`，所需的空間會是 $221 + \lfloor kN / 8 \rfloor$ 位元組。所以我們每個區塊可以省下 $229N - 221$ 位元組，在最大的 64 個委員會時那是 14.4&nbsp;KB。這看似不錯，但很可能會使[委員會聚合過程](/part2/building_blocks/aggregator/)更複雜。

在 [`compute_committee()`](/part3/helper/misc/#compute_committee) 中把驗證者指派到委員會時，還會出現另一個索引：一個以紀元為基礎的委員會索引，我會把它稱為 $j$。索引 $i$ 與 $j$ 的關係是 $i = \mod(j, N)$ 以及 $j = Ns + i$，其中 $s$ 是該紀元中的時段編號。

#### 委員會的大小

一個紀元中的驗證者，由 [`compute_committee()`](/part3/helper/misc/#compute_committee) 函式分到各委員會。

給定以紀元為基礎的索引 $j$，`compute_committee()` 回傳完整、已洗牌之驗證者集合的一個切片作為委員會的成員。在那份已洗牌的清單中，委員會中第一個驗證者的索引是 $\lfloor nj / 32N \rfloor$，委員會中最後一個驗證者的索引是 $\lfloor n(j + 1) / 32N \rfloor - 1$。所以每個委員會的大小要嘛是 $\lfloor n / 32N \rfloor$，要嘛是 $\lceil n / 32N \rceil$。無論如何，一個紀元內各委員會的大小至多相差一。

簡化形式的 [`compute_committee()`](/part3/helper/misc/#compute_committee) 計算看起來像這樣。`N` 是每個時段的委員會數量，`n` 是活躍驗證者的總數，而 `j` 是以紀元為基礎的委員會索引，

```code
def compute_committee_size(n, j, N):
    start = n * j // (32 * N)
    end = n * (j + 1) // (32 * N)
    return end - start
```

所回傳之向量的長度，要嘛是 `n // (32 * N)`，要嘛是 `1 + n // (32 * N)`。函式 [`compute_shuffled_index()`](/part3/helper/misc/#compute_shuffled_index) 在[前一節](/part2/building_blocks/shuffling/)有所描述。

<a id="img_committees_selection"></a>
<figure class="diagram" style="width: 95%">

![一張示意圖，顯示驗證者集合如何被切成各委員會。](images/diagrams/committees-selection.svg)

<figcaption>

在概念上，要計算一個紀元的委員會指派，整個活躍驗證者集合被洗牌成一份長度為 $n$ 的清單，然後被切成 $32N$ 個盡可能接近相同大小的委員會。$N$ 是每個時段的委員會數量。圖中顯示了以紀元為基礎的委員會編號 $j$。

</figcaption>
</figure>

在上方圖的說明文字中，我說這是「在概念上」委員會成員資格如何被決定的。實務上，由於我們使用一個[不經意洗牌](/part2/building_blocks/shuffling/)，一個個別委員會的成員資格可以在不洗牌整個驗證者集合的情況下被計算出來；結果會是相同的。

##### 目標委員會大小

要達到一個可取的安全水準，委員會需要大於某個大小。這使得攻擊者即使掌控可觀數量的驗證者，要隨機地最終在一個委員會中得到超級多數也不可行。此處的目標是一種對委員會大小的下界。如果沒有足夠的驗證者讓所有委員會都至少有 `TARGET_COMMITTEE_SIZE`（128）個成員，那麼作為第一項措施，每個時段的委員會數量會被減少以維持這個最低值。只有在總共少於 `SLOTS_PER_EPOCH` `*` `TARGET_COMMITTEE_SIZE`（4096）個驗證者時，委員會大小才會被減到 `TARGET_COMMITTEE_SIZE` 以下。在驗證者這麼少的情況下，系統無論如何都會不安全。

給定一個攻擊者所掌控的驗證者集合比例，「攻擊者最終在一個從完整驗證者集合中均勻隨機選出的委員會中掌控三分之二多數」的機率是多少？Vitalik [計算出 111](https://web.archive.org/web/20190504131341/https://vitalik.ca/files/Ithaca201807_Sharding.pdf) 是「維持『一個擁有三分之一驗證者的攻擊者靠機運在任何一個委員會中取得三分之二多數』的機率為 $2^{-40}$（兆分之一）」所需的最低委員會大小。128 這個值被選為下一個更高的二的次方。

如果一個攻擊者擁有驗證者集合的比例 $p$，那麼「選到一個 $n$ 個驗證者的委員會、其中有 $k$ 個或更多驗證者屬於該攻擊者」的機率是，

$$
\sum_{i=k}^{n} p^i{(1-p)}^{n-i}{n\choose i}
$$

用這個我們可以計算出，事實上 109 個成員就足以讓「一個擁有三分之一驗證者的攻擊者靠機運取得三分之二多數」的機率只有 $2^{-40}$。

<a id="target-committee-size-code"></a>
<details>
<summary>計算目標委員會大小的程式碼</summary>

以下是 Vitalik 用以計算這些機率的 Python 程式碼。

```code
def fac(n):
    return n * fac(n-1) if n else 1

def choose(n, k):
    return fac(n) / fac(k) / fac(n-k)

def prob(n, k, p):
    return p**k * (1-p)**(n-k) * choose(n,k)

def probge(n, k, p):
    return sum([prob(n,i,p) for i in range(k,n+1)])
```

有了這個，我們發現「以 $2^{-40}$ 的機率避免三分之二多數」所需的最低委員會大小是 109、而非 111。

```code
>>> probge(108, 72, 1.0 / 3) < 2**-40
False
>>> probge(109, 73, 1.0 / 3) < 2**-40
True
```

無論如何，128 的委員會大小，對抗一個擁有 1/3 質押的攻擊者非常安全：

```code
>>> probge(128, 86, 1.0 / 3)
5.551560731791749e-15
```

</details>

兆分之一的機率聽起來可能像是過度工程，但我們也必須考慮到攻擊者可能取得對 RANDAO 的某種[掌控力](/part2/building_blocks/randomness/#randao-biasability)，所以某種安全餘裕是可取的。

儘管有這一切，在當前的信標鏈設計中，最低目標委員會大小其實無關緊要，因為委員會從不單獨運作。只要我們有至少 8192 個活躍的驗證者，每個時段就有多個委員會全都一起運作，而賦予安全性的是它們的聚合大小、而非任何個別委員會的大小。如前所述，當前的委員會設計受到一個現已被取代的舊資料分片模型所影響。儘管如此，個別委員會在協定的未來版本中可能會找到一個角色，所以這個最低目標大小值得保留。

#### 另見

Vitalik 在他的綜覽文章[《通往單時段最終性的路徑》](https://notes.ethereum.org/@vbuterin/single_slot_finality)中，考慮了「在每個時段引入單一一個『超級委員會』來取代既有的信標委員會」會需要什麼。這個超級委員會會是整個驗證者集合中一個夠大的子集，足以在單一一個（延長至 16 秒或更長的）時段內達到一個令人滿意的安全最終性水準。

### 聚合者選擇 <!-- /part2/building_blocks/aggregator/ -->

<div class="summary">

  - 在每個委員會中，選出驗證者的一個子集來執行委員會訊息的聚合。這改善了擴展。
  - 聚合者的選擇是基於 BLS 簽章、機率性的。
  - 這種選擇方法既保留了聚合者身分的祕密性，也保留了它的易驗證性。

</div>

#### 引言

在[信標委員會](/part2/building_blocks/committees/)與[同步委員會](/part2/building_blocks/sync_committees/)兩者中，驗證者都建立並簽署它們自己的票（分別是 `Attestation` 與 `SyncCommitteeMessage`）。這些票在被納入信標區塊之前，必須被[聚合](/part2/building_blocks/signatures/#aggregation)成數量少得多的聚合已簽署票，理想情況下聚合成「對單一一票的單一一份聚合簽章」。

聚合的目標有三方面：減少下一個區塊提議者的簽章驗證負載、減少全域流言通道的網路負載、以及減少儲存簽章所需的區塊空間量。

在當前的信標鏈設計中，投票在委員會中進行，目標是讓委員會成員的多數為相同的票背書，雖然實務上視個別委員會成員的網路看法而定，可能會有若干不同的票。無論如何，不同委員會的成員所簽署的是不同的資料，無法跨委員會聚合。

聚合的過程如下：

1. 委員會成員簽署它們的票（視我們所考慮的是哪種類型的委員會而定，是 [`Attestation`](/part3/containers/operations/#attestation) 或 [`SyncCommitteeMessage`](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/validator.md#synccommitteemessage)），並把它們廣播到整個委員會都訂閱的一個點對點子網。
2. 委員會的一個子集被選為該委員會的聚合者。
3. 聚合者在該子網上聆聽各票，然後把它們所收到、與它們自己對網路之看法一致的所有票，聚合成單一一份聚合票（聚合 [`Attestation`](/part3/containers/operations/#attestation) 或 [`SyncCommitteeContribution`](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/validator.md#synccommitteecontribution)）。
4. 每個聚合者用一份「它的確是該委員會聚合者」的證明把它的聚合票包裹起來，並簽署所得的資料（[`SignedAggregateAndProof`](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#signedaggregateandproof) 或 [`SignedContributionAndProof`](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/validator.md#signedcontributionandproof)）。
5. 最後，聚合者把它的聚合票與證明廣播到一個全域通道，供下一個區塊提議者接收。

本節所關注的是步驟 2 與步驟 4：聚合者如何被選來執勤，以及它們如何證明它們的確被選中。

<a id="img_aggregators"></a>
<figure class="diagram" style="width: 80%">

![一張示意圖，呈現聚合信標委員會證明的工作流程。](images/diagrams/aggregators.svg)

<figcaption>

在一個信標委員會內，所有成員都把它們個別的證明送到一個流言子網。聚合者是委員會中一個被選出的子集，他們聆聽該子網並聚合他們所收到的證明。聚合者把他們的聚合廣播到全域通道，供下一個區塊提議者撿起。

</figcaption>
</figure>

#### 聚合者選擇之所求

聚合者選擇的設計考慮了三個性質。

第一，所得聚合者集合的大小。我們希望以非常高的機率，選出委員會的一個小而非空的子集，以便我們有非常高的機會選出至少一個誠實、連線良好的聚合者。如果我們的聚合者集合稍微偏大一點並不太要緊，但我們真的想避免完全沒有聚合者。考慮到驗證者有可能當機或惡意，只選出一兩個聚合者也有風險。

第二，祕密性。我們會偏好「在聚合者廣播他們的聚合之前，沒有人能計算出聚合者是誰」。這有助於避免阻斷服務（DoS）攻擊。透過對少數聚合者發動網路 DoS 攻擊來擾亂共識，會比對一整個委員會發動容易得多。祕密性性質防止了這一點。

第三，可驗證性。我們希望「某個特定驗證者被選為聚合者」這個宣稱容易被驗證。這麼做的理由[在 p2p 規格中有所解釋](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/p2p-interface.md#why-are-aggregate-attestations-broadcast-to-the-global-topic-as-aggregateandproofs-rather-than-just-as-attestations)。基本上，若沒有可驗證性，那麼對委員會中_所有_的驗證者而言，做出並廣播聚合證明、以確保至少有一份聚合納入它們自己的證明，就會是一個好策略。這會摧毀整個聚合者方案的好處。

#### 聚合者選擇細節

當前的聚合策略在 [PR 1440](https://github.com/ethereum/consensus-specs/pull/1440) 中被引入，並在[信標委員會](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#attestation-aggregation)與[同步委員會](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/validator.md#aggregation-selection)的誠實驗證者規格中有所描述。

結果是，我們可以用 [BLS 簽章](/part2/building_blocks/signatures/)直截了當地滿足我們所求的大小、祕密性、可驗證性這三個性質。演算法相當簡單。委員會中的每個驗證者都產生一個可驗證的隨機數；如果那個隨機數模另一個數為零，那麼它就是一個聚合者，否則它就不是聚合者。

驗證者藉由用它一般的祕密簽章金鑰對當前時段編號做一份簽章、然後雜湊該簽章，來建立它的可驗證隨機數。我們假設這的結果是均勻隨機的；我們沒有理由懷疑它不是。

任何「其隨機數模 `len(committee)` `//` `TARGET_AGGREGATORS_PER_COMMITTEE` 等於零」的驗證者，就是一個聚合者。這個模數被選來提供平均每個信標委員會 16 個聚合者。

以下是用以判定哪些驗證者是信標委員會中之聚合者的[規格函式](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#aggregation-selection)。

<a id="def_get_slot_signature"></a>

```python
def get_slot_signature(state: BeaconState, slot: Slot, privkey: int) -> BLSSignature:
    domain = get_domain(state, DOMAIN_SELECTION_PROOF, compute_epoch_at_slot(slot))
    signing_root = compute_signing_root(slot, domain)
    return bls.Sign(privkey, signing_root)
```

<a id="def_is_aggregator"></a>

```python
def is_aggregator(state: BeaconState, slot: Slot, index: CommitteeIndex, slot_signature: BLSSignature) -> bool:
    committee = get_beacon_committee(state, slot, index)
    modulo = max(1, len(committee) // TARGET_AGGREGATORS_PER_COMMITTEE)
    return bytes_to_uint64(hash(slot_signature)[0:8]) % modulo == 0
```

這種做法提供了祕密性，因為它仰賴驗證者的祕密金鑰：在我發布證明之前，沒有別人能判定我是否是一個聚合者。它也提供了可驗證性，因為證明一旦被發布，就很容易用驗證者的公鑰來檢查簽章的有效性。

那大小準則呢？

##### 信標委員會聚合者

假設 BLS 簽章是均勻隨機的，那麼在一個大小為 $N$ 的委員會中，每個驗證者被選中的機率是 `TARGET_AGGREGATORS_PER_COMMITTEE` `/` $N$（忽略整數算術）。所以在期望上，我們每個委員會會有 `TARGET_AGGREGATORS_PER_COMMITTEE`（16）個聚合者。

有零個聚合者的機率是 ${(1 - \frac{16}{N})}^N$。對於最低目標委員會大小 $N = 128$，這是兩千六百萬分之一，而對於最大委員會大小 $N = 2048$，是九百五十萬分之一。所以在前一種情況下，我們會預期約每 13,000 個紀元（8 週）看到一個沒有聚合者的信標委員會，後一種情況則約每 5000 個紀元（3 週）一次。每個委員會只構成總驗證者集合的 $1/2048$ 比例，所以偶爾沒有聚合者對協定而言無關緊要，但對那個委員會中的人而言很不幸，他們的證明很可能因此不會被納入一個區塊。

<a id="img_committee_aggregators"></a>
<figure class="chart">

![一張長條圖，顯示一個 256 人委員會中不同聚合者數量的機率。](images/charts/committee_aggregators.svg)

<figcaption>

一個大小為 256 的信標委員會中有 $k$ 個聚合者的機率。預期數量是 16。

</figcaption>
</figure>

##### 同步委員會聚合者

同步委員會的運作方式類似。每個委員會有 512 個成員，被分到四個獨立的子網。目標如上是每個子網有 16 個聚合者，而聚合者在每個時段都改變。

`TARGET_AGGREGATORS_PER_SYNC_SUBCOMMITTEE` 值在同步委員會的實作之前[被從 4 增為 16](https://github.com/ethereum/consensus-specs/pull/2514)。這是基於一份[分析](https://docs.google.com/spreadsheets/d/1C7pBqEWJgzk3_jesLkqJoDTnjZOODnGTOJUrxUMdxMA/edit#gid=1790975994)，它顯示若只瞄準四個聚合者，「一個同步委員會子網沒有聚合者」的機會會高得令人無法接受。

#### 激勵

聚合者並未被協定直接激勵：對於執行或不執行聚合職責，並沒有明示的獎勵或懲罰。

然而，有著隱含的誘因。其一，如果我產生一份高品質的聚合簽章，這有助於確保我自己的簽章被納入一個區塊（別人的聚合有可能不納入我的簽章）。其二，由於整體的證明獎勵[依參與率成比例縮放](/part2/incentives/rewards/#rewards-scale-with-participation)（證明被納入區塊），當聚合者做出納入許多票的高品質聚合時，他們會與所有其他驗證者一起從略高的獎勵中受益。

#### 另見

王曉薇（Hsiao-Wei Wang）記載了圍繞聚合者選擇的[原始研究](https://notes.ethereum.org/@hww/aggregation)。

這種聚合策略給「打造分散式驗證者技術（DVT）」帶來一個困難。實作 DVT 的一種做法，是讓代表單一一個驗證者的多個驗證者獨立運作，旁邊有一個結合它們已簽署證明的中介軟體。這之所以行得通，是因為 BLS 簽章是可加的：每個驗證者都有金鑰的一部分，而那些已簽署的證明可以用一個[門檻簽章](/part2/building_blocks/signatures/#threshold-signatures)方案結合成一份來自完整金鑰的簽章。然而，雜湊那份（結合後的）簽章的過程無法以分散的方式完成，所以個別驗證者很難判定那個集體驗證者是否被選為一個聚合者。Oisín Kyne 的 [ethresear.ch 文章](https://ethresear.ch/t/distributed-validator-middlewares-and-the-aggregation-duty/13044?u=benjaminion)探討了這個問題並建議了一個解決方案，它（略經修改）出現在向 Beacon API 規格[提議新增](https://github.com/ethereum/beacon-APIs/pull/224)兩個端點之中。

[TODO: link to DVT when done]::

### SSZ：簡易序列化 <!-- /part2/building_blocks/ssz/ -->

<div class="summary">

  - 信標鏈使用一種稱為簡易序列化（Simple Serialize，SSZ）的新穎序列化方法。
  - 在多番辯論之後，我們選擇對共識與通訊兩者都使用 SSZ。
  - SSZ 不是自我描述的；你需要事先知道你正在反序列化的是什麼。
  - 一種偏移量方案允許快速存取資料的子集。
  - SSZ 與 Merkle 化、以及 Merkle 證明中的廣義索引都配合良好。

</div>

#### 引言

[序列化](https://en.wikipedia.org/wiki/Serialization)是「取結構化的資訊（在我們的情況中是一個資料結構），並把它變換成一個可以被儲存或傳輸之表示」的過程。

一份烹飪食譜就是一種序列化。我可以把烹煮某樣東西的方法寫下來，使得你和其他人能重現那個方法、煮出同樣的東西。這份食譜可以寫在一本書裡、出現在線上，甚至被口述並記憶下來——這就是序列化。用這份食譜煮出某樣東西，就是反序列化。

序列化在信標鏈上被用於三個主要目的。

1. 共識：如果你和我各自在一個資料結構（例如信標狀態）中有資訊，我們怎麼能知道我們的資料結構相不相同？只要所有客戶端都使用相同的方法，序列化就讓我們得以回答這個問題。請注意，這也與 [Merkle 化](/part2/building_blocks/merkleization/)緊密相關。
2. 點對點通訊：我們需要透過網際網路交換資料結構，例如證明與區塊。我們無法照原樣傳輸結構化的資料，它必須為傳輸而被序列化，並在另一端被反序列化。所有客戶端都必須使用相同的 p2p 序列化，但它不需要與共識序列化相同。
3. 同樣地，資料結構需要為「存取信標節點 API 的使用者」而被序列化。客戶端可以自由選擇它們自己的 API 序列化。例如，Prysm 客戶端有[一個 API](https://docs.prylabs.network/docs/how-prysm-works/prysm-public-api/) 使用 [Protocol Buffers](https://developers.google.com/protocol-buffers)（既然我們已就一個同時使用 SSZ 與 JSON 的[共同 API 格式](https://github.com/ethereum/beacon-APIs)達成一致，它正被棄用）。

此外，資料在被寫入磁碟之前必須被序列化。每個客戶端可以自由地在內部以它們希望的任何方式做這件事。

以太坊&nbsp;2.0 對所有這些目的，都使用一種稱為簡易序列化（Simple Serialize）、或更常見地就稱「SSZ」[^fn-ssz-z]的訂製序列化方案。

[^fn-ssz-z]: 從而把那個醜陋的「z」奉入全名中，並奉入那個[可怕的](/preface/#british-english)「ess-ess-zee」發音中。

#### 歷史

我們在 2018 年底與 2019 年初似乎花了好幾個月談序列化，而下面的故事是高度簡化的。但我認為記錄一些考量與設計決定是值得的。

以太坊&nbsp;1 一直使用一種稱為 [RLP](https://eth.wiki/fundamentals/rlp)（遞迴長度前綴，recursive length prefix）的序列化格式。這被認為不適合以太坊&nbsp;2，主要因為它被視為[過度複雜](https://ethereum.org/en/developers/docs/networking-layer/#ssz-vs-rlp)。[^fn-rlp-complexity]

[TODO - https://web.archive.org/web/20220528042454/https://eth.wiki/en/concepts/wishlist#rlp is a better link, but archive.org seems very slow right now. Need to revisit this.]::

[^fn-rlp-complexity]: [Vitalik](https://github.com/ethereum/consensus-specs/issues/692#issuecomment-467684205)：「身為 RLP 的發明者，我傾向偏好 SSZ」，以及[又一次](https://ethresear.ch/t/replacing-ssz-with-rlp-zip-and-sha256/5706/12?u=benjaminion)：「老實說 RLP 爛透了」（並附上一些為什麼的解釋！）。

所以，我們有自由去選擇一個新的序列化協定。我們考慮了哪些決策點？

##### 用於共識的序列化

從共識協定中的序列化開始，第一個大問題是：要採用一個現成的既有協定，還是自己打造一個。

許多[既有方案](https://notes.ethereum.org/15_FcGc0Rq-GuxaBV5SP2Q?view)的一個重大問題是，它們不保證序列化是確定性的：它們有時會以不可預測的方式重新排序欄位。這使它們完全不適合共識；相同的資料每次都必須得出相同的輸出。

一個更一般性的疑慮，圍繞著在共識關鍵的情況下使用第三方函式庫。早在 2014 年，Vitalik 就寫了一篇辯護文，題為[《何不用 X？》](https://blog.ethereum.org/2014/02/09/why-not-just-use-x-an-instructive-example-from-bitcoin/)，為以太坊就這麼多事情實作自己的技術（例如 RLP）辯護。這裡有一段摘錄：

> 我們在以太坊的核心原則之一是簡潔；協定應當盡可能簡單，而協定不應含有任何黑箱。每一個子協定的每一項特性，都應在白皮書或維基上被精確地 100% 記載，並以此作為規格來實作。

當然，就序列化而言，某些第三方函式庫遠比我們所需的通用得多，這可能導致問題。其他的則無法很好地對應到我們想使用的資料型別。

有鑑於這些疑慮，趨勢傾向採用一種訂製的、緊湊規定的序列化方法。是在 SSZ 之上對 [Merkle 化](/part2/building_blocks/merkleization/)的開發鞏固了這一點，使 SSZ（以某種形式）成為共識序列化明顯的領先者。

##### 用於通訊的序列化

那個決定做出之後，下一個大問題是：要不要對共識序列化與點對點通訊序列化（「線路協定」）兩者使用相同的方案。這在天平上很難取捨，而[有力的論點](https://github.com/ethereum/consensus-specs/issues/129)被提出，主張對 p2p 通訊使用 Protocol Buffers、對共識使用 SSZ。

圍繞這一點的討論很廣泛（見[下面](#see-also)的參考），但我們最終[決定](https://github.com/ethereum/eth2.0-pm/blob/master/eth2.0-implementers-calls/call_003.md#tentative-decisions)對 p2p 通訊使用 SSZ。

讓天平倒向「通訊也用 SSZ」的因素是：(1) 一份「只維護一個序列化函式庫」的願望，以及 (2) 某種可能的效能好處。

關於第一點，以太坊&nbsp;2 中有一種[偏好](https://github.com/ethereum/consensus-specs/issues/692#issuecomment-467684205)「簡潔甚於效率」的傾向。維護兩個序列化函式庫，可以說比「使用不同函式庫的任何潛在收穫」更費工。話雖如此，RLP 在 Eth2 的探索層中[仍被使用](https://github.com/ethresearch/p2p/issues/15)（因為它與 Eth1 共用），所以這個論點失去了一些力道。

關於第二點，當我們透過線路收到一個物件時，我們想做的第一件事往往是把它序列化，以計算它的共識資料根。如果我們收到它時它已經以正確的格式被序列化了，那就省下了一趟反序列化／重新序列化的往返。

SSZ 並不費任何力氣去精簡或壓縮序列化後的資料，而曾有疑慮擔心這可能使它對於線路傳輸協定而言沒有效率。這些疑慮藉由在線路上加上 [Snappy 壓縮](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/p2p-interface.md#encoding-strategies)而獲得緩解，一如以太坊&nbsp;1 中已經這麼做的。

##### SSZ 的開發

SSZ [基於](https://ethresear.ch/t/replacing-ssz-with-rlp-zip-and-sha256/5706/12?u=benjaminion)以太坊的智慧合約 [ABI](https://docs.soliditylang.org/en/v0.8.11/abi-spec.html)，但用 4 位元組的位置與大小記錄、而非 32 位元組，並有著不同的基本資料型別。任何擺弄過那個的人都會立刻覺得熟悉。SSZ 的雛形由 Vitalik 在 [2017 年 8 月](https://github.com/ethereum/research/tree/master/py_ssz)奠定。

SSZ 最初、較成熟的規格在 [2018 年 10 月](https://github.com/ethereum/consensus-specs/pull/18)被併入信標鏈儲存庫，而 `Container` 型別在[一個月後](https://github.com/ethereum/consensus-specs/pull/102/files)被加入。

SSZ 的效用上一大向前邁進的步伐——也是確立它作為共識序列化首選協定的東西——是 [Merkle 化](/part2/building_blocks/merkleization/)（也稱為樹雜湊，tree hashing）的開發，它在 [2018 年 10 月](https://github.com/ethereum/consensus-specs/issues/54)首次被討論，並在 [11 月](https://github.com/ethereum/consensus-specs/pull/120)被採納進規格。

同樣在 [2018 年 11 月](https://github.com/ethereum/consensus-specs/pull/139)，我們應 Nimbus 團隊的請求，同意把整數型別的位元組順序從大端切換為小端。這意味著表示十進位 66 的 32 位元數，現在被序列化為 `0x42000000`、而非 `0x00000042`。這項變更的主要動機，是更好地對應到典型微處理器中的位元組順序。

[2019 年 4 月](https://github.com/ethereum/consensus-specs/pull/787)，SSZ 隨著偏移量（offset）的採用而有一次重大變更。這來自 Péter Szilágyi 先前提議的一個方案[《簡易偏移量序列化》](https://gist.github.com/karalabe/3a25832b1413ee98daad9f0c47be3632)。其構想是依「待序列化的物件是定長還是變長」來把它們切分開來。序列化於是有兩個區段。第一個區段同時含有任何定長物件的實際序列化、以及指向任何變長物件序列化的指標（偏移量）。第二個區段含有變長物件的序列化。這麼做的動機，是允許「在不必反序列化整個結構的情況下，快速存取序列化資料的任意部分」。

SSZ 規格在 [2019 年 6 月](https://github.com/ethereum/consensus-specs/pull/1180)還有最後一次實質的重新改造，其中 SSZ 清單被要求指定一個最大長度，並[加入了](https://github.com/ethereum/consensus-specs/pull/1224) bitlist 與 bitvector 型別。

#### 概觀

[SSZ 的規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md)維護於主要的共識規格儲存庫中，要看所有細節就去那裡。我在此只會呈現一份引介性的概觀，加上幾個範例。

SSZ 的終極目標，是能夠把複雜的內部資料結構（例如 [BeaconState](/part3/containers/state/#beaconstate)）表示為位元組字串。

「要讓 SSZ 對共識與通訊兩者都有用」我們所要求的形式化性質，如 [SSZ 形式化驗證](https://github.com/ConsenSys/eth2.0-dafny/blob/master/wiki/ssz-notes.md#expected-properties-of-serialisedeserialise)工作中所定義。給定都是 $T$ 型的物件 $O_1$ 與 $O_2$，我們要求 SSZ 是

  1. 對合的（involutive）：$\texttt{deserialise}\langle T \rangle(\texttt{serialise}\langle T \rangle(O_1)) = O_1$（通訊所需），以及
  2. 單射的（injective）：$\texttt{serialise}\langle T \rangle(O_1) = \texttt{serialise}\langle T \rangle(O_2)$ 意味著 $O_1 = O_2$（共識所需）。

第一個性質說，當我們序列化一個某型的物件、然後反序列化結果時，我們最終得到一個與我們起初那個相同的物件。這對通訊協定至關重要。

第二個性質說，如果我們序列化兩個同型的物件並得到相同的結果，那麼這兩個物件就是相同的。等價地說，如果我們有兩個不同的同型物件，那麼它們的序列化會不同。這對共識協定至關重要。

除了那些基本的功能要求之外，SSZ 的其他目標是（相對地）簡單、產生（相當）精簡的序列化、並與 [Merkle 化](/part2/building_blocks/merkleization/)相容。能夠在不反序列化整個物件的情況下快速存取序列化中特定的資料片段，也很有用。把偏移量採納進 SSZ，在那方面改善了它的效能。

與 RLP 不同，SSZ 不是自我描述的。你可以在不事先知道一個物件長什麼樣子的情況下，把 RLP 資料解碼成一個結構化的物件。SSZ 並非如此：你必須事先確切地知道你正在反序列化的是什麼。在實務上這對 Eth2 一直不是問題：我們總是事先知道某個反序列化後的資料團對應到哪一類物件。這的一個後果是：在 RLP 中兩個不同型別的物件無法序列化成相同的輸出，而在 SSZ 中它們可以。我們很快就會看到這的一個例子。

#### 規格

我不打算深入 SSZ 的每一個細節——那是[規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md)的用途——而是我們會做一份一般性的概觀，然後深入一個[工作範例](#worked-example)。

SSZ 的構成要素是它的基本型別與它的複合型別。

##### 基本型別

SSZ 的基本型別非常簡單而有限，只由下列兩類構成。

  - 無號整數：一個 `uintN` 是一個 `N` 位元的無號整數，其中 `N` 可以是 8、16、32、64、128 或 256。
  - 布林值：一個 `boolean` 要嘛是 `True`、要嘛是 `False`。

基本型別的序列化不負「簡易」之名：

  - `uintN` 型別被編碼為 `N/8` 個位元組中的小端表示。例如，十進位數 12345（十六進位 `0x3039`）作為 `uint16` 型別被序列化為 `0x3930`（兩個位元組）。同一個數作為 `uint32` 型別被序列化為 `0x39300000`（四個位元組）。
  - `boolean` 型別永遠是一個位元組，真被序列化為 `0x01`、假被序列化為 `0x00`。

我在接下來的描述中嵌入了一些範例。如果你依附錄中的[說明](/appendices/running/)設置好 Eth2 規格，你可以自己運行它們。這些範例可以透過 Python REPL 運行，或藉由把命令放進一個檔案來運行（我會展示這兩種做法）。

```python
>>> from eth2spec.utils.ssz.ssz_typing import uint64, boolean
>>> uint64(0x0123456789abcdef).encode_bytes().hex()
'efcdab8967452301'
>>> boolean(True).encode_bytes().hex()
'01'
>>> boolean(False).encode_bytes().hex()
'00'
```

##### 複合型別

複合型別容納較小型別的組合或多份。規格定義了下列複合型別：向量（vector）、清單（list）、位元向量（bitvector）、位元清單（bitlist）、聯集（union）、容器（container）。我在接下來的內容中會略過聯集，因為它們目前在以太坊&nbsp;2 中並未被使用。

###### 向量

一個向量是一個有序、定長、同質的群集，恰好有 `N` 個值。「同質」意味著一個向量的所有元素都必須是同一型別，但它們不需要是同一大小。例如，我們可以有一個向量含有各有不同元素數量的清單。

在 SSZ 規格中，一個向量記為 `Vector[type, N]`。例如，`Vector[uint8, 32]` 是一個 32 元素的 `uint8` 型別（位元組）清單。`type` 可以是任何東西，包括其他向量、甚至容器。

向量提供了一個簡單的例子，說明「你必須在嘗試反序列化一個物件之前，先知道你反序列化的是哪種物件」。在下面的範例中，同一串位元組既編碼一個四元素的雙位元組整數集合，也編碼一個八元素的單位元組整數集合。當我們反序列化這個時，我們需要知道我們預期得到這當中的哪一個（或許多其他的可能性）。

```python
>>> from eth2spec.utils.ssz.ssz_typing import uint8, uint16, Vector
>>> Vector[uint16, 4](1, 2, 3, 4).encode_bytes().hex()
'0100020003000400'
>>> Vector[uint8, 8](1, 0, 2, 0, 3, 0, 4, 0).encode_bytes().hex()
'0100020003000400'
```

有趣的事實：在 SSZ 規格的早期版本中，向量被稱為[元組](https://github.com/ethereum/consensus-specs/pull/794)（tuple）。

###### 清單

一個清單是一個有序、變長、同質的群集，至多有 `N` 個值。

在 SSZ 規格中，一個清單記為 `List[type, N]`。例如，`List[uint64, 100]` 是一個含有從零到一百個不等之 `uint64` 型別的清單。

清單上的最大長度參數 `N` 在序列化或反序列化中[並未被使用](https://github.com/ethereum/consensus-specs/pull/1180#issuecomment-504169216)。然而，它在 Merkle 化中被使用，尤其使 Merkle 證明產生中的[廣義索引](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/merkle-proofs.md#generalized-merkle-tree-index)成為可能。

[TODO: link to Merkleization and generalised indices]::

當向量與清單被當成獨立的物件來看待時，它們有著相同的序列化：

```python
>>> from eth2spec.utils.ssz.ssz_typing import uint8, List, Vector
>>> List[uint8, 100](1, 2, 3).encode_bytes().hex()
'010203'
>>> Vector[uint8, 3](1, 2, 3).encode_bytes().hex()
'010203'
```

那為什麼不到處都用清單？由於清單在 SSZ 中是變長物件，當被包含在另一個物件之內時，它們的編碼方式與定長向量不同，所以有一點小開銷。容納那個變長清單的容器 `Foo`，在開頭被多編碼了一個四位元組的偏移量。我們稍後一會兒就會看到為什麼。

```python
>>> from eth2spec.utils.ssz.ssz_typing import uint8, Vector, List, Container
>>> class Foo(Container):
...     x: List[uint8, 3]
>>> class Bar(Container):
...     x: Vector[uint8, 3]
>>> Foo(x = [1, 2, 3]).encode_bytes().hex()
'04000000010203'
>>> Bar(x = [1, 2, 3]).encode_bytes().hex()
'010203'
```

###### 位元向量

一個位元向量是一個有序、定長的 `boolean` 值群集，有 `N` 個位元。在 SSZ 規格中，一個位元向量記為 `Bitvector[N]`。

從規格看不明顯，但位元向量使用小端位元格式：

```python
>>> from eth2spec.utils.ssz.ssz_typing import Bitvector
>>> Bitvector[8](0,0,0,0,0,0,0,1).encode_bytes().hex()
'80'
```

位元向量被編碼進「必要的最少整數個位元組」（`N // 8`）中，而如果 `N` 不是 8 的倍數，就在高位元以零填補。

如規格中所提及，在功能上，我們可以用 `Vector[boolean, N]` 或 `Bitvector[N]` 之一來表示一份位元清單。然而，後者在實務上的序列化會短上多達八倍，因為前者每個位元會用一整個位元組。

```python
>>> from eth2spec.utils.ssz.ssz_typing import Vector, Bitvector, boolean
>>> Bitvector[5](1,0,1,0,1).encode_bytes().hex()
'15'
>>> Vector[boolean,5](1,0,1,0,1).encode_bytes().hex()
'0100010001'
```

同樣的考量適用於清單與位元清單。

###### 位元清單

一個位元清單是一個有序、變長的 `boolean` 值群集，至多有 `N` 個位元。在 SSZ 規格中，一個位元清單記為 `Bitlist[N]`。

位元清單[^fn-bitlist-sentinel]一個有意思的特性是，它們使用一個哨兵位元（sentinel bit）來指出清單的長度。位元清單中整數個位元組的數量，很容易從序列化中的偏移量導出，但那並不給我們精確的位元數。例如，在一個樸素的方案中，13 個位元會被序列化進兩個位元組，所以我們只會知道實際的清單長度落在 9 到 16 個位元之間的某處。

[^fn-bitlist-sentinel]: 不過[並非完全](https://github.com/ethereum/consensus-specs/issues/1266)沒有爭議。基本上，如果應用層已經知道它預期的位元清單長度——在 Eth2 中它一般確實知道，因為雖然委員會大小會變動，這些大小卻是已知的——那麼我們原則上就可以免掉那個哨兵位元。

為了解決這個問題，位元清單序列化在清單末端多加一個 `1` 位元（它在小端編碼中成為最高位的位元）。位元清單的確切長度，於是可以藉由忽略任何連續的高位零位元、然後剝掉那單一一個哨兵位元來找出。

舉例來說，這個有三個元素的位元清單被編碼進單一一個位元組。要反序列化這個，我們取以位元計的總長度（八），跳過那四個高位零位元，跳過哨兵位元，然後我們的清單就由剩下的三個位元構成。等價地說，位元清單長度就是序列化中最高 `1` 位元的索引。

```python
>>> from eth2spec.utils.ssz.ssz_typing import Bitlist
>>> Bitlist[100](0,0,0).encode_bytes().hex()
'08'
```

<a id="img_ssz_bitlist"></a>
<figure class="diagram" style="width: 60%">

![一張示意圖，顯示位元清單哨兵如何運作。](images/diagrams/ssz-bitlist.svg)

<figcaption>

哨兵位元指出位元清單的末端。哨兵之外的所有位元都是零。

</figcaption>
</figure>

哨兵的一個後果是：如果一個位元清單的實際長度是八的倍數（不論其最大長度為何），我們就需要一個額外的位元組來序列化它。位元向量則不是這樣。

```python
>>> Bitlist[8](0,0,0,0,0,0,0,0).encode_bytes().hex()
'0001'
>>> Bitvector[8](0,0,0,0,0,0,0,0).encode_bytes().hex()
'00'
```

###### 容器

一個容器是一個有序、異質的值群集。基本上，一個容器可以含有任意混合的型別，包括容器。

我們用 Python 的 `dataclass` 記法、以鍵—型別對來定義容器。例如，這是一個 [`Deposit`](/part3/containers/operations/#deposit) 容器。在接下來的範例中，我在所附的註解裡標示了底層的型別。

```python
class Deposit(Container):
    proof: Vector[Bytes32, DEPOSIT_CONTRACT_TREE_DEPTH + 1] # Vector[Vector[uint8, 32], N]
    data: DepositData
```

這個 `Deposit` 容器含有一個 [`DepositData`](/part3/containers/dependencies/#depositdata) 容器，它的定義如下。

```python
class DepositData(Container):
    pubkey: BLSPubkey                # Bytes48 / Vector[uint8, 48]
    withdrawal_credentials: Bytes32  # Vector[uint8, 32]
    amount: Gwei                     # uint64
    signature: BLSSignature          # Bytes96 / Vector[uint8, 96]
```

我們會在下面的[工作範例](#worked-example)中看到容器如何被序列化。

##### 定長與變長型別

SSZ 區分定長型別與變長型別，並在它們被包含在其他型別之內時以不同的方式對待它們。

  - 變長型別是清單、位元清單、以及任何含有變長型別的型別。
  - 其他一切都是定長的。

當我們序列化一個複合型別時，這項區分很重要。序列化後的輸出如下分兩部分產生。

  1. 定長型別的序列化，連同指向任何變長型別的 32 位元偏移量。
  2. 任何變長型別的序列化。

「定長部分」與「變長部分」之間的這種切分，是先前所描述的偏移量編碼的結果：它允許「在不必反序列化整個東西的情況下，快速存取序列化資料結構中特定的欄位」。

舉例來說，考慮下面這個容器。它有單一一個定長的 `uint8` 型別，後面跟著一個變長的 `List[uint8,10]` 型別，再跟著一個定長的 `uint8`。

```python
>>> from eth2spec.utils.ssz.ssz_typing import uint8, List, Container
>>> class Baz(Container):
...     x: uint8
...     y: List[uint8, 10]
...     z: uint8
>>> Baz(x = 1, y = [2, 3], z = 4).encode_bytes().hex()
'0106000000040203'
```

我們看到，序列化中含有一個出乎意料的 `0x06` 位元組以及一些零位元組。為了看出它們從何而來，我會如下拆解這個輸出，其中第一欄是序列化字串中的位元組編號。

```none
第 1 部分的起點（定長元素）
00 01       - x = uint8(1) 的序列化
01 06000000 - 一個指向位元組 6 的 32 位元偏移量（小端格式），
              即 y 序列化的起點
05 04       - z = uint8(4) 的序列化

第 2 部分的起點（變長元素）
06 0203     - y = List[uint8, N]([2, 3]) 的序列化
```

在第&nbsp;1 部分中，那個變長清單並不直接就地編碼，而是被替換成一個指向它在第&nbsp;2 部分中之序列化的指標（一個偏移量）。所以，對任何容器而言，不論存在哪幾種變長型別，第&nbsp;1 部分的大小都是已知且固定的。變長物件的實際長度，可以從第&nbsp;1 部分中的偏移量、以及序列化字串的整體長度推導出來。

<a id="img_ssz_examples_baz"></a>
<figure class="diagram" style="width:60%">

![Baz 容器序列化的示意圖。](images/diagrams/ssz-examples_Baz.svg)

<figcaption>

`Baz` 容器的序列化。定長部分先做，並為變長的 `List` 資料指定一個偏移量。

</figcaption>
</figure>

不只是容器使用這個格式，它適用於任何含有變長型別的型別。這裡有一個其元素為清單的向量。作為給讀者的練習，我把「解讀這裡發生了什麼事」留給你。

```python
>>> from eth2spec.utils.ssz.ssz_typing import uint8, List, Vector
>>> Vector[List[uint8,3],4]([1,2],[3,4,5],[],[6]).encode_bytes().hex()
'10000000120000001500000015000000010203040506'
```

##### 別名

為求完整，此處直接引用 [SSZ 規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md#aliases)[^fn-ssz-json]：

> 為求方便，我們為下列各項取別名：
>
>   - `bit` 為 `boolean`
>   - `byte` 為 `uint8`（這是一個基本型別）
>   - `BytesN` 與 `ByteVector[N]` 為 `Vector[byte, N]`（這_不_是一個基本型別）
>   - `ByteList[N]` 為 `List[byte, N]`

[^fn-ssz-json]: 當我們開始為 SSZ 資料定義一個[正典 JSON 映射](https://github.com/ethereum/consensus-specs/pull/2983)時，引發了一場關於「把 `byte` 取別名為 `uint8` 是否明智」的有教育意義的討論。「決一死戰」這幾個字被用上了。

在主要的信標鏈規格中，一堆[自訂型別](/part3/config/types/#table_custom_types)也是以標準 SSZ 型別與別名來定義的。例如，`Slot` 是一個 SSZ `uint64` 型別，`BLSPubkey` 是一個 SSZ `Bytes48` 型別，依此類推。

##### 預設值

最後，每個型別都有一個預設值。再一次直接引用 [SSZ 規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md#default-values)：

| 型別 | 預設值 |
| ---- | ------------- |
| `uintN` | `0` |
| `boolean` | `False` |
| `Container` | `[default(type) for type in container]` |
| `Vector[type, N]` | `[default(type)] * N` |
| `Bitvector[N]` | `[False] * N` |
| `List[type, N]` | `[]` |
| `Bitlist[N]` | `[]` |

#### 工作範例

讓我們探索一個工作範例，把這一切匯總起來。比起編造一個合成的物件，我寧願用一個真實的例子，所以我們會看那個被納入[時段 3080831](https://beaconcha.in/slot/3080831#attestations)信標鏈區塊、位於該區塊內第 87 個位置的聚合 `IndexedAttestation`。（它在區塊中實際上會是一個 [`Attestation`](/part3/containers/operations/#attestation) 物件，但那些位元清單很煩瑣，所以我們會看等價的 [`IndexedAttestation`](/part3/containers/dependencies/#indexedattestation)。）

##### 資料結構

[`IndexedAttestation`](/part3/containers/dependencies/#indexedattestation) 容器看起來像這樣。

```python
class IndexedAttestation(Container):
    attesting_indices: List[ValidatorIndex, MAX_VALIDATORS_PER_COMMITTEE]
    data: AttestationData
    signature: BLSSignature
```

It contains an [`AttestationData`](/part3/containers/dependencies/#attestationdata) container,

```python
class AttestationData(Container):
    slot: Slot
    index: CommitteeIndex
    beacon_block_root: Root
    source: Checkpoint
    target: Checkpoint
```

它接著含有兩個 [`Checkpoint`](/part3/containers/dependencies/#checkpoint) 容器，

```python
class Checkpoint(Container):
    epoch: Epoch
    root: Root
```

##### 序列化

現在我們有足夠的資訊來建立 `IndexedAttestation` 物件並計算它的 SSZ 序列化。

```python
from eth2spec.utils.ssz.ssz_typing import *
from eth2spec.capella import mainnet
from eth2spec.capella.mainnet import *

attestation = IndexedAttestation(
    attesting_indices = [33652, 59750, 92360],
    data = AttestationData(
        slot = 3080829,
        index = 9,
        beacon_block_root = '0x4f4250c05956f5c2b87129cf7372f14dd576fc152543bf7042e963196b843fe6',
        source = Checkpoint (
            epoch = 96274,
            root = '0xd24639f2e661bc1adcbe7157280776cf76670fff0fee0691f146ab827f4f1ade'
        ),
        target = Checkpoint(
            epoch = 96275,
            root = '0x9bcd31881817ddeab686f878c8619d664e8bfa4f8948707cba5bc25c8d74915d'
        )
    ),
    signature = '0xaaf504503ff15ae86723c906b4b6bac91ad728e4431aea3be2e8e3acc888d8af'
                + '5dffbbcf53b234ea8e3fde67fbb09120027335ec63cf23f0213cc439e8d1b856'
                + 'c2ddfc1a78ed3326fb9b4fe333af4ad3702159dbf9caeb1a4633b752991ac437'
)

print(attestation.encode_bytes().hex())
```

表示這個 `IndexedAttestation` 物件、所得的序列化資料團是（以十六進位）：

```none
e40000007d022f000000000009000000000000004f4250c05956f5c2b87129cf7372f14dd576fc15
2543bf7042e963196b843fe61278010000000000d24639f2e661bc1adcbe7157280776cf76670fff
0fee0691f146ab827f4f1ade13780100000000009bcd31881817ddeab686f878c8619d664e8bfa4f
8948707cba5bc25c8d74915daaf504503ff15ae86723c906b4b6bac91ad728e4431aea3be2e8e3ac
c888d8af5dffbbcf53b234ea8e3fde67fbb09120027335ec63cf23f0213cc439e8d1b856c2ddfc1a
78ed3326fb9b4fe333af4ad3702159dbf9caeb1a4633b752991ac437748300000000000066e90000
00000000c868010000000000
```

這可以作為一串位元組透過線路傳輸，而在另一端，由於知道它表示一個 `IndexedAttestation`，就能把它重新組成一份相同的副本。

##### 序列化拆解

為了理解這個，我們會把序列化拆解成它的各個部分。第一欄是從位元組字串起點算起的位元組偏移量（以十六進位）。在每一行之前，我標示了它對應到資料結構的哪一部分，並把型別別名翻譯成它們底層的基本 SSZ 型別。記住，所有整數型別都是小端，所以 `7d022f0000000000` 是十六進位數 `0x2f027d`，它十進位是 3080829（即時段編號）。

```none
第 1 部分的起點（定長元素）
   一個指向變長 attestation.attesting_indices（起於 0xe4）的 4 位元組偏移量
00 e4000000

   attestation.data.slot: Slot / uint64
04 7d022f0000000000

   attestation.data.index: CommitteeIndex / uint64
0c 0900000000000000

   attestation.data.beacon_block_root: Root / Bytes32 / Vector[uint8, 32]
14 4f4250c05956f5c2b87129cf7372f14dd576fc152543bf7042e963196b843fe6

   attestation.data.source.epoch: Epoch / uint64
34 1278010000000000

   attestation.data.source.root: Root / Bytes32 / Vector[uint8, 32]
3c d24639f2e661bc1adcbe7157280776cf76670fff0fee0691f146ab827f4f1ade

   attestation.data.target.epoch: Epoch / uint64
5c 1378010000000000

   attestation.data.target.root: Root / Bytes32 / Vector[uint8, 32]
64 9bcd31881817ddeab686f878c8619d664e8bfa4f8948707cba5bc25c8d74915d

   attestation.signature: BLSSignature / Bytes96 / Vector[uint8, 96]
84 aaf504503ff15ae86723c906b4b6bac91ad728e4431aea3be2e8e3acc888d8af
a4 5dffbbcf53b234ea8e3fde67fbb09120027335ec63cf23f0213cc439e8d1b856
c4 c2ddfc1a78ed3326fb9b4fe333af4ad3702159dbf9caeb1a4633b752991ac437

第 2 部分的起點（變長元素）
   attestation.attesting_indices: List[uint64, MAX_VALIDATORS_PER_COMMITTEE]
e4 748300000000000066e9000000000000c868010000000000
```

第一件要注意的事是，`attesting_indices` 清單是變長的，所以它在第&nbsp;1 部分中由一個指向「實際資料所在之處」的偏移量來表示。在這個例子中，是從序列化資料起點算起 `0xe4` 個位元組（228 個位元組）處。清單的實際長度可以這樣計算：整個字串的長度（252 個位元組）減去 228 個位元組（清單的起點），再除以 8 個位元組（每個元素一個）。於是，我們復原了我們那份三個驗證者索引的清單。

其餘所有的項目都是定長的，並就地編碼，包括遞迴地編碼定長的 `AttestationData` 物件、以及它定長的 `Checkpoint` 子物件。

<a id="img_ssz_examples_indexedattestation"></a>
<figure class="diagram" style="width:72%">

![IndexedAttestation 容器序列化的示意圖。](images/diagrams/ssz-examples_IndexedAttestation.svg)

<figcaption>

`IndexedAttestation` 容器的序列化。

</figcaption>
</figure>

##### 多個變長物件

看「一個含有多個變長子物件的容器如何被序列化」很有教育意義。為了這個範例，我們會做一個含有兩個上述 `IndexedAttestation` 物件的 [`AttesterSlashing`](/part3/containers/operations/#attesterslashing) 物件。這是一個刻意造出的範例；這份罰沒舉報並不有效，因為其內容是重複的。

一個 `AttesterSlashing` 容器的定義如下，

```python
class AttesterSlashing(Container):
    attestation_1: IndexedAttestation
    attestation_2: IndexedAttestation
```

我們可以用我們先前定義的 `IndexedAttestation` 物件 `attestation`，如下填充並序列化它。

```python
slashing = AttesterSlashing(
    attestation_1 = attestation,
    attestation_2 = attestation
)

print(slashing.encode_bytes().hex())
```

由此我們得到下面的序列化，同樣在第一欄顯示位元組字串內的位元組偏移量。

```none
第 1 部分的起點（定長元素）
0000 08000000
0004 04010000

第 2 部分的起點（變長元素）
0008 e40000007d022...
0104 e40000007d022...
```

這次我們有兩個變長型別，所以它們都被替換成指向「出現在第 2 部分中的實際變長資料」起點的偏移量。`attestation_1` 的長度被計算為這兩個偏移量之差，而 `attestation_2` 的長度被計算為「從它的偏移量到字串末端」的長度。

另一件要注意的事是，由於 `attestation_1` 與 `attestation_2` 相同，它們在這個複合物件內的序列化也相同，_包括_它們指向自己變長部分的內部偏移量。也就是說，這兩份證明在它們各自的序列化內，都在偏移量 `0xe4` 處有變長資料；這個偏移量是相對於每個子物件序列化的起點、而非整個字串。這個性質簡化了遞迴的序列化與反序列化：一個給定的物件不論被置於什麼情境中，都會有相同的序列化。

<a id="img_ssz_examples_attesterslashing"></a>
<figure class="diagram" style="width:60%">

![AttesterSlashing 容器序列化的示意圖。](images/diagrams/ssz-examples_AttesterSlashing.svg)

<figcaption>

`AttesterSlashing` 容器的序列化。

</figcaption>
</figure>

#### 另見

[SSZ 規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md)是權威來源。也有一份精選的 [SSZ 實作](https://github.com/ethereum/consensus-specs/issues/2138)清單。

圍繞「是否要對共識與 p2p 序列化兩者都使用 SSZ」的歷史討論串，是洞見與智慧的寶庫。

  - 圍繞「該採用哪種序列化方案」[可能是第一場](https://ethresear.ch/t/discussion-p2p-message-serialization-standard/2781?u=benjaminion)實質的討論。它涵蓋了各種替代方案，觸及 p2p 對共識的議題，並把一些所期望的性質演練了一遍。
  - 一場對 [SSZ 的早期討論](https://github.com/ethereum/beacon_chain/issues/94)檢視了一些議題，並引向下面的討論。
  - [僅對共識使用 SSZ 的提案](https://github.com/ethereum/consensus-specs/issues/129)。
  - Piper Merriam 的[《關於序列化你從不想知道的一切》](https://notes.ethereum.org/QF8jgOQbRTWUhK1zoi8D4Q#)至今仍是對許多考量的好總結。

其他 SSZ 資源：

  - Protolambda 所做的 [SSZ 編碼示意圖](https://github.com/protolambda/eth2-docs#ssz-encoding)。
  - SSZ 規格的形式化驗證：[筆記](https://github.com/ConsenSys/eth2.0-dafny/blob/master/wiki/ssz-notes.md)與[程式碼](https://github.com/ConsenSys/eth2.0-dafny/tree/master/src/dafny/ssz)。
  - Raul Jordan 所寫的一份出色的 [SSZ 講解](https://rauljordan.com/go-lessons-from-writing-a-serialization-library-for-ethereum/)，深入探討用 Golang 實作它。（請注意，該文中所引用的特定函式庫現已[被棄用](https://github.com/prysmaticlabs/go-ssz)，改用 [fastssz](https://github.com/ferranbt/fastssz)。）
  - ChainSafe 所做的一個[互動式 SSZ 序列化器／反序列化器](https://simpleserialize.com/)，備有各個共識層升級的所有容器可供擺弄。在「Deserialize」分頁，你可以貼上上方 `IndexedAttestation` 的資料，並驗證它正確地反序列化（你會需要移除換行）。

### 雜湊樹根與 Merkle 化 <!-- /part2/building_blocks/merkleization/ -->

<div class="summary">

  - 一個雜湊樹根提供一個 SSZ 資料結構簡潔的密碼學摘要。
  - 計算雜湊樹根涉及遞迴地 Merkle 化該資料結構。
  - Merkle 化與 [SSZ](/part2/building_blocks/ssz/) 緊密耦合，並在同一份規格中定義。
  - 雜湊樹根的使用，使信標狀態的大部分得以被快取，使得「以一個單體式信標狀態運作」變得實際可行。
  - Eth2 的 Merkle 化做法促成了[廣義索引與 Merkle 證明](/part2/building_blocks/merkle_proofs/)，它們對輕客戶端很重要。

</div>

#### 引言

在討論 [SSZ](/part2/building_blocks/ssz/) 時，我斷言序列化對共識很重要，卻沒有深入細節。在本節中，我們會把那一點展開，並深入探討以太坊&nbsp;2 節點如何知道它們共享一份對世界的看法。

假設你和我想比較我們的信標狀態，看我們是否對鏈的狀態有一份相同的看法。我們可以這麼做的一種方式，是序列化我們各自的信標狀態並把它們寄給對方。然後我們可以逐位元組地比較它們，以檢查它們是否相符。這的問題在於，撰寫本文時序列化後的信標狀態大小超過 41&nbsp;MB，透過網際網路傳輸要花好幾秒。這對一個全域共識協定而言完全不切實際。

我們所需要的是狀態的一個_摘要_（digest）：一份簡短的概述，足以以非常高的把握度判定你和我有沒有相同的狀態、或它們是否不同。這個摘要還必須有一個性質：沒有人能偽造它。也就是說，你不能在實際上有著不同狀態的情況下，說服我你有著與我相同的狀態。

所幸，這樣的摘要以[密碼學雜湊函式](https://en.wikipedia.org/wiki/Cryptographic_hash_function)的形式存在。這些函式取一份（可能）大量的輸入資料，把它攪成少量的位元組（通常是 32 個），就一切實務目的而言唯一地為那份資料指紋化。

有了這樣一個雜湊函式[^fn-hash-function-search]，我們可以改進先前的構想。你和我各自序列化我們的信標狀態，然後雜湊（對……套用雜湊函式）所得的字串。這比把所有資料透過網路寄送快得多。現在我們只需交換並比較我們非常短的 32 位元組雜湊。如果它們相符，那麼我們就有相同的狀態；如果它們不相符，那麼我們的狀態就不同。

[^fn-hash-function-search]: 關於 Eth2 雜湊函式的曲折歷程、以及我們如何最終採用 SHA256，見[註解規格](/part3/helper/crypto/#hash)。

這個過程很常見，並且是以太坊&nbsp;2 中共識用途的一個早期候選者，雖然[相當早](https://github.com/ethereum/consensus-specs/blame/24c8a53b5c7be0248015413b6c0f8586e79d6b67/specs/casper_sharding_v2.1.md#L588)就明朗：可能有更好的方式。

這種做法的一個問題是，如果你修改狀態的任何部分——即使是單一一個位元——你就需要重新計算整個序列化狀態的雜湊。這潛在地是一個龐大的開銷。在規格的早期版本中，這藉由把信標狀態切分成[兩部分](https://github.com/ethereum/consensus-specs/commit/0001b7b9de2bf87ff267547acdb99788cf9b463c#diff-4b26170476a5cef3886e7a1e74bb27a76abf80c7f4c4413d0ad1b47692571b6bR85)來處理：一個變動緩慢、會很少需要重新雜湊的「結晶化」狀態，以及一個較小、變動快速的「活躍」狀態。然而，這種狀態的劃分有點任意，並開始損及設計的[其他部分](https://github.com/ethereum/consensus-specs/pull/122#issuecomment-437170249)。

最終，切分狀態的做法被放棄，改採一種稱為「樹雜湊」（tree hashing）的方法，它建立在一種稱為 Merkle 化[^fn-merkleization-name]的技術之上。本節的其餘部分探索這種做法。

<!-- markdownlint-disable code-block-style -->
[^fn-merkleization-name]: Merkleization 這個名稱源自 [Merkle 樹](https://en.wikipedia.org/wiki/Merkle_tree)，而 Merkle 樹又是以電腦科學家 [Ralph Merkle](https://en.wikipedia.org/wiki/Ralph_Merkle) 命名的。

    不過，我相信「Merkleization」這個名詞是我們的。我採用了[多數](https://web.archive.org/web/20230630135623/https://nitter.it/sina_mahmoodi/status/1266026711512162305)偏好的拼法，那也是進入 [SSZ 規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md#merkleization)的那個版本。儘管我[盡了最大努力](https://web.archive.org/web/20230630135649/https://nitter.it/benjaminion_xyz/status/1266049966163857408)，那個醜陋的版本還是贏了。
<!-- markdownlint-enable code-block-style -->

相較於其他建立信標狀態摘要的方法，樹雜湊帶來兩項重大的優勢。

第一項優勢是效能。表面上，樹雜湊[相當沒有效率](https://github.com/ethereum/consensus-specs/pull/120#issue-378791752)，因為相較於「單純地雜湊整個序列化」的另一種方法，它需要雜湊約兩倍的資料量來計算一個結構的摘要（根）。然而，以太坊&nbsp;2 中雜湊樹被建構的方式，讓我們得以快取「未曾改變之整棵子樹」的根。所以，舉例來說，[依設計](/part2/incentives/balances/#engineering-aspects-of-effective-balance)，狀態中的驗證者記錄清單不會頻繁地改變。結果，我們可以快取那份清單的雜湊樹根，並不需要每次重新計算整個信標狀態根時都重新計算它。整體而言，這個特性使「計算狀態根所需的雜湊總量」大幅減少，並且是「使信標鏈協定在實務上可用」的一個重要部分。

第二項優勢是輕客戶端支援。事實上，實作樹雜湊的[原始動機](https://github.com/ethereum/consensus-specs/issues/54)就只是為了支援輕客戶端。樹雜湊使有效率的 Merkle 證明成為可能，這些證明允許把信標狀態的子集提供給輕客戶端。只要一個輕客戶端以某種方式擁有雜湊樹根，它就能用這些證明來驗證所提供的資料是正確的。

我們會先回顧 Merkle 樹，然後把它們擴充到 Merkle 化，最後再看雜湊樹根的構造，那是我們的終極目標。

##### 術語

SSZ 規格用「Merkleization」一詞同時指稱

  - 給定一棵 Merkle 樹的葉、找出它的根的操作，以及
  - 找出一個 SSZ 物件之雜湊樹根的操作。

為了教學的目的，我選擇更精確地區分這兩者。在接下來的各節中，我會把第一個稱為「Merkle 化」，把第二個稱為「計算一個雜湊樹根」。

有了這些定義，計算一個 SSZ 物件的雜湊樹根會_使用_ Merkle 化，可能用上它的多個步驟，但也涉及諸如打包（packing）、分塊（chunking）、長度混入（length mix-in）等其他步驟。此外，Merkle 化總是處理完整二元樹（葉的數量是二的次方），而雜湊樹根則可以從複雜得多的二元樹結構導出。

#### Merkle 樹

要理解 Merkle 化，我們首先需要理解 [Merkle 樹](https://en.wikipedia.org/wiki/Merkle_tree)。這些一點也不新，可回溯到 1970 年代。

其構想是：我們有一組「葉」，那就是我們的資料，我們透過雜湊把那些葉反覆地約化成單一一個簡短的根。這個約化是藉由把葉成對地雜湊、做出一個「父」節點來完成的。我們對父節點重複這個過程做出祖父節點，依此類推，建出一個以單一一個祖先根為頂點的二元樹結構。在 Merkle 化中，我們只會處理「葉的數量是二的次方」的結構，所以我們有一棵完整二元樹。

在下面的圖中，葉是我們的四個資料團 $A$、$B$、$C$、$D$。這些可以是任何資料字串，雖然在 Merkle 化中它們會是 32 位元組的「分塊」。函式 $H$ 是我們的雜湊函式，而運算子 $+$ 串接字串。所以 $H(A+B)$ 是「字串 $A$ 與 $B$ 串接」的雜湊[^fn-roots-and-leaves]。

[^fn-roots-and-leaves]: 出於某種原因，在電腦科學中，樹傳統上被畫成上下顛倒的。說我古怪也罷，但我喜歡我的樹葉在頂部、根在底部。

<a id="img_merkleization_tree"></a>
<figure class="diagram" style="width:80%">

![一棵 Merkle 樹的示意圖。](images/diagrams/merkleization-tree.svg)

<figcaption>

一棵 Merkle 樹的範例。

</figcaption>
</figure>

在 Eth2 的實作中，圖中的每個方塊都是一個 32 位元組的資料字串：要嘛是一個 32 位元組的葉，要嘛是雜湊函式 32 位元組的輸出。於是，我們得到樹的 32 位元組根，它是由那些葉所表示之資料的一個「摘要」。這個根唯一地表示那些葉中的資料；葉中的任何改變都導致一個不同的根。

這裡同樣的東西又一次在 Python REPL 上，把葉值指派為 $A=1$、$B=2$、$C=3$、$D=4$。我們從葉開始建構樹的根，往下穿過它的各層，直到抵達根 $H(H(A + B) + H(C + D))$。請注意，所有的葉值都被填補到 32 位元組，並且是小端的（依它們的 SSZ 序列化）。

```python
>>> from eth2spec.utils.ssz.ssz_typing import uint256
>>> from eth2spec.utils.hash_function import hash
>>> a = uint256(1).to_bytes(length = 32, byteorder='little')
>>> b = uint256(2).to_bytes(length = 32, byteorder='little')
>>> c = uint256(3).to_bytes(length = 32, byteorder='little')
>>> d = uint256(4).to_bytes(length = 32, byteorder='little')
>>> ab = hash(a + b)
>>> cd = hash(c + d)
>>> abcd = hash(ab + cd)
>>> abcd.hex()
'bfe3c665d2e561f13b30606c580cb703b2041287e212ade110f0bfd8563e21bb'
```

Merkle 樹的構造是計算一堆資料（例如一個區塊鏈狀態）之摘要的一種相當常見的方式。以太坊&nbsp;1 使用這的一個更精巧的版本，稱為十六元 Merkle–Patricia 字典樹（trie）（在 Eth1 中由於[複雜的原因](https://en.wikipedia.org/wiki/Trie)，它是「trie」而非「tree」），雖然有提案打算[簡化那個](https://eips.ethereum.org/EIPS/eip-3102)。

Merkle 樹一個極為有用的特性是，用它們來構造納入證明相當有效率。這對輕客戶端是關鍵性的功能，等我們看 [Merkle 證明](/part2/building_blocks/merkle_proofs/)時，我們會深入討論它。

#### Merkle 化

實作一棵 Merkle 樹的一般方式，是把整個樹結構儲存在記憶體或磁碟中，包括葉與根之間所有的中間層。隨著葉被更新，樹中受影響的節點也被更新：改變 $A$ 意味著更新 $H(A+B)$、然後更新根，其他一切都不變。

Merkle 化的不同之處在於：那棵 Merkle 樹是從給定的葉即時計算出來的。我們可以如下從上一場 REPL 工作階段停下的地方接續。

```python
>>> from eth2spec.utils.merkle_minimal import merkleize_chunks
>>> merkleize_chunks([a, b, c, d]).hex()
'bfe3c665d2e561f13b30606c580cb703b2041287e212ade110f0bfd8563e21bb'
```

Merkle 化函式（在 SSZ 規格中稱為 `merkleize()`，在可執行規格中稱為 [`merkleize_chunks()`](https://github.com/ethereum/consensus-specs/blob/v1.3.0/tests/core/pyspec/eth2spec/utils/merkle_minimal.py#L47)）取一份 32 位元組分塊的清單，並回傳「以那些分塊為葉之樹」的根。

傳給 `merkleize_chunks()` 的分塊清單可以是任何長度，但會被零分塊填補，使得分塊的總數被向上捨入到下一個完整的二的次方，使得我們在概念上有一棵完整二元樹。於是，一份三個分塊的清單會被隱含地以一個額外的零分塊填補：

```python
>>> z = bytearray(32)
>>> merkleize_chunks([a, b, c]).hex()
'66c419026fee8793be7fd0011b9db46b98a79f9c9b640e25317865c358f442db'
>>> merkleize_chunks([a, b, c, z]).hex()
'66c419026fee8793be7fd0011b9db46b98a79f9c9b640e25317865c358f442db'
```

可以把一個較大的樹寬作為參數提供給 `merkleize_chunks()`，那份清單就會據此被零分塊填補。這項能力在處理清單與位元清單時被使用。

```python
>>> merkleize_chunks([a]).hex()
'0100000000000000000000000000000000000000000000000000000000000000'
>>> merkleize_chunks([a], 4).hex()
'553c8ccfd20bb4db224b1ae47359e9968a5c8098c15d8bf728b19e55749c773b'
>>> merkleize_chunks([a, z, z, z]).hex()
'553c8ccfd20bb4db224b1ae47359e9968a5c8098c15d8bf728b19e55749c773b'
```

一個實作可以「虛擬地」做這個零填補，並可以藉由預先計算零分塊各層的雜湊——$H(0 + 0)$、$H(H(0 + 0) + H(0 + 0))$，依此類推——來進一步最佳化。如此一來，我們不總是需要建出整棵樹來找出 Merkle 根。

請注意，單一一個分塊的 Merkle 化永遠就只是那個分塊本身。這減少了所需的雜湊總量。

#### 雜湊樹根

雜湊樹根是 Merkle 化的一個推廣，我們可以把它套用在「我們在信標狀態中所擁有那種複雜的複合資料結構」上。計算雜湊樹根與[簡易序列化](/part2/building_blocks/ssz/)的型別方案緊密相連。

計算一個 SSZ 物件的雜湊樹根是遞迴的。給定一個複合 SSZ 物件，我們反覆地穿過它結構的各層，直到我們抵達一個「我們可以打包成分塊並直接 Merkle 化」的基本型別或基本型別的群集。然後我們穿回該結構，把所計算出的雜湊樹根本身當成分塊使用。

計算一個雜湊樹根的過程在[簡易序列化規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md#merkleization)中定義，要看完整的細節就去那裡。然而，以簡化的形式來說（再一次忽略 SSZ 聯集型別），在找出一個物件的雜湊樹根時，基本上有兩條路徑可選。

  - 對於基本型別、或基本型別的群集（清單與向量），我們就直接打包並 Merkle 化。
  - 對於容器、以及複合型別的群集，我們遞迴地找出其內容的雜湊樹根。

下面兩條規則是[規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md#merkleization)中所列前六條規則的一個簡化總結。

 1. 如果 `X` 是一個 SSZ 基本物件、基本物件的清單或向量、或一個位元清單或位元向量，那麼 `hash_tree_root(X) = merkleize_chunks(pack(X))`。`pack()` 函式回傳一份可以直接 Merkle 化的分塊清單。
 2. 如果 `X` 是一個 SSZ 容器、或複合物件的向量或清單，那麼雜湊樹根就遞迴地計算，`hash_tree_root(X) = merkleize_chunks([hash_tree_root(x) for x in X])`。那個串列生成式是一份雜湊樹根的清單，等價於一份分塊清單。

我們會在下面的[工作範例](#worked-example)中看到這兩條規則大量的具體應用。

##### 打包與分塊

Merkle 化作用於「分塊」清單之上，分塊是 32 位元組的資料團。藉由上述步驟 2 所產生的清單已經是這種形式。然而，步驟 1 涉及基本物件，它們需要在 Merkle 化之前進行一次「打包與分塊」操作。

[規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md#merkleization)給出了精確的規則，但它基本上看起來像這樣：

  - 該物件（一個基本型別、基本型別的清單／向量、或一個位元清單／位元向量）透過 SSZ 被序列化。哨兵位元被從位元清單型別的序列化中省略。
  - 該序列化被零位元組向右填補，直到下一個完整的分塊（32 位元組邊界）。
  - 結果被切分成一份 32 位元組分塊的清單。
  - 如有必要，會附加更多（虛擬的）零分塊，以達到下列的總長度（只有清單與位元清單可能實際需要額外的填補）：
    - 所有基本型別都給出單一一個分塊；沒有基本型別的序列化長於 32 位元組。
    - `Bitlist[N]` 與 `Bitvector[N]`：`(N + 255) // 256`（除以以位元計的分塊大小並向上捨入）
    - `List[B, N]` 與 `Vector[B, N]`，其中 `B` 是一個基本型別：`(N * size_of(B) + 31) // 32`（除以以位元組計的分塊大小並向上捨入）

由規則 2 所產生的容器與複合物件，會有下列數量的分塊，包括清單在需要時的零分塊填補。

  - `List[C, N]` 與 `Vector[C, N]`，其中 `C` 是一個複合型別：`N`，因為 Merkle 化由 `N` 個雜湊樹根構成。
  - 容器：`len(fields)`，因為容器中每個欄位有一個雜湊樹根。

「清單與位元清單為何被零分塊填補到它們完整的最大長度（即使這些是『虛擬』分塊）」並不立即顯而易見。然而，這使廣義索引的使用成為可能，廣義索引提供了「針對雜湊樹根建立 Merkle 證明」的一種一致方式，那是我們[下一節](/part2/building_blocks/merkle_proofs/)的主題。

回想一下，除了此處所加的任何填補之外，Merkle 化過程還會進一步以零分塊填補那份清單，使它的長度成為二的次方。

##### 混入長度

我們希望「型別相同但內容不同」的物件有著不同的雜湊樹根。這給清單帶來一個問題。考慮三個元素的清單 `a`，以及清單 `b`（它是相同的三個元素、外加末端的第四個零元素）。這些是型別相同的不同清單，但兩者都 Merkle 化成相同的值。

```python
>>> from eth2spec.utils.ssz.ssz_typing import uint256, List
>>> from eth2spec.utils.merkle_minimal import merkleize_chunks
>>> a = List[uint256, 4](1, 2, 3).encode_bytes()
>>> b = List[uint256, 4](1, 2, 3, 0).encode_bytes()
>>> merkleize_chunks([a[0:32], a[32:64], a[64:96]])
0x66c419026fee8793be7fd0011b9db46b98a79f9c9b640e25317865c358f442db
>>> merkleize_chunks([b[0:32], b[32:64], b[64:96], b[96:128]])
0x66c419026fee8793be7fd0011b9db46b98a79f9c9b640e25317865c358f442db
```

我們需要確保「一個以零值結尾的清單」與「沒有那個零值的相同清單」有著不同的雜湊樹根。為了做到這一點，我們讓清單（與位元清單）經過一道額外的 `mix_in_length()` 過程，它涉及雜湊「清單的 Merkle 根與清單長度的串接」。這等價於兩個分塊的 Merkle 化，第一個是清單的 Merkle 根，第二個是它的長度。

關於這在實務上的一個例證，見下面 `attesting_indices` 的[示意圖](#img_merkleization_attestingindices)。

位元清單需要類似的處理，因為我們在 Merkle 化之前移除了哨兵位元。

#### 摘要與展開

SSZ 規格描述了 Merkle 化的一些特性，稱為[摘要與展開](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md#summaries-and-expansions)（summaries and expansions）。這些不是 Merkle 化的明示函式，而是作為設計的後果隱含地產生。

簡單地說，在過程中的任何地方，一整個 SSZ 物件都可以被替換成它的雜湊樹根，而不影響最終的結果。

我們以若干方式利用這一點。首要的是「快取狀態中任何未曾改變部分之雜湊樹根」的能力，它使「在需要時重新計算整個狀態的雜湊樹根」變得實際可行。例如，如果一個驗證者記錄未曾改變，我們在找出驗證者註冊表的根時，就不需要重新計算它的雜湊樹根。如果驗證者註冊表未曾改變，我們在計算完整狀態根時，就不需要重新計算它的雜湊樹根。

作為另一個例子，考慮 [`BeaconBlock`](/part3/containers/blocks/#beaconblock) 與 [`BeaconBlockHeader`](/part3/containers/dependencies/#beaconblockheader) 型別。

```python
class BeaconBlock(Container):
    slot: Slot
    proposer_index: ValidatorIndex
    parent_root: Root
    state_root: Root
    body: BeaconBlockBody

class BeaconBlockHeader(Container):
    slot: Slot
    proposer_index: ValidatorIndex
    parent_root: Root
    state_root: Root
    body_root: Root
```

這兩者只在它們最後的欄位上不同，分別是 `body` 與 `body_root`。如果 `body_root` 是 `BeaconBlockBody`（即 `body`）的雜湊樹根，那麼這兩個物件就會有著完全相同的雜湊樹根。`BeaconBlock` 是 `BeaconBlockHeader` 的展開型別；`BeaconBlockHeader` 是 `BeaconBlock` 的一個摘要型別。[提議者罰沒](/part3/containers/operations/#proposerslashing)舉報利用這個事實來節省空間，方式是把區塊主體剝除、並以它們的雜湊樹根取代。

Flashbots 的 [MEV-Boost](https://ethresear.ch/t/mev-boost-merge-ready-flashbots-architecture/11177?u=benjaminion) 設計也利用了這項能力。在 MEV-Boost 系統中，驗證者被要求簽署「盲化區塊」（blinded block）。也就是它們沒有主體的區塊。由於標頭是該區塊的一個摘要（以我們此處所用「摘要」一詞的意義），同一份簽章對 `BeaconBlockHeader` 與對應的完整 `BeaconBlock` 兩者都會有效。這簡化了協定的設計。

#### 工作範例

對於本節的工作範例，我們會重訪我們的老朋友 [`IndexedAttestation`](/part3/containers/dependencies/#indexedattestation)。這給了我們 Merkle 化複合型別、清單型別、向量型別的好例子，也示範了摘要與展開。

回想一下，`IndexedAttestation` 型別的定義如下，

```python
class IndexedAttestation(Container):
    attesting_indices: List[ValidatorIndex, MAX_VALIDATORS_PER_COMMITTEE]
    data: AttestationData
    signature: BLSSignature
```

我們會就像[先前](/part2/building_blocks/ssz/#the-serialisation)所做的那樣建立這的一個實例，只是為求簡潔，我會把它稱為 `a`、而非 `attestation`。我們想計算這個 `IndexedAttestation`（即 `a`）的雜湊樹根。

一個容器的雜湊樹根，是「它所含物件之雜湊樹根清單」的 Merkle 化（依規則 2）。以圖來說，我們正在建出下面這棵樹並找出它的根。

<a id="img_merkleization_indexedattestation"></a>
<figure class="diagram" style="width:60%">

![一張示意圖，顯示如何計算一個 IndexedAttestation 型別的雜湊樹根。](images/diagrams/merkleization-IndexedAttestation.svg)

<figcaption>

計算一個 `IndexedAttestation` 的雜湊樹根。在這張與接下來的圖中，$R(X)$ 是 $X$ 的 Merkle 化，$S(X)$ 是 $X$ 的 SSZ 序列化。每個方塊是一個 32 位元組分塊，而那些小數字是 Merkle 化操作中葉的數量。

</figcaption>
</figure>

或者，以程式碼來說，我們有下列的東西。

```python
assert(a.hash_tree_root() == merkleize_chunks(
    [
        a.attesting_indices.hash_tree_root(),
        a.data.hash_tree_root(),
        a.signature.hash_tree_root()
    ]))
```

[`merkleize_chunks()`](https://github.com/ethereum/consensus-specs/blob/v1.3.0/tests/core/pyspec/eth2spec/utils/merkle_minimal.py#L47) 函式由 `merkle_minimal.py` 函式庫提供。我們可以直接套用這個函式，因為清單中的雜湊樹根已經構成分塊。（我們也可以用 [`get_merkle_root()`](https://github.com/ethereum/consensus-specs/blob/v1.3.0/tests/core/pyspec/eth2spec/utils/merkle_minimal.py#L30) 函式，但那樣我們就得指定一個值為 4 的 `pad_to`，才能得到正確深度的樹。）

##### `attesting_indices` 根

往下走過清單的成員，我們需要 `attesting_indices` 物件的雜湊樹根，它有型別 `List[ValidatorIndex, MAX_VALIDATORS_PER_COMMITTEE]`。這是一份基本型別的清單，也就是 `uint64`，因為那是 [`ValidatorIndex`](/part3/config/types/#table_custom_types) 的型別，於是規則 1 適用。

我們的 `attesting_indices` 清單有三個元素 `[33652, 59750, 92360]`，我們需要把它分塊並填補。首先我們照常用 SSZ 序列化這份清單，然後把它填補到 32 位元組：

```python
>>> serialize(a.attesting_indices).hex()
'748300000000000066e9000000000000c868010000000000'
>>> (serialize(a.attesting_indices) + bytearray(8)).hex()
'748300000000000066e9000000000000c8680100000000000000000000000000'
```

這給了我們第一個分塊。然而，我們所需分塊的完整數量是 `2048 // 4 = 512`（`MAX_VALIDATORS_PER_COMMITTEE` 除以每個分塊的 `uint64` 數），所以我們必須加上 511 個零分塊。實務上這個填補是「虛擬地」完成的。`merkleize_chunks()` 函式讓我們得以指定完整的分塊數，並負責加上多出來的那些。在幕後，它正在建立一棵以我們的 512 個分塊為葉、深十層的 Merkle 樹，並回傳該樹的根。

```python
>>> merkleize_chunks([serialize(a.attesting_indices) + bytearray(8)], 512).hex()
'04e3bf0951474a6b06dd506648fdf8e84866542614e1c14fa832cd4bebfda0e3'
```

如果這是一個向量，那麼我們的工作就完成了。然而，在處理清單時，還有一個小小的眉角：作為最後一步，我們需要把我們所有的根與清單的實際長度串接起來，並把它們一起雜湊。這就是[上文](#mixing-in-the-length)所描述的 `mix_in_length()` 函式，我們在此藉由把「清單的 Merkle 根」與「清單的長度」一起 Merkle 化來實作它。

```python
assert(a.attesting_indices.hash_tree_root() ==
       merkleize_chunks(
           [
               merkleize_chunks([a.attesting_indices.encode_bytes() + bytearray(8)], 512),
               a.attesting_indices.length().to_bytes(32, 'little')
           ]))
```

以圖的形式來說，這份清單的雜湊樹根計算看起來像這樣。

<a id="img_merkleization_attestingindices"></a>
<figure class="diagram" style="width:60%">

![一張示意圖，顯示如何計算一個 List 型別的雜湊樹根。](images/diagrams/merkleization-AttestingIndices.svg)

<figcaption>

計算 `attesting_indices` 的雜湊樹根。這是一個 `List[uint256, 2048]` 型別，而我們的範例清單有三個元素，構成單一一個分塊。注意套用於清單的那個額外的 `mix_in_length()` 步驟。

</figcaption>
</figure>

##### `data` 根

`IndexedAttestation` 的 `data` 欄位是另一個容器，一個 [`AttestationData`](/part3/containers/dependencies/#attestationdata) 物件，定義為，

```python
class AttestationData(Container):
    slot: Slot
    index: CommitteeIndex
    beacon_block_root: Root
    source: Checkpoint
    target: Checkpoint
```

如同之前，要找出一個容器的雜湊樹根，依規則 2 我們需要「它所含各根」的根。也就是說，

```python
assert(a.data.hash_tree_root() == merkleize_chunks(
    [
        a.data.slot.hash_tree_root(),
        a.data.index.hash_tree_root(),
        a.data.beacon_block_root.hash_tree_root(),
        a.data.source.hash_tree_root(),
        a.data.target.hash_tree_root()
    ]))
```

`Slot` 與 `CommitteeIndex` 就只是基本的 `uint64` 型別。它們的雜湊樹根就是它們的小端 256 位元表示。

```python
>>> a.data.slot.hash_tree_root().hex()
'7d022f0000000000000000000000000000000000000000000000000000000000'
>>> a.data.index.hash_tree_root().hex()
'0900000000000000000000000000000000000000000000000000000000000000'
```

`Root` 是 `Bytes32` 型別，它等價於一個 `Vector[unit8, 32]`。方便的是，雜湊樹根就只是 `Root` 值本身，因為它只是單一一個分塊。

```python
>>> a.data.beacon_block_root.hex()
'4f4250c05956f5c2b87129cf7372f14dd576fc152543bf7042e963196b843fe6'
>>> a.data.beacon_block_root.hash_tree_root().hex()
'4f4250c05956f5c2b87129cf7372f14dd576fc152543bf7042e963196b843fe6'
```

`source` 與 `target` 又一次是容器，兩者都有型別 [`Checkpoint`](/part3/containers/dependencies/#checkpoint)。以我們所擁有的知識，`Checkpoint` 型別 Merkle 化起來很簡單。所以，把一切湊在一起，我們可以如下手工找出 `data` 欄位的雜湊樹根。

```python
assert(a.data.hash_tree_root() == merkleize_chunks(
    [
        a.data.slot.to_bytes(32, 'little'),
        a.data.index.to_bytes(32, 'little'),
        a.data.beacon_block_root,
        merkleize_chunks([a.data.source.epoch.to_bytes(32, 'little'), a.data.source.root]),
        merkleize_chunks([a.data.target.epoch.to_bytes(32, 'little'), a.data.target.root])
    ]))
```

<a id="img_merkleization_attestationdata"></a>
<figure class="diagram" style="width:80%">

![一張示意圖，顯示如何計算一個 AttestationData 型別的雜湊樹根。](images/diagrams/merkleization-AttestationData.svg)

<figcaption>

計算一個 `AttestationData` 容器的雜湊樹根。它接著含有兩個 `Checkpoint` 容器 `source` 與 `target`。

</figcaption>
</figure>

##### `signature` 根

我們需要處理的 `IndexedAttestation` 最後一部分，是 `signature` 欄位。這是 `Signature` 型別，它是一個 `Vector[uint8, 96]`，於是規則 1 適用。這 Merkle 化起來很簡單，因為它打包之後恰好是三個分塊。`merkleize_chunks()` 函式負責加上單一一個虛擬零分塊，使葉的數量成為二的次方。

```python
assert(a.signature.hash_tree_root() ==
       merkleize_chunks([a.signature[0:32], a.signature[32:64], a.signature[64:96]]))
```

<a id="img_merkleization_signature"></a>
<figure class="diagram" style="width:60%">

![一張示意圖，顯示如何計算一個 Signature 型別的雜湊樹根。](images/diagrams/merkleization-Signature.svg)

<figcaption>

計算一個 `Signature`（它其實是一個 `Bytes96`、或 `Vector[uint8, 96]` 型別）的雜湊樹根。

</figcaption>
</figure>

#### 把這一切湊在一起

把所有這些部分組裝起來，我們可以同時以圖的形式與程式碼的形式，說明 `IndexedAttestation` 的雜湊樹根如何透過 Merkle 化的反覆套用、從底層基本型別的序列化計算出來。

##### 完整的全貌

<a id="img_merkleization_indexedattestation_all"></a>
<figure class="diagram" style="width:100%">

![一張示意圖，顯示如何計算一個 IndexedAttestation 型別之雜湊樹根的完整全貌。](images/diagrams/merkleization-IndexedAttestation_all.svg)

<figcaption>

說明計算一個 `IndexedAttestation` 的雜湊樹根所需的步驟。那些小數字是每次 Merkle 化操作中葉的數量。

</figcaption>
</figure>

##### 完整的程式碼

下面的程式碼說明了工作範例中的所有要點。你可以藉由如[附錄](/appendices/running/)中所描述設置好可執行規格來運行它。如果一切順利，它唯一應該印出的東西是 `Success!`。

```python
from eth2spec.capella import mainnet
from eth2spec.capella.mainnet import *
from eth2spec.utils.ssz.ssz_typing import *
from eth2spec.utils.merkle_minimal import merkleize_chunks

# Initialise an IndexedAttestation type
a = IndexedAttestation(
    attesting_indices = [33652, 59750, 92360],
    data = AttestationData(
        slot = 3080829,
        index = 9,
        beacon_block_root = '0x4f4250c05956f5c2b87129cf7372f14dd576fc152543bf7042e963196b843fe6',
        source = Checkpoint (
            epoch = 96274,
            root = '0xd24639f2e661bc1adcbe7157280776cf76670fff0fee0691f146ab827f4f1ade'
        ),
        target = Checkpoint(
            epoch = 96275,
            root = '0x9bcd31881817ddeab686f878c8619d664e8bfa4f8948707cba5bc25c8d74915d'
        )
    ),
    signature = '0xaaf504503ff15ae86723c906b4b6bac91ad728e4431aea3be2e8e3acc888d8af'
                + '5dffbbcf53b234ea8e3fde67fbb09120027335ec63cf23f0213cc439e8d1b856'
                + 'c2ddfc1a78ed3326fb9b4fe333af4ad3702159dbf9caeb1a4633b752991ac437'
)

# A container's root is the merkleization of the roots of its fields.
# This is IndexedAttestation.
assert(a.hash_tree_root() == merkleize_chunks(
    [
        a.attesting_indices.hash_tree_root(),
        a.data.hash_tree_root(),
        a.signature.hash_tree_root()
    ]))

# A list is serialised then (virtually) padded to its full number of chunks before Merkleization.
# Finally its actual length is mixed in via a further hash/merkleization.
assert(a.attesting_indices.hash_tree_root() ==
       merkleize_chunks(
           [
               merkleize_chunks([a.attesting_indices.encode_bytes() + bytearray(8)], 512),
               a.attesting_indices.length().to_bytes(32, 'little')
           ]))

# A container's root is the merkleization of the roots of its fields.
# This is AttestationData.
assert(a.data.hash_tree_root() == merkleize_chunks(
    [
        a.data.slot.hash_tree_root(),
        a.data.index.hash_tree_root(),
        a.data.beacon_block_root.hash_tree_root(),
        a.data.source.hash_tree_root(),
        a.data.target.hash_tree_root()
    ]))

# Expanding the above AttestationData roots by "manually" calculating the roots of its fields.
assert(a.data.hash_tree_root() == merkleize_chunks(
    [
        a.data.slot.to_bytes(32, 'little'),
        a.data.index.to_bytes(32, 'little'),
        a.data.beacon_block_root,
        merkleize_chunks([a.data.source.epoch.to_bytes(32, 'little'), a.data.source.root]),
        merkleize_chunks([a.data.target.epoch.to_bytes(32, 'little'), a.data.target.root]),
    ]))

# The Signature type has a simple Merkleization.
assert(a.signature.hash_tree_root() ==
       merkleize_chunks([a.signature[0:32], a.signature[32:64], a.signature[64:96]]))

# Putting everything together, we have a "by-hand" Merkleization of the IndexedAttestation.
assert(a.hash_tree_root() == merkleize_chunks(
    [
        # a.attesting_indices.hash_tree_root()
        merkleize_chunks(
            [
                merkleize_chunks([a.attesting_indices.encode_bytes() + bytearray(8)], 512),
                a.attesting_indices.length().to_bytes(32, 'little')
            ]),
        # a.data.hash_tree_root()
        merkleize_chunks(
            [
                a.data.slot.to_bytes(32, 'little'),
                a.data.index.to_bytes(32, 'little'),
                a.data.beacon_block_root,
                merkleize_chunks([a.data.source.epoch.to_bytes(32, 'little'), a.data.source.root]),
                merkleize_chunks([a.data.target.epoch.to_bytes(32, 'little'), a.data.target.root]),
            ]),
        # a.signature.hash_tree_root()
        merkleize_chunks([a.signature[0:32], a.signature[32:64], a.signature[64:96]])
    ]))

print("Success!")
```

#### 另見

Alin Tomescu 所寫的[《什麼是 Merkle 樹？》](https://decentralizedthoughts.github.io/2020-12-22-what-is-a-merkle-tree/)，是我所找到關於 Merkle 樹最好的入門讀物，如果你不確定它們的構造與性質，它是一個很棒的起點。

[SSZ 規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md)是 Merkle 化以及序列化的權威來源。許多 [SSZ 實作](https://github.com/ethereum/consensus-specs/issues/2138)也包含 Merkle 化。

已進行過一次 Merkle 化的形式化驗證：[筆記](https://github.com/ConsenSys/eth2.0-dafny/blob/master/wiki/merkleise-notes.md)與[程式碼](https://github.com/ConsenSys/eth2.0-dafny/tree/master/src/dafny/merkle)。

[Remerkleable](https://github.com/protolambda/remerkleable) 函式庫是一個 Python 實作，它引入了一些更進階的工具，例如為資料結構而設的支撐樹（backing tree）。[Ztyp](https://github.com/protolambda/ztyp) 是對支撐樹的進一步探索。支撐樹是「在客戶端實作內部表示並維護信標狀態」的一種有用做法。

[TODO: Link to backing trees section when done]::

鑑於 Merkle 化期間所做的雜湊類型有限（總是雜湊兩個 32 位元組字串的串接），值得探究是否有特定的效能最佳化可用。Potuz 製作了一個經最佳化的函式庫 [Hashtree](https://github.com/prysmaticlabs/hashtree)，用於 Merkle 樹計算，它利用了這一點。

### 廣義索引與 Merkle 證明 <!-- /part2/building_blocks/merkle_proofs/* -->

TODO

### 同步委員會 <!-- /part2/building_blocks/sync_committees/* -->

TODO

## 網路 <!-- /part2/networking/* -->

### 引言

TODO

### 探索

TODO

### 流言

TODO

### RPC

TODO

### 同步

TODO

### 訊息類型

TODO

## 實作 <!-- /part2/implementation/* -->

### 引言

TODO

### Protoarray

TODO

### SSZ 支撐樹

TODO

### 批次簽章驗證

TODO

### 罰沒保護

TODO

### 檢查點同步

TODO

# 第 3 部：註解規格 <!-- /part3/ -->

## 引言 <!-- /part3/introduction/ -->

信標鏈規格是機器的五臟六腑。就像電腦的內臟，所有元件都裸露在外、線路懸垂著：一切都攤開來展示。在接下來各節的過程中，我會逐行剖析整份核心信標鏈規格。我的目標不只是解釋事情如何運作，也要給出一些歷史背景：我們如何走到今天這一步背後的一些理路。

規格的[早期版本](https://github.com/ethereum/consensus-specs/blob/86ec833172704ea0889b5d595d17f45ba1a6676f/specs/core/0_beacon-chain.md)寫得比今天的有著多得多的敘事與解釋。隨著時間推移，為了更高的精確度以及「可執行」的好處，它們被以 Python 寫成程式碼。然而，在那個過程中，大部分的解釋與直覺都被移除了。[^fn-justinification] Vitalik 建立了他自己的[註解規格](https://github.com/ethereum/annotated-spec)，涵蓋了許多關鍵的洞見。要與 Vitalik 競爭很難，但我在此的用意是在徹底性與細節上更深一層。或許也提供一個獨立的視角。

[^fn-justinification]: 一個稱為「Justin 化」（Justinification）的過程。懂的就懂 `;-)`

隨著本書的其他部分陸續寫成，我會加上通往各主題特定章節（例如關於簡易序列化、共識、網路的章節）的連結。

請注意，這份線上的註解規格有兩種形式可用：

  - 分成各章節，在主書的[第 3 部](/part3/)中，以及
  - 作為一個獨立的[單一頁面](/annotated-spec/)，便於搜尋。

兩者的內容完全相同。

### 版本資訊

這一版的《升級以太坊》以信標鏈規格的 Capella 版本為基礎，對應於 2023 年 4 月 18 日所做的 [v1.3.0 發行版](https://github.com/ethereum/consensus-specs/releases/tag/v1.3.0)。

並沒有單一一份規格文件涵蓋 Capella。相反地，我們有 [Phase&nbsp;0 規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/beacon-chain.md)、[Altair 規格變更](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/beacon-chain.md)、[Bellatrix 規格變更](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/bellatrix/beacon-chain.md)、以及 [Capella 規格變更](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/capella/beacon-chain.md)。每一份都以一種文字式 diff 的方式建構在前一個版本之上。此外，這些文件在升級之間並不穩定。例如，Phase&nbsp;0 規格作為 Capella 發行版的一部分[被更新了](https://github.com/ethereum/consensus-specs/compare/v1.2.0..v1.3.0#diff-0e824f6ab9ff551699ddf9d108c0b3705ce41e2bd72f68c7f1f32269e58f0bdf)。這一切可能相當令人困惑、難以追蹤。

為了讓整件事在本章中更容易理解，我把迄今所有的規格整合在一起，（大多）省略了已被取代的部分[^fn-superseded-parts]。一般而言，我試著反映這些文件既有的結構，以便讓它們更容易與原始規格並列閱讀。然而，我把獨立的 [BLS](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/bls.md) 文件納入了本文的流程中。

[^fn-superseded-parts]: 如[前言](/preface/#versions)中所描述，你仍然可以找到舊版本。

#### 另見

除了上述所引用的規格文件之外，還存在其他幾份當前與歷史的文件。

  - Vitalik 的[註解規格](https://github.com/ethereum/annotated-spec)，涵蓋 Phase&nbsp;0、Altair、合併以及更遠。
  - [《Serenity 設計原理》](https://notes.ethereum.org/@vbuterin/rkhCgQteN)
  - [《給人類的 Phase 0〔v0.10.0〕》](https://notes.ethereum.org/@djrtwo/Bkn3zpwxB)
  - [《Phase 0 設計筆記》](https://notes.ethereum.org/@JustinDrake/rkPjB1_xr)（Justin Drake）
  - 我自己的 [Phase&nbsp;0 註解規格](https://benjaminion.xyz/eth2-annotated-spec/phase0/beacon-chain/)仍可供歷史趣味之用。

王曉薇在 Devcon VI 就共識 Pyspec 做了一場[閃電演講](https://archive.devcon.org/archive/watch/6/how-to-use-executable-consensus-pyspec/)，簡短地描述了它的結構以及它如何能被執行。

## 型別、常數、預設值與設定 <!-- /part3/config/ -->

### 前言

對某些人而言，一章談常數、預設值與參數的內容，會顯得比納米布沙漠還乾燥，但我長久以來都發現這些是進入「我們在後面各章會詳細拆解之構想與機制」一條豐富而肥沃的入口。這部分的規格遠非沙漠，而是充滿生機。

基礎以一組自訂資料型別奠定。信標鏈規格在 Python 中是可執行的；規格頂端所定義的資料型別代表那些將會頻繁再現的基本量。

然後——藉由常數、預設值與參數——我們會檢視那些定義並約束鏈行為的數字。這些量每一個都訴說著一個故事。每一個參數都封裝著一個洞見、或一個機制、或一個折衷。它為什麼在這裡？它隨時間如何改變？它的值從何而來？

### 自訂型別 <!-- /part3/config/types/ -->

規格定義了下列 Python 自訂型別，「用於型別提示與可讀性」：此處所定義的資料型別在整份規格中頻繁出現；它們是其他一切的構成要素。

每個型別都有一個名稱、一個「SSZ 等價物」、以及一段描述。[SSZ](/part2/building_blocks/ssz/) 是用於（在客戶端之間傳遞資料等等的）編碼方法。在這裡，它可以就被想成一個原始資料型別。

整份規格中，（幾乎）所有整數都是無號 64 位元數 `uint64`，但這並非一直如此。

關於「無號」，圍繞「Eth2 應該用有號還是無號整數」曾有[許多討論](https://github.com/ethereum/consensus-specs/issues/626)，最終選擇了無號。結果，在某些地方保留運算的順序至關重要，以避免無意中造成下溢，因為負數是被禁止的。

而關於「64 位元」，規格的早期版本使用過 64 以外的[其他](https://github.com/ethereum/consensus-specs/commit/4c3c8510d4abf969a7170fce10dcfb5d4df408c8)位元長度（一種「[過早最佳化](https://wiki.c2.com/?PrematureOptimization)」），但算術整數現在整份規格都[標準化為 64 位元](https://github.com/ethereum/consensus-specs/pull/1746)，唯一的例外是在 Altair 升級中引入的 [`ParticipationFlags`](#participationflags)，它有型別 `uint8`，其實是一個 `byte` 型別。

<a id="table_custom_types"></a>

| 名稱                 | SSZ 等價物 | 描述                                                |
| --                   | ---            | -----                                                      |
| `Slot`               | `uint64`       | 一個時段編號                                              |
| `Epoch`              | `uint64`       | 一個紀元編號                                            |
| `CommitteeIndex`     | `uint64`       | 一個時段中的委員會索引                                |
| `ValidatorIndex`     | `uint64`       | 一個驗證者註冊表索引                                 |
| `Gwei`               | `uint64`       | 一個以 Gwei 計的數額                                          |
| `Root`               | `Bytes32`      | 一個 Merkle 根                                              |
| `Hash32`             | `Bytes32`      | 一個 256 位元雜湊                                             |
| `Version`            | `Bytes4`       | 一個分叉版本編號                                      |
| `DomainType`         | `Bytes4`       | 一個網域類型                                            |
| `ForkDigest`         | `Bytes4`       | 當前分叉資料的一個摘要                          |
| `Domain`             | `Bytes32`      | 一個簽章網域                                         |
| `BLSPubkey`          | `Bytes48`      | 一把 BLS12-381 公鑰                                     |
| `BLSSignature`       | `Bytes96`      | 一份 BLS12-381 簽章                                     |
| `ParticipationFlags` | `uint8`        | 8 個布林參與旗標的一個精簡表示 |
| `Transaction`        | `ByteList[MAX_BYTES_PER_TRANSACTION]` | 一個[型別化交易封套](https://eips.ethereum.org/EIPS/eip-2718#opaque-byte-array-rather-than-an-rlp-array)、或一筆舊式交易 |
| `ExecutionAddress`   | `Bytes20`      | 執行層上一個帳戶的位址 |
| `WithdrawalIndex`    | `uint64`       | 一個 `Withdrawal` 的索引 |

#### `Slot`

時間被劃分成定長的時段。在每個時段內，恰好有一個驗證者被隨機選來提議一個信標鏈區塊。時段的推進是信標鏈根本的心跳。

[TODO: link to Slots chapter]::

#### `Epoch`

時段的序列被組合成定長的紀元。

紀元邊界是「鏈能被證成並最終確定（由 Casper FFG 機制）」的那些時點。它們也是「驗證者餘額被更新、驗證者委員會被洗牌、驗證者退出、進入、罰沒被處理」的那些時點。也就是說，主要的狀態轉換工作是每個紀元、而非每個時段執行的。

紀元一直給人一種「疊加在信標鏈逐時段推進之上、略不自在的一層」的感覺，但卻是 Casper FFG 最終性所必需的。曾有[提案](https://ethresear.ch/t/epoch-less-casper-ffg-liveness-safety-argument/2702?u=benjaminion)打算擺脫紀元，也有可能的未來發展能讓我們得以完全[免掉](https://ethresear.ch/t/a-model-for-cumulative-committee-based-finality/10259?u=benjaminion)紀元。但目前，它們仍然存在。

[TODO: link to Epochs chapter]::
[TODO: link to Casper FFG]::

有趣的事實：紀元原本[被稱為週期](https://github.com/ethereum/consensus-specs/pull/149)（Cycle）。

#### CommitteeIndex

驗證者被組織成委員會，集體對區塊投票（做出證明）。每個委員會每個紀元恰好在一個時段活躍，但每個時段有數個委員會活躍。`CommitteeIndex` 型別是一個進入「某時段中活躍委員會清單」的索引。

信標鏈[以委員會為基礎的設計](/part2/building_blocks/committees/)，是「使它在維持安全性的同時實作起來實際可行」的一大原因。如果所有驗證者一直都活躍，就會有壓倒性數量的訊息要處理。委員會的隨機洗牌，使得一個沒有超級多數質押的攻擊者非常難以顛覆它們。

#### ValidatorIndex

每個成功做出存款的驗證者，都被連續地指派一個唯一的驗證者索引編號，這個編號是永久的，即使在該驗證者退出之後仍然存在。它之所以永久，是因為驗證者的餘額與它的索引相關聯，所以當驗證者退出時，這份資料需要被保留，至少要保留到那筆餘額在未來某個未知的時間被提領為止。

#### Gwei

共識層上所有的以太幣數額都以 Gwei（$10^9$ Wei，$10^{-9}$ 以太幣）為單位指定。這基本上是一個權宜之計，以避免在儲存驗證者餘額、以及進行計算時必須使用寬於 64 位元的整數，因為 $2^{64}$ Wei 只是 18 以太幣。即便如此，在某些地方仍需小心，以避免在處理以太幣計算時發生算術溢位。

#### Root

Merkle 根在 Eth2 協定中無處不在。它們是表示大量資料的一種非常簡潔、防竄改的方式，是一種[密碼學累加器](https://en.wikipedia.org/wiki/Accumulator_%28cryptography%29)的例子。區塊由它們的 Merkle 根摘要；狀態由它的 Merkle 根摘要；Eth1 存款清單由它的 Merkle 根摘要；一則訊息的數位簽章，是從該訊息所含資料結構的 Merkle 根計算出來的。

#### Hash32

Merkle 根是用密碼學雜湊函式構造的。在規格中，一個 `Hash32` 型別被用來表示 Eth1 區塊根（它們也是 Merkle 根）。

我不知道為什麼只有 Eth1 區塊雜湊被授予 `Hash32` 型別：規格中其他的雜湊[仍然是](https://github.com/ethereum/consensus-specs/pull/2689) `Bytes32`。在規格的早期版本中，`Hash32` 被用於所有密碼學雜湊量，但這[被改](https://github.com/ethereum/consensus-specs/pull/458)成了 `Bytes32`。

無論如何，值得花點時間來欣賞謙卑的[密碼學雜湊函式](https://en.wikipedia.org/wiki/Cryptographic_hash_function)。雜湊函式可以說是支撐區塊鏈技術、乃至我們大部分線上生活的單一最重要的演算法創新。很容易被視為理所當然，但對於使我們的現代世界成為可能而言絕對關鍵。

#### Version

與以太坊 1 不同[^fn-eth1-forkid]，信標鏈有一個協定內的版本編號概念。預期協定會不時被更新／升級，這個過程通常稱為「硬分叉」。例如，從 Phase&nbsp;0 到 Altair 的升級於 2021 年 10 月 27 日發生，並被指派[它自己的分叉版本](/part3/config/configuration/#altair_fork_version)。同樣地，從 Altair 到 Bellatrix 的升級被指派了一個[不同的分叉版本](/part3/config/configuration/#bellatrix_fork_version)。

`Version` 在計算 [`ForkDigest`](#forkdigest) 時被使用。

[^fn-eth1-forkid]: 以太坊 1.0 引入了一個分叉識別碼，如 [EIP-2124](https://eips.ethereum.org/EIPS/eip-2124) 中所定義，它與 `Version` 相似，但 Eth1 分叉 ID 不是共識協定的一部分，只在[網路協定](https://eips.ethereum.org/EIPS/eip-2364)中被使用。

[TODO: Link to networking section]::

#### DomainType

`DomainType` 只是一個[密碼學上的雅緻安排](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-hash-to-curve-12#section-2.2.5)：意圖用於不同目的的訊息，在被雜湊、並可能被簽章之前，會被標上不同的網域。它是一種避免衝突的命名空間；大概非必要，但被認為是一種最佳實務。Capella 中[定義了](/part3/config/constants/#domain-types)十一種網域類型。

#### ForkDigest

`ForkDigest` 是唯一的鏈識別碼，藉由把「在創世時所蒐集的資訊」與「當前鏈的 [`Version`](#version) 識別碼」結合而產生。

`ForkDigest` 有兩個用途。

  1. 在共識協定內，舉例來說，防止來自某個分叉上之驗證者（也許還沒升級）的證明，在一個不同的分叉上被計入。
  2. 在網路協定內，幫助區分「在同一條鏈上的有用對等節點」與「在不同鏈上的無用對等節點」。這個用途在[以太坊 2.0 網路規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/p2p-interface.md#how-should-fork-version-be-used-in-practice)中有所描述，`ForkDigest` 在其中頻繁出現。

具體而言，`ForkDigest` 是 [`ForkData`](/part3/containers/dependencies/#forkdata) 物件雜湊樹根的前四個位元組，該物件含有當前鏈的 [`Version`](#version) 以及在信標鏈[初始化](/part3/initialise/#def_initialize_beacon_state_from_eth1)時所建立的 [`genesis_validators_root`](/part3/containers/state/#genesis_validators_root)。它在 [`compute_fork_digest()`](/part3/helper/misc/#def_compute_fork_digest) 中被計算。

[TODO: link to networking section]::

#### Domain

`Domain` 在驗證驗證者的協定訊息時被使用。要有效，一則訊息必須已[結合](/part3/helper/misc/#def_compute_signing_root)了正確的網域與正確的分叉版本兩者。它被計算為「四位元組的 [`DomainType`](#domaintype)」與「[分叉資料根](/part3/helper/misc/#compute_fork_data_root)前 28 個位元組」的串接。

#### BLSPubkey

BLS（Boneh-Lynn-Shacham）是 Eth2 所使用的數位簽章方案。它有一些[非常不錯的性質](https://ethresear.ch/t/pragmatic-signature-aggregation-with-bls/2105?u=benjaminion)，尤其是聚合簽章的能力。這意味著許多驗證者可以簽署同一則訊息（例如，它們支持區塊 X），而這些簽章全都可以被有效率地聚合成單一一份簽章來驗證。能夠有效率地做這件事，使 Eth2 作為一個協定變得實際可行。其他好幾個協定已採用或將採用 BLS，例如 Zcash、Chia、Dfinity、Algorand。我們使用以 [BLS12-381](/part2/building_blocks/bls12-381/)（Barreto-Lynn-Scott）橢圓曲線為基礎的 BLS 簽章方案。

`BLSPubkey` 型別容納一個驗證者的公鑰，或數個驗證者公鑰的聚合。這被用來驗證「被宣稱來自那個驗證者或驗證者群組」的訊息。

在以太坊&nbsp;2.0 中，BLS 公鑰是來自 BLS12-381 $G_1$ 群的橢圓曲線點，因此壓縮後是 48 位元組長。

關於這些東西更深入的探討，見第&nbsp;2 部中關於 [BLS 簽章](/part2/building_blocks/signatures/)的章節。

#### `BLSSignature`

如上，我們使用 [BLS12-381](/part2/building_blocks/bls12-381/) 橢圓曲線上的 BLS 簽章，以便簽署參與者之間的訊息。如同所有的數位簽章方案，這同時保證了發送者的身分與任何訊息內容的完整性。

在以太坊&nbsp;2.0 中，BLS 簽章是來自 BLS12-381 $G_2$ 群的橢圓曲線點，因此壓縮後是 96 位元組長。

#### `ParticipationFlags`

`ParticipationFlags` 型別在 Altair 升級中作為記帳改革的一部分被引入。

在 Altair 之前，所有在區塊中所見的證明都會被儲存在狀態中兩個紀元。在一個紀元結束時，最終性計算、以及對每個活躍驗證者的獎勵與懲罰計算，會藉由把前一個紀元的所有證明當成一批來處理而完成。這在紀元邊界造成了處理的尖峰，並導致紀元最初幾個時段期間遲到的區塊與證明明顯增加。有了 Altair，[參與旗標](https://github.com/ethereum/consensus-specs/pull/2140)現在被用來持續追蹤驗證者的證明，減少紀元結束時的處理負載。

八個位元中有三個[目前被使用](/part3/config/constants/#participation-flag-indices)；五個保留供未來使用。

順帶一提，如果 `ParticipationFlags` 是一個 `Bytes1` 型別、而不是把一個怪異的 `uint8` 引入規格，可能會更直覺。畢竟，它並不被當作一個算術整數來使用。然而，`Bytes1` 在 SSZ 中是一個複合型別，其實是 `Vector[uint8, 1]` 的一個別名，而 `uint8` 是一個基本型別。在計算一個 `List` 型別的雜湊樹根時，多個基本型別可以被打包進單一一個葉，而複合型別則各佔一個葉。這會使一份 `Bytes1` 清單的雜湊操作多出 32 倍。基於類似的原因，`ParticipationFlags` 的型別[被從](https://github.com/ethereum/consensus-specs/pull/2176#pullrequestreview-566879992) `bitlist` 改成了 `uint8`。

#### `Transaction`

`Transaction` 型別在 Bellatrix 合併前升級中被引入，以容許以太坊交易被納入信標區塊。它出現在 [`ExecutionPayload`](/part3/containers/execution/#executionpayload) 物件中。

交易對信標鏈而言完全不透明，並且只在執行層中處理。[Bellatrix 規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/bellatrix/beacon-chain.md)中收錄了一則反映這一點的註記：

> _註_：`Transaction` 型別是一個並非最終定案的存根（stub）。

一筆交易的最大大小是 [`MAX_BYTES_PER_TRANSACTION`](/part3/config/preset/#max_bytes_per_transaction)，它看起來巨大，但由於底層型別是一個 SSZ `ByteList`（它是一個 [`List`](/part2/building_blocks/ssz/#lists)），一個 Transaction 物件只會佔用必要的空間。

#### `ExecutionAddress`

`ExecutionAddress` 型別在 Bellatrix 合併前升級中被引入，以表示「含有交易之信標區塊」在執行鏈上的費用接收者。它是一個一般的 20 位元組以太坊位址，並在 [`ExecutionPayload`](/part3/containers/execution/#executionpayload) 類別中被使用。

#### `WithdrawalIndex`

`WithdrawalIndex` 追蹤「從共識層做出到執行層的提領交易」的總數。所有節點都把這個數字儲存在它們的狀態中，所以一個「含有帶著出乎意料之提領索引的提領交易」的區塊是無效的。

以每個時段 16 筆提領的最大速率，一個 `uint64` 要花 4380 億年才會溢位。這應該夠了。

#### 參考

  - 一份 [Merkle 根入門](https://www.mycryptopedia.com/merkle-tree-merkle-root-explained/)。
    - 另見[維基百科談 Merkle 樹](https://en.wikipedia.org/wiki/Merkle_tree)。

### 常數 <!-- /part3/config/constants/ -->

「常數」、「預設值」與「設定值」之間的區別並不總是清楚，而事情有時在這幾個區段之間來回移動過[^fn-presets]。本質上，「常數」是那些「預期信標鏈永遠不會改變」的東西，無論它運行的是哪個分叉或測試網路。

[^fn-presets]: 關於目前「分成常數、預設值、設定變數」這種分類的討論與理路，見[議題 2390](https://github.com/ethereum/consensus-specs/pull/2390)。

#### 雜項

| 名稱 | 值 |
| - | - |
| `GENESIS_SLOT` | `Slot(0)` |
| `GENESIS_EPOCH` | `Epoch(0)` |
| `FAR_FUTURE_EPOCH` | `Epoch(2**64 - 1)` |
| `DEPOSIT_CONTRACT_TREE_DEPTH` | `uint64(2**5)`（= 32） |
| `JUSTIFICATION_BITS_LENGTH` | `uint64(4)` |
| `PARTICIPATION_FLAG_WEIGHTS` | `[TIMELY_SOURCE_WEIGHT, TIMELY_TARGET_WEIGHT, TIMELY_HEAD_WEIGHT]` |
| `ENDIANNESS` | `'little'` |

##### `GENESIS_SLOT`

信標鏈最最初的時段編號是零。

這或許看似沒有爭議，但它實際上在[先前](/part3/config/types/#custom-types)提到的「正負號大戰」中佔了很重的戲份。問題在於，對無號整數的計算可能有負的中間值，那會造成問題。對此一個被提議的變通辦法，是讓鏈從一個非零的時段編號開始。它起初被設為 [2^19](https://github.com/ethereum/consensus-specs/commit/656eae6f6ad85de5f4b9493ca0a4f8ca16d2e261#diff-51a43328a58414e132a744f3771f018cR193)，然後 [2^63](https://github.com/ethereum/consensus-specs/commit/7f39f79b2e72654920b2e12127cfdfe6ad0088c6)，然後 [2^32](https://github.com/ethereum/consensus-specs/commit/9b7b35bc9d18d0fac92ee142f1ea66ab289d3175)，最後[又回到零](https://github.com/ethereum/consensus-specs/commit/8c32128ffbda5c7e056c218cdb78ab76d856c5f5#diff-51a43328a58414e132a744f3771f018cR219)。以我淺見，這場瘋狂只證實了我們從頭到尾就應該用有號整數。

##### `GENESIS_EPOCH`

如上。當鏈啟動時，它從紀元零開始。

##### `FAR_FUTURE_EPOCH`

最無趣常數的一個候選者。它被用作驗證者啟用與退出時間在被適當設定之前的預設初始化值。沒有紀元編號會比這一個更大。

##### `DEPOSIT_CONTRACT_TREE_DEPTH`

`DEPOSIT_CONTRACT_TREE_DEPTH` 指定 Eth1 存款合約用以儲存所做出存款之（稀疏）Merkle 樹的大小。值為 32 時，這容許 $2^{32}$ = 43 億筆存款。鑑於最低存款是 1 以太幣，那個數字顯然夠了。

由於存款收據含有 Merkle 證明，它們的大小取決於這個常數的值。

##### `JUSTIFICATION_BITS_LENGTH`

作為對 Casper FFG（將最終性賦予紀元的過程）的一項最佳化，信標鏈使用一條「$k$-最終性」規則。等我們看處理[證成與最終確定](/part3/transition/epoch/#def_weigh_justification_and_finalization)時，我們會更完整地描述這一點。目前，這個常數就只是「我們為實作 $k$-最終性而需要在狀態中儲存的位元數」。在 $k = 2$ 時，我們追蹤最後四個紀元的證成狀態。

##### `PARTICIPATION_FLAG_WEIGHTS`

這個陣列只是「在計算獎勵時存取『給予不同驗證者成就之各種權重』」的一種方便方式。這三個權重在[激勵權重](#incentivization-weights)下定義，而每個權重都對應到一個「儲存在狀態中、並在[參與旗標索引](#participation-flag-indices)下定義」的旗標。

##### `ENDIANNESS`

[位元組順序](https://en.wikipedia.org/wiki/Endianness)（endianness）指的是一個數字二進位表示中位元組的順序：最高位的位元組在前是大端；最低位的位元組在前是小端。在絕大部分情況下，這些細節被編譯器隱藏起來，我們不需要擔心位元組順序。但在整數與位元組之間轉換時，位元組順序就有關係了，這與洗牌與提議者選擇、RANDAO、以及用 SSZ 序列化時相關。

規格一開始是大端，但 Status 的 Nimbus 團隊成功遊說把它改成小端，以便更好地匹配處理器硬體實作、以及 [WASM 的](https://webassembly.org/docs/portability/)位元組順序。SSZ [先](https://github.com/ethereum/consensus-specs/pull/139)被改，然後規格的其餘部分[跟進](https://github.com/ethereum/consensus-specs/pull/564)。

#### 參與旗標索引

| Name                       | Value |
| -                          | -     |
| `TIMELY_SOURCE_FLAG_INDEX` | `0`   |
| `TIMELY_TARGET_FLAG_INDEX` | `1`   |
| `TIMELY_HEAD_FLAG_INDEX`   | `2`   |

做出「被納入鏈上」之證明的驗證者，因三件事而獲得獎勵：

  - 讓證明在 5 個時段內（`integer_squareroot(SLOTS_PER_EPOCH)`）以正確的來源檢查點被納入；
  - 讓證明在 32 個時段內（`SLOTS_PER_EPOCH`）以正確的目標檢查點被納入；以及
  - 讓證明在 1 個時段內（`MIN_ATTESTATION_INCLUSION_DELAY`，基本上是立即）以正確的鏈頭被納入。

這些旗標在證明被處理時暫時記錄在 [`BeaconState`](/part3/containers/state/#beaconstate) 中，然後在紀元結束時用以更新最終性、並計算驗證者做出證明的獎勵。

「獎勵及時納入證明（從而懲罰遲到的證明）」的機制，在 Altair 與 Phase&nbsp;0 之間有所不同。在 Phase&nbsp;0，在 32 個時段內被納入的證明，會就它們投對的票（來源、目標、鏈頭）收到完整的獎勵，加上一個基於納入延遲而遞減的獎勵：兩個時段延遲為 $\frac{1}{2}$，三個時段延遲為 $\frac{1}{3}$，依此類推。有了 Altair，現在對每一票，我們都有一個懸崖，在它之前驗證者收到完整的獎勵、在它之後收到一筆懲罰。這些懸崖的時長各異，這意在更精準地把激勵瞄準「真正有助於鏈的行為」（例如，獎勵一張遲了 30 個時段才做出的正確鏈頭投票，價值不大）。這在程式碼中如何實作，見 [`get_attestation_participation_flag_indices()`](/part3/helper/accessors/#get_attestation_participation_flag_indices)。

#### 激勵權重

| Name | Value |
| - | - |
| `TIMELY_SOURCE_WEIGHT` | `uint64(14)` |
| `TIMELY_TARGET_WEIGHT` | `uint64(26)` |
| `TIMELY_HEAD_WEIGHT` | `uint64(14)` |
| `SYNC_REWARD_WEIGHT` | `uint64(2)` |
| `PROPOSER_WEIGHT` | `uint64(8)` |
| `WEIGHT_DENOMINATOR` | `uint64(64)` |

這些權重被用來計算一個驗證者因履行其職責而賺得的獎勵。職責總共有五項。三項與做出證明有關：為來源紀元做出證明、為目標紀元做出證明、為鏈頭區塊做出證明。也有提議區塊、以及參與同步委員會的獎勵。請注意，這五個權重之和等於 `WEIGHT_DENOMINATOR`。

長期平均下來，一個驗證者每個紀元可以預期賺得總計 [`get_base_reward()`](/part3/transition/epoch/#def_get_base_reward) 的數額，而這些權重是構成那個總額的各項職責各自的相對份額。提議區塊與參與同步委員會並不在每個紀元都發生，而是被隨機指派的，所以在小段時間內，驗證者的收益可能與 `get_base_reward()` 不同。

[TODO: link to discussion of things that can reduce rewards, a la V's annotated spec]::

獎勵的分派在 Altair 升級中被徹底翻修，以更好地反映每種活動在協定內的重要性。總獎勵數額維持不變，但加入了同步委員會獎勵，並調整了相對權重。先前，這些權重對應於來源正確 16、目標正確 16、鏈頭正確 16、納入 14（等價於來源正確）、區塊提議 2。提議者獎勵增加四倍，解決了一個長期存在的[規格臭蟲](https://github.com/ethereum/consensus-specs/issues/2152#issuecomment-747465241)。

<a id="img_incentives_weights"></a>
<figure class="diagram" style="width:50%">

![一張圓餅圖，呈現一個驗證者總獎勵中來自每一份微獎勵的比例。](images/diagrams/incentives-weights.svg)

<figcaption>

總獎勵中來自每一份微獎勵的比例。

</figcaption>
</figure>

#### 提領前綴

| 名稱 | 值 |
| - | - |
| `BLS_WITHDRAWAL_PREFIX` | `Bytes1('0x00')` |
| `ETH1_ADDRESS_WITHDRAWAL_PREFIX` | `Bytes1('0x01')` |

[TODO: link to somewhere useful for withdrawal creds]::

提領前綴與「為驗證者做出存款時所提供的提領憑證」有關。

目前有兩種指定提領憑證的方式可用，以這些前綴標註版本，而諸如 [`0x02`](https://github.com/ethereum/consensus-specs/pull/2454) 與 [`0x03`](https://ethresear.ch/t/0x03-withdrawal-credentials-simple-eth1-triggerable-withdrawals/10021?u=benjaminion) 等其他方式則在討論中。

在把存款處理到共識層上時，存款的 `withdrawal_credential` 不會以任何方式被檢查。確保「使用正確的前綴與內容，以便能在退出共識層後收到他們的獎勵並取回他們的質押」，是存款者自己的責任。這也意味著我們有可能在任何時候引入新類型的提領憑證，之後再以一次硬分叉啟用它們，正如我們在開始使用 `0x01` 憑證的 [Capella 升級](/part4/history/capella/)之前對它們所做的那樣。

##### `BLS_WITHDRAWAL_PREFIX`

信標鏈上線時只有 BLS 式的提領憑證可用，所以所有早期的質押者都使用這種。

在早期，以太坊&nbsp;2.0 上的帳戶會長什麼樣子、它們可能用哪種定址方案，完全不明朗。`0x00` 憑證建立了一個占位符、或一份對未來提領憑證變更的承諾。

有了這種類型的憑證，除了一把 BLS 簽章金鑰之外，質押者還有第二把 BLS「提領」金鑰。自 Capella 升級以來，質押者一直能夠用他們的提領金鑰簽署一則訊息，指示共識層把它的提領憑證[從 `0x00` 類型改為 `0x01` 類型](/part3/transition/block/#def_process_bls_to_execution_change)。

登錄在存款資料中的憑證，是驗證者提領公鑰的 32 位元組 SHA256 雜湊，第一個位元組設為 `0x00`（`BLS_WITHDRAWAL_PREFIX`）。

##### `ETH1_ADDRESS_WITHDRAWAL_PREFIX`

Eth1 提領憑證簡單得多，它是在「以太坊&nbsp;2.0 短期內不會為帳戶使用以 BLS 為基礎的位址方案」變得明朗之後[被採用](https://github.com/ethereum/consensus-specs/pull/2149)的。Capella 升級使「驗證者餘額從信標鏈自動部分與完整提領到一般以太坊帳戶與錢包」成為可能。

一個 Eth1 提領憑證看起來像位元組 `0x01`（`ETH1_ADDRESS_WITHDRAWAL_PREFIX`），後面跟著十一個 `0x00` 位元組，再跟著目的地帳戶的 20 位元組以太坊位址。

除了為擁有 `0x01` Eth1 憑證的驗證者啟用提領交易之外，Capella 升級也給了「擁有舊式 `0x00` BLS 式憑證」的驗證者一個機會，去做一次「從 BLS 改為 Eth1 提領憑證」的[一次性變更](/part3/transition/block/#def_process_bls_to_execution_change)[^fn-capella-bls-eth1]。

[^fn-capella-bls-eth1]: 有趣的事實：在 Capella 升級的時間點，總共 567,144 個驗證者中，322,491 個（56.9%）有 `0x00` BLS 提領憑證，244,653 個（43.1%）有 `0x01` Eth1 提領憑證。

#### 網域類型

<a id="domain_beacon_proposer"></a>
<a id="domain_beacon_attester"></a>
<a id="domain_randao"></a>
<a id="domain_deposit"></a>
<a id="domain_voluntary_exit"></a>
<a id="domain_selection_proof"></a>
<a id="domain_aggregate_and_proof"></a>
<a id="domain_sync_committee"></a>
<a id="domain_sync_committee_selection_proof"></a>
<a id="domain_contribution_and_proof"></a>
<a id="domain_bls_to_execution_change"></a>

| Name | Value |
| - | - |
| `DOMAIN_BEACON_PROPOSER`                | `DomainType('0x00000000')` |
| `DOMAIN_BEACON_ATTESTER`                | `DomainType('0x01000000')` |
| `DOMAIN_RANDAO`                         | `DomainType('0x02000000')` |
| `DOMAIN_DEPOSIT`                        | `DomainType('0x03000000')` |
| `DOMAIN_VOLUNTARY_EXIT`                 | `DomainType('0x04000000')` |
| `DOMAIN_SELECTION_PROOF`                | `DomainType('0x05000000')` |
| `DOMAIN_AGGREGATE_AND_PROOF`            | `DomainType('0x06000000')` |
| `DOMAIN_SYNC_COMMITTEE`                 | `DomainType('0x07000000')` |
| `DOMAIN_SYNC_COMMITTEE_SELECTION_PROOF` | `DomainType('0x08000000')` |
| `DOMAIN_CONTRIBUTION_AND_PROOF`         | `DomainType('0x09000000')` |
| `DOMAIN_BLS_TO_EXECUTION_CHANGE`        | `DomainType('0x0A000000')` |

這些網域類型以三種方式被使用：用於種子、用於簽章、以及用於選擇聚合者。

##### 作為種子

當協定內需要隨機數時，產生它們的一種方式，是把 RANDAO 混合值與其他的量一起雜湊，其中一個量就是一個網域類型（見 [`get_seed()`](/part3/helper/accessors/#def_get_seed)）。[原始動機](https://github.com/ethereum/consensus-specs/pull/1415)是為了避免「Phase&nbsp;0 委員會」與「Phase&nbsp;1 持久委員會」（當年它們還存在時）之間偶爾的衝突。所以，計算信標區塊提議者時，`DOMAIN_BEACON_PROPOSER` 被雜湊進種子；計算證明委員會時，`DOMAIN_BEACON_ATTESTER` 被雜湊進去；計算同步委員會時，`DOMAIN_SYNC_COMMITTEE` 被雜湊進去。

更多資訊見[隨機性](/part2/building_blocks/randomness/)一章。

##### 作為簽章

此外，作為一個密碼學上的雅緻安排，協定的每一種簽章類型在被簽章之前，都以適當的網域加以增補：

  - 已簽署的區塊提議納入 `DOMAIN_BEACON_PROPOSER`
  - 已簽署的證明納入 `DOMAIN_BEACON_ATTESTER`
  - RANDAO 揭露值是 BLS 簽章，使用 `DOMAIN_RANDAO`
  - 存款資料訊息納入 `DOMAIN_DEPOSIT`
  - 驗證者自願退出訊息納入 `DOMAIN_VOLUNTARY_EXIT`
  - 同步委員會簽章納入 `DOMAIN_SYNC_COMMITTEE`
  - BLS 提領憑證變更訊息納入 `DOMAIN_BLS_TO_EXECUTION_CHANGE`

對於這當中的大多數，分叉版本在簽章之前[也被納入](/part3/helper/accessors/#get_domain)。這讓驗證者得以——如果它們願意——參與信標鏈的兩個獨立分叉，而不必擔心被罰沒。

然而，存款（`DOMAIN_DEPOSIT`）與 BLS 提領憑證變更（`DOMAIN_BLS_TO_EXECUTION_CHANGE`）的使用者簽署訊息，在簽章時並不納入分叉版本。這使它們在所有分叉上都有效，這是一項可用性的增強。

自願退出訊息（`DOMAIN_VOLUNTARY_EXIT`）有點異常，因為它們是使用者簽署的、卻也納入分叉版本，意味著它們在兩次升級之後失效（在 Phase 0 或 Altair 簽署的自願退出訊息在 Capella 中不再有效）。關於未來把自願退出做成不會失效，有[一些討論](https://github.com/ethereum/consensus-specs/pull/3288)。

更多資訊見 [BLS 簽章](/part2/building_blocks/signatures/)一章。

##### 聚合者選擇

其餘四種以 `_PROOF` 為字尾的類型，並未在信標鏈規格中被直接使用。它們[被引入](https://github.com/ethereum/consensus-specs/pull/1615)，是為了實作[證明子網驗證](https://github.com/ethereum/consensus-specs/issues/1595)，以抗阻斷服務。這項技術在 Altair 升級中[被擴充](https://github.com/ethereum/consensus-specs/pull/2266)到同步委員會。

簡言之，在每個時段，驗證者被選來聚合來自它們委員會的證明。這項選擇是基於驗證者對時段編號的簽章而做出的，並混入 `DOMAIN_SELECTION_PROOF`。驗證者接著用 `DOMAIN_AGGREGATE_AND_PROOF` 簽署整份聚合證明，包括把先前那份簽章作為「它被選為一個聚合者」的證明納入。同步委員會也類似。如此一來，一切都可驗證、可歸因，使得「以假訊息淹沒網路」變得困難。

這四種不是共識關鍵之狀態轉換的一部分，但儘管如此對鏈的健康運作很重要。

這個機制在 [Phase&nbsp;0 誠實驗證者規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#aggregation-selection)中針對證明聚合有所描述，並在 [Altair 誠實驗證者規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/validator.md#aggregation-selection)中針對同步委員會聚合有所描述。

更多資訊見[聚合者選擇](/part2/building_blocks/aggregator/)一章。

#### 密碼學

<a id="g2_point_at_infinity"></a>

| 名稱 | 值 |
| - | - |
| `G2_POINT_AT_INFINITY` | `BLSSignature(b'\xc0' + b'\x00' * 95)` |

這是我們用於簽章的 BLS12-381 曲線 G2 群「無窮遠點」（單位元點）的壓縮[序列化](https://github.com/zcash/librustzcash/blob/6e0364cd42a2b3d2b958a54771ef51a8db79dd29/pairing/src/bls12_381/README.md#serialization)。請注意，它是大端格式（不同於規格中所有其他的常數）。

它被引入，是作為「在 [`eth_fast_aggregate_verify()`](/part3/helper/crypto/#def_eth_fast_aggregate_verify) 中驗證不含公鑰的聚合簽章」時的一個方便。BLS 簽章標準中底層的 [FastAggregateVerify](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-bls-signature-04#section-3.3.4) 函式會拒絕這些。

`G2_POINT_AT_INFINITY` 在獨立的 [BLS 擴充](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/bls.md)文件中有所描述，但為求方便此處也收錄。

### 預設值 <!-- /part3/config/preset/ -->

「預設值」（preset）是被捆在一起的「一致的設定變數集合」。[規格儲存庫](https://github.com/ethereum/consensus-specs/tree/v1.3.0/configs)目前定義了兩組預設值：[mainnet](https://github.com/ethereum/consensus-specs/blob/v1.3.0/configs/mainnet.yaml) 與 [minimal](https://github.com/ethereum/consensus-specs/blob/v1.3.0/configs/minimal.yaml)。mainnet 設定正在信標鏈上於生產環境運行；minimal 常被用於測試。也可能有其他設定。例如，Teku 使用一個 [swift](https://github.com/ConsenSys/teku/blob/d368fd44ec43eb93923dd4c150a6649d82798e43/util/src/main/resources/tech/pegasys/teku/util/config/configs/swift.yaml) 設定來進行驗收測試。

下面所討論的所有值都來自 mainnet 設定。

你會注意到，這些值大多是二的次方。這沒有什麼重大的意義。電腦科學家覺得這樣很俐落，而且它確保了東西一般能乾淨地整除其他東西。有[一種看法](https://github.com/ethereum/consensus-specs/issues/1633#issuecomment-592949297)認為，這種做法有助於把[腳踏車棚效應](https://en.wikipedia.org/wiki/Law_of_triviality)（為瑣事爭論不休）降到最低。

下面有些設定參數相當技術性、或許晦澀。我會藉這個機會引介一些概念，並在它們於後面各章出現時給出更詳細的解釋。

#### 雜項

| 名稱 | 值 |
| - | - |
| `MAX_COMMITTEES_PER_SLOT` | `uint64(2**6)`（= 64） |
| `TARGET_COMMITTEE_SIZE` | `uint64(2**7)`（= 128） |
| `MAX_VALIDATORS_PER_COMMITTEE` | `uint64(2**11)`（= 2,048） |
| `SHUFFLE_ROUND_COUNT` | `uint64(90)` |

##### `MAX_COMMITTEES_PER_SLOT`

驗證者被組織成委員會來做它們的工作。在任一時刻，每個驗證者都恰好是一個信標鏈委員會的成員，並被要求每個紀元恰好做出一份證明。一份證明是「對驗證者在那個時間點對鏈之看法」的一張投票、或一項陳述。

在信標鏈上，一個時段中至多有 64 個委員會活躍，就分叉選擇規則而言它們實際上作為單一一個委員會行動。它們全都對該時段所提議的區塊投票，而它們的票／證明被匯聚起來。以類似的方式，就證成與最終確定而言，一個紀元期間所有活躍的委員會（也就是整個活躍驗證者集合）實際上作為單一一個委員會行動。

64 這個數字原本意在於「資料分片在以太坊&nbsp;2.0 路線圖如今已被放棄的 Phase&nbsp;1 中被部署之後」映射到[每個分片一個委員會](https://github.com/ethereum/consensus-specs/pull/1428)。計畫是讓每個委員會也對一個分片交叉連結投票，總共 64 個分片。我們不再走那條路，但這些委員會仍在每個時段存在。

以上的一切在[委員會](/part2/building_blocks/committees/)一節有進一步的討論。

請注意，同步委員會是不同的東西：在任一時刻只有一個同步委員會活躍。

##### `TARGET_COMMITTEE_SIZE`

要達到一個可取的安全水準，委員會需要大於某個大小。這使得攻擊者即使掌控可觀數量的驗證者，要隨機地最終在一個委員會中得到超級多數也不可行。此處的目標是一種對委員會大小的下界。如果沒有足夠的驗證者讓所有委員會都至少有 128 個成員，那麼作為第一項措施，每個時段的委員會數量會被減少以維持這個最低值。只有在總共少於 `SLOTS_PER_EPOCH` * `TARGET_COMMITTEE_SIZE` = 4096 個驗證者時，委員會大小才會被減到 `TARGET_COMMITTEE_SIZE` 以下。在驗證者這麼少的情況下，系統無論如何都會不安全。

關於 `TARGET_COMMITTEE_SIZE` 的值如何被設定的進一步討論與解釋，見[委員會一節](/part2/building_blocks/committees/#target-committee-size)。

##### `MAX_VALIDATORS_PER_COMMITTEE`

這只被用來為某些資料結構設定大小，並不特別有意思。達到這個上限會意味著超過 400 萬個活躍的驗證者、總共質押 1.28 億以太幣，那超過了今天的[總供給量](https://etherscan.io/stat/supply)。

##### `SHUFFLE_ROUND_COUNT`

信標鏈實作了一種[相當有意思的](/part2/building_blocks/shuffling/)、為選擇委員會而洗牌驗證者的方式，稱為「交換或不交換洗牌」。這個洗牌以輪為單位進行，而洗牌的程度由輪數 `SHUFFLE_ROUND_COUNT` 決定。洗牌所花的時間與輪數成線性，所以對於輕量、非 mainnet 的設定，輪數可以被減少。

90 這個值在 Vitalik 的[最初提交](https://github.com/ethereum/consensus-specs/pull/576/commits/c58410e6ce9904c6619cd925b64fbd04c00b9a89)中被引入，沒有解釋。描述洗牌技術的[原始論文](https://link.springer.com/content/pdf/10.1007%2F978-3-642-32009-5_1.pdf)似乎暗示，在密碼學上安全的輪數是 $6\log{N}$。那麼，有了 90 輪，我們應該足以洗牌 330 萬個驗證者，那接近（給定以太幣供給量）可能的最大數量。

#### 遲滯參數

| 名稱 | 值 |
| - | - |
| `HYSTERESIS_QUOTIENT` | `uint64(4)` |
| `HYSTERESIS_DOWNWARD_MULTIPLIER` | `uint64(1)` |
| `HYSTERESIS_UPWARD_MULTIPLIER` | `uint64(5)` |

以 `HYSTERESIS_` 為前綴的參數，控制有效餘額被改變的方式（見 [`EFFECTIVE_BALANCE_INCREMENT`](#effective_balance_increment)）。如那裡所描述，一個驗證者的有效餘額以階梯式的方式跟隨實際餘額的變化，並套用[遲滯](https://en.wikipedia.org/wiki/Hysteresis)。這確保有效餘額不會經常改變。

最初的遲滯設計有一個[非預期的效果](https://github.com/ethereum/consensus-specs/issues/1609)，它可能會鼓勵質押者過度存款、或做多筆存款，以隨時把餘額維持在 32 以太幣以上。如果一個驗證者的餘額在存款後不久就掉到 32 以太幣以下，不論多麼短暫，有效餘額本會立即掉到 31 以太幣、並花很長時間才恢復。這本會導致一段時期內獎勵減少 3%。

這個問題藉由透過這些參數[讓遲滯可設定](https://github.com/ethereum/consensus-specs/pull/1627)而獲得解決。具體而言，這些設定意味著：

 1. 如果一個驗證者的餘額掉到其有效餘額以下 0.25&nbsp;以太幣，那麼它的有效餘額就被減少 1&nbsp;以太幣
 2. 如果一個驗證者的餘額升到其有效餘額以上 1.25&nbsp;以太幣，那麼它的有效餘額就被增加 1&nbsp;以太幣

這些計算在紀元結束處理期間於 [`process_effective_balance_updates()`](/part3/transition/epoch/#def_process_effective_balance_updates) 中完成。

#### Gwei 值

| 名稱 | 值 |
| - | - |
| `MIN_DEPOSIT_AMOUNT` | `Gwei(2**0 * 10**9)`（= 1,000,000,000） |
| `MAX_EFFECTIVE_BALANCE` | `Gwei(2**5 * 10**9)`（= 32,000,000,000） |
| `EFFECTIVE_BALANCE_INCREMENT` | `Gwei(2**0 * 10**9)`（= 1,000,000,000） |

##### `MIN_DEPOSIT_AMOUNT`

`MIN_DEPOSIT_AMOUNT` 實際上並未在信標鏈規格文件內任何地方被使用。相反地，它是在[部署到](https://etherscan.io/address/0x00000000219ab540356cbb839cbe05303d7705fa#code)以太坊 1 鏈的[存款合約](https://github.com/ethereum/consensus-specs/blob/v1.3.0/solidity_deposit_contract/deposit_contract.sol#L113)中被強制執行的。任何送往存款合約、小於這個值的數額都會被回退。

允許質押者做出小於一筆完整質押的存款，對於「在一個驗證者的有效餘額掉到 32&nbsp;以太幣以下時為它的餘額加值、以維持完整的生產力」很有用。然而，這實際上為某些質押池導致了一個[弱點](https://medium.com/immunefi/rocketpool-lido-frontrunning-bug-fix-postmortem-e701f26d7971)，涉及搶先交易（front-running）存款。在某些情況下，一個搶先交易的攻擊者可以把一個真正存款者的提領憑證改成他們自己的。

##### `MAX_EFFECTIVE_BALANCE`

驗證者有一個「有效餘額」的概念：無論一個驗證者的總餘額為何，它的投票權都依它的有效餘額加權，即使它的實際餘額更高。有效餘額也是「所有獎勵、懲罰、罰沒都據以計算」的數額——它在協定中被大量使用。

`MAX_EFFECTIVE_BALANCE` 是一個驗證者所能擁有的最高有效餘額：32 以太幣。任何高於這個值的餘額都被忽略。請注意，這意味著質押獎勵在一般情況下不會複利（除非一個驗證者的有效餘額不知怎地掉到 32&nbsp;以太幣以下，在那種情況下獎勵算是會複利）。

[設計原理](https://notes.ethereum.org/@vbuterin/rkhCgQteN#Why-32-ETH-validator-sizes)中有一段討論「32 以太幣為何被選為質押金額」。簡言之，我們想要足夠多的驗證者來讓鏈在攻擊下既存活又安全，但不要多到網路上的訊息開銷變得太高。

##### `EFFECTIVE_BALANCE_INCREMENT`

整份協定中，一個稱為「有效餘額」的量被用來代替驗證者的實際餘額。有效餘額追蹤實際餘額，但有兩處差異：(1) 無論一個驗證者的實際餘額多高，有效餘額的上限都封在 `MAX_EFFECTIVE_BALANCE`，以及 (2) 有效餘額粗顆粒得多——它只以 `EFFECTIVE_BALANCE_INCREMENT` 為步長改變，而非以 [`Gwei`](/part3/config/types/#gwei)。

有效餘額的這種離散化，意在減少做狀態更新時所需的雜湊量。目標是避免必須過於頻繁地重新計算驗證者記錄的雜湊樹根。驗證者頻繁變動的實際餘額，被當成一份連續的清單儲存在 BeaconState 中、在驗證者記錄之外。有效餘額被儲存在驗證者各自的記錄內，更新起來代價較高（需要更多雜湊）。所以我們試著相對不頻繁地更新有效餘額。

有效餘額是依一個帶有遲滯的過程被改變的，以避免它可能頻繁改變的情況。見 [`HYSTERESIS_QUOTIENT`](#hysteresis-parameters)。

關於有效餘額你可以在[設計原理](https://notes.ethereum.org/@vbuterin/rkhCgQteN#Effective-balances)、以及[這篇文章](https://www.attestant.io/posts/understanding-validator-effective-balance/)中讀到更多。

#### 時間參數

| Name                               | Value                     | Unit   | Duration     |
|------------------------------------|---------------------------|--------|--------------|
| `MIN_ATTESTATION_INCLUSION_DELAY`  | `uint64(2**0)` (= 1)      | slots  | 12 seconds   |
| `SLOTS_PER_EPOCH`                  | `uint64(2**5)` (= 32)     | slots  | 6.4 minutes  |
| `MIN_SEED_LOOKAHEAD`               | `uint64(2**0)` (= 1)      | epochs | 6.4 minutes  |
| `MAX_SEED_LOOKAHEAD`               | `uint64(2**2)` (= 4)      | epochs | 25.6 minutes |
| `MIN_EPOCHS_TO_INACTIVITY_PENALTY` | `uint64(2**2)` (= 4)      | epochs | 25.6 minutes |
| `EPOCHS_PER_ETH1_VOTING_PERIOD`    | `uint64(2**6)` (= 64)     | epochs | ~6.8 hours   |
| `SLOTS_PER_HISTORICAL_ROOT`        | `uint64(2**13)` (= 8,192) | slots  | ~27 hours    |

##### `MIN_ATTESTATION_INCLUSION_DELAY`

A design goal of Ethereum&nbsp;2.0 is not to heavily disadvantage validators that are running on lower-spec systems, or, conversely, to reduce any advantage gained by running on high-spec systems.

One aspect of performance is network bandwidth. When a validator becomes the block proposer, it needs to gather attestations from the rest of its committee. On a low-bandwidth link, this takes longer, and could result in the proposer not being able to include as many past attestations as other better-connected validators might, thus receiving lower rewards.

`MIN_ATTESTATION_INCLUSION_DELAY` was an attempt to "level the playing field" by setting a minimum number of slots before an attestation can be included in a beacon block. It was [originally set at 4](https://github.com/ethereum/consensus-specs/pull/143), with a 6-second slot time, allowing 24 seconds for attestations to propagate around the network.

It was [later set to one](https://github.com/ethereum/consensus-specs/pull/1157) &ndash; attestations are included as early as possible &ndash; and `MIN_ATTESTATION_INCLUSION_DELAY` exists today as a relic of the earlier design. The current slot time of 12 seconds is assumed to allow sufficient time for attestations to propagate and be aggregated sufficiently within one slot.

##### `SLOTS_PER_EPOCH`

我們目前有 12 秒的時段與 32 時段的紀元。在較早的設計中，時段是 6 秒、每個紀元有 64 個時段。所以時段被加長時，紀元邊界之間的時間並未改變。

每個紀元 32 個時段這個選擇，是「最終確定時間」（我們需要兩個紀元來最終確定，所以我們偏好讓它們盡可能短）與「盡可能確定每個紀元至少有一個誠實的提議者會做出一個區塊來更新 RANDAO」（為此我們偏好較長的紀元）之間的一個取捨。

此外，[紀元邊界](/part3/transition/epoch/#epoch-processing)是信標鏈狀態轉換計算最沉重的部分發生之處，所以那是「不讓它們靠得太近」的另一個原因。

由於每個驗證者每個紀元做出一份證明，每個紀元的時段數、每個時段的委員會數、委員會大小、以及驗證者總數之間，存在一種交互作用。

##### `MIN_SEED_LOOKAHEAD`

一個隨機種子被用來選出一個紀元的所有委員會與提議者。在每個紀元期間，信標鏈透過 RANDAO 從提議者那裡累積隨機性並儲存它。當前紀元的種子，基於 `MIN_SEED_LOOKAHEAD` ` + ` `1` 個紀元之前的 RANDAO 輸出。在 `MIN_SEED_LOOKAHEAD` 設為一的情況下，效果是我們可以知道當前紀元與下一個紀元的種子，但不能更遠，因為再下一個紀元取決於「當前紀元尚未累積的隨機性」。

這個機制被設計來「讓新組成之委員會的成員有足夠的時間在點對點網路上找到彼此」，同時「防止委員會組成被太早知道，限制了驗證者之間協同勾結的機會」。

##### `MAX_SEED_LOOKAHEAD`

儘管有上述機制，如果一個攻擊者擁有一大部分的質押、或例如能夠對區塊提議者 DoS 一陣子，那麼攻擊者就有可能比 `MIN_SEED_LOOKAHEAD` 通常所容許的更往前地預測 RANDAO 的輸出。這可能使攻擊者得以藉由「在恰當的時機讓它們的驗證者退出與啟用」來操縱委員會成員資格、使之對它們有利。

為了防止這一點，我們假設一個攻擊者可能達到的最大可行前瞻（`MAX_SEED_LOOKAHEAD`），並把所有的啟用與退出都延遲這麼多，這讓新的隨機性得以透過誠實驗證者的區塊提議進來。在 `MAX_SEED_LOOKAHEAD` 設為 4 的情況下，如果只有 10% 的驗證者在線且誠實，那麼攻擊者能成功預測超過（`MAX_SEED_LOOKAHEAD` ` - ` `MIN_SEED_LOOKAHEAD`）= 3 個紀元之種子的機會是 $0.9^{3\times 32}$，那約為兩萬五千分之一。

##### `MIN_EPOCHS_TO_INACTIVITY_PENALTY`

怠惰懲罰在[下文](#inactivity_penalty_quotient)討論。這個參數設定「直到它啟動為止」的時間長度。如果最近一個已最終確定的紀元在比 `MIN_EPOCHS_TO_INACTIVITY_PENALTY` 更久以前，那麼信標鏈就開始以「洩漏」模式運作。在這個模式中，參與的驗證者不再獲得獎勵，而不參與的驗證者則受到懲罰。

##### `EPOCHS_PER_ETH1_VOTING_PERIOD`

為了安全地迎入新的驗證者，信標鏈需要對 Eth1 鏈的樣貌採取一個看法。這是藉由從信標區塊提議者那裡蒐集投票來完成的——它們被期望去查詢一個可用的 Eth1 客戶端，以構造它們的票。

`EPOCHS_PER_ETH1_VOTING_PERIOD` ` * ` `SLOTS_PER_EPOCH` 是所蒐集之「對 Eth1 區塊的投票」總數。一旦這個數量的票中有一半投給同一個 Eth1 區塊，那個區塊就被信標鏈採納，存款處理就能繼續。這項處理在 [`process_eth1_data()`](/part3/transition/block/#def_process_eth1_data) 中完成。

「驗證者如何選出要投票支持的正確區塊」的規則，在[驗證者指南](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#get_eth1_data)中列出。[`ETH1_FOLLOW_DISTANCE`](/part3/config/configuration/#eth1_follow_distance) 是可被考慮之區塊的（近似）最小深度。

對於信標鏈主網，這個參數[被從](https://github.com/ethereum/consensus-specs/pull/2093/files) 32 增加到 64 個紀元。除了 `ETH1_FOLLOW_DISTANCE` 所提供的八小時寬限之外，這個增加意在讓開發者有更多時間在 Eth1 鏈上發生任何麻煩時做出回應。

關於這些參數的詳細分析，見這篇[文章](https://ethresear.ch/t/on-the-way-to-eth1-finality/7041?u=benjaminion)。

##### `SLOTS_PER_HISTORICAL_ROOT`

信標鏈儲存其過往歷史的方式經歷過好幾次重新設計。當前的設計是一個[雙重批次累加器](https://ethresear.ch/t/double-batched-merkle-log-accumulator/571?u=benjaminion)。每個時段的區塊根與狀態根被儲存在狀態中 `SLOTS_PER_HISTORICAL_ROOT` 個時段。當那些清單滿了，每份清單就[各別被 Merkle 化](/part3/transition/epoch/#def_process_historical_summaries_update)，而它們的根被加到不斷增長的 `state.historical_summaries` 清單中、置於一個 [`HistoricalSummary`](/part3/containers/dependencies/#historicalsummary) 容器內。

#### 狀態清單長度

下面的參數設定信標鏈狀態中某些清單的大小。有些清單有著自然的大小，其他的——例如驗證者註冊表——則需要一個明示的最大大小[來引導 SSZ 序列化](https://github.com/ethereum/consensus-specs/pull/1180)。

| 名稱                           | 值                                 | 單位             | 時長      |
|--------------------------------|-----------------------------------    |------------------|---------------|
| `EPOCHS_PER_HISTORICAL_VECTOR` | `uint64(2**16)`（= 65,536）            | 紀元           | ~0.8 年    |
| `EPOCHS_PER_SLASHINGS_VECTOR`  | `uint64(2**13)`（= 8,192）             | 紀元           | ~36 天      |
| `HISTORICAL_ROOTS_LIMIT`       | `uint64(2**24)`（= 16,777,216）        | 歷史根 | ~52,262 年 |
| `VALIDATOR_REGISTRY_LIMIT`     | `uint64(2**40)`<br/>（= 1,099,511,627,776） | 驗證者       | -         |

##### `EPOCHS_PER_HISTORICAL_VECTOR`

這是「被儲存之先前 RANDAO 混合值」的紀元數（每個紀元一個）。能夠存取過去的 RANDAO 混合值，使歷史的洗牌得以被重新計算。由於 [Validator](/part3/containers/dependencies/#validator) 記錄追蹤所有過去驗證者的啟用與退出紀元，我們可以重建過去的委員會，只要我們有那些 RANDAO 值就能回溯。舉例來說，這項資訊可以用於罰沒久遠之前的證明。這個參數的值[是如何決定的](https://github.com/ethereum/consensus-specs/pull/1196)並不清楚。

##### `EPOCHS_PER_SLASHINGS_VECTOR`

在一個行為不良之驗證者被罰沒的那個紀元，它的有效餘額被加到狀態中的一個累加器。如此一來，`state.slashings` 清單就追蹤「在最後 `EPOCHS_PER_SLASHINGS_VECTOR` 個紀元期間被罰沒的所有驗證者」的總有效餘額。

在被罰沒之後 `EPOCHS_PER_SLASHINGS_VECTOR` `//` `2` 的時間點，一筆進一步的懲罰被套用於被罰沒的驗證者，這筆懲罰基於「在它原本被罰沒之前的 4096 個紀元、與之後的 4096 個紀元期間被罰沒之價值的總量」。

這的構想是「不成比例地重罰協同攻擊」——其中許多驗證者大約在同一時間違反罰沒條件——同時只輕微地懲罰「因犯錯而被罰沒」的驗證者。Eth2 的早期設計總是會罰沒一個驗證者的全部存款。

另見 [`PROPORTIONAL_SLASHING_MULTIPLIER_BELLATRIX`](#proportional_slashing_multiplier)。

##### `HISTORICAL_ROOTS_LIMIT`

每隔 [`SLOTS_PER_HISTORICAL_ROOT`](#slots_per_historical_root) 個時段，信標狀態中的區塊根清單與狀態根清單就被 Merkle 化並加到 `state.historical_roots` 清單。雖然 `state.historical_roots` 原則上是無界限的，所有 SSZ 清單都必須指定最大大小。`HISTORICAL_ROOTS_LIMIT` 這個大小在接下來的數千年都沒問題，在那之後它就是別人的問題了。這份清單以每年不到 10 KB 的速度增長。

像這樣儲存過去的根，使得在需要時可以針對信標鏈歷史中任何東西構造 Merkle 證明。

##### `VALIDATOR_REGISTRY_LIMIT`

每次 Eth1 存款合約處理一筆來自新驗證者（以其公鑰辨識）的存款，一個新條目就被附加到 `state.validators` 清單。

在當前的設計中，驗證者永遠不會被從這份清單中移除，即使在它退出驗證者身分之後。它們會永遠繼續在信標鏈中被追蹤。有一項提案 [EIP-6914](https://eips.ethereum.org/EIPS/eip-6914)，打算在一個驗證者退出並提領之後過一段時間重複使用（回收）驗證者記錄，但它尚未被採納。

這份清單的最大長度是 `VALIDATOR_REGISTRY_LIMIT`，它是一兆，所以我們應該有好一陣子沒問題，尤其鑑於最低存款數額是 1 以太幣。

#### 獎勵與懲罰

| Name | Value |
| - | - |
| `BASE_REWARD_FACTOR` | `uint64(2**6)` (= 64) |
| `WHISTLEBLOWER_REWARD_QUOTIENT` | `uint64(2**9)` (= 512) |
| `PROPOSER_REWARD_QUOTIENT` | `uint64(2**3)` (= 8) |
| `INACTIVITY_PENALTY_QUOTIENT` | `uint64(2**26)` (= 67,108,864) |
| `MIN_SLASHING_PENALTY_QUOTIENT` | `uint64(2**7)` (= 128) |
| `PROPORTIONAL_SLASHING_MULTIPLIER` | `uint64(1)` |
| `INACTIVITY_PENALTY_QUOTIENT_ALTAIR` | `uint64(3 * 2**24)` (= 50,331,648) |
| `MIN_SLASHING_PENALTY_QUOTIENT_ALTAIR` | `uint64(2**6)` (= 64) |
| `PROPORTIONAL_SLASHING_MULTIPLIER_ALTAIR` | `uint64(2)` |
| `INACTIVITY_PENALTY_QUOTIENT_BELLATRIX` | `uint64(2**24)` (= 16,777,216) |
| `MIN_SLASHING_PENALTY_QUOTIENT_BELLATRIX` | `uint64(2**5)` (= 32) |
| `PROPORTIONAL_SLASHING_MULTIPLIER_BELLATRIX` | `uint64(3)` |

請注意，此處有著值不同的相似常數。

  - 最初的信標鏈 Phase&nbsp;0 常數沒有字尾。
  - 在 Altair 升級中被更新的常數有字尾 `_ALTAIR`。
  - 在 Bellatrix 升級中被更新的常數有字尾 `_BELLATRIX`。

這在規格儲存庫中[如此解釋](https://github.com/ethereum/consensus-specs/tree/v1.3.0/configs#forking)：

> 變數不會被取代，而是隨分叉而被擴充。這是為了支援「跨越一個分叉邊界、從一個狀態同步到另一個狀態」，而不必熱抽換一份設定。相反地，對於引入某個變數變更的分叉，該變數名稱會被加上分叉名稱作為字尾。

##### `BASE_REWARD_FACTOR`

這是「為改變 Eth2 發行率而要轉動」的那個大旋鈕。幾乎所有驗證者獎勵都以一個「每增量基礎獎勵」為基準來計算，它[被表述為](/part3/transition/epoch/#def_get_base_reward_per_increment)，

```code
  EFFECTIVE_BALANCE_INCREMENT * BASE_REWARD_FACTOR // integer_squareroot(get_total_active_balance(state))
```

因此，每個紀元的驗證者總獎勵（Eth2 發行率）可以藉由增加或減少 `BASE_REWARD_FACTOR` 來調校。

例外是「提議者因在區塊中納入罰沒舉報而得的獎勵」。然而，這些被「所燒掉的質押量」抵銷有餘，所以不會增加整體的發行率。

##### `WHISTLEBLOWER_REWARD_QUOTIENT`

[TODO: link to some explanation of WB process]::

一個不與基礎獎勵綁定的獎勵，是吹哨者獎勵。這是一筆給予「含有一份或多份『提議者或證明者違反某項罰沒條件』之證明的區塊」之提議者的數額。吹哨者獎勵被設為被罰沒驗證者有效餘額的 $\frac{1}{512}$。

吹哨者獎勵來自信標鏈上以太幣的新發行，但被「因罰沒懲罰而燒掉的以太幣」抵銷有餘。

##### `PROPOSER_REWARD_QUOTIENT`

`PROPOSER_REWARD_QUOTIENT` 在 Altair 升級中被移除，改用 [`PROPOSER_WEIGHT`](/part3/config/constants/#incentivization-weights)。它曾被用來在把證明納入區塊時，於證明者與提議者之間分派獎勵。

<a id="inactivity_penalty_quotient"></a>

##### `INACTIVITY_PENALTY_QUOTIENT_BELLATRIX`

這個值取代了 `INACTIVITY_PENALTY_QUOTIENT` 與 `INACTIVITY_PENALTY_QUOTIENT_ALTAIR`。

如果信標鏈未最終確定一個檢查點的時間超過 [`MIN_EPOCHS_TO_INACTIVITY_PENALTY`](#min_epochs_to_inactivity_penalty) 個紀元，那麼它就進入「洩漏」模式。在這個模式中，任何不投票（或為一個不正確的目標投票）的驗證者，每個紀元都被處以一筆 `(effective_balance * inactivity_score) // (` `INACTIVITY_SCORE_BIAS` ` * ` `INACTIVITY_PENALTY_QUOTIENT_BELLATRIX` `)` 的懲罰。

自 Altair 升級以來，`inactivity_score` 已成為一個每驗證者的量，而先前驗證者在洩漏期間錯失一項職責時，是被一個全域計算出的數額所懲罰。關於這的理路、以及這個分數如何按每個驗證者計算的更多內容，見[怠惰懲罰](/part3/config/configuration/#inactivity-penalties)。

在洩漏期間，沒有驗證者收到獎勵，而當它們未能履行職責時，它們繼續累積正常的懲罰。此外，對於驗證者未做出正確、及時之目標投票的紀元，它們收到一筆洩漏懲罰。

要檢視洩漏對單一一個驗證者餘額的影響，假設在一段怠惰洩漏（未最終確定）的期間，該驗證者完全離線。在每個紀元，離線的驗證者會被處以一筆額外的數額 $nB / \alpha$，其中 $n$ 是自洩漏開始以來的紀元數，$B$ 是該驗證者的有效餘額，而 $\alpha$ 是當時通行的怠惰懲罰商（目前是 `INACTIVITY_PENALTY_QUOTIENT_BELLATRIX`）。

有效餘額 $B$ 依設計會維持恆定一陣子，在這段時間內，$n$ 個紀元之後的懲罰總額會是 $n(n+1)B / 2\alpha$。這有時被稱為「平方洩漏」，因為它以一階近似而言以 $n^2$ 成長。如果 $B$ 是連續可變的，那麼這項懲罰會滿足 $\frac{dB}{dt}=-\frac{Bt}{\alpha}$，解之可得 $B(t)=B_0e^{-t^2/2\alpha}$。實際的行為介於這兩者之間（分段平方），因為有效餘額既非恆定、也非連續可變，而是以階梯式的方式遞減。

在連續近似中，怠惰懲罰商 $\alpha$ 是「把一個不參與驗證者的餘額減到 $1 / \sqrt{e}$（即其初始值約 60.7%）所需時間」的平方。`INACTIVITY_PENALTY_QUOTIENT_BELLATRIX` 的值為 `2**24` 時，這相當於 4096 個紀元，或 18.2 天。

怠惰洩漏（又稱平方洩漏）的構想，在最初的 [Casper FFG 論文](https://arxiv.org/abs/1710.09437)中被提出。它所處理的問題是：如果驗證者集合中一大部分同時離線，就不可能繼續最終確定檢查點，因為最終確定需要代表總質押 2/3 的驗證者投出多數票。

為了恢復，怠惰洩漏逐步減少「未做出證明之驗證者」的質押，直到最終，參與的驗證者掌控了剩餘質押的 2/3。屆時它們就能再次開始最終確定檢查點。

這個怠惰懲罰機制，被設計來在面對災難性事件時長期保護鏈（有時被稱為「在第三次世界大戰中存活的能力」）。其結果可能是信標鏈在一個網路分區的兩側永久地分裂成兩條獨立的鏈，而對於任何無法在幾週內修復的問題，這被假定為一個合理的結果。在這個意義上，信標鏈在形式上把可用性置於一致性之上的優先位置。（你[兩者不可兼得](https://en.wikipedia.org/wiki/CAP_theorem)。）

`INACTIVITY_PENALTY_QUOTIENT` 的值在信標鏈上線時[被增加](https://github.com/ethereum/consensus-specs/commit/157f7e8ef4be3675543980e68581eb4b73284763)了四倍，從 `2**24` 增為 `2**26`，用意是萬一在早期由於實作問題而發生未最終確定，較不嚴厲地懲罰驗證者。事實上，信標鏈 Phase&nbsp;0 的十一個月期間並沒有任何未最終確定的情形。

這個值在 Altair 升級中被減少了四分之一，從 `2**26`（`INACTIVITY_PENALTY_QUOTIENT`）減為 `3 * 2**24`（`INACTIVITY_PENALTY_QUOTIENT_ALTAIR`），並在 Bellatrix 升級中減為它的最終值 `2**24`（`INACTIVITY_PENALTY_QUOTIENT_BELLATRIX`）。降低怠惰懲罰商，會在發生怠惰洩漏時加快最終確定的恢復。

<a id="min_slashing_penalty_quotient"></a>

##### `MIN_SLASHING_PENALTY_QUOTIENT_BELLATRIX`

當一個驗證者首次被定罪犯了一項可罰沒的過錯時，一筆初始懲罰被套用。這被計算為 `validator.effective_balance` ` // ` `MIN_SLASHING_PENALTY_QUOTIENT_BELLATRIX`。

因此，初始罰沒懲罰介於 0.5&nbsp;ETH 與 1&nbsp;ETH 之間，視該驗證者的有效餘額而定（它介於 16 與 32 以太幣之間；請注意有效餘額以 Gwei 為單位）。

一筆進一步的罰沒懲罰之後會被套用，它基於「在一段 [`EPOCHS_PER_SLASHINGS_VECTOR`](#epochs_per_slashings_vector) 期間被罰沒的餘額總量」。

`MIN_SLASHING_PENALTY_QUOTIENT` 的值在信標鏈上線時[被增加](https://github.com/ethereum/consensus-specs/commit/157f7e8ef4be3675543980e68581eb4b73284763)了四倍，從 `2**5` 增為 `2**7`，預料到對以太坊&nbsp;2.0 質押規則的不熟悉，很可能會導致一些不留神的使用者被罰沒。結果，Phase&nbsp;0 期間總共有 157 個驗證者被罰沒，就所能查明的範圍而言全都是使用者錯誤或設定錯誤的結果。

這個參數的值在 Altair 升級中被減半，從 `2**7`（`MIN_SLASHING_PENALTY_QUOTIENT`）減為 `2**6`（`MIN_SLASHING_PENALTY_QUOTIENT_ALTAIR`），並在 Bellatrix 升級中設為它的最終值 `2**5`（`MIN_SLASHING_PENALTY_QUOTIENT_BELLATRIX`）。

<a id="proportional_slashing_multiplier"></a>

##### `PROPORTIONAL_SLASHING_MULTIPLIER_BELLATRIX`

當一個驗證者已被罰沒時，一筆進一步的懲罰之後會被套用於該驗證者，它基於「在一個以那次罰沒事件為中心、大小為 [`EPOCHS_PER_SLASHINGS_VECTOR`](#epochs_per_slashings_vector) 個紀元的窗口（前後各約 18 天）期間，有多少其他驗證者被罰沒」。

「該驗證者剩餘有效餘額中將被扣除的比例」[被計算為](/part3/transition/epoch/#slashings)：`PROPORTIONAL_SLASHING_MULTIPLIER_BELLATRIX` 乘以「該窗口中被罰沒驗證者的有效餘額總和」，除以「所有驗證者的總有效餘額」。這個機制的構想，是輕罰意外（其中只有少量驗證者被罰沒）、重罰攻擊（其中許多驗證者協同地雙重投票）。

要最終確定相衝突的檢查點，至少三分之一的餘額必定為兩者都投過票。這就是為什麼 `PROPORTIONAL_SLASHING_MULTIPLIER` 的「自然」設定是三：萬一發生一場最終確定相衝突檢查點的攻擊，攻擊者會失去他們的全部質押。這提供了「最大的最小可問責安全餘裕」。

然而，對於信標鏈的初始階段 Phase&nbsp;0，`PROPORTIONAL_SLASHING_MULTIPLIER` 被設為一。它在 Altair 升級時被增為二，並在 Bellatrix 升級時增為它的最終值三。較低的值提供了某種保險，以防客戶端臭蟲在早期可能造成大規模罰沒。

#### 每個區塊的最大操作數

<a id="max_proposer_slashings"></a>
<a id="max_attester_slashings"></a>
<a id="max_attestations"></a>
<a id="max_deposits"></a>
<a id="max_voluntary_exits"></a>
<a id="max_bls_to_execution_changes"></a>

| Name | Value |
| - | - |
| `MAX_PROPOSER_SLASHINGS`       | `2**4` (= 16)  |
| `MAX_ATTESTER_SLASHINGS`       | `2**1` (= 2)   |
| `MAX_ATTESTATIONS`             | `2**7` (= 128) |
| `MAX_DEPOSITS`                 | `2**4` (= 16)  |
| `MAX_VOLUNTARY_EXITS`          | `2**4` (= 16)  |
| `MAX_BLS_TO_EXECUTION_CHANGES` | `2**4` (= 16)  |

這些參數被用來為了 SSZ 序列化的目的而界定信標區塊主體中各串列的大小，同時也約束信標區塊的最大尺寸，使其能高效傳播，並避免 DoS 攻擊。

對所選用值的一些評論：

  - 我曾[在別處](https://github.com/ethereum/consensus-specs/issues/2152)建議把 `MAX_DEPOSITS` 從十六減為一，以確保更多驗證者必須處理存款，這會鼓勵它們運行 Eth1 客戶端。
  - 乍看之下，一個區塊中可納入的提議者罰沒數與證明者罰沒數之間，似乎有不對等之處。但請注意，一筆證明者罰沒（attester slashing）（a）可以比一筆提議者罰沒（proposer slashing）大得多，而且（b）可能導致比一筆提議者罰沒多得多的驗證者被罰沒。
  - `MAX_ATTESTATIONS` 是 [`MAX_COMMITTEES_PER_SLOT`](#max_committees_per_slot) 值的兩倍。這容許有一個空的時段（沒有區塊提議），卻仍然能在下一個時段中納入那個空時段的所有證明。由於理想上每個委員會產生單一一筆聚合證明，一個區塊能容納兩個時段份的聚合證明。

#### 同步委員會

<a id="sync_committee_size"></a>
<a id="epochs_per_sync_committee_period"></a>

| Name | Value | Unit | Duration |
| - | - | - | - |
| `SYNC_COMMITTEE_SIZE` | `uint64(2**9)` (= 512) | Validators | |
| `EPOCHS_PER_SYNC_COMMITTEE_PERIOD` | `uint64(2**8)` (= 256) | epochs | ~27 hours |

[TODO: Link to sync committees section]::

同步委員會（sync committee）由 Altair 升級引入，用以讓輕客戶端能快速且無須信任地判定信標鏈的鏈頭。

我們為什麼需要一種新的委員會型別？難道不能建構在既有的委員會之上嗎，比如一個時段中的委員會 0 到 3？畢竟為鏈頭投票本就已是它們的職責之一。原因在於，同步委員會不要太頻繁地更換，對於降低輕客戶端的負載很重要。標準委員會每個時段都更換；我們在這裡需要某種存續長久得多的東西。

任何時候都只有單一一個同步委員會在運作中，它包含「全體驗證者集合中、隨機選出之大小為 `SYNC_COMMITTEE_SIZE` 的子集」。

一個同步委員會只在 `EPOCHS_PER_SYNC_COMMITTEE_PERIOD` 個紀元內履行其職責（並因此而收到獎勵），直到下一個委員會接手。

<!-- Number of validators -->

在有 500,000 個驗證者的情況下，被選中擔任同步委員會職責的兩次之間，預期間隔約為 37 個月。某個驗證者身在當前同步委員會中的機率，會是每驗證者 $\frac{512}{500{,}000}$。

`SYNC_COMMITTEE_SIZE` 是[安全性](https://notes.ethereum.org/iMxxlEkuQMiPkEL1S6SfbQ)（確保始終有足夠多誠實的驗證者在場）與輕客戶端效率（確保它們不必處理太多運算）之間的一項[權衡取捨](https://github.com/ethereum/consensus-specs/pull/2130)。就安全性而言，512 這個值是保守的。舉例來說，若一個同步委員會把一個無效的區塊投票通過，對通往其他協定的無須信任跨鏈橋而言會是災難性的。

`EPOCHS_PER_SYNC_COMMITTEE_PERIOD` 約為一天，同樣是安全性（夠短，使攻擊者難以找到並腐化委員會成員）與效率（降低輕客戶端的資料負載）之間的一項權衡取捨。

#### 執行（Execution）

<a id="max_bytes_per_transaction"></a>
<a id="max_transactions_per_payload"></a>
<a id="bytes_per_logs_bloom"></a>
<a id="max_extra_data_bytes"></a>
<a id="max_withdrawals_per_payload"></a>

| Name | Value |
| - | - |
| `MAX_BYTES_PER_TRANSACTION` | `uint64(2**30)` (= 1,073,741,824) |
| `MAX_TRANSACTIONS_PER_PAYLOAD` | `uint64(2**20)` (= 1,048,576) |
| `BYTES_PER_LOGS_BLOOM` | `uint64(2**8)` (= 256) |
| `MAX_EXTRA_DATA_BYTES` | `2**5` (= 32) |
| `MAX_WITHDRAWALS_PER_PAYLOAD` | `uint64(2**4)` (= 16) |

這些常數中的前四個，是在合併前的 Bellatrix 升級時引入的，只被用來界定 [`ExecutionPayload`](/part3/containers/execution/#executionpayload) 類別中某些欄位的大小。

執行酬載（execution payload，舊稱 Eth1 區塊）包含一個最多 `MAX_TRANSACTIONS_PER_PAYLOAD` 筆一般以太坊交易的串列。其中每一筆的大小最多為 `MAX_BYTES_PER_TRANSACTION`。需要這些常數的唯一原因，是 [SSZ 串列型別](/part2/building_blocks/ssz/#lists)要求必須指定一個最大尺寸。它們被設得大得荒謬，但這在實務上不成問題。

`BYTES_PER_LOGS_BLOOM` 與 `MAX_EXTRA_DATA_BYTES` 是直接沿用自[黃皮書](https://ethereum.github.io/yellowpaper/paper.pdf)所規範的 Eth1 區塊，分別是一個區塊的布隆過濾器（Bloom filter）大小，以及一個區塊的額外資料欄位大小。執行酬載的額外資料，類比於一個信標區塊的塗鴉（graffiti）——區塊建構者可以把它設為他們所選的任何值。

`MAX_WITHDRAWALS_PER_PAYLOAD` 是在 [Capella 升級](/part4/history/capella/)時引入的。它是「共識客戶端會要求執行客戶端納入一個執行酬載中的提領數」的最大值。其結果是，提領的速率被限制為每個時段 `MAX_WITHDRAWALS_PER_PAYLOAD` 筆。

#### 提領處理

<a id="max_validators_per_withdrawals_sweep"></a>

| Name | Value |
| - | - |
| `MAX_VALIDATORS_PER_WITHDRAWALS_SWEEP` | `16384` (= 2**14 ) |

這個 preset 常數是在 [Capella 升級](/part4/history/capella/)中引入的，用以約束每個節點在處理提領時必須做的工作量。

每個區塊的提領交易數，被約束在 [`MAX_WITHDRAWALS_PER_PAYLOAD`](#max_withdrawals_per_payload)。但並非所有驗證者都符合提領交易的資格，這意味著節點可能必須無限制地搜遍整個驗證者集合，才能找到足夠多的提領來納入。搜尋驗證者集合可能是一項昂貴的操作，因此我們[約束這項搜尋](/part3/transition/block/#def_get_expected_withdrawals)，每個區塊只考慮 `MAX_VALIDATORS_PER_WITHDRAWALS_SWEEP` 個驗證者。如果我們找到的可提領驗證者數少於 `MAX_WITHDRAWALS_PER_PAYLOAD`，那麼我們就製作較少的提領交易。

一個驗證者可能不可提領的主要原因，是它仍持有一個舊的 `0x00` [BLS 提領憑證](/part3/config/constants/#withdrawal-prefixes)。至少在 Capella 的早期，這可能會導致驗證者集合中出現長段不可提領的區段，那時許多驗證者尚未更新它們的憑證。

另一個原因可能是有效餘額低於 [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance)。萬一發生[怠惰洩漏](/part2/incentives/inactivity/)，這也可能導致長段的驗證者不可提領。

### 配置（Configuration）<!-- /part3/config/configuration/ -->

#### 創世設定

信標鏈的創世早已遠去。儘管如此，能夠快速架起測試網的能力在各種情境下都很有用，因此規格保留了創世功能，現在稱為[初始化](/part3/initialise/#initialise-state)。

以下參數指的是實際的主網信標鏈創世，我會在那個脈絡下解釋它們。在啟動新的測試網時，這些參數當然會被更改。例如，可參見 [Prater 測試網](https://github.com/eth2-clients/eth2-networks/blob/274e71c7af8fb26f65b47016ffa6169079315e2c/shared/prater/config.yaml)的配置檔。

| Name | Value |
| - | - |
| `MIN_GENESIS_ACTIVE_VALIDATOR_COUNT` | `uint64(2**14)` (= 16,384) |
| `MIN_GENESIS_TIME` | `uint64(1606824000)` (Dec 1, 2020, 12pm UTC) |
| `GENESIS_FORK_VERSION` | `Version('0x00000000')` |
| `GENESIS_DELAY` | `uint64(604800)` (7 days) |

##### `MIN_GENESIS_ACTIVE_VALIDATOR_COUNT`

`MIN_GENESIS_ACTIVE_VALIDATOR_COUNT` 是「在信標鏈能開始產生區塊之前，必須已存入的完整驗證者質押」的最小數目。這個數字被選來確保某種程度的安全性。它容許每個時段有四個 128 名成員的委員會，而非每個時段 64 個委員會——後者是當時路線圖上（但如今已不在）為了支援全面運作的資料分片所最終想要的。較少的驗證者意味著每驗證者的獎勵較高，所以它被設計來吸引早期參與者，把事情啟動起來。

`MIN_GENESIS_ACTIVE_VALIDATOR_COUNT` 曾經高得多（65,536 = 質押 200 萬以太幣），但在下方的 `MIN_GENESIS_TIME` 被加入時調降了。

在信標鏈創世的實際事件中，有 21,063 個參與的驗證者，舒適地超出了所需的最小數量。

##### `MIN_GENESIS_TIME`

`MIN_GENESIS_TIME` 是信標鏈能開始的最早日期。

有一個 `MIN_GENESIS_TIME`，讓我們能以比先前認為所需更少的驗證者來啟動鏈。先前的計畫是一旦有 `MIN_GENESIS_ACTIVE_VALIDATOR_COUNT` 個驗證者完成質押就啟動鏈。但有人擔心，在初始驗證者數偏低的情況下，單一一個實體可能構成它們的多數，然後採取行動阻止其他驗證者進入（一種「[守門人攻擊](https://github.com/ethereum/consensus-specs/pull/1467)」）。有一個最小創世時間，讓所有想要存款的人，能在他們可能被守門人攻擊排除之前，有時間完成存款。

信標鏈實際上於 2020 年 12 月 1 日 UTC 12:00:23 啟動。多出來的 23 秒，來自第一個符合[創世判準](/part3/initialise/#genesis-state)之 Eth1 區塊的時間戳，即[區塊 11320899](https://etherscan.io/block/11320899)。我喜歡把這想成是工作量證明的一小點殘餘，永遠嵌在信標鏈的歷史之中。

##### `GENESIS_FORK_VERSION`

與以太坊&nbsp;1.0 不同，信標鏈為它的各個分叉賦予協定內的版本。更多解釋見 [Version 自訂型別](/part3/config/types/#version)。

`GENESIS_FORK_VERSION` 是信標鏈在其「創世」事件——鏈首次開始產生區塊的時點——所起始使用的分叉版本。如今，這個值只在[計算](/part3/helper/misc/#compute_domain)存款訊息與 BLS 憑證變更訊息的加密域時被用到，這兩種訊息在所有分叉之間都有效。

[Altair](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/fork.md#configuration)、[Bellatrix](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/bellatrix/fork.md#configuration) 與 [Capella](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/capella/fork.md#configuration) 升級的分叉版本與時機，在它們各自的規格中定義如下。

<a id="altair_fork_version"></a>
<a id="altair_fork_epoch"></a>
<a id="bellatrix_fork_version"></a>
<a id="bellatrix_fork_epoch"></a>
<a id="capella_fork_version"></a>
<a id="capella_fork_epoch"></a>

| Name | Value |
| - | - |
| `ALTAIR_FORK_VERSION`    | `Version('0x01000000')` |
| `ALTAIR_FORK_EPOCH`      | `Epoch(74240)` (Oct 27, 2021, 10:56:23am UTC) |
| `BELLATRIX_FORK_VERSION` | `Version('0x02000000')` |
| `BELLATRIX_FORK_EPOCH`   | `Epoch(144896)` (Sept 6, 2022, 11:34:47am UTC) |
| `CAPELLA_FORK_VERSION`   | `Version('0x03000000')` |
| `CAPELLA_FORK_EPOCH`     | `Epoch(194048)` (April 12, 2023, 10:27:35pm UTC) |

##### `GENESIS_DELAY`

`GENESIS_DELAY` 是一段寬限期，讓節點與節點運營者有時間為創世事件做準備。創世事件不能在 [`MIN_GENESIS_TIME`](#min_genesis_time) 之前發生。如果 [`MIN_GENESIS_ACTIVE_VALIDATOR_COUNT`](#min_genesis_active_validator_count) 個驗證者沒有在 `MIN_GENESIS_TIME` 之前足夠提早地完成註冊，那麼創世會在足夠多的驗證者完成註冊之後 `GENESIS_DELAY` 秒發生。

七天的預先通知被認為足夠：一旦創世參數確定，讓客戶端開發團隊有時間發布一個版本，並讓節點運營者升級到那個版本。當然，也讓大家有時間籌辦一些派對。它隨著時間從 2 天增加而來，這是基於某些創世前測試網所學到的教訓。

#### 時間參數

| Name                                  | Value                     | Unit        | Duration   |
|---------------------------------------|---------------------------|-------------|------------|
| `SECONDS_PER_SLOT`                    | `uint64(12)`              | seconds     | 12 seconds |
| `SECONDS_PER_ETH1_BLOCK`              | `uint64(14)`              | seconds     | 14 seconds |
| `MIN_VALIDATOR_WITHDRAWABILITY_DELAY` | `uint64(2**8)` (= 256)    | epochs      | ~27 hours  |
| `SHARD_COMMITTEE_PERIOD`              | `uint64(2**8)` (= 256)    | epochs      | ~27 hours  |
| `ETH1_FOLLOW_DISTANCE`                | `uint64(2**11)` (= 2,048) | Eth1 blocks | ~8 hours   |

##### `SECONDS_PER_SLOT`

This was originally six seconds, but [is now twelve](https://github.com/ethereum/consensus-specs/pull/1428#issue-327424983), and has been [other values](https://github.com/ethereum/consensus-specs/pull/143/files#diff-51a43328a58414e132a744f3771f018cL42) in between.

Network delays are the main limiting factor in shortening the slot length. Three communication activities need to be accomplished within a slot, and it is supposed that four seconds is enough for the vast majority of nodes to have participated in each:

1. 區塊在一個時段的開始時被提議，並應在最初四秒內傳播到網路的大部分。
2. 在進入一個時段四秒時，委員會成員建立並廣播證明，包括為這個時段的區塊作證。在接下來的四秒內，這些證明被各委員會中的聚合者收集。
3. 在進入該時段八秒時，聚合者廣播它們的聚合證明，這些證明接著有四秒的時間抵達正在提議下一個區塊的驗證者。

[TODO: find this discussion and link to it]::

人們普遍有意在未來縮短時段時間，也許縮短到 [8 秒](https://github.com/ethereum/consensus-specs/issues/1890#issue-638024803)，如果這在實務上證明可行的話。又或者把它延長到 [16 秒](https://ethresear.ch/t/two-slot-proposer-builder-separation/10980?u=benjaminion)。

合併之後，執行客戶端用來驗證執行酬載內容（也就是一般以太坊交易）所花的時間，如今處在步驟 1（最初四秒）期間驗證者的關鍵路徑上。為了讓驗證者正確地作證，信標區塊必須先被廣播、傳播並接收，然後被共識客戶端驗證，也被執行客戶端驗證，全部都要在那最初的四秒窗口內完成。在臨界的情況下，執行驗證所多花的時間，可能把整個過程推過「必須做出證明」的那個四秒時點。這可能導致錯誤地為一個空時段投票。進一步的解釋見 Adrian Sutton 的文章 [Understanding Attestation Misses](https://symphonious.net/2022/09/25/understanding-attestation-misses/)。

##### `SECONDS_PER_ETH1_BLOCK`

假設的 Eth1 鏈區塊間隔，在考量 Eth1 鏈上的區塊時——無論是在創世時、或在為存款合約狀態投票時——與 [`ETH1_FOLLOW_DISTANCE`](#eth1_follow_distance) 搭配使用。

自 2020 年 1 月以來的 [Eth1 平均出塊時間](https://etherscan.io/chart/blocktime)其實更接近 13 秒，不過沒關係。淨效果是，我們會在 Eth1 鏈中往回追溯得比 [`ETH1_FOLLOW_DISTANCE`](#eth1_follow_distance) 所暗示的稍微深一些，這應該更安全。

##### `MIN_VALIDATOR_WITHDRAWABILITY_DELAY`

一個驗證者一旦通過了退出佇列，就能停止參與。然而，它的質押在 `MIN_VALIDATOR_WITHDRAWABILITY_DELAY` 的期間內仍維持鎖定。這是為了留一些時間，讓任何可罰沒的行為被偵測並回報，使得該驗證者仍可被懲罰（在這種情況下，該驗證者的可提領時間會被往未來推 [`EPOCHS_PER_SLASHINGS_VECTOR`](/part3/config/preset/#epochs_per_slashings_vector)）。

`MIN_VALIDATOR_WITHDRAWABILITY_DELAY` 期間一旦過去，只要該驗證者設定了 [`ETH1_ADDRESS_WITHDRAWAL_PREFIX`](/part3/config/constants/#eth1_address_withdrawal_prefix)（`0x01`）的提領憑證，它就符合資格在下一次提領掃描時完整提領其質押與獎勵。無論如何，處於「可提領」狀態意味著一個驗證者如今已完全退出協定。

##### `SHARD_COMMITTEE_PERIOD`

這其實是預期資料分片的實作，而資料分片如今已不在計畫中——至少其最初構想的形式是如此。其[構想是](https://github.com/ethereum/consensus-specs/issues/675#issuecomment-468159678)：若驗證者能非常迅速地出現與消失，對存續較久之委員會的穩定性是不利的。因此，一個驗證者在被啟用之後 `SHARD_COMMITTEE_PERIOD` 個紀元之內，不能發起自願退出。然而，它在這段時間之前仍可能被罰沒而遭逐出。

##### `ETH1_FOLLOW_DISTANCE`

這被用來計算「以太坊&nbsp;1 鏈上能被 Eth2 鏈考量之區塊」的最小深度：它適用於[創世](/part3/initialise/#initialise-state)過程，以及驗證者[對存款的處理](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#process-deposit)。Eth1 鏈深度是把這個值乘以目標 Eth1 平均出塊時間 [`SECONDS_PER_ETH1_BLOCK`](#seconds_per_eth1_block) 估算出來的。

`ETH1_FOLLOW_DISTANCE` 的值並非基於 Eth1 鏈任何鏈重組的預期深度——這類重組鮮少（如果曾經有過的話）超過 2 至 3 個區塊深。它是為了提供時間，以回應 Eth1 鏈上的某個事故，例如客戶端之間的共識失敗。

這個參數為信標鏈主網[從 1024 增加](https://github.com/ethereum/consensus-specs/pull/2093/files)到 2048 個區塊，以便在 Eth1 鏈出現任何麻煩時，讓開發者有更多時間回應。

整個追隨距離的概念已因合併而變得多餘，可能會在未來的某次升級中被移除，使得驗證者能或多或少即時地存款並變為啟用。

#### 驗證者週期

| Name | Value |
| - | - |
| `EJECTION_BALANCE` | `Gwei(2**4 * 10**9)` (= 16,000,000,000) |
| `MIN_PER_EPOCH_CHURN_LIMIT` | `uint64(2**2)` (= 4) |
| `CHURN_LIMIT_QUOTIENT` | `uint64(2**16)` (= 65,536) |

##### `EJECTION_BALANCE`

如果一個驗證者的有效餘額跌到 16 以太幣或以下，它就會被退出系統。這最可能是「[怠惰洩漏](/part3/config/preset/#inactivity_penalty_quotient)」的結果——怠惰洩漏為了維持信標鏈的活性，逐步減少不活躍驗證者的餘額。

這個機制意在保護那些已無法存取自己金鑰的質押者。如果一個驗證者離線久到失去了一半的餘額，它不太可能會回來了。為了讓質押者免於失去一切，我們選擇在驗證者的餘額抵達零之前就把它逐出。

請注意，對有效餘額的依賴意味著：一旦驗證者的實際餘額跌到 16.75 以太幣，它就會被排入逐出佇列。

##### `MIN_PER_EPOCH_CHURN_LIMIT`

驗證者被容許退出系統並停止驗證，新的驗證者也可在任何時候申請加入。基於一些[有趣的理由](https://notes.ethereum.org/@vbuterin/rkhCgQteN#Exiting)，一項設計決定被做出：對進入（啟用）與退出施加速率限制。基本上，在權益證明協定中，驗證者集合不要變化得太快是很重要的。

在正常情況下，一個驗證者能相當迅速地退出：它只需要等待 [`MAX_SEED_LOOKAHEAD`](/part3/config/preset/#max_seed_lookahead)（目前是四）個紀元。然而，如果大量驗證者想在同一時間退出，就會形成一個佇列，每個紀元只容許有限數目的退出。每個紀元的最小退出數（最小的「變動量」）是 `MIN_PER_EPOCH_CHURN_LIMIT`，使得驗證者最終總是能退出。每個紀元實際容許的變動量，是與 `CHURN_LIMIT_QUOTIENT` 搭配[計算](/part3/helper/accessors/#get_validator_churn_limit)出來的。

一旦一個驗證者被標記為符合啟用資格，同樣的規則也適用於新的驗證者啟用。

驗證者能退出的速率，與弱主觀性（weak subjectivity）這個概念、以及弱主觀性週期，有著很強的關聯。

[TODO: Link to weak subjectivity discussion when done]::

##### `CHURN_LIMIT_QUOTIENT`

這與 `MIN_PER_EPOCH_CHURN_LIMIT` 搭配使用，以[計算](/part3/helper/accessors/#get_validator_churn_limit)每個紀元實際容許的驗證者退出數與啟用數。容許的退出數是 `max(MIN_PER_EPOCH_CHURN_LIMIT, n // CHURN_LIMIT_QUOTIENT)`，其中 `n` 是活躍驗證者的數目。同樣的規則也適用於啟用。

#### 怠惰懲罰

| Name | Value | Description |
| - | - | - |
| `INACTIVITY_SCORE_BIAS` | `uint64(2**2)` (= 4) | 每個不活躍紀元的分數點數 |
| `INACTIVITY_SCORE_RECOVERY_RATE` | `uint64(2**4)` (= 16) | 每個無洩漏紀元的分數點數 |

##### `INACTIVITY_SCORE_BIAS`

如果信標鏈未最終確定一個紀元的時間超過 [`MIN_EPOCHS_TO_INACTIVITY_PENALTY`](/part3/config/preset/#min_epochs_to_inactivity_penalty) 個紀元，那麼它就進入「洩漏」模式。在這個模式中，任何不投票（或為一個不正確的目標投票）的驗證者，每個紀元都被處以一筆 `(effective_balance * inactivity_score) // (INACTIVITY_SCORE_BIAS * INACTIVITY_PENALTY_QUOTIENT_BELLATRIX)` 的懲罰。關於怠惰洩漏本身的討論，見 [`INACTIVITY_PENALTY_QUOTIENT_BELLATRIX`](/part3/config/preset/#inactivity_penalty_quotient)。

每驗證者的 `inactivity-score`（怠惰分數）是在 Altair 升級中引入的。在 Phase&nbsp;0 期間，怠惰懲罰是一個遞增的全域數額，套用於所有未在某個紀元中參與的驗證者，不論它們各自的參與紀錄為何。所以一個能在相當大比例時間內參與的驗證者，仍可能因為每紀元怠惰懲罰的成長而被相當嚴厲地懲罰。Vitalik 給出了一個簡化的[例子](https://github.com/ethereum/consensus-specs/issues/2125#issue-737768917)：「如果完全離線的驗證者被洩漏並失去其餘額的 40%，那麼一個努力嘗試保持在線、並成功履行 90% 職責的人，仍會失去其餘額的 4%。這可說是不公平的。」

此外，如果許多驗證者能斷斷續續地參與，這表示降臨到鏈上的那個事件——無論它是什麼——是有可能恢復的（不像永久的網路分區，或是超多數的網路分叉那樣）。怠惰洩漏意在為無法恢復的情況帶來最終性，所以如果情況並非無法恢復，那麼延長達到最終性的時間很可能是件好事。

每個驗證者在信標狀態中都有一個各自的怠惰分數，它由 [`process_inactivity_updates()`](/part3/transition/epoch/#def_process_inactivity_updates) 依如下方式更新。

  - 每個紀元，不論是否處於怠惰洩漏，
    - 當驗證者做出正確、及時的目標投票時，把分數減一，
    - 否則把分數加上 `INACTIVITY_SCORE_BIAS`。
  - 當「不」處於怠惰洩漏時
    - 把每個驗證者的分數減去 `INACTIVITY_SCORE_RECOVERY_RATE`。

分數有一個零的下限。所以，在洩漏之外，驗證者的分數會迅速回到零並停留在那裡，因為 `INACTIVITY_SCORE_RECOVERY_RATE` 大於 `INACTIVITY_SCORE_BIAS`。

在洩漏期間，若 $p$ 是介於 $0$ 與 $1$ 之間的參與率，而 $\lambda$ 是 `INACTIVITY_SCORE_BIAS`，那麼 $N$ 個紀元之後的預期分數是 $\max (0, N((1-p)\lambda - p))$。對於 $\lambda = 4$，這是 $\max (0, N(4 - 5p))$。所以一個有 80% 或更多時間都在參與的驗證者，能維持一個界限在接近零附近的分數。平均參與率低於 80% 時，它的分數會無界地增加。

##### `INACTIVITY_SCORE_RECOVERY_RATE`

當不處於怠惰洩漏時，驗證者做出及時目標投票的紀元，其怠惰分數每紀元減少 `INACTIVITY_SCORE_RECOVERY_RATE` ` + ` `1`；未做出時則減少 `INACTIVITY_SCORE_RECOVERY_RATE` ` - ` `INACTIVITY_SCORE_BIAS`。所以即使對於表現不佳的驗證者，分數減少的速度也是其增加速度的三倍。

新的計分系統意味著，即使在最終確定再次開始之後，某些驗證者仍會因為洩漏而繼續被懲罰。這是[刻意的](https://github.com/ethereum/consensus-specs/issues/2098)。當洩漏使信標鏈達成最終確定時，那個時點我們只有 2/3 的質押在線。如果我們立即停止洩漏（像我們以前那樣），那麼在線的質押量會維持接近 2/3，而隨著少量驗證者來來去去，鏈會容易在最終性的內外反覆翻轉。我們在上線前的某些測試網上見過這種行為。在最終確定之後繼續洩漏，作用是把參與驗證者的餘額提升到大於 2/3，提供一個應有助於防止這種行為的餘裕。

關於怠惰分數的更多分析以及其效果的一些圖表，見[怠惰洩漏](/part2/incentives/inactivity/)那一節。

#### 過渡設定

| Name | Value |
| - | - |
| `TERMINAL_TOTAL_DIFFICULTY` | `58750000000000000000000` |
| `TERMINAL_BLOCK_HASH` | `Hash32()` |
| `TERMINAL_BLOCK_HASH_ACTIVATION_EPOCH` | `FAR_FUTURE_EPOCH` |

這些值不用於信標鏈主規格，而是用於 Bellatrix 的[分叉選擇](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/bellatrix/fork-choice.md)與[驗證者指南](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/bellatrix/validator.md)，以判定執行鏈從工作量證明交接到權益證明的時點。

以太坊工作量證明鏈先前的所有升級，都在一個預先定義的區塊高度發生。對於合併而言，那種做法被認為不安全，因為切換到權益證明的動態是不可逆的。其理路在 [EIP-3675](https://eips.ethereum.org/EIPS/eip-3675) 的「安全考量」一節中給出。

> 在這個脈絡下，為硬分叉使用一個預先定義的區塊號是不安全的，因為 PoS 分叉選擇在過渡期間取得優先權。
>
> 攻擊者可能用少數的雜湊算力，建構一個會滿足區塊高度要求的惡意鏈分叉。然後，第一個 PoS 區塊可能被惡意地提議在這個敵對分叉的 PoW 區塊之上，成為鏈頭，並顛覆過渡的安全性。
>
> 為了保護網路免於這種攻擊情境，鏈所累積的難度（總難度）被用來觸發升級。

因此，Bellatrix 升級定義了一個終端總難度（terminal total difficulty，TTD），合併將在此發生。以太坊工作量證明鏈上的每個區塊，都有一個與之相關的「難度」，它對應於挖出該區塊預期所需的雜湊運算次數。總難度是迄今所有區塊單調遞增的累積難度。

第一個超出 `TERMINAL_TOTAL_DIFFICULTY` 的區塊是以太坊區塊號 [15537393](https://etherscan.io/block/15537393)。那個區塊成為工作量證明之下產生的最後一個正典區塊。[下一個執行酬載](https://etherscan.io/block/15537394)在時段 [4700013](https://beaconcha.in/slot/4700013) 被納入信標鏈，它於 2022 年 9 月 15 日 UTC 06:42:59 產生。

`TERMINAL_BLOCK_HASH` 與 `TERMINAL_BLOCK_HASH_ACTIVATION_EPOCH` 之所以存在，是以防萬一出現麻煩時需要手動選定一個特定的工作量證明分叉來追隨。`TERMINAL_BLOCK_HASH` 本來會透過手動覆寫或客戶端更新而在客戶端中設定，使其指向一個經協議選定為終端區塊的特定工作量證明區塊。實際上並不需要這項功能。

## 容器（Containers）<!-- /part3/containers/ -->

### 前言

我們即將在可執行規格中看到我們的第一段 Python 程式碼。為了規格的目的，這些容器（Container）資料結構，只是衍生自 SSZ 基底 `Container` 類別的 Python 資料類別。

[SSZ](/part2/building_blocks/ssz/) 是在以太坊&nbsp;2.0 中無所不在的序列化與 Merkle 化格式。它不是自我描述的，所以在反序列化時，你需要事先知道你正在解開什麼。SSZ 處理基本型別與複合型別。像下面這樣的類別被當成 SSZ 容器處理，這是一種被定義為「值的有序異質集合」的複合型別。

不同語言的客戶端實作，顯然會使用它們自己的範式來表示這些資料結構。

直接來自規格的兩點說明：

  - 這些定義依拓樸順序排列，以利於規格的執行。
  - 容器實例化時缺少的欄位，預設為它們的[零值](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md#default-values)。

### 雜項依賴 <!-- /part3/containers/dependencies/ -->

#### `Fork`

```python
class Fork(Container):
    previous_version: Version
    current_version: Version
    epoch: Epoch  # Epoch of latest fork
```

分叉資料儲存在 [BeaconState](/part3/containers/state/#beaconstate) 中，用以指明當前與先前的分叉版本。分叉版本被併入加密域中，以使來自其他分叉上驗證者的訊息失效。先前的分叉版本以及變更發生的紀元被儲存下來，使得分叉前的訊息仍可被驗證（至少直到下一次分叉為止）。這確保了證明跨越分叉邊界時的連續性。

請注意，這全都關乎計畫中的協定分叉（升級），與分叉選擇規則、或因狀態轉換錯誤而導致的非預期分叉無關。

#### `ForkData`

```python
class ForkData(Container):
    current_version: Version
    genesis_validators_root: Root
```

`ForkData` 只在 [`compute_fork_data_root()`](/part3/helper/misc/#def_compute_fork_data_root) 中使用。這在為了[對等網路 gossip](https://github.com/ethereum/consensus-specs/pull/1652) 的目的而區分不同的鏈時、以及為了[域分離](/part3/config/constants/#domain-types)時被用到。藉由同時納入當前分叉版本與創世驗證者根，我們可以乾淨俐落地區分諸如主網與某個測試網。即使它們有相同的分叉歷史，創世驗證者根也會不同。

[`Version`](/part3/config/types/#version) 是分叉版本號的資料型別。

#### `Checkpoint`

```python
class Checkpoint(Container):
    epoch: Epoch
    root: Root
```

`Checkpoint`（檢查點）是 [Casper FFG 協定](https://arxiv.org/pdf/1710.09437.pdf)所使用的證成（justification）與最終確定的時點。驗證者用它們來建立 [`AttestationData`](#attestationdata) 投票，而近期檢查點的狀態被記錄在 [`BeaconState`](/part3/containers/state/#beaconstate) 中。

依照 Casper 論文，檢查點包含一個高度與一個區塊根。在這個 Casper FFG 的實作中，每當時段號是 [`SLOTS_PER_EPOCH`](/part3/config/preset/#slots_per_epoch) 的倍數時就出現檢查點，因此它們對應於 `epoch` 號碼。具體而言，檢查點 $N$ 是紀元 $N$ 的第一個時段。[創世區塊](/part3/initialise/#genesis-block)是檢查點 0，一開始就既被證成又被最終確定。

因此，這裡的 `root` 元素是該 `epoch` 中第一個區塊的區塊根。（如果某些時段被跳過了——也就是那些時段沒有區塊——這可能會是一個更早區塊的區塊根。）

談論「證成與最終確定紀元」是非常常見的。這嚴格說來並不正確：被證成與被最終確定的是檢查點。

一個檢查點一旦被最終確定，它所指向的時段以及所有先前的時段就絕不會被回退。

#### `Validator`

```python
class Validator(Container):
    pubkey: BLSPubkey
    withdrawal_credentials: Bytes32  # Commitment to pubkey for withdrawals
    effective_balance: Gwei  # Balance at stake
    slashed: boolean
    # Status epochs
    activation_eligibility_epoch: Epoch  # When criteria for activation were met
    activation_epoch: Epoch
    exit_epoch: Epoch
    withdrawable_epoch: Epoch  # When validator can withdraw funds
```

這是儲存「關於某個別驗證者之大部分資訊」的資料結構，只有驗證者的餘額與怠惰分數儲存在別處。

驗證者的實際餘額分開儲存在 `BeaconState` 結構中，這裡只儲存緩慢變化的「[有效餘額](/part2/incentives/balances/)」。這是因為實際餘額容易相當頻繁地變化（至少每個紀元一次，有時更頻繁）：用來計算狀態根的 Merkle 化過程意味著，只有變化的部分需要重新計算；未變化部分的根可以被快取。把驗證者餘額分離出去，潛在地意味著相較於儲存在這裡，每個紀元只需重新雜湊 1/15（8/121）那麼多的資料，這是一項重要的最佳化。

基於類似的理由，驗證者的怠惰分數也儲存在驗證者紀錄之外，因為它們也是每個紀元更新一次。

一個驗證者的紀錄在它的存款首次被處理時被[建立](/part3/transition/block/#def_get_validator_from_deposit)。送出多筆存款並不會建立多筆驗證者紀錄：使用相同公鑰的存款被聚合在一筆紀錄中。驗證者紀錄絕不過期；它們被永久儲存，即使在該驗證者已退出系統之後也是如此。因此，「驗證者在串列中的索引」與「驗證者的身分」之間存在 1:1 的對應（驗證者紀錄只會被附加到串列上）。

也儲存在 `Validator` 中的有：

  - `pubkey` 既作為該驗證者的唯一身分，也作為「以加密方式驗證宣稱由它簽署之訊息」的手段。公鑰以原始形式儲存，這與 Eth1 不同——在 Eth1 中公鑰被雜湊以構成帳戶位址。這讓公鑰能被聚合，以驗證聚合的證明。
  - `withdrawal_credentials` 視其[前綴](/part3/config/constants/#withdrawal-prefixes)而定，可能指明一個「提領交易將匯入」的 Eth1 帳戶，或者可能是一個舊式的 BLS 承諾，必須先更新它，該驗證者才能進行提領。一個驗證者存款資料中所含的提領憑證，不會被共識層以任何方式檢查。
  - `effective_balance` 是一個自成一格的主題，我們已[略略提及](/part3/config/preset/#max_effective_balance)，在我們檢視[有效餘額更新](/part3/transition/epoch/#effective-balances-updates)時會更完整地討論。
  - `slashed` 指明一個驗證者已被罰沒，也就是因違反罰沒條件而受罰。一個驗證者只能被罰沒一次。
  - 其餘的值是「該驗證者改變狀態、或預定改變狀態」所在的紀元。

[TODO: link to validator lifecycle chapter]::

驗證者生命週期各階段的詳細解釋在[這裡](https://notes.ethereum.org/@hww/lifecycle)，而我們在逐步講解信標鏈邏輯時會詳細涵蓋它。但以簡化的形式，其進程如下：

  1. 一筆 32&nbsp;ETH 的存款已在以太坊&nbsp;1 鏈上完成。尚未有驗證者紀錄存在。
  2. 該存款在某個時段被信標鏈處理。一筆驗證者紀錄被建立，所有紀元欄位都設為 `FAR_FUTURE_EPOCH`。
  3. 在當前紀元結束時，`activation_eligibility_epoch` 被設為下一個紀元。
  4. 在紀元 `activation_eligibility_epoch` 被最終確定之後，藉由適當地設定其 `activation_epoch`，該驗證者被加入啟用佇列，此時會把每紀元的[變動上限](/part3/config/configuration/#min_per_epoch_churn_limit)與 [`MAX_SEED_LOOKAHEAD`](/part3/config/preset/#max_seed_lookahead) 納入考量。
  5. 抵達 `activation_epoch` 時，該驗證者變為啟用，並應履行其職責。
  6. 在 [`SHARD_COMMITTEE_PERIOD`](/part3/config/configuration/#shard_committee_period) 個紀元過去之後的任何時候，一個驗證者都可以請求自願退出。`exit_epoch` 依該驗證者在退出佇列中的位置與 [`MAX_SEED_LOOKAHEAD`](/part3/config/preset/#max_seed_lookahead) 設定，而 `withdrawable_epoch` 被設在那之後 [`MIN_VALIDATOR_WITHDRAWABILITY_DELAY`](/part3/config/configuration/#min_validator_withdrawability_delay) 個紀元。
  7. 從 `exit_epoch` 起，該驗證者不再啟用。已退出的驗證者沒有重新加入的機制：退出是永久的。
  8. 在 `withdrawable_epoch` 之後，該驗證者的全部質押可以被提領。

以上沒有把罰沒、或因餘額過低而被強制退出的情形納入考量。

#### `AttestationData`

```python
class AttestationData(Container):
    slot: Slot
    index: CommitteeIndex
    # LMD GHOST vote
    beacon_block_root: Root
    # FFG vote
    source: Checkpoint
    target: Checkpoint
```

信標鏈仰賴兩種不同共識機制的結合：LMD GHOST 讓鏈持續前進，而 Casper FFG 帶來最終確定。這些在 [Gasper 論文](https://arxiv.org/abs/2003.03052)中有所記載。來自（委員會中的）驗證者的證明，被用來同時為這兩種共識機制各自提供投票。

這個容器是證明資料的基本單位。它提供以下元素。

  - `slot`：每個活躍的驗證者每個紀元應正好做出一筆證明。驗證者有一個指派給其證明的時段，為了驗證的目的把它記錄在這裡。
  - `index`：單一一個時段中可以有數個委員會在運作中。這是該驗證者在那個時段中所屬委員會的編號。它可被用來重建該委員會，以檢查作證的驗證者是否為其成員。理想上，一個時段中來自單一一個委員會的所有（或至少多數）證明會是相同的，因此能被聚合成單一一筆聚合證明。
  - `beacon_block_root` 是該驗證者在本地運行 LMD GHOST 分叉選擇規則後，為那個時段的鏈頭區塊所投的票。如果該驗證者認為當前時段是空的，它可能會是來自某個先前時段之區塊的根。
  - `source` 是該驗證者對「當前最佳之已證成檢查點」的看法，供 Casper FFG 最終確定過程使用。
  - `target` 是該驗證者對「當前紀元起始處之區塊」的看法，同樣供 Casper FFG 最終確定使用。

這個 `AttestationData` 結構會被包裝進數個其他類似但不同的結構中：

  - [`Attestation`](/part3/containers/operations/#attestation) 是證明通常在網路上四處傳遞時的形式。它是經簽署的、且可聚合的，而做出這筆證明的驗證者串列被壓縮成一個位元串列（bitlist）。
  - [`IndexedAttestation`](#indexedattestation) 主要用於[證明者罰沒](/part3/containers/operations/#attesterslashing)。它是經簽署且經聚合的，作證驗證者的串列是一個未經壓縮的索引串列。
  - [`PendingAttestation`](#pendingattestation)。在 Phase&nbsp;0 中，`PendingAttestation` 在區塊處理期間其有效性被檢查過後，被儲存在信標狀態中，待紀元結束時處理。這在 Altair 升級中被重新設計，`PendingAttestation` 不再被使用。

#### `IndexedAttestation`

```python
class IndexedAttestation(Container):
    attesting_indices: List[ValidatorIndex, MAX_VALIDATORS_PER_COMMITTEE]
    data: AttestationData
    signature: BLSSignature
```

這是聚合證明——把同一委員會中多個驗證者的相同證明合併起來——被處理時的形式之一。

[`Attestation`](/part3/containers/operations/#attestation) 與 `IndexedAttestation` 本質上包含相同的資訊。差別在於，作證驗證者的串列在 `IndexedAttestation` 中以未經壓縮的形式儲存。也就是說，每個作證的驗證者都以其全域驗證者索引被指涉，而未作證的驗證者不被納入。要[有效](/part3/helper/predicates/#is_valid_indexed_attestation)，驗證者索引必須唯一且已排序，而簽章必須是一個正好來自所列驗證者集合的聚合簽章。

`IndexedAttestation` 主要在回報[證明者罰沒](/part3/containers/operations/#attesterslashing)時使用。一筆 `Attestation` 可用 [`get_indexed_attestation()`](/part3/helper/accessors/#def_get_indexed_attestation) 轉換成一筆 `IndexedAttestation`。

#### `PendingAttestation`

```python
class PendingAttestation(Container):
    aggregation_bits: Bitlist[MAX_VALIDATORS_PER_COMMITTEE]
    data: AttestationData
    inclusion_delay: Slot
    proposer_index: ValidatorIndex
```

`PendingAttestation` 在 Altair 升級中被移除，現在只出現在分叉期間[升級狀態](/part4/history/altair/)的過程中。以下內容供歷史參考。

在 Altair 之前，區塊中收到的 `Attestation` 會被驗證，然後以 `PendingAttestation` 的形式暫時儲存在信標狀態中，待紀元結束時進一步處理。

一筆 `PendingAttestation` 是一筆 [`Attestation`](/part3/containers/operations/#attestation) 減去簽章，再加上幾個與獎勵計算相關的欄位：

  - `inclusion_delay` 是「該證明被做出」與「它被區塊提議者納入一個信標區塊」之間的時段數。驗證者因其證明被納入區塊而獲得獎勵，但這個獎勵以前會與納入延遲成反比地遞減。這激勵了驗證者迅速地作證與通訊。
  - `proposer_index` 是納入該證明的區塊提議者。區塊提議者每納入一個驗證者的證明就得到一筆微小的獎勵，而不只是為整筆聚合證明而獲獎。這激勵了高效地尋找與打包聚合，因為每個區塊的聚合證明數有上限。

合在一起看，這些獎勵被設計來激勵整個網路協作以進行高效的證明聚合（提議者想只納入聚合良好的證明；驗證者想讓其證明被納入，因而會確保它們被聚合良好）。

這整套機制在 Altair 升級中被 [`ParticipationFlags`](/part3/config/types/#participationflags) 取代。

#### `Eth1Data`

```python
class Eth1Data(Container):
    deposit_root: Root
    deposit_count: uint64
    block_hash: Hash32
```

提議者在區塊中納入它們對以太坊&nbsp;1 鏈的觀點，而它們就是這樣做的。信標鏈把這些投票累積儲存在[信標狀態](/part3/containers/state/#beaconstate)中，直到有一個簡單多數的共識，然後勝出者被提交到信標狀態。這是為了容許 Eth1 存款的[處理](/part3/transition/block/#deposits)，並建立了一座從 Eth1 通往 Eth2 的簡單「誠實多數」單向橋。此處採用 1/2 多數的假設（而非委員會的 2/3）被認為是安全的，因為每次投票的驗證者數量很大：[`EPOCHS_PER_ETH1_VOTING_PERIOD`](/part3/config/preset/#epochs_per_eth1_voting_period) `*` [`SLOTS_PER_EPOCH`](/part3/config/preset/#slots_per_epoch) = 64 `*` 32 = 2048。

  - `deposit_root` 是 Eth1 存款合約的 [`get_deposit_root()`](https://github.com/ethereum/consensus-specs/blob/v1.3.0/solidity_deposit_contract/deposit_contract.sol#L80) 方法在執行所投票之 Eth1 區塊後的結果——它是（增量式的）[存款 Merkle 樹](/part2/deposits-withdrawals/contract/#get_deposit_root)的根。
  - `deposit_count` 是該時點存款合約中的存款數，即合約上 [`get_deposit_count`](https://github.com/ethereum/consensus-specs/blob/v1.3.0/solidity_deposit_contract/deposit_contract.sol#L97) 方法的結果。這會等於、或（若有待處理的未處理存款）大於 `state.eth1_deposit_index` 的值。
  - `block_hash` 是所投票之 Eth1 區塊的雜湊。這在 Eth2 協定內目前沒有任何用途，但用 Danny Ryan 的話說，是「潛在用處太大了，不放進去說不過去」。

#### `HistoricalBatch`

```python
class HistoricalBatch(Container):
    block_roots: Vector[Root, SLOTS_PER_HISTORICAL_ROOT]
    state_roots: Vector[Root, SLOTS_PER_HISTORICAL_ROOT]
```

`HistoricalBatch` 容器在 [Capella 升級](/part4/history/capella/)中已被 [`HistoricalSummary`](/part3/containers/dependencies/#historicalsummary) 取代。它仍留在規格中，因為 `historical_roots` 串列仍留在 [`BeaconState`](/part3/containers/state/#beaconstate) 中，儘管它現在永遠凍結了。

`HistoricalBatch` 在狀態轉換中已不再被任何地方使用。然而，根據 `historical_roots` 串列來驗證 Capella 之前資料的應用程式，將會需要用到它。

關於這項變更的更多討論，見 [`process_historical_summaries_update()`](/part3/transition/epoch/#def_process_historical_summaries_update)。

#### `DepositMessage`

```python
class DepositMessage(Container):
    pubkey: BLSPubkey
    withdrawal_credentials: Bytes32
    amount: Gwei
```

這是「把一個驗證者加入註冊表、或為一個既有驗證者的質押加值」所必需的基本資訊。

`pubkey` 是該驗證者的唯一公鑰。如果它已存在於註冊表（信標狀態中的驗證者串列）中，那麼 `amount` 就被加到它的餘額上。否則，一筆新的 [`Validator`](#validator) 條目被附加到串列上，並被記入 `amount`。

關於 `withdrawal_credentials` 的更多內容，見 [`Validator`](#validator) 容器。

`DepositMessage` 在不同的時點得到兩種保護。

   1. [`DepositData`](#depositdata) 以一筆 [`Deposit`](/part3/containers/operations/#deposit) 的形式被納入信標區塊，這加上了一個 Merkle 證明，證明該資料已向 Eth1 存款合約註冊。
   2. 當含有它的信標區塊被處理時，存款訊息以 [`DepositData`](#depositdata) 的形式被儲存在信標狀態中，待紀元結束時處理。這包含待處理驗證者的 BLS 簽章，使得在一個驗證者被加入之前，`DepositMessage` 的真確性可被驗證。

#### `DepositData`

```python
class DepositData(Container):
    pubkey: BLSPubkey
    withdrawal_credentials: Bytes32
    amount: Gwei
    signature: BLSSignature  # Signing over DepositMessage
```

一筆經簽署的 [`DepositMessage`](#depositmessage)。註解說簽署是針對 `DepositMessage` 進行的。實際發生的是：一筆 `DepositMessage` 從前三個欄位建構出來；它的根與 [`DOMAIN_DEPOSIT`](/part3/config/constants/#domain_deposit) 在一個 [`SigningData`](#signingdata) 物件中結合；最後這個物件的根被簽署，並納入 `DepositData` 中。

#### `BeaconBlockHeader`

```python
class BeaconBlockHeader(Container):
    slot: Slot
    proposer_index: ValidatorIndex
    parent_root: Root
    state_root: Root
    body_root: Root
```

一個獨立版本的信標區塊標頭：[`BeaconBlock`](/part3/containers/blocks/#beaconblock) 包含它們自己的標頭。它與 [`BeaconBlock`](/part3/containers/blocks/#beaconblock) 完全相同，只是 `body` 被換成了 `body_root`。它是 `BeaconBlock` 的精簡版。

`BeaconBlockHeader` 儲存在信標狀態中，以記錄上一個被處理的區塊標頭。這被用來確保我們沿著一條連續的區塊鏈前進，這條鏈上的區塊始終指向它們的前驅[^fn-its-a-blockchain-yo]。見 [`process_block_header()`](/part3/transition/block/#def_process_block_header)。

[^fn-its-a-blockchain-yo]: 這是一條區塊鏈，老兄！

它的[經簽署版本](/part3/containers/envelopes/#signedbeaconblockheader)用於[提議者罰沒](/part3/containers/operations/#proposerslashing)。

#### `SyncCommittee`

```python
class SyncCommittee(Container):
    pubkeys: Vector[BLSPubkey, SYNC_COMMITTEE_SIZE]
    aggregate_pubkey: BLSPubkey
```

同步委員會是在 Altair 升級中引入的，用以支援信標鏈協定的輕客戶端。當前與下一個同步委員會各自的委員會成員串列，儲存在信標狀態中。成員每 [`EPOCHS_PER_SYNC_COMMITTEE_PERIOD`](/part3/config/preset/#epochs_per_sync_committee_period) 個紀元由 [`get_next_sync_committee()`](/part3/helper/accessors/#def_get_next_sync_committee) 更新一次。

納入同步委員會的 `aggregate_pubkey` 是一項[最佳化](https://github.com/ethereum/consensus-specs/commit/9c3d5982cfbe9a52b02e2bd028a873c9226a34c9)，意在讓輕客戶端在驗證同步委員會的簽章時省下一些工作。委員會所有成員的公鑰（包括任何重複者）都被聚合進這單一一個公鑰中。如果 [`SyncAggregate`](/part3/containers/operations/#syncaggregate) 中缺少任何簽章，輕客戶端可以透過進行橢圓曲線減法來把它們「去聚合」。只要超過半數的委員會為簽章做出了貢獻，這就會比從頭建構參與成員的聚合更快。如果為簽章做出貢獻的不到半數，輕客戶端可以改從單位元公鑰（identity public key）開始，並使用橢圓曲線加法來聚合那些在場的公鑰。

亦見 [`SYNC_COMMITTEE_SIZE`](/part3/config/preset/#sync_committee_size)。

#### `SigningData`

```python
class SigningData(Container):
    object_root: Root
    domain: Domain
```

這只是一個便利容器，只在 [`compute_signing_root()`](/part3/helper/misc/#def_compute_signing_root) 中使用，用以計算「一個物件連同一個域」的雜湊樹根。所得的根就是會被 BLS 簽章簽署的訊息資料。`SigningData` 物件本身絕不會被儲存或傳輸。

#### `Withdrawal`

```python
class Withdrawal(Container):
    index: WithdrawalIndex
    validator_index: ValidatorIndex
    address: ExecutionAddress
    amount: Gwei
```

一個用於處理「驗證者餘額從共識層提領到執行層」的容器。[`index`](/part3/config/types/#withdrawalindex) 是「自提領在 [Capella 升級](/part4/history/capella/)中啟用以來，所做出之提領交易總數」的簡單計數。

依照 `amount` 欄位的型別定義，共識層以 Gwei 為提領計值單位（如同它對所有以太幣數額的做法），而執行層以 Wei 為提領計值單位（如同它對所有以太幣數額的做法）。在處理提領交易時需要小心，別搞錯了 $10^9$ 倍。

#### `HistoricalSummary`

```python
class HistoricalSummary(Container):
    """
    `HistoricalSummary` matches the components of the phase0 `HistoricalBatch`
    making the two hash_tree_root-compatible.
    """
    block_summary_root: Root
    state_summary_root: Root
```

這是 [`process_historical_summaries_update()`](/part3/transition/epoch/#def_process_historical_summaries_update) 所實作之[雙重批次累加器](https://ethresear.ch/t/double-batched-merkle-log-accumulator/571?u=benjaminion)機制的一部分。它在 [Capella 升級](/part4/history/capella/)中引入，並取代 [`HistoricalBatch`] 成為「儲存歷史資料之根」的結構。

這裡的註解很有意思。它反映了一項不變式：「一個由物件構成之容器」的 SSZ [雜湊樹根](/part2/building_blocks/merkleization/#the-hash-tree-root)，與「一個由那些物件之雜湊樹根構成之容器」的雜湊樹根相同——我稱之為 [Merkle 化的魔法](/part2/building_blocks/merkleization/#summaries-and-expansions)。

以下程式碼示範了 Capella 之前與之後兩種建構方式之間的這種等價性。它應可無誤地[運行](/appendices/running/)。

```python
from eth2spec.capella import mainnet
from eth2spec.capella.mainnet import *
from eth2spec.utils.ssz.ssz_typing import *

# Dummy data
roots = [Root('0x0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef')] * SLOTS_PER_HISTORICAL_ROOT
block_roots = state_roots = Vector[Root, SLOTS_PER_HISTORICAL_ROOT](*roots)

# Pre-Capella
historical_batch = HistoricalBatch(
    block_roots = block_roots,
    state_roots = state_roots)

# Post-Capella
historical_summary = HistoricalSummary(
    block_summary_root = hash_tree_root(block_roots),
    state_summary_root = hash_tree_root(state_roots))

assert(hash_tree_root(historical_batch) == hash_tree_root(historical_summary))
```

### 信標操作 <!-- /part3/containers/operations/ -->

以下是各種能在信標鏈上的一個[區塊](/part3/containers/blocks/#beaconblockbody)中被傳輸的協定訊息。

對其中大部分而言，提議者會因把該物件納入一個區塊而獲得明確或隱含的獎勵。

提議者因把以下各項納入區塊而收到明確的協定內獎勵：

  - `ProposerSlashing`，
  - `AttesterSlashing`，
  - `Attestation`，以及
  - `SyncAggregate`。

把 `Deposit` 物件納入區塊只會被隱含地獎勵，意思是：如果有待處理的存款而區塊提議者未納入它們，那麼這個區塊就無效，所以提議者收不到獎勵。

納入 `VoluntaryExit` 物件沒有直接的獎勵。然而，每退出一個驗證者，其餘驗證者的獎勵就會非常輕微地增加，所以提議者不忽略 `VoluntaryExit` 仍是有利的。

#### `ProposerSlashing`

```python
class ProposerSlashing(Container):
    signed_header_1: SignedBeaconBlockHeader
    signed_header_2: SignedBeaconBlockHeader
```

`ProposerSlashing` 可被納入區塊中，以證明某個驗證者違反了規則、應被罰沒。提議者因正確地提交這些而收到獎勵。

在這個情況下，規則是：一個驗證者不可在同一高度提議兩個不同的區塊，而酬載是「證明此罪行的兩個[區塊](/part3/containers/dependencies/#beaconblockheader)」的經簽署標頭。[`SignedBeaconBlockHeader`](/part3/containers/envelopes/#signedbeaconblockheader) 上的簽章會被檢查，以驗證它們兩者都是由被指控的驗證者簽署的。

#### `AttesterSlashing`

```python
class AttesterSlashing(Container):
    attestation_1: IndexedAttestation
    attestation_2: IndexedAttestation
```

`AttesterSlashing` 可被納入區塊中，以證明一個委員會中的一個或多個驗證者違反了規則、應被罰沒。提議者因正確地提交這些而收到獎勵。

[`IndexedAttestation`](/part3/containers/dependencies/#indexedattestation) 的內容會在 [`is_slashable_attestation_data()`](/part3/helper/predicates/#def_is_slashable_attestation_data) 中根據證明者罰沒條件被檢查。如果有違反，那麼任何同時為 `attestation_1` 與 `attestation_2` 作證的驗證者都會被罰沒，見 [`process_attester_slashing()`](/part3/transition/block/#def_process_attester_slashing)。

`AttesterSlashing` 可能非常大，因為它原則上可能列出一個委員會中所有驗證者的索引。然而，與提議者罰沒相反，許多驗證者可能因單一一次回報而被罰沒。

#### `Attestation`

```python
class Attestation(Container):
    aggregation_bits: Bitlist[MAX_VALIDATORS_PER_COMMITTEE]
    data: AttestationData
    signature: BLSSignature
```

這是證明在網路上四處傳遞時的形式。它被設計成易於聚合：包含相同 `AttestationData` 的 `Attestation`，可藉由聚合簽章而被合併成單一一筆證明。

`Attestation` 包含與 [`IndexedAttestation`](/part3/containers/dependencies/#indexedattestation) 相同的資訊，但利用「對各時段驗證者委員會的知識」，把作證驗證者的串列壓縮成一個位元串列。因此，`Attestation` 至少比 `IndexedAttestation` 小 5 倍，最多可小到 35 倍（分別對應每委員會 128 或 2048 個驗證者的情形）。

當一個驗證者首次把它的證明廣播到網路上時，`aggregation_bits` 串列會只有單一一個位元被設定，而對它呼叫 [`get_attesting_indices()`](/part3/helper/accessors/#def_get_attesting_indices) 會回傳一個只含單一一個條目的串列，即該驗證者自己的索引。

#### `Deposit`

```python
class Deposit(Container):
    proof: Vector[Bytes32, DEPOSIT_CONTRACT_TREE_DEPTH + 1]  # Merkle path to deposit root
    data: DepositData
```

這個容器被用來把「來自準驗證者的存款資料」納入信標區塊中，使它們能被處理進信標狀態。

`proof` 是區塊提議者建構的一個 Merkle 證明，證明 [`DepositData`](/part3/containers/dependencies/#depositdata) 對應於先前協議的「Eth1 合約存款樹的存款根」。它在 [`process_deposit()`](/part3/transition/block/#def_process_deposit) 中由 [`is_valid_merkle_branch()`](/part3/helper/predicates/#def_is_valid_merkle_branch) 驗證。

#### `VoluntaryExit`

```python
class VoluntaryExit(Container):
    epoch: Epoch  # Earliest epoch when voluntary exit can be processed
    validator_index: ValidatorIndex
```

自願退出訊息是一個驗證者用來示意「它想要不再當驗證者」的方式。包含「紀元晚於當前紀元之 `VoluntaryExit` 資料」的區塊是無效的，所以節點應緩衝或忽略它們所見到的任何未來日期的退出。

`VoluntaryExit` 物件絕不會被赤裸地使用；它們總是被包裝進一個 [`SignedVoluntaryExit`](/part3/containers/envelopes/#signedvoluntaryexit) 物件中。

#### `SyncAggregate`

```python
class SyncAggregate(Container):
    sync_committee_bits: Bitvector[SYNC_COMMITTEE_SIZE]
    sync_committee_signature: BLSSignature
```

當前通行的同步委員會儲存在信標狀態中，所以納入區塊的 `SyncAggregate` 只需用一個位元向量來指明哪些委員會成員為該訊息簽了字。

`sync_committee_signature` 是「位元向量中所指涉的所有驗證者，針對前一個時段之區塊根」的聚合簽章。

`SyncAggregate` 由 [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate) 處理。

#### `BLSToExecutionChange`

```python
class BLSToExecutionChange(Container):
    validator_index: ValidatorIndex
    from_bls_pubkey: BLSPubkey
    to_execution_address: ExecutionAddress
```

[Capella 升級](/part4/history/capella/)給予「持有舊式 [BLS 提領憑證](/part3/config/constants/#withdrawal-prefixes)」的驗證者一次性的機會，把它們更新為 Eth1 提領憑證。

要做這項變更，質押者需要透過一個共識節點，廣播一個包含此資訊的[經簽署訊息](/part3/containers/envelopes/#signedblstoexecutionchange)。它最終會被納入一個區塊，屆時節點會驗證它並更新它們的驗證者註冊表。`from_bls_pubkey` 會根據該驗證者的既有提領憑證被驗證，而訊息的簽章會根據 `from_bls_pubkey` 被驗證。

### 信標區塊 <!-- /part3/containers/blocks/ -->

#### `BeaconBlockBody`

```python
class BeaconBlockBody(Container):
    randao_reveal: BLSSignature
    eth1_data: Eth1Data  # Eth1 data vote
    graffiti: Bytes32  # Arbitrary data
    # Operations
    proposer_slashings: List[ProposerSlashing, MAX_PROPOSER_SLASHINGS]
    attester_slashings: List[AttesterSlashing, MAX_ATTESTER_SLASHINGS]
    attestations: List[Attestation, MAX_ATTESTATIONS]
    deposits: List[Deposit, MAX_DEPOSITS]
    voluntary_exits: List[SignedVoluntaryExit, MAX_VOLUNTARY_EXITS]
    sync_aggregate: SyncAggregate  # [New in Altair]
    # Execution
    execution_payload: ExecutionPayload  # [New in Bellatrix]
    # Capella operations
    bls_to_execution_changes: List[SignedBLSToExecutionChange, MAX_BLS_TO_EXECUTION_CHANGES]  # [New in Capella]
```

節點的兩個基本資料結構是 `BeaconBlock` 與 `BeaconState`。`BeaconBlock` 是領導者（一個時段中被選出的提議者）向所有其他驗證者傳達網路更新的方式，而那些驗證者藉由套用 `BeaconBlock` 來更新它們自己的 `BeaconState`。其構想是，網路上所有驗證者（最終）會對同一個 `BeaconState` 達成一致。

驗證者被隨機選出來提議信標區塊，而如果事情正確運行，每個時段應正好有一個信標區塊。如果一個驗證者離線、或錯過了它的時段、或提議了一個無效的區塊、或它的區塊被孤立，那麼一個時段就可能是空的。

以下物件在一個有效的信標區塊中始終存在。

  - `randao_reveal`：如果 RANDAO reveal 無法根據提議者的公鑰正確驗證，那麼這個區塊就無效。這是區塊提議者對信標鏈隨機性的貢獻。提議者藉由用其私鑰簽署當前紀元號（與 [`DOMAIN_RANDAO`](/part3/config/constants/#domain_randao) 結合）來產生它。就任何人所知，其結果與隨機無法區別。它會被[混入](/part3/transition/block/#randao)信標狀態的 RANDAO 中。
  - 關於 `eth1_data`，見 [Eth1Data](/part3/containers/dependencies/#eth1data)。原則上這是必填的，但它不會被檢查，捏造它也沒有懲罰。
  - `graffiti` 留給提議者自由插入它想要的任何資料。它沒有協定層級的意義。它可以留為零；大多數客戶端把客戶端名稱與版本字串設為它們自己的預設 graffiti 值。
  - `sync_aggregate` 是「當前同步委員會中，哪些驗證者在前一個時段為鏈頭投票」的紀錄。
  - `execution_payload` 是合併之前所稱的 Eth1 區塊。以太坊交易如今以一個 [`ExecutionPayload`](/part3/containers/execution/#executionpayload) 結構的形式被納入信標區塊之內。

存款是一個特例。它們只在「有待處理的存款需要處理」時才是必填的。納入存款沒有明確的獎勵，只不過缺少任何「應在那裡」的存款會使區塊無效。

  - `deposits`：如果區塊未依存款順序包含所有未結的 [`Deposit`](/part3/containers/operations/#deposit)、或其中的 [`MAX_DEPOSITS`](/part3/config/preset/#max_deposits) 筆，那麼它就[無效](/part3/transition/block/#operations)。

納入其餘任何物件都是可選的。它們若存在，會在 [`process_operations()`](/part3/transition/block/#def_process_operations) 函式中被處理。

提議者因納入以下任何各項而賺取獎勵。證明與同步聚合的獎勵每個時段都有。然而，罰沒非常罕見。

  - `proposer_slashings`：最多可納入 [`MAX_PROPOSER_SLASHINGS`](/part3/config/preset/#max_proposer_slashings) 個 [`ProposerSlashing`](/part3/containers/operations/#proposerslashing) 物件。
  - `attester_slashings`：最多可納入 [`MAX_ATTESTER_SLASHINGS`](/part3/config/preset/#max_attester_slashings) 個 [`AttesterSlashing`](/part3/containers/operations/#attesterslashing) 物件。
  - `attestations`：最多可納入 [`MAX_ATTESTATIONS`](/part3/config/preset/#max_attestations) 個（經聚合的）[`Attestation`](/part3/containers/operations/#attestation) 物件。區塊提議者被激勵去納入打包良好的聚合證明，因為它每納入一筆獨特的證明就收到一筆微小的獎勵。在一個完美的世界裡，若證明聚合得完美，`MAX_ATTESTATIONS` 會等於 `MAX_COMMITTEES_PER_SLOT`；在我們的配置中它是兩倍。這在區塊中提供了容量，以便在略過的時段之後趕上證明，也留有空間納入一些聚合得不完美的證明。

納入自願退出與 BLS 至執行變更是可選的，這麼做也沒有明確的獎勵。

  - `voluntary_exits`：最多可納入 [`MAX_VOLUNTARY_EXITS`](/part3/config/preset/#max_voluntary_exits) 個 [`SignedVoluntaryExit`](/part3/containers/envelopes/#signedvoluntaryexit) 物件。
  - `bls_to_execution_changes`：最多可納入 [`MAX_BLS_TO_EXECUTION_CHANGES`](/part3/config/preset/#max_bls_to_execution_changes) 個 [`SignedBLSToExecutionChange`](/part3/containers/envelopes/#signedblstoexecutionchange) 物件。

#### `BeaconBlock`

```python
class BeaconBlock(Container):
    slot: Slot
    proposer_index: ValidatorIndex
    parent_root: Root
    state_root: Root
    body: BeaconBlockBody
```

`BeaconBlock` 只是為 [`BeaconBlockBody`](#beaconblockbody) 加上一些區塊鏈的隨身配件。它與 [`BeaconBlockHeader`](/part3/containers/dependencies/#beaconblockheader) 完全相同，只是 `body_root` 被換成了實際的區塊 `body`。

`slot` 是該區塊被提議所針對的時段。

`proposer_index` 是被[加入](https://github.com/ethereum/consensus-specs/pull/1626)的，為了避免一個潛在的 [DoS 攻擊向量](https://github.com/ethereum/consensus-specs/issues/1601#issue-556546908)，並讓「無法完整存取狀態」的客戶端仍能知道一些[有用的事情](https://github.com/ethereum/consensus-specs/pull/1626#pullrequestreview-372265515)。

`parent_root` 被用來確保這個區塊是「我們上一個處理之區塊」的直接子代。

為了計算 `state_root`，提議者被預期在傳播該區塊之前，先以該區塊運行狀態轉換。在信標節點處理過該區塊之後，狀態根會被比對以確保它們相符。這就是把整個系統綁在一起、並確保所有驗證者與信標節點始終以同一版本之狀態運作（在沒有短期分叉的情況下）的機制。

如果這些當中有任何一項不正確，那麼這個區塊相對於當前信標狀態而言就是無效的，會被忽略。

### 信標狀態 <!-- /part3/containers/state/ -->

#### `BeaconState`

```python
class BeaconState(Container):
    # Versioning
    genesis_time: uint64
    genesis_validators_root: Root
    slot: Slot
    fork: Fork
    # History
    latest_block_header: BeaconBlockHeader
    block_roots: Vector[Root, SLOTS_PER_HISTORICAL_ROOT]
    state_roots: Vector[Root, SLOTS_PER_HISTORICAL_ROOT]
    historical_roots: List[Root, HISTORICAL_ROOTS_LIMIT]  # Frozen in Capella, replaced by historical_summaries
    # Eth1
    eth1_data: Eth1Data
    eth1_data_votes: List[Eth1Data, EPOCHS_PER_ETH1_VOTING_PERIOD * SLOTS_PER_EPOCH]
    eth1_deposit_index: uint64
    # Registry
    validators: List[Validator, VALIDATOR_REGISTRY_LIMIT]
    balances: List[Gwei, VALIDATOR_REGISTRY_LIMIT]
    # Randomness
    randao_mixes: Vector[Bytes32, EPOCHS_PER_HISTORICAL_VECTOR]
    # Slashings
    slashings: Vector[Gwei, EPOCHS_PER_SLASHINGS_VECTOR]  # Per-epoch sums of slashed effective balances
    # Participation
    previous_epoch_participation: List[ParticipationFlags, VALIDATOR_REGISTRY_LIMIT]  # [Modified in Altair]
    current_epoch_participation: List[ParticipationFlags, VALIDATOR_REGISTRY_LIMIT]  # [Modified in Altair]
    # Finality
    justification_bits: Bitvector[JUSTIFICATION_BITS_LENGTH]  # Bit set for every recent justified epoch
    previous_justified_checkpoint: Checkpoint
    current_justified_checkpoint: Checkpoint
    finalized_checkpoint: Checkpoint
    # Inactivity
    inactivity_scores: List[uint64, VALIDATOR_REGISTRY_LIMIT]  # [New in Altair]
    # Sync
    current_sync_committee: SyncCommittee  # [New in Altair]
    next_sync_committee: SyncCommittee  # [New in Altair]
    # Execution
    latest_execution_payload_header: ExecutionPayloadHeader  # [New in Bellatrix]
    # Withdrawals
    next_withdrawal_index: WithdrawalIndex  # [New in Capella]
    next_withdrawal_validator_index: ValidatorIndex  # [New in Capella]
    # Deep history valid from Capella onwards
    historical_summaries: List[HistoricalSummary, HISTORICAL_ROOTS_LIMIT]  # [New in Capella]
```

條條大路通往 `BeaconState`。維護這個資料結構，是所有規格文件中所有機制的唯一目的。這個狀態是信標節點之間共識的焦點；它是每個人最終都必須達成一致的東西。

信標鏈的狀態是整塊式的：一切都被綑綁進單一一個狀態物件（有時被稱為「[上帝物件](https://github.com/ethereum/consensus-specs/issues/582#issuecomment-461591281)」）。有些人[曾主張](https://github.com/ethereum/consensus-specs/issues/582)採用可能更高效、更細粒度的做法，但至少當前的做法是簡單的。

讓我們把這東西拆解開來。

<a id="genesis_validators_root"></a>

```code
    # Versioning
    genesis_time: uint64
    genesis_validators_root: Root
    slot: Slot
    fork: Fork
```

我們怎麼知道我們在哪一條鏈上、以及我們在它上面的何處？這裡的資訊應該足夠了。一條通回創世區塊的連續路徑也足夠。

`genesis_validators_root` 在[創世時刻](/part3/initialise/#initialisation)（鏈啟動時）被計算出來，並在鏈的存續期間維持固定。它與 `fork` 識別碼結合起來，應足以唯一地識別我們所在的鏈。

`genesis_time` 被[分叉選擇規則](/part3/forkchoice/)用來推算我們處於哪個時段，並（自合併以來）用來[驗證執行酬載](/part3/transition/block/#process_execution_payload)。

這兩個欄位的值在鏈的存續期間維持固定。對於主網信標鏈，它們有以下的值：

|||
|-|-|
| `genesis_time` | 1606824023 |
| `genesis_validators_root` | <span class="wrap">`0x4b363db94e286120d76eb905340fdd4e54bfe9f06bf33ff6cf5ad27f511bfe95`</span> |

`fork` [物件](/part3/containers/dependencies/#fork)作為信標鏈升級（也稱為硬分叉）的一部分被手動更新。這會使「不追隨新分叉之驗證者」的區塊與證明失效。

自 Capella 分叉以來，`fork` 欄位包含以下的值：

|||
|-|-|
| `previous_version` | `0x02000000` |
| `current_version` | `0x03000000` |
| `epoch` | 194048 |

關於分叉版本與升級時機的歷史資訊，在[升級歷史](/part4/history/)那一章。

```code
    # History
    latest_block_header: BeaconBlockHeader
    block_roots: Vector[Root, SLOTS_PER_HISTORICAL_ROOT]
    state_roots: Vector[Root, SLOTS_PER_HISTORICAL_ROOT]
    historical_roots: List[Root, HISTORICAL_ROOTS_LIMIT]  # Frozen in Capella, replaced by historical_summaries
```

`latest_block_header` 只被用來確保我們處理的下一個區塊是前一個區塊的直接後代。這是區塊鏈的玩意兒。

過去的 `block_roots` 與 `state_roots` 被儲存在這裡的串列中，直到串列填滿。在 Capella 升級之前，一旦串列填滿，它們會被一起 Merkle 化，根被附加到 `historical_roots`。自 Capella 以來，它們現在被分開 Merkle 化，並附加到 `historical_summaries`（見下文）。`historical_roots` 串列如今被凍結，繼續存在只是為了讓人能針對 Capella 之前的區塊與狀態做出證明。

```code
    # Eth1
    eth1_data: Eth1Data
    eth1_data_votes: List[Eth1Data, EPOCHS_PER_ETH1_VOTING_PERIOD * SLOTS_PER_EPOCH]
    eth1_deposit_index: uint64
```

`eth1_data` 是 Eth1 鏈與存款合約之最新協議狀態。`eth1_data_votes` 累積來自各區塊的 [`Eth1Data`](/part3/containers/dependencies/#eth1data)，直到對某一個 Eth1 狀態有了整體的多數支持。如果到串列填滿時仍未達成多數，那麼它就被清空，投票從頭開始。`eth1_deposit_index` 是信標鏈已處理之存款的總數（它大於或等於驗證者的數目，因為一筆存款可以為一個既有驗證者的餘額加值）。

<a id="registry"></a>

```code
    # Registry
    validators: List[Validator, VALIDATOR_REGISTRY_LIMIT]
    balances: List[Gwei, VALIDATOR_REGISTRY_LIMIT]
```

[`Validator`](/part3/containers/dependencies/#validator) 及其餘額的註冊表。`balances` 串列被分離出來，因為它的變化比 `validators` 串列頻繁得多。粗略地說，活躍驗證者的餘額每個紀元至少更新一次，而 `validators` 串列每個紀元只有些微的更新。與 [SSZ 樹雜湊](/part2/building_blocks/merkleization/)結合時，這在註冊表更新時需重新雜湊的資料量上帶來了很大的節省。亦見 [Inactivity](#inactivity) 之下的驗證者怠惰分數，我們以類似的方式處理它。

```code
    # Randomness
    randao_mixes: Vector[Bytes32, EPOCHS_PER_HISTORICAL_VECTOR]
```

過去的 randao 混合值被儲存在一個固定大小的環狀串列中，保存 [`EPOCHS_PER_HISTORICAL_VECTOR`](/part3/config/preset/#epochs_per_historical_vector) 個紀元（約 290 天）。這些可被用來重新計算過去的委員會，使得對歷史證明的罰沒成為可能。更多資訊見 [`EPOCHS_PER_HISTORICAL_VECTOR`](/part3/config/preset/#epochs_per_historical_vector)。

```code
    # Slashings
    slashings: Vector[Gwei, EPOCHS_PER_SLASHINGS_VECTOR]
```

一個固定大小的環狀串列，記錄過去被罰沒的數額。每個紀元，該紀元中所有被罰沒驗證者的總有效餘額，被儲存為這個串列中的一個條目。當一個被罰沒驗證者的最終罰沒懲罰被計算時，它會以這個串列的總和[加權](/part3/transition/epoch/#slashings)。這個機制被設計來較輕地懲罰最可能是意外的一次性罰沒，並較重地懲罰一段時間窗口內的大規模罰沒——後者較可能是一場協同的攻擊。

```code
    # Participation
    previous_epoch_participation: List[ParticipationFlags, VALIDATOR_REGISTRY_LIMIT]  # [Modified in Altair]
    current_epoch_participation: List[ParticipationFlags, VALIDATOR_REGISTRY_LIMIT]  # [Modified in Altair]
```

這些串列藉由記錄「為正確來源、正確目標與正確鏈頭所做之及時投票」的[旗標](/part3/config/constants/#participation-flag-indices)，來記錄哪些驗證者在當前與先前紀元期間參與了作證。我們儲存兩個紀元份，因為驗證者有最多 32 個時段的時間來把一個正確的目標投票納入。這些旗標被用來計算最終性，並在紀元結束時分派獎勵。

先前在 Phase&nbsp;0 期間，我們在狀態中儲存兩個紀元份的實際證明，並在紀元結束時整批處理它們。這很慢，而且被認為是「在紀元前幾個時段觀察到的出塊延遲」的成因之一。改用新方案的變更是在 Altair 升級中、以[會計改革](https://github.com/ethereum/consensus-specs/pull/2176)為標題實作的。

```code
    # Finality
    justification_bits: Bitvector[JUSTIFICATION_BITS_LENGTH]
    previous_justified_checkpoint: Checkpoint
    current_justified_checkpoint: Checkpoint
    finalized_checkpoint: Checkpoint
```

以太坊&nbsp;2.0 使用 [Casper FFG](https://arxiv.org/pdf/1710.09437.pdf) 最終性機制，並帶有一項 [k-最終性](https://docs.google.com/presentation/d/1MZ-E6TVwomt4rqz-P2Bd_X3DFUW9fWDQkxUP_QJhkyw/edit#slide=id.g621d74a5e7_0_159)最佳化，其中 k&nbsp;=&nbsp;2。狀態中以上各物件，就是為了套用最終性規則而需要被追蹤的資料。

  - `justification_bits` 只有四個位元長。它追蹤最近四個紀元的證成狀態：已證成為 1，否則為 0。這在[計算](/part3/transition/epoch/#justification-and-finalization)我們能否最終確定一個紀元時被用到。
  - 在最終性計算之外，`previous_justified_checkpoint` 與 `current_justified_checkpoint` 被用來[過濾](/part3/helper/accessors/#get_attestation_participation_flag_indices)證明：有效的區塊只納入「來源檢查點與『該證明所屬紀元在狀態中之已證成檢查點』相符」的證明。
  - `finalized_checkpoint`：網路已協議「在那個紀元及之前的信標鏈狀態絕不會被回退」。所以，舉一例，分叉選擇規則不需要往回追溯得比這更遠。Casper FFG 機制是特意建構的，使得若沒有至少三分之一的驗證者被罰沒，就無法建立兩個相衝突的已最終確定檢查點。

<a id="inactivity"></a>

```code
    # Inactivity
    inactivity_scores: List[uint64, VALIDATOR_REGISTRY_LIMIT]  # [New in Altair]
```

這在邏輯上是上述「註冊表」的一部分，放在那裡會更好。它是每驗證者的[怠惰分數](/part3/config/configuration/#inactivity-penalties)紀錄，每個紀元更新一次。這個串列儲存在 Validator 物件的主串列之外，因為它非常頻繁地更新。更多解釋見 [Registry](#registry)。

```code
    # Sync
    current_sync_committee: SyncCommittee  # [New in Altair]
    next_sync_committee: SyncCommittee  # [New in Altair]
```

同步委員會是在 Altair 升級中引入的。下一個同步委員會會被計算並儲存，使得參與的驗證者能藉由訂閱所需的 p2p 子網來預先準備。

```code
    # Execution
    latest_execution_payload_header: ExecutionPayloadHeader  # [New in Bellatrix]
```

自合併以來，最近一個執行酬載的[標頭](/part3/containers/execution/#executionpayloadheader)被快取在信標狀態中。目前這發揮兩項功能，未來可能更多。第一，它讓鏈能檢查合併是否已完成。見 [`is_merge_transition_complete()`](/part3/helper/predicates/#is_merge_transition_complete)。第二，它讓信標鏈在處理一個新執行酬載時，能檢查執行鏈未中斷。見 [`process_execution_payload()`](/part3/transition/block/#process_execution_payload)。

<a id="withdrawals"></a>

```code
    # Withdrawals
    next_withdrawal_index: WithdrawalIndex  # [New in Capella]
    next_withdrawal_validator_index: ValidatorIndex  # [New in Capella]
```

自動的驗證者餘額提領是在 [Capella 升級](/part4/history/capella/)中加入的。`next_withdrawal_index` 維持「迄今所執行之提領交易總數」的計數，而 `next_withdrawal_validator_index` 循環走遍驗證者註冊表，以追蹤接下來該考慮哪個驗證者進行提領。驗證者依其驗證者索引的順序被連續地考慮提領，而提領掃描在考慮過編號最高的驗證者之後會繞回到零。每個區塊最多可進行 [`MAX_WITHDRAWALS_PER_PAYLOAD`](/part3/config/preset/#max_withdrawals_per_payload) 筆提領。

```code
    # Deep history valid from Capella onwards
    historical_summaries: List[HistoricalSummary, HISTORICAL_ROOTS_LIMIT]  # [New in Capella]
```

作為協定[雙重批次累加器](https://ethresear.ch/t/double-batched-merkle-log-accumulator/571?u=benjaminion)的一部分，`state.block_roots` 與 `state.state_roots` 的雜湊樹根，每 [`SLOTS_PER_HISTORICAL_ROOT`](/part3/config/preset/#slots_per_historical_root) 個時段就被週期性地加入 `historical_summaries`。這項工作由 [`process_historical_summaries_update()`](/part3/transition/epoch/#def_process_historical_summaries_update) 完成。

`state.historical_summaries` 串列是在 Capella 升級中引入的，在功能上取代了如今被凍結的 `state.historical_roots` 串列（見上文）。它使用 [`HistoricalSummary`](/part3/containers/dependencies/#historicalsummary) 容器，後者是 `Root` 型別的兩倍大（每項 64 位元組，而非 32）。這個串列實質上會無界地成長（[`HISTORICAL_ROOTS_LIMIT`](/part3/config/preset/#historical_roots_limit) 「很大」），但成長速度只有每年 20&nbsp;KB。保留這份資料對輕客戶端有用，也讓人能針對過去的狀態建立 Merkle 證明，例如[歷史存款資料](https://github.com/ethereum/consensus-specs/issues/1343#issuecomment-521453223)。

#### 歷史注記

曾有一段時期，信標狀態被切分為「結晶化狀態」（crystallized state）與「活躍狀態」（active state）。活躍狀態不斷地變化；結晶化狀態每個紀元（或那時所謂的紀元）只變化一次。把快速變化的狀態與較慢變化的狀態分離開來，是一種嘗試，意在避免必須每個時段都不斷地重新雜湊整個狀態。隨著 [SSZ 樹雜湊](/part2/building_blocks/merkleization/)的引入，這[不再必要](https://github.com/ethereum/consensus-specs/pull/122#issuecomment-437170249)，因為較慢變化部分的根可以直接被快取，這是個不錯的簡化。不過，在「把驗證者餘額與怠惰分數分離成信標狀態內不同的結構」之中，仍留有這種做法的一點回響。

### 執行（Execution）<!-- /part3/containers/execution/ -->

#### `ExecutionPayload`

```python
class ExecutionPayload(Container):
    # Execution block header fields
    parent_hash: Hash32
    fee_recipient: ExecutionAddress  # 'beneficiary' in the yellow paper
    state_root: Bytes32
    receipts_root: Bytes32
    logs_bloom: ByteVector[BYTES_PER_LOGS_BLOOM]
    prev_randao: Bytes32  # 'difficulty' in the yellow paper
    block_number: uint64  # 'number' in the yellow paper
    gas_limit: uint64
    gas_used: uint64
    timestamp: uint64
    extra_data: ByteList[MAX_EXTRA_DATA_BYTES]
    base_fee_per_gas: uint256
    # Extra payload fields
    block_hash: Hash32  # Hash of execution block
    transactions: List[Transaction, MAX_TRANSACTIONS_PER_PAYLOAD]
    withdrawals: List[Withdrawal, MAX_WITHDRAWALS_PER_PAYLOAD]  # [New in Capella]
```

自合併以來，信標鏈上的區塊包含以太坊交易資料——它從前稱為 Eth1 區塊，現在稱為執行酬載。

這是一項重大的變更，也是「合併」這個名稱的由來。

  - 合併之前，以太坊系統中有兩種型別的區塊：
    - Eth1 區塊包含使用者的交易，在 Eth1 節點之間以 gossip 傳播；
    - Eth2 區塊（信標區塊）只包含共識資訊，在 Eth2 節點之間以 gossip 傳播。
  - 合併之後，只有一種區塊，即合併後的信標區塊：
    - 信標區塊包含執行酬載，而執行酬載又包含使用者的交易。這些區塊只在共識（Eth2）節點之間以 gossip 傳播。

`ExecutionPayload` 被包含在 [`BeaconBlock`](/part3/containers/blocks/#beaconblock) 結構中。

`ExecutionPayload` 的欄位大多反映了以太坊[黃皮書](https://ethereum.github.io/yellowpaper/paper.pdf)第 4.3 節所描述之 Eth1 區塊的舊結構。與 Eth1 區塊結構的差異在註解中標明。

執行酬載在以下幾個方面與舊的 Eth1 區塊不同：

  - `ommersHash`（亦稱 `uncle_hashes`）、`difficulty`、`mixHash` 與 `nonce` 沒有從 Eth1 區塊沿用過來，因為它們是工作量證明機制特有的。
  - `fee_recipient` 是「將收到交易費用中未銷毀部分（優先費用）」的以太坊帳戶位址。它在不同時期被叫過各種名稱：原本的黃皮書稱它為 `beneficiary`；[EIP-1559](https://eips.ethereum.org/EIPS/eip-1559) 稱它為 `author`。無論如何，區塊的提議者設定 `fee_recipient`，以指明該區塊的相應交易費用要送往何處。在工作量證明之下，這與收到區塊獎勵的 `COINBASE` 位址是同一個位址。在權益證明之下，區塊獎勵被記入該驗證者的信標鏈餘額，而交易費用被記入 `fee_recipient` 這個以太坊位址。
  - `prev_randao` 取代 `difficulty`。Eth1 鏈無法取得良好品質的隨機性。有時區塊的雜湊或難度被用來作為隨機性的種子，但這些品質不佳。`prev_randao` 欄位讓執行層能取用信標鏈的隨機性。這[更好](/part2/building_blocks/randomness/)，但仍未達加密品質。
  - 執行層中的 `block_number` 是那條鏈中的區塊高度，在合併時接續 Eth1 的區塊高度。每產生一個信標區塊它就遞增一。信標鏈本身不追蹤區塊高度，只追蹤時段號，由於有空時段，時段號可能與區塊高度不同。
  - 執行酬載的 `block_hash` 被納入。共識層不知道如何計算執行區塊的根雜湊，但在[執行酬載處理](/part3/transition/block/#process_execution_payload)期間檢查執行鏈未中斷時，需要取用它們。
  - 儘管在註解中被標為「額外的酬載欄位」，一個交易串列向來都是 Eth1 區塊的一部分。然而，叔塊（ommers/uncles）的串列不再存在。

個別交易由 [Transaction](/part3/config/types/#transaction) 自訂型別表示。單一一個執行酬載中最多可有 [`MAX_TRANSACTIONS_PER_PAYLOAD`](/part3/config/preset/#max_transactions_per_payload) 筆。`MAX_BYTES_PER_TRANSACTION` 與 `MAX_TRANSACTIONS_PER_PAYLOAD` 的值極大，暗示一個執行酬載的大小可能高達一 petabyte。指定這些大小只是因為 [SSZ `List`](/part2/building_blocks/ssz/#lists) 型別要求它們。它們在實務上只會佔用最少的必要空間。

`withdrawals` 欄位是在 [Capella 升級](/part4/history/capella/)中加入的。提領交易的不尋常之處在於，它們同時影響共識端與執行端的狀態。提領交易很獨特：它們是唯一一種「由共識層產生、卻只在執行酬載中於節點之間傳達」的資料。

#### `ExecutionPayloadHeader`

```python
class ExecutionPayloadHeader(Container):
    # Execution block header fields
    parent_hash: Hash32
    fee_recipient: ExecutionAddress
    state_root: Bytes32
    receipts_root: Bytes32
    logs_bloom: ByteVector[BYTES_PER_LOGS_BLOOM]
    prev_randao: Bytes32
    block_number: uint64
    gas_limit: uint64
    gas_used: uint64
    timestamp: uint64
    extra_data: ByteList[MAX_EXTRA_DATA_BYTES]
    base_fee_per_gas: uint256
    # Extra payload fields
    block_hash: Hash32  # Hash of execution block
    transactions_root: Root
    withdrawals_root: Root  # [New in Capella]
```

與 [`ExecutionPayload`](#executionpayload) 相同，但交易只以其根來表示。藉由 [Merkle 化的魔法](/part2/building_blocks/merkleization/#summaries-and-expansions)，一個 `ExecutionPayloadHeader` 的[雜湊樹根](/part2/building_blocks/merkleization/#the-hash-tree-root)，會與其對應之 `ExecutionPayload` 的雜湊樹根相同。

最近一個 `ExecutionPayloadHeader` 儲存在[信標狀態](/part3/containers/state/#beacon-state)中。

### 經簽署的封包 <!-- /part3/containers/envelopes/ -->

以下只是更基本型別的包裝器，外加一個簽章。

#### `SignedVoluntaryExit`

```python
class SignedVoluntaryExit(Container):
    message: VoluntaryExit
    signature: BLSSignature
```

一筆自願退出目前是用該驗證者的線上簽署金鑰簽署的。

曾有一些討論，談到[改變這一點](https://github.com/ethereum/consensus-specs/issues/1578)，使得自願退出也能用該驗證者的離線提領金鑰來簽署。然而，多種[提領憑證](/part3/config/constants/#withdrawal-prefixes)型別的引入使這變得更複雜，它如今不太可能切實可行了。

#### `SignedBeaconBlock`

```python
class SignedBeaconBlock(Container):
    message: BeaconBlock
    signature: BLSSignature
```

`BeaconBlock` 由區塊提議者簽署，並在區塊處理時被拆開包裝。

這個簽章使提議一個區塊變得「可問責」。如果出現兩個正確簽署的相衝突區塊，這些簽章保證它們兩者都是同一個提議者產生的，因此該提議者會面臨被罰沒。這也是為什麼質押者需要嚴密守護它們的簽署金鑰。

#### `SignedBeaconBlockHeader`

```python
class SignedBeaconBlockHeader(Container):
    message: BeaconBlockHeader
    signature: BLSSignature
```

這只在回報提議者罰沒時、於一個 [`ProposerSlashing`](/part3/containers/operations/#proposerslashing) 物件之內使用。

藉由 [SSZ 雜湊樹根](/part2/building_blocks/merkleization/)的魔法，一個對 `SignedBeaconBlock` 有效的簽章，也是一個對 `SignedBeaconBlockHeader` 有效的簽章。提議者罰沒利用這一點，在罰沒回報中節省空間。

#### `SignedBLSToExecutionChange`

```python
class SignedBLSToExecutionChange(Container):
    message: BLSToExecutionChange
    signature: BLSSignature
```

一個[請求](/part3/containers/operations/#blstoexecutionchange)「從 BLS 提領憑證變更為 Eth1 提領憑證」的訊息。

很獨特地，這個訊息是用該驗證者的提領金鑰、而非其平常的簽署金鑰簽署的。只有以 `0x00` [BLS 憑證](/part3/config/constants/#withdrawal-prefixes)做存款的驗證者才有提領金鑰，而它通常會與簽署金鑰不同（儘管它可能[衍生自同一個助記詞](https://eips.ethereum.org/EIPS/eip-2334#validator-keys)）。

## 輔助函式 <!-- /part3/helper/ -->

### 前言

> _注意_：以下定義是為了規格的目的，不必然是最佳的實作。

規格中的這條注記對實作者來說超級重要！下列的常式有非常非常多在實務上被使用的最佳化；一個樸素的實作對主網配置而言會慢得不切實際。只要最佳化過的程式碼產生與此處程式碼相同的結果，那就一切都好。

### 數學 <!-- /part3/helper/math/ -->

#### `integer_squareroot`

<a id="def_integer_squareroot"></a>

```python
def integer_squareroot(n: uint64) -> uint64:
    """
    Return the largest integer ``x`` such that ``x**2 <= n``.
    """
    x = n
    y = (x + 1) // 2
    while y < x:
        x = y
        y = (x + n // x) // 2
    return x
```

驗證者獎勵與「所有驗證者總活躍餘額之平方根」的倒數成比例。這在 [`get_base_reward_per_increment()`](/part3/transition/epoch/#def_get_base_reward_per_increment) 中計算。

原則上 `integer_squareroot` 也用於 [`get_attestation_participation_flag_indices()`](/part3/helper/accessors/#def_get_attestation_participation_flag_indices)，用以指定「來源投票要收到獎勵」的最大延遲。但這只是常數 `integer_squareroot(SLOTS_PER_EPOCH)`，其值為 `5`。

此處使用[牛頓法](https://en.wikipedia.org/wiki/Newton%27s_method)，它有相當好的收斂特性，但實作可以使用任何能給出相同結果的方法。

|||
|-|------|
| 使用&nbsp;者 | [`get_base_reward_per_increment()`](/part3/transition/epoch/#def_get_base_reward_per_increment), [`get_attestation_participation_flag_indices()`](/part3/helper/accessors/#def_get_attestation_participation_flag_indices) |

#### `xor`

<a id="def_xor"></a>

```python
def xor(bytes_1: Bytes32, bytes_2: Bytes32) -> Bytes32:
    """
    Return the exclusive-or of two 32-byte strings.
    """
    return Bytes32(a ^ b for a, b in zip(bytes_1, bytes_2))
```

兩個 32 位元組量的逐位元 `xor`，此處以 Python 的方式定義。

這只在 [`process_randao()`](/part3/transition/block/#def_process_randao) 中、於混入新的 randao reveal 時被使用。

有趣的小知識：如果你在 Java 中對兩個 `byte` 型別做 `xor`，結果是一個 32 位元（有號）整數。這是我們需要在此把「顯而易見之事」定義出來的原因之一。但主要是因為規格是可執行的，我們需要把 Python 尚不知道的事告訴它。

|||
|-|------|
| 使用&nbsp;者 | [`process_randao()`](/part3/transition/block/#def_process_randao) |

#### `uint_to_bytes`

<a id="def_uint_to_bytes"></a>

> `def uint_to_bytes(n: uint) -> bytes` 是一個把 `uint` 型別物件以 ``ENDIANNESS`` 端序序列化為位元組的函式。輸出的預期長度是 `uint` 型別的位元組長度。

大體上，整數就是整數、位元組就是位元組，它們不太混用。但有幾個地方我們需要從整數轉換為位元組：

  - 在 [`compute_shuffled_index()`](/part3/helper/misc/#def_compute_shuffled_index) 演算法中數次；
  - 在 [`compute_proposer_index()`](/part3/helper/misc/#def_compute_proposer_index) 中，用於選出一個依質押加權的提議者；
  - 在 [`get_seed()`](/part3/helper/accessors/#def_get_seed) 中，把紀元號混入 randao 混合值；
  - 在 [`get_beacon_proposer_index()`](/part3/helper/accessors/#def_get_beacon_proposer_index) 中，把時段號混入每紀元的 randao 種子；以及
  - 在 [`get_next_sync_committee_indices()`](/part3/helper/accessors/#def_get_next_sync_committee_indices) 中。

你會注意到，在每個情況中，這項轉換的目的都是讓該整數成為「一個被雜湊以建立（偽）隨機性之位元組字串」的一部分。

這項轉換的結果取決於我們對端序的任意選擇，也就是我們選擇如何把整數表示為位元組字串。對於 Eth2，我們選擇了小端序：更多背景見 [`ENDIANNESS`](/part3/config/constants/#endianness) 的討論。

`uint_to_bytes()` 函式在規格中沒有被給定一個明確的實作，這很不尋常。這是[為了避免](https://github.com/ethereum/consensus-specs/pull/1935)把 Python SSZ（`uint` 的）實作的內臟暴露給規格的其餘部分。當把規格作為可執行檔運行時，它使用 [SSZ 公用程式](https://github.com/ethereum/consensus-specs/blob/fb34e162ef3476f2dd5d7dc6ebfc51c626608ffa/tests/core/pyspec/eth2spec/utils/ssz/ssz_impl.py#L16)中的定義。

|||
|-|------|
| 使用&nbsp;者 | [`compute_shuffled_index()`](/part3/helper/misc/#def_compute_shuffled_index), [`compute_proposer_index()`](/part3/helper/misc/#def_compute_proposer_index), [`get_seed()`](/part3/helper/accessors/#def_get_seed), [`get_beacon_proposer_index()`](/part3/helper/accessors/#def_get_beacon_proposer_index), [`get_next_sync_committee_indices()`](/part3/helper/accessors/#def_get_next_sync_committee_indices) |
| 亦見 | [`ENDIANNESS`](/part3/config/constants/#endianness), [SSZ utilities](https://github.com/ethereum/consensus-specs/blob/fb34e162ef3476f2dd5d7dc6ebfc51c626608ffa/tests/core/pyspec/eth2spec/utils/ssz/ssz_impl.py#L16) |

#### `bytes_to_uint64`

<a id="def_bytes_to_uint64"></a>

```python
def bytes_to_uint64(data: bytes) -> uint64:
    """
    Return the integer deserialization of ``data`` interpreted as ``ENDIANNESS``-endian.
    """
    return uint64(int.from_bytes(data, ENDIANNESS))
```

`bytes_to_uint64()` 是 [`uint_to_bytes()`](#def_uint_to_bytes) 的反函式，被[洗牌演算法](/part3/helper/misc/#compute_shuffled_index)用來從一個雜湊的輸出建立一個隨機索引。

它也在驗證者規格中被使用，於選出驗證者來聚合[證明](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#aggregation-selection)與[同步委員會訊息](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/validator.md#aggregation-selection)時。

`int.from_bytes` 是一個 Python&nbsp;3 的[內建](https://docs.python.org/3/library/stdtypes.html#int.from_bytes)方法。`uint64` 轉型由規格的 SSZ 實作提供。

|||
|-|------|
| 使用&nbsp;者 | [`compute_shuffled_index`](/part3/helper/misc/#def_compute_shuffled_index) |
| 亦見 | [attestation aggregator selection](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#aggregation-selection), [sync committee aggregator selection](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/validator.md#aggregation-selection) |

### 加密（Crypto）<!-- /part3/helper/crypto/ -->

#### `hash`

> `def hash(data: bytes) -> Bytes32` 是 SHA256。

SHA256 之所以被[選為](https://github.com/ethereum/consensus-specs/pull/779)協定的基底雜湊演算法，是為了更容易的跨鏈互通性：許多其他的鏈都使用 SHA256，而 Eth1 有一個 SHA256 預編譯。

在設計過程的早期，曾對這個選擇有很多[討論](https://github.com/ethereum/consensus-specs/issues/612)。[原本的計畫](https://github.com/ethereum/consensus-specs/pull/11)曾是使用 BLAKE2b-512 雜湊函式——它是一個比 SHA3 更快的現代雜湊函式——並在某個時點轉用一個對 STARK/SNARK 友善的雜湊函式（例如 [MiMC](https://ethresear.ch/t/hash-based-vdfs-mimc-and-starks/2337?u=benjaminion)）。然而，為了保持與 Eth1 的互通性，尤其是為了存款合約的實作，雜湊函式被[改為 Keccak256](https://github.com/ethereum/consensus-specs/issues/151)。最後，我們[定案使用 SHA256](https://github.com/ethereum/consensus-specs/pull/779)，因為它有更廣泛的相容性。

雜湊函式在協定內發揮兩項用途。就運算而言，主要的用途在於 [Merkle 化](/part2/building_blocks/merkleization/)，即雜湊樹根的計算，這在協定中無所不在。它的另一個用途是強化各處所用的隨機性。

|||
|-|------|
| 使用&nbsp;者 | [`hash_tree_root`](#def_hash_tree_root), [`is_valid_merkle_branch()`](/part3/helper/predicates/#def_is_valid_merkle_branch), [`compute_shuffled_index()`](/part3/helper/misc/#def_compute_shuffled_index), [`compute_proposer_index()`](/part3/helper/misc/#def_compute_proposer_index), [`get_seed()`](/part3/helper/accessors/#def_get_seed), [`get_beacon_proposer_index()`](/part3/helper/accessors/#def_get_beacon_proposer_index), [`get_next_sync_committee_indices()`](/part3/helper/accessors/#def_get_next_sync_committee_indices), [`process_randao()`](/part3/transition/block/#def_process_randao) |

#### `hash_tree_root`

<a id="def_hash_tree_root"></a>

> `def hash_tree_root(object: SSZSerializable) -> Root` 是一個函式，藉由利用雜湊樹結構，把物件雜湊成單一一個根，如 [SSZ 規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md#merkleization)所定義。

樹雜湊過程的開發，對以太坊&nbsp;2.0 規格而言是變革性的，如今它被用於各處。

為一個資料結構建立摘要的樸素做法，是把它[序列化](https://en.wikipedia.org/wiki/Serialization)，然後對結果直接運行一個雜湊函式。在樹雜湊中，基本構想是把「一個有序的複合資料結構」的每個元素當成一棵 Merkle 樹的葉，必要時遞迴下去直到抵達一個原始型別，並回傳所得之樹的 [Merkle 根](https://en.wikipedia.org/wiki/Merkle_tree)。

乍看之下，這一切看起來相當沒效率。樹雜湊時需要雜湊的資料量是兩倍，而實際速度比線性雜湊[慢 4 至 6 倍](https://github.com/ethereum/consensus-specs/pull/120)。然而，它有利於[支援輕客戶端](https://github.com/ethereum/consensus-specs/issues/54)，因為它讓人能輕易地為完整狀態的子集建構 Merkle 證明。

突破性的洞見，在於體認到大部分重新雜湊的工作可以被快取：如果狀態資料結構的某一部分未曾改變，那部分就不需要被重新雜湊：整棵子樹可以用它被快取的雜湊取代。這結果是一項巨大的效率提升，讓先前那個「帶有累贅、分開的結晶化狀態與活躍狀態」的設計，得以[簡化](https://github.com/ethereum/consensus-specs/pull/122)成單一一個狀態物件。

Merkle 化——計算一個物件之 `hash_tree_root()` 的過程——在 [SSZ 規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/ssz/simple-serialize.md)中定義，並在 [SSZ 那一節](/part2/building_blocks/ssz/)中有進一步的解釋。

#### BLS 簽章

關於這個主題更深入的探討，見 [BLS 簽章](/part2/building_blocks/signatures/)的主要說明。

> The [IETF BLS signature draft standard v4](https://tools.ietf.org/html/draft-irtf-cfrg-bls-signature-04) with ciphersuite `BLS_SIG_BLS12381G2_XMD:SHA-256_SSWU_RO_POP_` defines the following functions:
>
>   - `def Sign(privkey: int, message: Bytes) -> BLSSignature`
>   - `def Verify(pubkey: BLSPubkey, message: Bytes, signature: BLSSignature) -> bool`
>   - `def Aggregate(signatures: Sequence[BLSSignature]) -> BLSSignature`
>   - `def FastAggregateVerify(pubkeys: Sequence[BLSPubkey], message: Bytes, signature: BLSSignature) -> bool`
>   - `def AggregateVerify(pubkeys: Sequence[BLSPubkey], messages: Sequence[Bytes], signature: BLSSignature) -> bool`
>   - `def KeyValidate(pubkey: BLSPubkey) -> bool`
>
> 以上函式透過 `bls` 模組存取，例如 `bls.Verify`。

支撐以太坊&nbsp;2.0 BLS 簽署方案之加密函式的詳細規格，如規格所述，被委交給 IRTF 草案標準[^fn-ietf-irtf-1]。這包括把橢圓曲線 BLS12-381 指定為我們所選用的域。

[^fn-ietf-irtf-1]: 這份文件不具備一個 IETF 標準的完整效力。一來，它仍是一份草案（現已過期）；二來，它是一份 IRTF 文件，意味著它出自一個研究小組，而非處在 IETF 標準軌道上。前 IETF 主席 Brian Carpenter 提供的[一些脈絡](https://mailarchive.ietf.org/arch/msg/ietf/A8MaBwNpbWf_DJoWj0sRROIml3Y/)：
    > 我推測你指的是 draft-irtf-cfrg-bls-signature-04 中的一個議題。那甚至不是一份 IETF 草案；它是一份 IRTF 草案，顯然正在一個 IRTF 研究小組中討論。所以它連「考慮成為一個 IETF 標準」都還沾不上邊……

我們遵循這份進行中標準的用意，是為了提供與其他鏈、應用程式與加密函式庫的最大互通性。以太坊基金會的研究人員與 Eth2 開發者對該標準的[開發](https://github.com/cfrg/draft-irtf-cfrg-bls-signature)有所貢獻。儘管如此，在標準演進時試圖跟上它，仍涉及一些挑戰。舉例來說，[Hashing to Elliptic Curves](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-hash-to-curve-09) 標準在信標鏈測試階段[相當晚](https://hackmd.io/@benjaminion/BkdbG45II#Multiclient-testnet-discussion)的時候仍在變動。最後，一切都順利解決了。

以下兩個函式在另一份 [BLS 擴充](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/bls.md)文件中描述，但為了方便而納入此處。

#### `eth_aggregate_pubkeys`

<a id="def_eth_aggregate_pubkeys"></a>

```python
def eth_aggregate_pubkeys(pubkeys: Sequence[BLSPubkey]) -> BLSPubkey:
    """
    Return the aggregate public key for the public keys in ``pubkeys``.

    NOTE: the ``+`` operation should be interpreted as elliptic curve point addition, which takes as input
    elliptic curve points that must be decoded from the input ``BLSPubkey``s.
    This implementation is for demonstrative purposes only and ignores encoding/decoding concerns.
    Refer to the BLS signature draft standard for more information.
    """
    assert len(pubkeys) > 0
    # Ensure that the given inputs are valid pubkeys
    assert all(bls.KeyValidate(pubkey) for pubkey in pubkeys)

    result = copy(pubkeys[0])
    for pubkey in pubkeys[1:]:
        result += pubkey
    return result
```

公鑰的獨立聚合並不由 BLS 簽章標準定義。在該標準中，公鑰只在「透過 `AggregateVerify()` 或 `FastAggregateVerify()` 進行聚合簽章驗證」的脈絡下被聚合。

`eth_aggregate_pubkeys()` 函式是在 Altair 升級中加入的，用以實作一項[最佳化](/part3/containers/dependencies/#synccommittee)，供輕客戶端在驗證 `SyncAggregate` 上的簽章時使用。

|||
|-|------|
| 使用&nbsp;者 | [`get_next_sync_committee()`](/part3/helper/accessors/#def_get_next_sync_committee) |
| 使用 | [`bls.KeyValidate()`](#bls-signatures) |

#### `eth_fast_aggregate_verify`

<a id="def_eth_fast_aggregate_verify"></a>

```python
def eth_fast_aggregate_verify(pubkeys: Sequence[BLSPubkey], message: Bytes32, signature: BLSSignature) -> bool:
    """
    Wrapper to ``bls.FastAggregateVerify`` accepting the ``G2_POINT_AT_INFINITY`` signature when ``pubkeys`` is empty.
    """
    if len(pubkeys) == 0 and signature == G2_POINT_AT_INFINITY:
        return True
    return bls.FastAggregateVerify(pubkeys, message, signature)
```

`FastAggregateVerify()` 在 [BLS 簽章標準中](https://datatracker.ietf.org/doc/html/draft-irtf-cfrg-bls-signature-04#section-3.3.4)的規格規定，若給定的公鑰數為零，就回傳 `INVALID`。

這個函式是在 Altair 中引入的，用以處理「沒有任何同步委員會成員簽過字」的 [`SyncAggregate`](/part3/containers/operations/#syncaggregate)，在這種情況下 [`G2_POINT_AT_INFINITY`](/part3/config/constants/#g2_point_at_infinity) 可被視為一個「正確」的簽章（在我們的情況下如此，但依標準而言並非如此）。

網路與驗證者規格後來被釐清，要求 `SyncAggregate` 須有[至少一個簽章](https://github.com/ethereum/consensus-specs/pull/2528)。但這項要求在共識層中（在 [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate) 裡）並未被強制執行，所以我們需要保留這個 `eth_fast_aggregate_verify()` 包裝器，以容許空簽章是有效的。

|||
|-|------|
| 使用&nbsp;者 | [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate) |
| 使用 | [`FastAggregateVerify()`](#bls-signatures) |
| 亦見 | [`G2_POINT_AT_INFINITY`](/part3/config/constants/#g2_point_at_infinity) |

### 述詞（Predicates）<!-- /part3/helper/predicates/ -->

#### `is_active_validator`

<a id="def_is_active_validator"></a>

```python
def is_active_validator(validator: Validator, epoch: Epoch) -> bool:
    """
    Check if ``validator`` is active.
    """
    return validator.activation_epoch <= epoch < validator.exit_epoch
```

驗證者不明確地追蹤它們自己的狀態（符合啟用資格、啟用、已退出、可提領——唯一的例外是它們是否已被罰沒）。取而代之的是，一個驗證者的狀態是藉由查看 [`Validator`](/part3/containers/dependencies/#validator) 紀錄中「儲存各狀態轉換之紀元號」的欄位來計算的。

在這個情況下，如果該驗證者過去曾被啟用、且尚未退出，那麼它就是啟用的。

這在規格中被用到幾次，最值得注意的是在 [`get_active_validator_indices()`](/part3/helper/accessors/#def_get_active_validator_indices) 中——它回傳某個紀元時所有啟用驗證者的串列。

|||
|-|------|
| 使用&nbsp;者 | [`get_active_validator_indices()`](/part3/helper/accessors/#def_get_active_validator_indices), [`get_eligible_validator_indices()`](/part3/transition/epoch/#def_get_eligible_validator_indices), [`process_registry_updates()`](/part3/transition/epoch/#def_process_registry_updates), [`process_voluntary_exit()`](/part3/transition/block/#def_process_voluntary_exit) |
| 亦見 | [`Validator`](/part3/containers/dependencies/#validator) |

#### `is_eligible_for_activation_queue`

<a id="def_is_eligible_for_activation_queue"></a>

```python
def is_eligible_for_activation_queue(validator: Validator) -> bool:
    """
    Check if ``validator`` is eligible to be placed into the activation queue.
    """
    return (
        validator.activation_eligibility_epoch == FAR_FUTURE_EPOCH
        and validator.effective_balance == MAX_EFFECTIVE_BALANCE
    )
```

當一筆使用「先前未見過之公鑰」的存款被[處理](/part3/transition/block/#deposits)時，一筆新的 [`Validator`](/part3/containers/dependencies/#validator) 紀錄被建立，所有狀態轉換欄位都設為預設值 [`FAR_FUTURE_EPOCH`](/part3/config/constants/#far_future_epoch)。

向存款合約存入任何超過 [`MIN_DEPOSIT_AMOUNT`](/part3/config/preset/#min_deposit_amount)（目前是 1 以太幣）的數額都是可能的。然而，驗證者要到它們的有效餘額等於 [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance)（對應於 32 以太幣或更多的實際餘額）時，才變為符合啟用資格。

這個述詞在紀元處理期間[被使用](/part3/transition/epoch/#registry-updates)，用以找出「已取得最低必要餘額、但尚未被加入啟用佇列」的驗證者。這些驗證者接著藉由把 `validator.activation_eligibility_epoch` 設為下一個紀元，而被標記為符合啟用資格。

|||
|-|------|
| 使用&nbsp;者 | [`process_registry_updates()`](/part3/transition/epoch/#def_process_registry_updates) |
| 亦見 | [`Validator`](/part3/containers/dependencies/#validator), [`FAR_FUTURE_EPOCH`](/part3/config/constants/#far_future_epoch), [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance) |

#### `is_eligible_for_activation`

<a id="def_is_eligible_for_activation"></a>

```python
def is_eligible_for_activation(state: BeaconState, validator: Validator) -> bool:
    """
    Check if ``validator`` is eligible for activation.
    """
    return (
        # Placement in queue is finalized
        validator.activation_eligibility_epoch <= state.finalized_checkpoint.epoch
        # Has not yet been activated
        and validator.activation_epoch == FAR_FUTURE_EPOCH
    )
```

一個 `is_eligible_for_activation()` 為真的驗證者，它的 `activation_eligibility_epoch` 已被[設定](/part3/transition/epoch/#registry-updates)，但它的 `activation_epoch` 尚未被設定。

為了避免驗證者端對其狀態有任何含混或混淆，我們會等到它的「資格啟用紀元」被最終確定之後，才藉由設定它的 `activation_epoch` 來[把它加入啟用佇列](/part3/transition/epoch/#registry-updates)。否則，它可能在某一刻變為啟用，然後信標鏈可能翻轉到「它並未啟用」的一個分叉。如果後一個分叉有較少的區塊、因而處理了較少的存款，這就可能發生。

請注意，`state.finalized_checkpoint.epoch` 並不表示那個紀元中的所有時段都被最終確定了。我們最終確定的是檢查點，不是紀元，所以只有那個紀元的第一個時段（檢查點）被最終確定。這在 [`process_registry_updates()`](/part3/transition/epoch/#def_process_registry_updates) 中被納入考量：在設定 `validator.activation_eligibility_epoch` 時把當前紀元加一，使得我們可以確定「包含該存款的區塊」已被最終確定。[^fn-activation-eligibility]

[^fn-activation-eligibility]: 我本來偏好不在那裡加一、而在這裡用 `<`。但事情就是這樣了。

|||
|-|------|
| 使用&nbsp;者 | [`process_registry_updates()`](/part3/transition/epoch/#def_process_registry_updates) |
| 亦見 | [`Validator`](/part3/containers/dependencies/#validator), [`FAR_FUTURE_EPOCH`](/part3/config/constants/#far_future_epoch) |

#### `is_slashable_validator`

<a id="def_is_slashable_validator"></a>

```python
def is_slashable_validator(validator: Validator, epoch: Epoch) -> bool:
    """
    Check if ``validator`` is slashable.
    """
    return (not validator.slashed) and (validator.activation_epoch <= epoch < validator.withdrawable_epoch)
```

驗證者只能被罰沒一次：當「針對該驗證者的第一份正確罰沒回報」被處理時，[`validator.slashed`](/part3/containers/dependencies/#validator) 旗標就被[設定](/part3/helper/mutators/#def_slash_validator)。

一個未被罰沒的驗證者，從它變為啟用之時起、一直到它變為可提領為止，都仍然符合被罰沒的資格。後者是在它退出驗證者身分、停止驗證職責之後 [`MIN_VALIDATOR_WITHDRAWABILITY_DELAY`](/part3/config/configuration/#min_validator_withdrawability_delay) 個紀元（約 27 小時）。

|||
|-|------|
| 使用&nbsp;者 | [`process_proposer_slashing()`](/part3/transition/block/#def_process_proposer_slashing), [`process_attester_slashing()`](/part3/transition/block/#def_process_attester_slashing) |
| 亦見 | [`Validator`](/part3/containers/dependencies/#validator) |

#### `is_slashable_attestation_data`

<a id="def_is_slashable_attestation_data"></a>

```python
def is_slashable_attestation_data(data_1: AttestationData, data_2: AttestationData) -> bool:
    """
    Check if ``data_1`` and ``data_2`` are slashable according to Casper FFG rules.
    """
    return (
        # Double vote
        (data_1 != data_2 and data_1.target.epoch == data_2.target.epoch) or
        # Surround vote
        (data_1.source.epoch < data_2.source.epoch and data_2.target.epoch < data_1.target.epoch)
    )
```

這個述詞被 [`process_attester_slashing()`](/part3/transition/block/#def_process_attester_slashing) 用來檢查「一個 [`AttesterSlashing`](/part3/containers/operations/#attesterslashing) 中,兩組被指稱相衝突的證明資料」是否確實夠格被罰沒。

在 Casper FFG 之下，驗證者有兩種被罰沒的方式：

  1. 雙重投票（double vote）：為同一個目標紀元投票超過一次，或
  2. 環繞投票（surround vote）：一筆證明的「來源—目標」區間，完全包含「來自同一個或同一批驗證者之第二筆證明」的「來源—目標」區間。回報的區塊提議者需要留意，把 `AttesterSlashing` 物件內的 `IndexedAttestation` 排序，使得第一組投票環繞第二組。（相反的排序同樣描述一項可罰沒的過錯，但此處不會檢查，所以引數的順序很重要。）

這一點遠非顯而易見，但這個述詞也對證明的模稜兩可（equivocation）強制執行 [LMD GHOST 罰沒](/part2/consensus/lmd_ghost/#attester-slashing)。[`AttestationData`](/part3/containers/dependencies/#attestationdata) 物件既包含 Casper FFG 投票，也包含 LMD GHOST 鏈頭投票（`beacon_block_root`）。所以，Casper FFG 檢查點投票可能相同而不可罰沒，但如果 LMD GHOST 投票在兩筆證明之間有所不同，那麼它就會被判定為可罰沒。

|||
|-|------|
| 使用&nbsp;者 | [`process_attester_slashing()`](/part3/transition/block/#def_process_attester_slashing) |
| 亦見 | [`AttestationData`](/part3/containers/dependencies/#attestationdata), [`AttesterSlashing`](/part3/containers/operations/#attesterslashing) |

#### `is_valid_indexed_attestation`

<a id="def_is_valid_indexed_attestation"></a>

```python
def is_valid_indexed_attestation(state: BeaconState, indexed_attestation: IndexedAttestation) -> bool:
    """
    Check if ``indexed_attestation`` is not empty, has sorted and unique indices and has a valid aggregate signature.
    """
    # Verify indices are sorted and unique
    indices = indexed_attestation.attesting_indices
    if len(indices) == 0 or not indices == sorted(set(indices)):
        return False
    # Verify aggregate signature
    pubkeys = [state.validators[i].pubkey for i in indices]
    domain = get_domain(state, DOMAIN_BEACON_ATTESTER, indexed_attestation.data.target.epoch)
    signing_root = compute_signing_root(indexed_attestation.data, domain)
    return bls.FastAggregateVerify(pubkeys, signing_root, indexed_attestation.signature)
```

`is_valid_indexed_attestation()` 用於[證明處理](/part3/transition/block/#attestations)與[證明者罰沒](/part3/transition/block/#attester-slashings)。

[IndexedAttestation](/part3/containers/dependencies/#indexedattestation) 與 [Attestation](/part3/containers/operations/#attestation) 的不同在於：後者以一個位元串列記錄出力的驗證者，而前者明確地列出出力驗證者的全域索引。

一筆 [IndexedAttestation](/part3/containers/dependencies/#indexedattestation) 只在以下全部成立時才通過這個有效性測試。

 1. 至少有一個驗證者索引存在。
 2. 驗證者的串列不含重複者（Python 的 `set` 函式進行去重）。
 3. 驗證者的索引已排序。（我不清楚為什麼這是必要的。它在此處的重複檢查中被用到，但那其實可以用「檢查 set 的大小」來取代。）
 4. 它的聚合簽章針對所列驗證者的聚合公鑰能驗證通過。

驗證簽章運用了[聚合 BLS 簽章](/part2/building_blocks/signatures/#aggregation)的魔法。索引化證明包含一個 BLS 簽章，它應是「該證明中所列每個驗證者之個別簽章」的合併。這藉由把它連同「來自同一批驗證者的公鑰串列」一起傳給 `bls.FastAggregateVerify()` 而被驗證。只有當「簽署該訊息（`signing_root`）的驗證者集合」與「出現在公鑰串列中的集合」正好相同時，驗證才會成功。請注意，[`get_domain()`](/part3/helper/accessors/#def_get_domain) 會混入分叉版本，使得證明在跨分叉時無效。

此處不會檢查 `attesting_indices`（它們是全域驗證者索引）是否全都是「這筆證明之正確委員會」的成員。在 [`process_attestation()`](/part3/transition/block/#def_process_attestation) 中，依其建構方式它們必定是。在 [`process_attester_slashing()`](/part3/transition/block/#def_process_attester_slashing) 中這無關緊要：「任何」簽署相衝突證明的驗證者，都該被罰沒。

|||
|-|------|
| 使用&nbsp;者 | [`process_attester_slashing()`](/part3/transition/block/#def_process_attester_slashing), [`process_attestation()`](/part3/transition/block/#def_process_attestation) |
| 使用 | [`get_domain()`](/part3/helper/accessors/#def_get_domain), [`compute_signing_root()`](/part3/helper/misc/#def_compute_signing_root), [`bls.FastAggregateVerify()`](/part2/building_blocks/signatures/#bls-library-functions) |
| 亦見 | [IndexedAttestation](/part3/containers/dependencies/#indexedattestation), [Attestation](/part3/containers/operations/#attestation) |

#### `is_valid_merkle_branch`

<a id="def_is_valid_merkle_branch"></a>

```python
def is_valid_merkle_branch(leaf: Bytes32, branch: Sequence[Bytes32], depth: uint64, index: uint64, root: Root) -> bool:
    """
    Check if ``leaf`` at ``index`` verifies against the Merkle ``root`` and ``branch``.
    """
    value = leaf
    for i in range(depth):
        if index // (2**i) % 2:
            value = hash(branch[i] + value)
        else:
            value = hash(value + branch[i])
    return value == root
```

這是[驗證一條 Merkle 分支](https://blog.ethereum.org/2015/11/15/merkling-in-ethereum/)（也稱為 Merkle 證明）的經典演算法。隨著樹從葉往根被走訪，節點被迭代地雜湊。`index` 的各位元選出我們在每一層是父節點的右子代還是左子代。結果應與所給定之樹的 `root` 相符。

以這種方式，我們證明了我們知道 `leaf` 是「葉串列中位置 `index` 處的值」，並且我們知道樹其餘部分的整個結構，如 `branch` 中所總結的那樣。

我們在 [`process_deposit()`](/part3/transition/block/#def_process_deposit) 中使用這個函式，以檢查我們所收到的存款資料是否正確。Eth2 客戶端基於它們所見過的存款資料，建構一個「[存款合約](/part2/deposits-withdrawals/contract/)中存款 Merkle 樹」的複本。納入該存款之區塊的提議者，使用它對存款合約的觀點來建構 Merkle 證明，而所有其他節點使用 `is_valid_merkle_branch()` 來檢查它們的觀點與提議者的相符。如果任何一筆存款的 Merkle 分支驗證失敗，那麼整個區塊就無效。

|||
|-|------|
| 使用&nbsp;者 | [`process_deposit()`](/part3/transition/block/#def_process_deposit) |

#### `is_merge_transition_complete`

<a id="def_is_merge_transition_complete"></a>

```python
def is_merge_transition_complete(state: BeaconState) -> bool:
    return state.latest_execution_payload_header != ExecutionPayloadHeader()
```

一個簡單的測試，判斷給定的信標狀態是合併之前還是合併之後。如果狀態中的 `latest_execution_payload_header` 是預設的 `ExecutionPayloadHeader`，那麼這條鏈就是合併之前的，否則就是合併之後的。升級通常在一個預先決定的區塊高度（或信標鏈上的紀元號）發生，那是測試升級的一般方式。然而，合併的區塊高度事先未知，所以需要一種不同的測試。

雖然主網信標鏈現在無疑已是合併之後的，這仍對「從合併之前的起點同步節點」有用。

這個函式是在合併前的 Bellatrix 升級中加入的。

|||
|-|------|
| 使用&nbsp;者 | [`process_execution_payload()`](/part3/transition/block/#def_process_execution_payload), [`is_merge_transition_block()`](#def_is_merge_transition_block), [`is_execution_enabled()`](#def_is_execution_enabled) |
| 亦見 | [`ExecutionPayloadHeader`](/part3/containers/execution/#executionpayloadheader) |

#### `is_merge_transition_block`

<a id="def_is_merge_transition_block"></a>

```python
def is_merge_transition_block(state: BeaconState, body: BeaconBlockBody) -> bool:
    return not is_merge_transition_complete(state) and body.execution_payload != ExecutionPayload()
```

如果合併過渡尚未完成（意味著信標狀態中仍持有預設的執行酬載標頭），但我們的區塊卻有一個非預設的執行酬載，那麼這必定是我們所見過第一個帶有執行酬載的區塊。因此它就是合併過渡區塊。

[TODO - link to Merge transition info]::

這個函式是在合併前的 Bellatrix 升級中加入的。

|||
|-|------|
| 使用 | [`is_merge_transition_complete()`](#def_is_merge_transition_complete) |
| 使用&nbsp;者 | [`is_execution_enabled()`](#def_is_execution_enabled), [`on_block()`](/part3/forkchoice/bellatrix/#on_block) (Bellatrix version) |
| 亦見 | [`ExecutionPayload`](/part3/containers/execution/#executionpayload) |

#### `is_execution_enabled`

<a id="def_is_execution_enabled"></a>

```python
def is_execution_enabled(state: BeaconState, body: BeaconBlockBody) -> bool:
    return is_merge_transition_block(state, body) or is_merge_transition_complete(state)
```

如果我們所持有的區塊是第一個帶有執行酬載的區塊（合併過渡區塊），或者我們從狀態得知我們先前已見過一個帶有執行酬載的區塊，那麼執行就是啟用的，執行鏈與共識鏈已經合併了。

這個函式是在合併前的 Bellatrix 升級中加入的。

|||
|-|------|
| 使用 | [`is_merge_transition_block()`](#def_is_merge_transition_block), [`is_merge_transition_complete()`](#def_is_merge_transition_complete) |
| 使用&nbsp;者 | [`process_block()`](/part3/transition/block/#def_process_block) |

#### `has_eth1_withdrawal_credential`

<a id="def_has_eth1_withdrawal_credential"></a>

```python
def has_eth1_withdrawal_credential(validator: Validator) -> bool:
    """
    Check if ``validator`` has an 0x01 prefixed "eth1" withdrawal credential.
    """
    return validator.withdrawal_credentials[:1] == ETH1_ADDRESS_WITHDRAWAL_PREFIX
```

只有持有 [Eth1 提領憑證](/part3/config/constants/#withdrawal-prefixes)的驗證者，才符合進行任何種類餘額提領的資格。

|||
|-|------|
| 使用&nbsp;者 | [`is_fully_withdrawable_validator()`](#def_is_fully_withdrawable_validator), [`is_partially_withdrawable_validator()`](#is_partially_withdrawable_validator) |
| 亦見 | [`ETH1_ADDRESS_WITHDRAWAL_PREFIX`](/part3/config/constants/#eth1_address_withdrawal_prefix) |

#### `is_fully_withdrawable_validator`

<a id="def_is_fully_withdrawable_validator"></a>

```python
def is_fully_withdrawable_validator(validator: Validator, balance: Gwei, epoch: Epoch) -> bool:
    """
    Check if ``validator`` is fully withdrawable.
    """
    return (
        has_eth1_withdrawal_credential(validator)
        and validator.withdrawable_epoch <= epoch
        and balance > 0
    )
```

一個驗證者只在以下情況才完全可提領：（a）它有一個可供提領匯入的 [Eth1 提領憑證](/part3/config/constants/#withdrawal-prefixes)，（b）它已變為可提領，意味著它的退出已被處理、且它已度過它的 [`MIN_VALIDATOR_WITHDRAWABILITY_DELAY`](/part3/config/configuration/#min_validator_withdrawability_delay) 期間，以及（c）它有非零的餘額。

|||
|-|------|
| 使用 | [`has_eth1_withdrawal_credential()`](#def_has_eth1_withdrawal_credential) |
| 使用&nbsp;者 | [`get_expected_withdrawals()`](/part3/transition/block/#def_get_expected_withdrawals) |

#### `is_partially_withdrawable_validator`

<a id="def_is_partially_withdrawable_validator"></a>

```python
def is_partially_withdrawable_validator(validator: Validator, balance: Gwei) -> bool:
    """
    Check if ``validator`` is partially withdrawable.
    """
    has_max_effective_balance = validator.effective_balance == MAX_EFFECTIVE_BALANCE
    has_excess_balance = balance > MAX_EFFECTIVE_BALANCE
    return has_eth1_withdrawal_credential(validator) and has_max_effective_balance and has_excess_balance
```

部分提領（partial withdrawal）是從一個啟用（未退出）驗證者提領多餘的以太幣。

一個驗證者只在以下情況才有多餘的以太幣：（a）它的有效餘額處在 [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance)，（b）它的實際餘額大於 MAX_EFFECTIVE_BALANCE，以及（c）它有一個可供提領匯入的 Eth1 提領憑證。

這些條件中的第一個，與有效餘額中的[遲滯](/part2/incentives/balances/#hysteresis)有關。如果一個驗證者先前曾遭受餘額下跌，它的有效餘額可能是 31 以太幣，即使它的實際餘額大於 32 以太幣。如果我們在這種情況下開始撇取提領，那麼該驗證者的餘額就永遠不會抵達「把它的有效餘額提升到 32 以太幣所需的 32.25 以太幣」，它會永遠卡在 31 ETH。因此，只有持有完整有效餘額的驗證者，才符合「提領多餘部分」的資格。

|||
|-|------|
| 使用&nbsp;者 | [`get_expected_withdrawals()`](/part3/transition/block/#def_get_expected_withdrawals) |
| 使用 | [`has_eth1_withdrawal_credential()`](#def_has_eth1_withdrawal_credential) |
| 亦見 | [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance)、[遲滯](/part2/incentives/balances/#hysteresis) |

### 雜項（Misc）<!-- /part3/helper/misc/ -->

#### `compute_shuffled_index`

<a id="def_compute_shuffled_index"></a>

```python
def compute_shuffled_index(index: uint64, index_count: uint64, seed: Bytes32) -> uint64:
    """
    Return the shuffled index corresponding to ``seed`` (and ``index_count``).
    """
    assert index < index_count

    # Swap or not (https://link.springer.com/content/pdf/10.1007%2F978-3-642-32009-5_1.pdf)
    # See the 'generalized domain' algorithm on page 3
    for current_round in range(SHUFFLE_ROUND_COUNT):
        pivot = bytes_to_uint64(hash(seed + uint_to_bytes(uint8(current_round)))[0:8]) % index_count
        flip = (pivot + index_count - index) % index_count
        position = max(index, flip)
        source = hash(
            seed
            + uint_to_bytes(uint8(current_round))
            + uint_to_bytes(uint32(position // 256))
        )
        byte = uint8(source[(position % 256) // 8])
        bit = (byte >> (position % 8)) % 2
        index = flip if bit else index

    return index
```

選出隨機、相異的驗證者委員會，是以太坊&nbsp;2.0 的一大部分；它對於以太坊的可擴展性與安全性兩者都是基礎性的。這項選取是藉由洗牌（shuffling）完成的。

把一個物件串列洗牌，在電腦科學中是個被充分理解的問題。然而請注意，這個常式只知道串列的總長度，就設法把「單一一個索引」洗到一個新位置。用這方面的術語來說，它是「無察覺的」（oblivious）。要把整個串列洗牌，這個常式需要對串列中每個驗證者索引各呼叫一次。依其建構方式，每個輸入索引對應到一個相異的輸出索引。因此，當它被套用於串列中所有索引時，結果是一個排列（permutation），也稱為一次洗牌。

為什麼這樣做，而不用一個更簡單、更高效、傳統的洗牌？這全是為了輕客戶端。信標節點一般會需要知道整個洗牌結果，但輕客戶端往往只對少數委員會感興趣。使用這項技術，讓單一一個委員會的組成能被計算出來，而無須把整個集合洗牌：這潛在地大幅節省時間與記憶體。

如程式碼註解所述，這是「交換或不交換」（swap-or-not）洗牌的一個實作，描述於[所引用的論文](https://link.springer.com/content/pdf/10.1007%2F978-3-642-32009-5_1.pdf)中。Vitalik 在 2018 年末[啟動了一場搜尋](https://github.com/ethereum/consensus-specs/issues/323)，尋找一個具備這些特性的洗牌。在史丹佛大學 Dan Boneh 教授的協助下，swap-or-not 在幾個月後[被認定](https://github.com/ethereum/consensus-specs/issues/563)為一個候選者，並被[採納](https://github.com/ethereum/consensus-specs/pull/576)進規格。

這個演算法拆解如下。對每一次迭代（每一輪），我們以一個當前的 `index` 開始。

1. 偽隨機地選出一個樞軸（pivot）。這是一個基於種子與當前輪數的 64 位元整數。這個值域夠大，使得下一步取模數所造成的任何不均勻性[完全可以忽略](https://github.com/ethereum/consensus-specs/pull/576#issuecomment-463293660)。
2. 用 `pivot` 在驗證者串列中找出另一個索引 `flip`，它是 `pivot - index`，並考量串列中的環繞。
3. 基於種子、當前輪數，以及來自 `index` 或 `flip`（取較大者）的一些位元組，計算單一一個偽隨機位元。
4. 如果我們的位元是零，我們保持 `index` 不變；如果它是一，我們把 `index` 設為 `flip`。

我們實際上是基於一個確定性演算法在交換一副牌中的牌。

`position` 被拆解的方式值得留意：

  - 位元 0-2（3 位元）被用來從 `byte` 的八個位元中選出單一一個位元。
  - 位元 3-7（5 位元）被用來從 `source` 的三十二個位元組中選出單一一個位元組。
  - 位元 8-39（32 位元）被用於產生 `source`。請注意，由於活躍驗證者數量的限制，在實務上其高位兩個位元組永遠會是零。

[`SHUFFLE_ROUND_COUNT`](/part3/config/preset/#shuffle_round_count) 在主網配置中是、而且向來都是 90，如該處所解釋。

關於這個演算法更有條理的闡述與分析（附圖！），見[洗牌那一節](/part2/building_blocks/shuffling/)。

在實務上，完整的信標節點實作會每個紀元運行這個演算法一次，使用一個「把整個串列洗牌」的最佳化版本，並把那次的結果為該紀元快取起來。

|||
|-|------|
| 使用&nbsp;者 | [`compute_committee()`](#def_compute_committee), [`compute_proposer_index()`](#def_compute_proposer_index), [`get_next_sync_committee_indices()`](/part3/helper/accessors/#def_get_next_sync_committee_indices) |
| 使用 | [`bytes_to_uint64()`](/part3/helper/math/#def_bytes_to_uint64) |
| 亦見 | [`SHUFFLE_ROUND_COUNT`](/part3/config/preset/#shuffle_round_count) |

#### `compute_proposer_index`

<a id="def_compute_proposer_index"></a>

```python
def compute_proposer_index(state: BeaconState, indices: Sequence[ValidatorIndex], seed: Bytes32) -> ValidatorIndex:
    """
    Return from ``indices`` a random index sampled by effective balance.
    """
    assert len(indices) > 0
    MAX_RANDOM_BYTE = 2**8 - 1
    i = uint64(0)
    total = uint64(len(indices))
    while True:
        candidate_index = indices[compute_shuffled_index(i % total, total, seed)]
        random_byte = hash(seed + uint_to_bytes(uint64(i // 32)))[i % 32]
        effective_balance = state.validators[candidate_index].effective_balance
        if effective_balance * MAX_RANDOM_BYTE >= MAX_EFFECTIVE_BALANCE * random_byte:
            return candidate_index
        i += 1
```

每個時段正好有一個信標區塊提議者，從所有活躍驗證者之中隨機選出。種子參數在 [`get_beacon_proposer_index`](/part3/helper/accessors/#get_beacon_proposer_index) 中基於紀元與時段被設定。請注意，同一個驗證者在一個紀元中被點名提議區塊超過一次的機率雖小，卻是有限非零的。

一個驗證者成為提議者的機會，依其有效餘額被[加權](https://github.com/ethereum/consensus-specs/pull/772)：一個有效餘額為 32 以太幣的驗證者，被選中的可能性是有效餘額 16 以太幣之驗證者的兩倍。

為了顧及「需要依[有效餘額](/part2/incentives/balances/)加權」這一點，這個函式以一個「嘗試並遞增」（try-and-increment）演算法來實作。一個計數器 `i` 從零開始。這個計數器身兼兩職：

  - 首先，`i` 被用來以機率 $1/N$ 均勻地選出一個候選提議者，其中 $N$ 是活躍驗證者的數目。這是藉由使用 [`compute_shuffled_index`](#compute_shuffled_index) 常式把索引 `i` 洗到一個新位置而完成的，那個位置接著就是 `candidate_index`。
  - 接著，`i` 被用來產生一個偽隨機位元組，做法是把雜湊函式當成一個有種子、輸出至少 256 位元的 PRNG 來使用。`i` 的低 5 位元在雜湊函式中選出一個位元組，而高位元為種子加鹽。（一項明顯的最佳化是：雜湊的輸出每 32 次迭代才改變一次。）

`if` 測試就是依有效餘額加權之處。如果候選者有 `MAX_EFFECTIVE_BALANCE`，它永遠會通過這個測試並被回傳為提議者。如果候選者有 `MAX_EFFECTIVE_BALANCE` 的一個分數，那麼那個分數就是它被回傳為提議者的機率。

如果候選者未被選中，那麼 `i` 就遞增，我們再試一次。由於最小有效餘額是最大值的一半，這應該會相當迅速地終止。在最壞的情況下，所有驗證者都有 16 以太幣的有效餘額，所以必須再做一次迭代的機會是 50%，在這種情況下，必須做 20 次迭代的機率是百萬分之一。

請注意，這種對「驗證者有效餘額」的依賴——而有效餘額在每個紀元結束時更新——意味著提議者指派[只在當前紀元中](https://github.com/ethereum/consensus-specs/pull/772#issuecomment-475574357)有效。這與證明委員會指派不同，後者有提前一個紀元的有效性。

|||
|-|------|
| 使用&nbsp;者 | [`get_beacon_proposer_index()`](/part3/helper/accessors/#def_get_beacon_proposer_index) |
| 使用 | [`compute_shuffled_index()`](#def_compute_shuffled_index) |
| 亦見 | [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance) |

#### `compute_committee`

<a id="def_compute_committee"></a>

```python
def compute_committee(indices: Sequence[ValidatorIndex],
                      seed: Bytes32,
                      index: uint64,
                      count: uint64) -> Sequence[ValidatorIndex]:
    """
    Return the committee corresponding to ``indices``, ``seed``, ``index``, and committee ``count``.
    """
    start = (len(indices) * index) // count
    end = (len(indices) * uint64(index + 1)) // count
    return [indices[compute_shuffled_index(uint64(i), uint64(len(indices)), seed)] for i in range(start, end)]
```

`compute_committee` 被 [`get_beacon_committee()`](/part3/helper/accessors/#get_beacon_committee) 用來找出「一個時段中某個委員會」的特定成員。

每個紀元，都會產生一組嶄新的委員會；在一個紀元期間，委員會是穩定的。

以相反的順序檢視這些參數：

  - `count` 是一個紀元中委員會的總數。它是 `SLOTS_PER_EPOCH` 乘以 [`get_committee_count_per_slot()`](/part3/helper/accessors/#def_get_committee_count_per_slot) 的輸出。
  - `index` 是紀元內的委員會編號，從 `0` 跑到 `count - 1`。它在 [`get_beacon_committee()`](/part3/helper/accessors/#def_get_beacon_committee) 中，由「時段內的委員會編號 `index`」與時段號計算出來，計算式為 `(slot % SLOTS_PER_EPOCH) * committees_per_slot + index`。
  - `seed` 是用於計算偽隨機洗牌的種子值，基於紀元號與一個域參數。（[`get_beacon_committee()`](/part3/helper/accessors/#def_get_beacon_committee) 使用 [`DOMAIN_BEACON_ATTESTER`](/part3/config/constants/#domain_beacon_attester)。）
  - `indices` 是符合納入委員會資格之驗證者的串列，亦即活躍驗證者索引的整個串列。

在驗證者之中的隨機抽樣，是藉由取一段從 `start` 到 `end` 的連續陣列索引切片，並查看每一個被 `compute_shuffled_index()` 洗到何處而完成的。請注意，上文中的 `ValidatorIndex(i)` 是一個型別轉換：它只是把 `i` 轉成一個 [`ValidatorIndex`](/part3/config/types/#validatorindex) 型別，以輸入洗牌。洗牌的輸出值接著被當成 `indices` 串列的一個索引使用。此處有許多地方客戶端實作會以快取與批次操作來最佳化。

這一點可能不是立刻顯而易見的，但回傳的委員會不會全都是相同大小（它們可能相差一），而 `indices` 中的每個驗證者都會正好是一個委員會的成員。隨著我們把 `index` 從零遞增，顯然 `index == j + 1` 的 `start` 就是 `index == j` 的 `end`，所以沒有空隙。此外，最高的 `index` 是 `count - 1`，所以 `indices` 中的每個驗證者都找得到進入某個委員會的途徑。[^fn_formal_verif_committee_size]

[^fn_formal_verif_committee_size]: 同樣不是立刻顯而易見的是：委員會大小有一個微妙的議題，是[由形式驗證所發現的](https://github.com/ethereum/consensus-specs/issues/2500)，不過，考量到 ETH 的最大供應量，它永遠不會被觸發。

這種選取委員會的方法對輕客戶端友善。輕客戶端可以只計算它們感興趣的委員會，而無須處理整個驗證者集合。關於這如何運作的解釋，見[洗牌那一節](/part2/building_blocks/shuffling/)。

同步委員會由一個[不同的過程](/part3/helper/accessors/#get_next_sync_committee_indices)指派，那個過程比較類似於反覆執行 [`compute_proposer_index()`](#def_compute_proposer_index)。

|||
|-|------|
| 使用&nbsp;者 | [`get_beacon_committee`](/part3/helper/accessors/#get_beacon_committee) |
| 使用 | [`compute_shuffled_index()`](#compute_shuffled_index) |

#### `compute_epoch_at_slot`

<a id="def_compute_epoch_at_slot"></a>

```python
def compute_epoch_at_slot(slot: Slot) -> Epoch:
    """
    Return the epoch number at ``slot``.
    """
    return Epoch(slot // SLOTS_PER_EPOCH)
```

這夠瑣碎，我就不解釋了。但請注意，它確實仰賴 [`GENESIS_SLOT`](/part3/config/constants/#miscellaneous) 與 [`GENESIS_EPOCH`](/part3/config/constants/#miscellaneous) 為零。我們之中比較講究的人，可能偏好它寫成：

```code
    return GENESIS_EPOCH + Epoch((slot - GENESIS_SLOT) // SLOTS_PER_EPOCH)
```

#### `compute_start_slot_at_epoch`

<a id="def_compute_start_slot_at_epoch"></a>

```python
def compute_start_slot_at_epoch(epoch: Epoch) -> Slot:
    """
    Return the start slot of ``epoch``.
    """
    return Slot(epoch * SLOTS_PER_EPOCH)
```

或許應寫成：

```code
    return GENESIS_SLOT + Slot((epoch - GENESIS_EPOCH) * SLOTS_PER_EPOCH))
```

|||
|-|------|
| 使用&nbsp;者 | [`get_block_root()`](/part3/helper/accessors/#def_get_block_root), [`compute_slots_since_epoch_start()`](/part3/forkchoice/phase0/#compute_slots_since_epoch_start) |
| 亦見 | [`SLOTS_PER_EPOCH`](/part3/config/preset/#slots_per_epoch), [`GENESIS_SLOT`](/part3/config/constants/#genesis_slot), [`GENESIS_EPOCH`](/part3/config/constants/#genesis_epoch) |

#### `compute_activation_exit_epoch`

<a id="def_compute_activation_exit_epoch"></a>

```python
def compute_activation_exit_epoch(epoch: Epoch) -> Epoch:
    """
    Return the epoch during which validator activations and exits initiated in ``epoch`` take effect.
    """
    return Epoch(epoch + 1 + MAX_SEED_LOOKAHEAD)
```

當分別在 [`process_registry_updates()`](/part3/transition/epoch/#def_process_registry_updates) 與 [`initiate_validator_exit()`](/part3/helper/mutators/#def_initiate_validator_exit) 中把驗證者排入啟用或退出佇列時，啟用或退出被延遲到下一個紀元，再加上 [`MAX_SEED_LOOKAHEAD`](/part3/config/preset/#time-parameters) 個紀元（目前為 4）。

細節見 [`MAX_SEED_LOOKAHEAD`](/part3/config/preset/#time-parameters)，但簡言之，它被設計來讓攻擊者極難透過啟用與退出來操縱委員會的成員組成。

|||
|-|------|
| 使用&nbsp;者 | [`initiate_validator_exit()`](/part3/helper/mutators/#def_initiate_validator_exit), [`process_registry_updates()`](/part3/transition/epoch/#def_process_registry_updates) |
| 亦見 | [`MAX_SEED_LOOKAHEAD`](/part3/config/preset/#time-parameters) |

#### `compute_fork_data_root`

<a id="def_compute_fork_data_root"></a>

```python
def compute_fork_data_root(current_version: Version, genesis_validators_root: Root) -> Root:
    """
    Return the 32-byte fork data root for the ``current_version`` and ``genesis_validators_root``.
    This is used primarily in signature domains to avoid collisions across forks/chains.
    """
    return hash_tree_root(ForkData(
        current_version=current_version,
        genesis_validators_root=genesis_validators_root,
    ))
```

分叉資料根作為「我們所在之鏈」的唯一識別碼。`genesis_validators_root` 識別我們獨特的創世事件，而 `current_version` 識別我們自己在那個創世事件之後的硬分叉。舉例來說，這對於區分測試網與主網很有用：兩者可能有相同的分叉版本，但肯定會有不同的創世驗證者根。

它被 [`compute_fork_digest()`](#def_compute_fork_digest) 與 [`compute_domain()`](#def_compute_domain) 使用。

|||
|-|------|
| 使用&nbsp;者 | [`compute_fork_digest()`](#def_compute_fork_digest), [`compute_domain()`](#def_compute_domain) |
| 使用 | [`hash_tree_root()`](/part3/helper/crypto/#hash_tree_root) |
| 亦見 | [`ForkData`](/part3/containers/dependencies/#forkdata) |

#### `compute_fork_digest`

<a id="def_compute_fork_digest"></a>

```python
def compute_fork_digest(current_version: Version, genesis_validators_root: Root) -> ForkDigest:
    """
    Return the 4-byte fork digest for the ``current_version`` and ``genesis_validators_root``.
    This is a digest primarily used for domain separation on the p2p layer.
    4-bytes suffices for practical separation of forks/chains.
    """
    return ForkDigest(compute_fork_data_root(current_version, genesis_validators_root)[:4])
```

擷取[分叉資料根](#compute_fork_data_root)的前四個位元組，作為一個 [`ForkDigest`](/part3/config/types/#forkdigest) 型別。它主要被用於對等網路層上的域分離。

`compute_fork_digest()` 在[以太坊 2.0 網路規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/p2p-interface.md#how-should-fork-version-be-used-in-practice)中被廣泛使用，以區分各個獨立的信標鏈網路或分叉：一條鏈上的活動不干擾其他鏈，這一點很重要。

|||
|-|------|
| 使用 | [`compute_fork_data_root()`](#def_compute_fork_data_root) |
| 亦見 | [`ForkDigest`](/part3/config/types/#forkdigest) |

#### `compute_domain`

<a id="def_compute_domain"></a>

```python
def compute_domain(domain_type: DomainType, fork_version: Version=None, genesis_validators_root: Root=None) -> Domain:
    """
    Return the domain for the ``domain_type`` and ``fork_version``.
    """
    if fork_version is None:
        fork_version = GENESIS_FORK_VERSION
    if genesis_validators_root is None:
        genesis_validators_root = Root()  # all bytes zero by default
    fork_data_root = compute_fork_data_root(fork_version, genesis_validators_root)
    return Domain(domain_type + fork_data_root[:28])
```

在處理經簽署的訊息時，簽章「域」依三個獨立的因素被分離：

 1. 所有簽章都包含一個與訊息用途相關的 [`DomainType`](/part3/config/constants/#domain-types)，這只是某種加密上的衛生習慣，以防同一個訊息在任何時候要為不同用途而被簽署。
 2. 除了存款訊息上的簽章之外，所有簽章都包含分叉版本。這確保了「跨鏈不同分叉的訊息」變為無效，並確保驗證者不會因為在兩條不同的鏈上簽署證明而被罰沒（這是被容許的）。
 3. 而且，[如今](https://github.com/ethereum/consensus-specs/pull/1614)，創世時驗證者 Merkle 樹的根雜湊也被納入。它連同分叉版本，為我們的鏈給出了一個唯一的識別碼。

這個函式主要被 [`get_domain()`](/part3/helper/accessors/#def_get_domain) 使用。它也用於[存款處理](/part3/transition/block/#deposits)，在那種情況下 `fork_version` 與 `genesis_validators_root` 取它們的預設值，因為存款跨分叉都有效。

有趣的小知識：這個函式看起來相當簡單，但[我發現了一個微妙的臭蟲](https://github.com/ethereum/consensus-specs/issues/1582)——是在先前一個實作中產生測試的方式裡。

|||
|-|------|
| 使用&nbsp;者 | [`get_domain()`](/part3/helper/accessors/#def_get_domain), [`process_deposit()`](/part3/transition/block/#def_process_deposit) |
| 使用 | [`compute_fork_data_root()`](#def_compute_fork_data_root) |
| 亦見 | [`Domain`](/part3/config/types/#domain), [`DomainType`](/part3/config/constants/#domain-types) [`GENESIS_FORK_VERSION`](/part3/config/configuration/#genesis_fork_version) |

#### `compute_signing_root`

<a id="def_compute_signing_root"></a>

```python
def compute_signing_root(ssz_object: SSZObject, domain: Domain) -> Root:
    """
    Return the signing root for the corresponding signing data.
    """
    return hash_tree_root(SigningData(
        object_root=hash_tree_root(ssz_object),
        domain=domain,
    ))
```

這是一個「用 BLS 簽章簽署物件」的前置處理器：

 1. 計算該物件的[雜湊樹根](/part2/building_blocks/merkleization/#the-hash-tree-root)；
 2. 在一個暫時的 [`SigningData`](/part3/containers/dependencies/#signingdata) 物件之內，把雜湊樹根與 [`Domain`](/part3/config/types/#domain) 結合；
 3. 回傳那個物件的雜湊樹根，它就是要被簽署的資料。

`domain` 通常是 [`get_domain()`](/part3/helper/accessors/#def_get_domain) 的輸出——它把[加密域](/part3/config/constants/#domain-types)、分叉版本與創世驗證者根混入訊息雜湊。對於存款，它是 [`compute_domain()`](#def_compute_domain) 的輸出，忽略分叉版本與創世驗證者根。

這完全等同於「把域加到一個物件上、再取整個東西的雜湊樹根」。確實，這個函式從前叫做 [`compute_domain_wrapper_root()`](https://github.com/ethereum/consensus-specs/blob/502ee295379c1f3c5c3649e12330fb5be5d7a83b/specs/core/0_beacon-chain.md#compute_domain_wrapper_root)。

|||
|-|------|
| 使用&nbsp;者 | 許多地方 |
| 使用 | [`hash_tree_root()`](/part3/helper/crypto/#hash_tree_root) |
| 亦見 | [`SigningData`](/part3/containers/dependencies/#signingdata), [`Domain`](/part3/config/types/#domain) |

#### `compute_timestamp_at_slot`

> _注意_：這個函式在溢位與下溢方面是不安全的。

<a id="def_compute_timestamp_at_slot"></a>

```python
def compute_timestamp_at_slot(state: BeaconState, slot: Slot) -> uint64:
    slots_since_genesis = slot - GENESIS_SLOT
    return uint64(state.genesis_time + slots_since_genesis * SECONDS_PER_SLOT)
```

一個簡單的公用程式，用於計算給定時段開始時的 Unix 時間戳。這在[驗證執行酬載](/part3/transition/block/#process_execution_payload)時被使用。

這個函式是在合併前的 Bellatrix 升級中加入的。

|||
|-|------|
| 使用&nbsp;者 | [`process_execution_payload()`](/part3/transition/block/#def_process_execution_payload) |

### 參與旗標 <!-- /part3/helper/participation/ -->

這兩個簡單的公用程式是在 Altair 升級中加入的。

#### `add_flag`

<a id="def_add_flag"></a>

```python
def add_flag(flags: ParticipationFlags, flag_index: int) -> ParticipationFlags:
    """
    Return a new ``ParticipationFlags`` adding ``flag_index`` to ``flags``.
    """
    flag = ParticipationFlags(2**flag_index)
    return flags | flag
```

這簡單且不言自明。`2**flag_index` 有點 Python 風格。在類 C 的語言中，我們會使用位元移位：

```code
    1 << flag_index
```

|||
|-|------|
| 使用&nbsp;者 | [`process_attestation()`](/part3/transition/block/#def_process_attestation) |
| 亦見 | [`ParticipationFlags`](/part3/config/types/#participationflags) |

#### `has_flag`

<a id="def_has_flag"></a>

```python
def has_flag(flags: ParticipationFlags, flag_index: int) -> bool:
    """
    Return whether ``flags`` has ``flag_index`` set.
    """
    flag = ParticipationFlags(2**flag_index)
    return flags & flag == flag
```

走吧，這裡沒什麼好看的。

|||
|-|------|
| 使用&nbsp;者 | [`get_unslashed_participating_indices()`](/part3/helper/accessors/#def_get_unslashed_participating_indices), [`process_attestation()`](/part3/transition/block/#def_process_attestation) |
| 亦見 | [`ParticipationFlags`](/part3/config/types/#participationflags) |

### 信標狀態存取器 <!-- /part3/helper/accessors/ -->

顧名思義，這些函式存取信標狀態以計算各種有用的東西，而不修改它。

#### `get_current_epoch`

<a id="def_get_current_epoch"></a>

```python
def get_current_epoch(state: BeaconState) -> Epoch:
    """
    Return the current epoch.
    """
    return compute_epoch_at_slot(state.slot)
```

當前紀元的取值器（getter），由 [`compute_epoch_at_slot()`](/part3/helper/misc/#def_compute_epoch_at_slot) 計算。

|||
|-|------|
| 使用&nbsp;者 | 各處 |
| 使用 | [`compute_epoch_at_slot()`](/part3/helper/misc/#def_compute_epoch_at_slot) |

#### `get_previous_epoch`

<a id="def_get_previous_epoch"></a>

```python
def get_previous_epoch(state: BeaconState) -> Epoch:
    """`
    Return the previous epoch (unless the current epoch is ``GENESIS_EPOCH``).
    """
    current_epoch = get_current_epoch(state)
    return GENESIS_EPOCH if current_epoch == GENESIS_EPOCH else Epoch(current_epoch - 1)
```

把前一個紀元號作為一個 [`Epoch`](/part3/config/types/#epoch) 型別回傳。如果我們處在 `GENESIS_EPOCH`，就回傳 [`GENESIS_EPOCH`](/part3/config/constants/#genesis_epoch)，因為它沒有前驅，而我們不處理負數。

|||
|-|------|
| 使用&nbsp;者 | 各處 |
| 使用 | [`get_current_epoch()`](#def_get_current_epoch) |
| 亦見 | [`GENESIS_EPOCH`](/part3/config/constants/#genesis_epoch) |

#### `get_block_root`

<a id="def_get_block_root"></a>

```python
def get_block_root(state: BeaconState, epoch: Epoch) -> Root:
    """
    Return the block root at the start of a recent ``epoch``.
    """
    return get_block_root_at_slot(state, compute_start_slot_at_epoch(epoch))
```

共識的 Casper FFG 部分處理的是 [`Checkpoint`](/part3/containers/dependencies/#checkpoint)，它們是一個紀元的第一個時段。`get_block_root` 是 [`get_block_root_at_slot()`](#get_block_root_at_slot) 的一個特化版本，它只需給定一個紀元，就回傳該檢查點的區塊根。

|||
|-|------|
| 使用&nbsp;者 | [`get_attestation_participation_flag_indices()`](#def_get_attestation_participation_flag_indices), [`weigh_justification_and_finalization()`](/part3/transition/epoch/#def_weigh_justification_and_finalization) |
| 使用 | [`get_block_root_at_slot()`](#def_get_block_root_at_slot), [`compute_start_slot_at_epoch()`](/part3/helper/misc/#def_compute_start_slot_at_epoch) |
| 亦見 | [`Root`](/part3/config/types/#root) |

#### `get_block_root_at_slot`

<a id="def_get_block_root_at_slot"></a>

```python
def get_block_root_at_slot(state: BeaconState, slot: Slot) -> Root:
    """
    Return the block root at a recent ``slot``.
    """
    assert slot < state.slot <= slot + SLOTS_PER_HISTORICAL_ROOT
    return state.block_roots[slot % SLOTS_PER_HISTORICAL_ROOT]
```

近期的區塊根儲存在狀態中的一個環狀串列裡，其長度為 [`SLOTS_PER_HISTORICAL_ROOT`](/part3/config/preset/#slots_per_historical_root)（目前約 27 小時）。

`get_block_root_at_slot()` 被 [`get_attestation_participation_flag_indices()`](#def_get_attestation_participation_flag_indices) 用來檢查一筆證明是否為正確的鏈頭投票。它也用於 [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate)，以找出同步委員會正在簽字認可的區塊。

|||
|-|------|
| 使用&nbsp;者 | [`get_block_root()`](#def_get_block_root), [`get_attestation_participation_flag_indices()`](#def_get_attestation_participation_flag_indices), [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate) |
| 亦見 | [`SLOTS_PER_HISTORICAL_ROOT`](/part3/config/preset/#slots_per_historical_root), [`Root`](/part3/config/types/#root) |

#### `get_randao_mix`

<a id="def_get_randao_mix"></a>

```python
def get_randao_mix(state: BeaconState, epoch: Epoch) -> Bytes32:
    """
    Return the randao mix at a recent ``epoch``.
    """
    return state.randao_mixes[epoch % EPOCHS_PER_HISTORICAL_VECTOR]
```

RANDAO 混合值儲存在一個長度為 [`EPOCHS_PER_HISTORICAL_VECTOR`](/part3/config/preset/#epochs_per_historical_vector) 的環狀串列中。它們在計算「指派信標提議者與委員會」之[種子](#get_seed)時被使用。

當前紀元的 RANDAO 混合值，隨著新的 RANDAO reveal 進來而以逐區塊的方式更新。先前紀元的混合值，是該紀元結束時被凍結的 RANDAO 值。

|||
|-|------|
| 使用&nbsp;者 | [`get_seed`](#def_get_seed), [`process_randao_mixes_reset()`](/part3/transition/epoch/#def_process_randao_mixes_reset), [`process_randao()`](/part3/transition/block/#def_process_randao) |
| 亦見 | [`EPOCHS_PER_HISTORICAL_VECTOR`](/part3/config/preset/#epochs_per_historical_vector) |

#### `get_active_validator_indices`

<a id="def_get_active_validator_indices"></a>

```python
def get_active_validator_indices(state: BeaconState, epoch: Epoch) -> Sequence[ValidatorIndex]:
    """
    Return the sequence of active validator indices at ``epoch``.
    """
    return [ValidatorIndex(i) for i, v in enumerate(state.validators) if is_active_validator(v, epoch)]
```

逐一走過驗證者的整個串列，只回傳活躍者的串列。也就是，由 [`is_active_validator()`](/part3/helper/predicates/#def_is_active_validator) 判定為「已被啟用但未退出」之驗證者的串列。

這個函式被大量使用，我預期它在實務上會被[記憶化](https://en.wikipedia.org/wiki/Memoization)（memoised）。

|||
|-|------|
| 使用&nbsp;者 | 許多地方 |
| 使用 | [`is_active_validator()`](/part3/helper/predicates/#def_is_active_validator) |

#### `get_validator_churn_limit`

<a id="def_get_validator_churn_limit"></a>

```python
def get_validator_churn_limit(state: BeaconState) -> uint64:
    """
    Return the validator churn limit for the current epoch.
    """
    active_validator_indices = get_active_validator_indices(state, get_current_epoch(state))
    return max(MIN_PER_EPOCH_CHURN_LIMIT, uint64(len(active_validator_indices)) // CHURN_LIMIT_QUOTIENT)
```

「變動上限」（churn limit）在[啟用](/part3/transition/epoch/#registry-updates)與[退出](/part3/helper/mutators/#initiate_validator_exit)驗證者時適用，並作為對「驗證者集合變化」的一項[速率限制](https://notes.ethereum.org/@vbuterin/rkhCgQteN#Exiting)。這個函式回傳的值，提供「一個紀元中可變為啟用的驗證者數」與「一個紀元中可退出的驗證者數」。

某個少量的變動量始終被容許，由 [`MIN_PER_EPOCH_CHURN_LIMIT`](/part3/config/configuration/#min_per_epoch_churn_limit) 設定，而當前每多 [`CHURN_LIMIT_QUOTIENT`](/part3/config/configuration/#churn_limit_quotient) 個啟用的驗證者，每紀元容許的變動量就增加一（在超過最小值之後）。

<!-- Number of validators -->

具體而言，在有 500,000 個驗證者的情況下，這意味著每個紀元最多有七個驗證者能進入或退出活躍驗證者集合（每天 1,575 個）。在 524,288 個活躍驗證者時，上限會升到每紀元八個（每天 1,800 個）。

|||
|-|------|
| 使用&nbsp;者 | [`initiate_validator_exit()`](/part3/helper/mutators/#def_initiate_validator_exit), [`process_registry_updates()`](/part3/transition/epoch/#def_process_registry_updates) |
| 使用 | [`get_active_validator_indices()`](#def_get_active_validator_indices) |
| 亦見 | [`MIN_PER_EPOCH_CHURN_LIMIT`](/part3/config/configuration/#min_per_epoch_churn_limit), [`CHURN_LIMIT_QUOTIENT`](/part3/config/configuration/#churn_limit_quotient) |

#### `get_seed`

<a id="def_get_seed"></a>

```python
def get_seed(state: BeaconState, epoch: Epoch, domain_type: DomainType) -> Bytes32:
    """
    Return the seed at ``epoch``.
    """
    mix = get_randao_mix(state, Epoch(epoch + EPOCHS_PER_HISTORICAL_VECTOR - MIN_SEED_LOOKAHEAD - 1))  # Avoid underflow
    return hash(domain_type + uint_to_bytes(epoch) + mix)
```

用於 [`get_beacon_committee()`](#def_get_beacon_committee)、[`get_beacon_proposer_index()`](#def_get_beacon_proposer_index) 與 [`get_next_sync_committee_indices()`](#def_get_next_sync_committee_indices)，為計算提議者與委員會提供隨機性。`domain_type` 分別是 [`DOMAIN_BEACON_ATTESTER`](/part3/config/constants/#domain_beacon_attester)、[`DOMAIN_BEACON_PROPOSER`](/part3/config/constants/#domain_beacon_proposer) 與 [`DOMAIN_SYNC_COMMITTEE`](/part3/config/constants/#domain_sync_committee)。

RANDAO 混合值儲存在一個長度為 [`EPOCHS_PER_HISTORICAL_VECTOR`](/part3/config/preset/#epochs_per_historical_vector) 的環狀串列中。一個紀元的種子，基於 [`MIN_SEED_LOOKAHEAD`](/part3/config/preset/#min_seed_lookahead) 個紀元之前的 randao 混合值。這是為了限制隨機性向前的可見度：見該處的解釋。

回傳的種子不只基於域與 randao 混合值，紀元號也被混入。這是為了處理「超過兩個紀元都沒見到任何區塊」的病態情況，在那種情況下我們會用盡 randao 更新。那可能會把一組不參與的區塊提議者永遠鎖定。把紀元號混入，意味著嶄新的委員會與提議者能繼續被選出。

|||
|-|------|
| 使用&nbsp;者 | [`get_beacon_committee()`](#def_get_beacon_committee), [`get_beacon_proposer_index()`](#def_get_beacon_proposer_index), [`get_next_sync_committee_indices()`](#def_get_next_sync_committee_indices) |
| 使用 | [`get_randao_mix()`](#def_get_randao_mix) |
| 亦見 | [`EPOCHS_PER_HISTORICAL_VECTOR`](/part3/config/preset/#epochs_per_historical_vector), [`MIN_SEED_LOOKAHEAD`](/part3/config/preset/#min_seed_lookahead) |

#### `get_committee_count_per_slot`

<a id="def_get_committee_count_per_slot"></a>

```python
def get_committee_count_per_slot(state: BeaconState, epoch: Epoch) -> uint64:
    """
    Return the number of committees in each slot for the given ``epoch``.
    """
    return max(uint64(1), min(
        MAX_COMMITTEES_PER_SLOT,
        uint64(len(get_active_validator_indices(state, epoch))) // SLOTS_PER_EPOCH // TARGET_COMMITTEE_SIZE,
    ))
```

在一個給定的紀元中，每個時段都有相同數目的信標委員會，由這個函式計算。

就 LMD GHOST 共識協定而言，一個時段中所有作證的驗證者，實際上充當單一一個大委員會。然而，把它們組織成多個委員會帶來兩項好處。

 1. 有多個較小的委員會，減輕了「收集並聚合委員會成員之證明」之聚合者的負載。這很重要，因為驗證簽章並把它們聚合起來需要時間。缺點是區塊需要更大，因為在最佳情況下，每個區塊要儲存多達 64 筆聚合證明，而不是一個「涵蓋所有證明」的單一大型聚合簽章。
 2. 它與資料分片的未來計畫對應得很好——屆時每個委員會除了當前職責之外，還會負責對某一個分片上的一個區塊作出承諾。

由於最初那個「需要這些委員會」的 Phase&nbsp;1 分片設計如今已被放棄，這兩點中的第二點不再適用。

每個時段始終至少有一個委員會，也絕不會超過 [`MAX_COMMITTEES_PER_SLOT`](/part3/config/preset/#max_committees_per_slot)（目前是 64）。

在這些約束之下，每個時段委員會的實際數目是 $N / 4096$，其中 $N$ 是活躍驗證者的總數。

預期的行為看起來是這樣的：

  - 理想的情況是每個時段有 [`MAX_COMMITTEES_PER_SLOT`](/part3/config/preset/#max_committees_per_slot) = 64 個委員會。一旦資料分片被實作，這對應到每個時段、每個分片一個委員會。這些委員會會負責為分片交叉連結（crosslink）投票。要達成這一點，必須至少有 262,144 個活躍驗證者。
  - 如果活躍驗證者較少，那麼每個分片的委員會數會被減到 64 以下，以維持一個 [`TARGET_COMMITTEE_SIZE`](/part3/config/preset/#target_committee_size) = 128 的最小委員會大小。在這種情況下（一旦分片就位），並非每個分片在每個時段都會被交叉連結。
  - 最後，只有在活躍驗證者數跌到 4096 以下時，委員會大小才會被減到少於 128。在驗證者如此之少的情況下，無論如何這條鏈都沒有有意義的安全性了。

|||
|-|------|
| 使用&nbsp;者 | [`get_beacon_committee()`](#def_get_beacon_committee), [`process_attestation()`](/part3/transition/block/#def_process_attestation) |
| 使用 | [`get_active_validator_indices()`](/part3/helper/accessors/#def_get_active_validator_indices) |
| 亦見 | [`MAX_COMMITTEES_PER_SLOT`](/part3/config/preset/#max_committees_per_slot), [`TARGET_COMMITTEE_SIZE`](/part3/config/preset/#target_committee_size) |

#### `get_beacon_committee`

<a id="def_get_beacon_committee"></a>

```python
def get_beacon_committee(state: BeaconState, slot: Slot, index: CommitteeIndex) -> Sequence[ValidatorIndex]:
    """
    Return the beacon committee at ``slot`` for ``index``.
    """
    epoch = compute_epoch_at_slot(slot)
    committees_per_slot = get_committee_count_per_slot(state, epoch)
    return compute_committee(
        indices=get_active_validator_indices(state, epoch),
        seed=get_seed(state, epoch, DOMAIN_BEACON_ATTESTER),
        index=(slot % SLOTS_PER_EPOCH) * committees_per_slot + index,
        count=committees_per_slot * SLOTS_PER_EPOCH,
    )
```

信標委員會在每個時段透過證明為信標區塊投票。每個時段最多有 [`MAX_COMMITTEES_PER_SLOT`](/part3/config/preset/#max_committees_per_slot) 個信標委員會，而每個委員會每個紀元正好運作一次。

這個函式給定一個時段號、以及那個時段內用以選出所要委員會的一個索引，回傳委員會成員的串列，並仰賴 [`compute_committee()`](/part3/helper/misc/#def_compute_committee) 來做粗重的工作。

請注意，由於這使用 [`get_seed()`](#def_get_seed)，我們只能取得往回回溯最多 [`EPOCHS_PER_HISTORICAL_VECTOR`](/part3/config/preset/#epochs_per_historical_vector) 個紀元（減去 [`MIN_SEED_LOOKAHEAD`](/part3/config/preset/#min_seed_lookahead)）的委員會。

`get_beacon_committee` 被 [`get_attesting_indices()`](#def_get_attesting_indices) 與 [`process_attestation()`](/part3/transition/block/#def_process_attestation) 在處理來自一個委員會的證明時使用，也被驗證者在檢查它們的[委員會指派](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#validator-assignments)與[聚合職責](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#aggregation-selection)時使用。

|||
|-|------|
| 使用&nbsp;者 | [`get_attesting_indices()`](/part3/helper/accessors/#def_get_attesting_indices), [`process_attestation()`](/part3/transition/block/#def_process_attestation) |
| 使用 | [`get_committee_count_per_slot()`](#def_get_committee_count_per_slot), [`compute_committee()`](/part3/helper/misc/#def_compute_committee), [`get_active_validator_indices()`](/part3/helper/accessors/#def_get_active_validator_indices), [`get_seed()`](#def_get_seed) |
| 亦見 | [`MAX_COMMITTEES_PER_SLOT`](/part3/config/preset/#max_committees_per_slot), [`DOMAIN_BEACON_ATTESTER`](/part3/config/constants/#domain_beacon_attester) |

#### `get_beacon_proposer_index`

<a id="def_get_beacon_proposer_index"></a>

```python
def get_beacon_proposer_index(state: BeaconState) -> ValidatorIndex:
    """
    Return the beacon proposer index at the current slot.
    """
    epoch = get_current_epoch(state)
    seed = hash(get_seed(state, epoch, DOMAIN_BEACON_PROPOSER) + uint_to_bytes(state.slot))
    indices = get_active_validator_indices(state, epoch)
    return compute_proposer_index(state, indices, seed)
```

每個時段，活躍驗證者中正好有一個被隨機選為那個時段之信標區塊的提議者。被選中的機率，在 [`compute_proposer_index()`](/part3/helper/misc/#def_compute_proposer_index) 中依該驗證者的有效餘額被加權。

被選中的區塊提議者不需要是那個時段任一信標委員會的成員：它是從那個紀元的整個活躍驗證者集合中選出的。

[`get_seed()`](#def_get_seed) 回傳的 RANDAO 種子每個紀元更新一次。時段號用一個雜湊被混入種子，使我們能在每個時段選出一個不同的提議者。這也在「有一整個紀元的空區塊」的情況下保護我們。如果那發生了，RANDAO 不會被更新，但我們仍能透過這個「混入時段號」的過程，為下一個紀元選出一組不同的提議者。

同一個提議者在兩個連續時段中被選中、或在一個紀元中被選中超過一次，是有機會的。如果每個驗證者都有相同的有效餘額，那麼在某個特定時段被選中的機率就只是 $\frac{1}{N}$，與任何其他時段無關，其中 $N$ 是對應於該時段之紀元中的活躍驗證者數。

目前，`get_beacon_proposer_index()` 與 [`compute_proposer_index()`](/part3/helper/misc/#def_compute_proposer_index) 兩者都不會把被罰沒的驗證者過濾掉。這可能導致一個被罰沒的驗證者，在其退出之前，被選中提議一個區塊。然而，由於 [`process_block_header()`](/part3/transition/block/#def_process_block_header) 中的檢查，它的區塊會是無效的。已有人[提出對此的一個修正](https://github.com/ethereum/consensus-specs/pull/3175)，以避免在發生大規模罰沒時出現許多錯失的時段（帶有無效區塊的時段）。

|||
|-|------|
| 使用&nbsp;者 | [`slash_validator()`](/part3/helper/mutators/#def_slash_validator), [`process_block_header()`](/part3/transition/block/#def_process_block_header), [`process_randao()`](/part3/transition/block/#def_process_randao), [`process_attestation()`](/part3/transition/block/#def_process_attestation), [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate) |
| 使用 | [`get_seed()`](#def_get_seed), [`uint_to_bytes()`](/part3/helper/math/#uint_to_bytes), [`get_active_validator_indices()`](/part3/helper/accessors/#def_get_active_validator_indices), [`compute_proposer_index()`](/part3/helper/misc/#def_compute_proposer_index) |

#### `get_total_balance`

<a id="def_get_total_balance"></a>

```python
def get_total_balance(state: BeaconState, indices: Set[ValidatorIndex]) -> Gwei:
    """
    Return the combined effective balance of the ``indices``.
    ``EFFECTIVE_BALANCE_INCREMENT`` Gwei minimum to avoid divisions by zero.
    Math safe up to ~10B ETH, after which this overflows uint64.
    """
    return Gwei(max(EFFECTIVE_BALANCE_INCREMENT, sum([state.validators[index].effective_balance for index in indices])))
```

一個簡單的公用程式，回傳所傳入串列 `indices` 中所有驗證者的總餘額。

順帶一提，這裡潛藏著一個「規格中某種脆弱性」的有趣例子。這個函式[從前](https://github.com/ethereum/consensus-specs/blame/8c532c0e9ad1e6016a1ef3f36012cfd9b3870c13/specs/phase0/beacon-chain.md#L1002)回傳最小值 1 Gwei，以避免在獎勵與懲罰計算中可能發生的除以零。然而，獎勵計算被[修改](https://github.com/ethereum/consensus-specs/pull/1635)以避免一個可能的整數溢位狀況，卻沒有修改這個函式，這重新引入了[除以零](https://github.com/ethereum/consensus-specs/issues/1663)的可能性。這後來藉由回傳最小值 [`EFFECTIVE_BALANCE_INCREMENT`](/part3/config/preset/#effective_balance_increment) 而被[修正](https://github.com/ethereum/consensus-specs/pull/1664)。規格的[形式驗證](https://github.com/ConsenSys/eth2.0-dafny)有助於避免像這樣的問題。

|||
|-|------|
| 使用&nbsp;者 | [`get_total_active_balance()`](#def_get_total_active_balance), [`get_flag_index_deltas()`](#def_get_flag_index_deltas), [`process_justification_and_finalization()`](/part3/transition/epoch/#def_process_justification_and_finalization) |
| 亦見 | [`EFFECTIVE_BALANCE_INCREMENT`](/part3/config/preset/#effective_balance_increment) |

#### `get_total_active_balance`

<a id="def_get_total_active_balance"></a>

```python
def get_total_active_balance(state: BeaconState) -> Gwei:
    """
    Return the combined effective balance of the active validators.
    Note: ``get_total_balance`` returns ``EFFECTIVE_BALANCE_INCREMENT`` Gwei minimum to avoid divisions by zero.
    """
    return get_total_balance(state, set(get_active_validator_indices(state, get_current_epoch(state))))
```

使用 [`get_total_balance()`](#def_get_total_balance) 來計算當前紀元中所有活躍驗證者有效餘額的總和。

這個量在規格中經常被用到。舉例來說，Casper FFG 用總活躍餘額來判斷在[證成與最終確定](/part3/transition/epoch/#justification-and-finalization)中是否已達到 2/3 的證明多數門檻。而它是獎勵與懲罰計算的一個基礎部分。[基礎獎勵](/part3/transition/epoch/#def_get_base_reward_per_increment)與總活躍餘額平方根的倒數成比例。因此，當質押的餘額少（活躍驗證者少）時，驗證者獎勵較高；當質押的餘額多（活躍驗證者多）時，驗證者獎勵較低。

由於它是從有效餘額計算出來的，總活躍餘額在一個紀元期間不會改變，所以是一個非常適合被快取的候選對象。

|||
|-|------|
| 使用&nbsp;者 | [`get_flag_index_deltas()`](#def_get_flag_index_deltas), [`process_justification_and_finalization()`](/part3/transition/epoch/#def_process_justification_and_finalization), [`get_base_reward_per_increment()`](/part3/transition/epoch/#def_get_base_reward_per_increment), [`process_slashings()`](/part3/transition/epoch/#def_process_slashings), [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate) |
| 使用 | [`get_total_balance()`](#def_get_total_balance), [`get_active_validator_indices()`](/part3/helper/accessors/#def_get_active_validator_indices) |

#### `get_domain`

<a id="def_get_domain"></a>

```python
def get_domain(state: BeaconState, domain_type: DomainType, epoch: Epoch=None) -> Domain:
    """
    Return the signature domain (fork version concatenated with domain type) of a message.
    """
    epoch = get_current_epoch(state) if epoch is None else epoch
    fork_version = state.fork.previous_version if epoch < state.fork.epoch else state.fork.current_version
    return compute_domain(domain_type, fork_version, state.genesis_validators_root)
```

每當需要驗證簽章時，`get_domain()` 就會冒出來，因為一個 [`DomainType`](/part3/config/types/#domaintype) 總是被混入被簽署的資料中。關於域背後的學問，見[域型別](/part3/config/constants/#domain-types)與 [`compute_domain()`](/part3/helper/misc/#def_compute_domain)。

除了 `DOMAIN_DEPOSIT` 之外，域在被用於簽章產生之前，總是與分叉[版本](/part3/config/types/#version)結合。這是為了區分來自不同鏈的訊息，並確保驗證者若選擇在兩個獨立的分叉上參與，不會被罰沒。（這指的是刻意的分叉，又稱硬分叉。在臨時共識分叉的兩個分支上都參與是會受罰的：那基本上就是罰沒的全部重點。）

請注意，在某一個分叉版本下簽署的訊息，在下一個分叉版本期間有效，但之後就無效了。所以，舉例來說，在 Altair 期間簽署的自願退出訊息，在 Bellatrix 信標鏈升級之後有效，但在 Capella 升級之後就無效。在 Phase&nbsp;0 期間簽署的自願退出訊息在 Altair 之下有效，但被 Bellatrix 升級弄成無效[^fn-vem-fork-agnostic]。

[^fn-vem-fork-agnostic]: 有[一些討論](https://github.com/ethereum/consensus-specs/pull/3288)圍繞著改變這一點，使自願退出訊息在未來與分叉無關，但那尚未被實作。

|||
|-|------|
| 使用&nbsp;者 | [`is_valid_indexed_attestation()`](/part3/helper/predicates/#def_is_valid_indexed_attestation), [`verify_block_signature()`](/part3/transition/#def_verify_block_signature), [`process_randao()`](/part3/transition/block/#def_process_randao), [`process_proposer_slashing()`](/part3/transition/block/#def_process_proposer_slashing), [`process_voluntary_exit()`](/part3/transition/block/#def_process_voluntary_exit), [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate) |
| 使用 | [`compute_domain()`](/part3/helper/misc/#def_compute_domain) |
| 亦見 | [`DomainType`](/part3/config/types/#domaintype), [Domain types](/part3/config/constants/#domain-types) |

#### `get_indexed_attestation`

<a id="def_get_indexed_attestation"></a>

```python
def get_indexed_attestation(state: BeaconState, attestation: Attestation) -> IndexedAttestation:
    """
    Return the indexed attestation corresponding to ``attestation``.
    """
    attesting_indices = get_attesting_indices(state, attestation.data, attestation.aggregation_bits)

    return IndexedAttestation(
        attesting_indices=sorted(attesting_indices),
        data=attestation.data,
        signature=attestation.signature,
    )
```

委員會內的驗證者串列在規格中以兩種形式出現。

  - 它們可以被壓縮成一個位元串列，其中每個位元代表某個特定委員會中一個驗證者的在場或不在場。該委員會以時段、以及該時段內的委員會索引被指涉。這就是驗證者集合在 [`Attestation`](/part3/containers/operations/#attestation) 中被表示的方式。
  - 或者它們可以用其驗證者索引明確地列出，如同 [`IndexedAttestation`](/part3/containers/dependencies/#indexedattestation) 中那樣。請注意，索引的串列是已排序的：若非如此，這筆證明就[無效](/part3/helper/predicates/#is_valid_indexed_attestation)。

`get_indexed_attestation()` 從前一種表示法轉換成後一種。時段號與委員會索引由 [`AttestationData`](/part3/containers/dependencies/#attestationdata) 提供，並被用來透過 [`get_beacon_committee()`](/part3/helper/accessors/#def_get_beacon_committee) 重建委員會成員。所提供的位元串列會是來自一筆 `Attestation`。

證明是可聚合的，這意味著「來自多個做出相同投票之驗證者」的證明，能透過 BLS 簽章聚合的魔法被捲合成單一一筆證明。然而，為了之後能驗證簽章，需要保留一筆紀錄，記下哪些驗證者實際上對該證明出了力。這是為了能把那些驗證者的公鑰聚合起來，以匹配簽章的建構方式。

從位元串列格式到串列格式的轉換，由下方的 [`get_attesting_indices()`](#get_attesting_indices) 執行。

|||
|-|------|
| 使用&nbsp;者 | [`process_attestation()`](/part3/transition/block/#def_process_attestation) |
| 使用 | [`get_attesting_indices()`](#def_get_attesting_indices) |
| 亦見 | [`Attestation`](/part3/containers/operations/#attestation), [`IndexedAttestation`](/part3/containers/dependencies/#indexedattestation) |

#### `get_attesting_indices`

<a id="def_get_attesting_indices"></a>

```python
def get_attesting_indices(state: BeaconState,
                          data: AttestationData,
                          bits: Bitlist[MAX_VALIDATORS_PER_COMMITTEE]) -> Set[ValidatorIndex]:
    """
    Return the set of attesting indices corresponding to ``data`` and ``bits``.
    """
    committee = get_beacon_committee(state, data.slot, data.index)
    return set(index for i, index in enumerate(committee) if bits[i])
```

如 [`get_indexed_attestation()`](#def_get_indexed_attestation) 之下所描述，驗證者串列有兩種形式。這個常式從壓縮形式（其中驗證者被表示為一個委員會的子集，它們的在場或不在場分別以一個 1 位元或一個 0 位元指明）轉換成一個明確的 [`ValidatorIndex`](/part3/config/types/#validatorindex) 型別串列。

|||
|-|------|
| 使用&nbsp;者 | [`get_indexed_attestation()`](#def_get_indexed_attestation), [`process_attestation()`](/part3/transition/block/#def_process_attestation) |
| 使用 | [`get_beacon_committee()`](#def_get_beacon_committee) |
| 亦見 | [`AttestationData`](/part3/containers/dependencies/#attestationdata), [`IndexedAttestation`](/part3/containers/dependencies/#indexedattestation) |

#### `get_next_sync_committee_indices`

<a id="def_get_next_sync_committee_indices"></a>

```python
def get_next_sync_committee_indices(state: BeaconState) -> Sequence[ValidatorIndex]:
    """
    Return the sync committee indices, with possible duplicates, for the next sync committee.
    """
    epoch = Epoch(get_current_epoch(state) + 1)

    MAX_RANDOM_BYTE = 2**8 - 1
    active_validator_indices = get_active_validator_indices(state, epoch)
    active_validator_count = uint64(len(active_validator_indices))
    seed = get_seed(state, epoch, DOMAIN_SYNC_COMMITTEE)
    i = 0
    sync_committee_indices: List[ValidatorIndex] = []
    while len(sync_committee_indices) < SYNC_COMMITTEE_SIZE:
        shuffled_index = compute_shuffled_index(uint64(i % active_validator_count), active_validator_count, seed)
        candidate_index = active_validator_indices[shuffled_index]
        random_byte = hash(seed + uint_to_bytes(uint64(i // 32)))[i % 32]
        effective_balance = state.validators[candidate_index].effective_balance
        if effective_balance * MAX_RANDOM_BYTE >= MAX_EFFECTIVE_BALANCE * random_byte:
            sync_committee_indices.append(candidate_index)
        i += 1
    return sync_committee_indices
```

`get_next_sync_committee_indices()` 被用來選出「會組成一個同步委員會」的驗證者子集。委員會大小是 [`SYNC_COMMITTEE_SIZE`](/part3/config/preset/#sync_committee_size)，而委員會被容許包含重複者，也就是同一個驗證者超過一次。這是為了[優雅地處理](https://github.com/ethereum/consensus-specs/pull/2130#discussion_r532499943)「活躍驗證者少於 `SYNC_COMMITTEE_SIZE`」的情況。

與被選中提議一個區塊類似，任何驗證者被選入一個同步委員會的機率，與其有效餘額成比例。因此，這個演算法與 [`compute_proposer_index()`](/part3/helper/misc/#def_compute_proposer_index) 的演算法幾乎相同，只是這一個只在找到 `SYNC_COMMITTEE_SIZE` 個成員之後才退出，而非一找到候選者就退出。兩個常式都使用「嘗試並遞增」方法，以驗證者的有效餘額為選取機率加權。

區塊提議者為什麼以「與其有效餘額成比例」的機率被選出，相當清楚：出塊會受罰沒，而質押較少的提議者可罰沒的也較少，所以我們相應地降低它們的影響力。但「身在一個同步委員會中的機率也與一個驗證者的有效餘額成比例」這一點，就不那麼清楚了；同步委員會不受罰沒。它與「讓[輕客戶端的計算保持簡單](https://github.com/ethereum/consensus-specs/pull/2130#discussion_r524848644)」有關。我們不想加給輕客戶端「把驗證者餘額加總起來、以判斷委員會中是否有 2/3 超多數質押為一個區塊投票」的負擔。理想上，它們可以只計算參與旗標的數目。為了讓這在某種程度上可靠，我們把「一個驗證者參與的機率」以「與其有效餘額成比例」的方式加權。

|||
|-|------|
| 使用&nbsp;者 | [`get_next_sync_committee()`](#def_get_next_sync_committee) |
| 使用 | [`get_active_validator_indices()`](/part3/helper/accessors/#def_get_active_validator_indices), [`get_seed()`](/part3/helper/accessors/#def_get_seed), [`compute_shuffled_index()`](/part3/helper/misc/#def_compute_shuffled_index), [`uint_to_bytes()`](/part3/helper/math/#uint_to_bytes) |
| 亦見 | [`SYNC_COMMITTEE_SIZE`](/part3/config/preset/#sync_committee_size), [`compute_proposer_index()`](/part3/helper/misc/#def_compute_proposer_index) |

#### `get_next_sync_committee`

> _注意_：函式 `get_next_sync_committee` 應只在同步委員會週期邊界、以及[把狀態升級到 Altair](/part4/history/altair/) 時被呼叫。

產生同步委員會的隨機種子，基於下一個紀元的編號。[`get_next_sync_committee_indices()`](#def_get_next_sync_committee_indices) 不包含任何「檢查該紀元是否對應於同步委員會更換邊界」的檢查，這讓 Altair 升級的時機能更有彈性。但其後果是，如果你在錯誤的時間呼叫 `get_next_sync_committee()`，你會得到一個不正確的委員會。

<a id="def_get_next_sync_committee"></a>

```python
def get_next_sync_committee(state: BeaconState) -> SyncCommittee:
    """
    Return the next sync committee, with possible pubkey duplicates.
    """
    indices = get_next_sync_committee_indices(state)
    pubkeys = [state.validators[index].pubkey for index in indices]
    aggregate_pubkey = eth_aggregate_pubkeys(pubkeys)
    return SyncCommittee(pubkeys=pubkeys, aggregate_pubkey=aggregate_pubkey)
```

`get_next_sync_committee()` 是 [`get_next_sync_committee_indices()`](#def_get_next_sync_committee_indices) 的一個簡單包裝器，把一切打包成一個漂亮的 [`SyncCommittee`](/part3/containers/dependencies/#synccommittee) 物件。

關於 `aggregate_pubkey` 預計如何被使用的解釋，見 [`SyncCommittee`](/part3/containers/dependencies/#synccommittee) 型別。

|||
|-|------|
| 使用&nbsp;者 | [`process_sync_committee_updates()`](/part3/transition/epoch/#def_process_sync_committee_updates), [`initialize_beacon_state_from_eth1()`](/part3/initialise/#def_initialize_beacon_state_from_eth1) |
| 使用 | [`get_next_sync_committee_indices()`](#def_get_next_sync_committee_indices), [`eth_aggregate_pubkeys()`](/part3/helper/crypto/#def_eth_aggregate_pubkeys) |
| 亦見 | [`SyncCommittee`](/part3/containers/dependencies/#synccommittee) |

#### `get_unslashed_participating_indices`

<a id="def_get_unslashed_participating_indices"></a>

```python
def get_unslashed_participating_indices(state: BeaconState, flag_index: int, epoch: Epoch) -> Set[ValidatorIndex]:
    """
    Return the set of validator indices that are both active and unslashed for the given ``flag_index`` and ``epoch``.
    """
    assert epoch in (get_previous_epoch(state), get_current_epoch(state))
    if epoch == get_current_epoch(state):
        epoch_participation = state.current_epoch_participation
    else:
        epoch_participation = state.previous_epoch_participation
    active_validator_indices = get_active_validator_indices(state, epoch)
    participating_indices = [i for i in active_validator_indices if has_flag(epoch_participation[i], flag_index)]
    return set(filter(lambda index: not state.validators[index].slashed, participating_indices))
```

`get_unslashed_participating_indices()` 回傳「在所討論的 `epoch` 期間，做出了類型為 [`flag_index`](/part3/config/constants/#participation-flag-indices) 之及時證明」的驗證者串列。

它在 [`process_justification_and_finalization()`](/part3/transition/epoch/#def_process_justification_and_finalization) 中與 `TIMELY_TARGET_FLAG_INDEX` 旗標一起使用，以計算「在當前與先前紀元為候選檢查點投票之質押」的比例。

它也與 `TIMELY_TARGET_FLAG_INDEX` 一起，用於在 [`process_inactivity_updates()`](/part3/transition/epoch/#def_process_inactivity_updates) 與 [`get_inactivity_penalty_deltas()`](/part3/transition/epoch/#def_get_inactivity_penalty_deltas) 中套用怠惰懲罰。如果一個驗證者在怠惰洩漏期間錯失了一個正確的目標投票，那麼它就被視為根本沒有參與（它沒有貢獻任何有用的東西）。

而它在 [`get_flag_index_deltas()`](#def_get_flag_index_deltas) 中被用來計算每種正確投票應得的獎勵。

被罰沒的驗證者被忽略。一旦被罰沒，驗證者就不再收到獎勵或參與共識，雖然在它們最終被退出之前仍會受到懲罰。

|||
|-|------|
| 使用&nbsp;者 | [`get_flag_index_deltas()`](#def_get_flag_index_deltas), [`process_justification_and_finalization()`](/part3/transition/epoch/#def_process_justification_and_finalization), [`process_inactivity_updates()`](/part3/transition/epoch/#def_process_inactivity_updates), [`get_inactivity_penalty_deltas()`](/part3/transition/epoch/#def_get_inactivity_penalty_deltas) |
| 使用 | [`get_active_validator_indices()`](/part3/helper/accessors/#def_get_active_validator_indices), [`has_flag()`](/part3/helper/participation/#def_has_flag) |
| 亦見 | [Participation flag indices](/part3/config/constants/#participation-flag-indices) |

#### `get_attestation_participation_flag_indices`

<a id="def_get_attestation_participation_flag_indices"></a>

```python
def get_attestation_participation_flag_indices(state: BeaconState,
                                               data: AttestationData,
                                               inclusion_delay: uint64) -> Sequence[int]:
    """
    Return the flag indices that are satisfied by an attestation.
    """
    if data.target.epoch == get_current_epoch(state):
        justified_checkpoint = state.current_justified_checkpoint
    else:
        justified_checkpoint = state.previous_justified_checkpoint

    # Matching roots
    is_matching_source = data.source == justified_checkpoint
    is_matching_target = is_matching_source and data.target.root == get_block_root(state, data.target.epoch)
    is_matching_head = is_matching_target and data.beacon_block_root == get_block_root_at_slot(state, data.slot)
    assert is_matching_source

    participation_flag_indices = []
    if is_matching_source and inclusion_delay <= integer_squareroot(SLOTS_PER_EPOCH):
        participation_flag_indices.append(TIMELY_SOURCE_FLAG_INDEX)
    if is_matching_target and inclusion_delay <= SLOTS_PER_EPOCH:
        participation_flag_indices.append(TIMELY_TARGET_FLAG_INDEX)
    if is_matching_head and inclusion_delay == MIN_ATTESTATION_INCLUSION_DELAY:
        participation_flag_indices.append(TIMELY_HEAD_FLAG_INDEX)

    return participation_flag_indices
```

這在區塊處理期間被 [`process_attestation()`](/part3/transition/block/#def_process_attestation) 呼叫，它是「記錄驗證者證明中所含投票」之機制的核心。它把給定的證明對照信標狀態當前對鏈的觀點加以過濾，並只為「既正確又及時」的投票回傳[參與旗標索引](/part3/config/constants/#participation-flag-indices)。

`data` 是一個 [`AttestationData`](/part3/containers/dependencies/#attestationdata) 物件，包含「對該證明出力之驗證者」的來源、目標與鏈頭投票。這筆證明可能代表一個或多個驗證者的投票。

`inclusion_delay` 是「信標鏈上的當前時段」與「該證明被建立所針對之時段」之間的差。要讓含有該證明的區塊有效，`inclusion_delay` 必須介於 [`MIN_ATTESTATION_INCLUSION_DELAY`](/part3/config/preset/#min_attestation_inclusion_delay) 與 [`SLOTS_PER_EPOCH`](/part3/config/preset/#slots_per_epoch)（含兩端）之間。換句話說，證明必須被納入下一個區塊、或任何最晚 32 個時段之後的區塊，之後它們就被忽略。

由於該證明可能最舊有 32 個時段之久，它可能是在當前紀元或先前紀元被產生的，所以我們做的第一件事，就是檢查該證明的目標投票紀元，以看出我們在信標狀態中該查看哪個紀元。

接著，我們檢查該證明中的每一個投票是否正確：

  - 該證明的來源投票，是否與「我們相信是所討論紀元中之已證成檢查點」相符？
  - 若是，該證明的目標投票，是否與「該紀元檢查點處的鏈頭區塊」（即該紀元的第一個時段）相符？
  - 若是，該證明的鏈頭投票，是否與「我們相信是該證明時段處之鏈頭區塊」相符？請注意，該時段可能不含區塊——它可能是一個略過的時段——在那種情況下，最後一個已知的區塊被視為鏈頭。

這三者彼此疊加，使得「沒有正確的來源投票就不可能有正確的目標投票」，並且「沒有正確的目標投票就不可能有正確的鏈頭投票」。

`assert` 陳述句很有意思。如果一筆證明沒有正確的來源投票，那麼含有它的區塊就無效並被丟棄。有一個不正確的來源投票，意味著區塊提議者在「上一個已證成檢查點」這件事上與我意見不合，這是一個無法調和的歧異。

[TODO: check the irreconcilable bit. Maybe explain it.]::

在檢查過投票的有效性之後，每個投票的及時性被檢查。讓我們以相反的順序來看它們。

  - 正確的鏈頭投票必須立即被納入，也就是在緊接的下一個時段。
    - 鏈頭投票用於 LMD GHOST 共識，過了一個時段之後就沒有用了。
  - 正確的目標投票必須在 32 個時段（一個紀元）之內被納入。
    - 目標投票在任何時候都有用，但如果它們跨越不超過幾個紀元就會比較簡單，所以 32 個時段是一個合理的限制。這項檢查其實是多餘的，因為區塊中的證明不可能比 32 個時段更舊。
  - 正確的來源投票必須在 5 個時段（`integer_squareroot(32)`）之內被納入。
    - 這是 1（及時鏈頭門檻）與 32（及時目標門檻）的幾何平均數。這是一個任意的選擇。Vitalik 的看法[^fn_vitalik_geometric_mean]是：在這個設定下，累積的及時性獎勵最接近一條指數遞減曲線，這「感覺更合邏輯」。

[^fn_vitalik_geometric_mean]: 出自以太坊研究 Discord 伺服器上的一段[對話](https://discord.com/channels/595666850260713488/595701173944713277/871340571107655700)。

及時納入的要求在 Altair 中是新的。在 Phase&nbsp;0 中，所有正確的投票都收到一筆獎勵，並且有一筆「與納入距離倒數成比例」的額外納入獎勵。這導致了一個怪象：為一個正確的鏈頭投票永遠是更有利可圖的，即使那意味著等待更久、冒著無法被納入下一個時段的風險。

|||
|-|------|
| 使用&nbsp;者 | [`process_attestation()`](/part3/transition/block/#def_process_attestation) |
| 使用 | [`get_block_root()`](#def_get_block_root), [`get_block_root_at_slot()`](#def_get_block_root_at_slot), [`integer_squareroot()`](/part3/helper/math/#def_integer_squareroot) |
| 亦見 | [Participation flag indices](/part3/config/constants/#participation-flag-indices), [`AttestationData`](/part3/containers/dependencies/#attestationdata), [`MIN_ATTESTATION_INCLUSION_DELAY`](/part3/config/preset/#min_attestation_inclusion_delay) |

#### `get_flag_index_deltas`

<a id="def_get_flag_index_deltas"></a>

```python
def get_flag_index_deltas(state: BeaconState, flag_index: int) -> Tuple[Sequence[Gwei], Sequence[Gwei]]:
    """
    Return the deltas for a given ``flag_index`` by scanning through the participation flags.
    """
    rewards = [Gwei(0)] * len(state.validators)
    penalties = [Gwei(0)] * len(state.validators)
    previous_epoch = get_previous_epoch(state)
    unslashed_participating_indices = get_unslashed_participating_indices(state, flag_index, previous_epoch)
    weight = PARTICIPATION_FLAG_WEIGHTS[flag_index]
    unslashed_participating_balance = get_total_balance(state, unslashed_participating_indices)
    unslashed_participating_increments = unslashed_participating_balance // EFFECTIVE_BALANCE_INCREMENT
    active_increments = get_total_active_balance(state) // EFFECTIVE_BALANCE_INCREMENT
    for index in get_eligible_validator_indices(state):
        base_reward = get_base_reward(state, index)
        if index in unslashed_participating_indices:
            if not is_in_inactivity_leak(state):
                reward_numerator = base_reward * weight * unslashed_participating_increments
                rewards[index] += Gwei(reward_numerator // (active_increments * WEIGHT_DENOMINATOR))
        elif flag_index != TIMELY_HEAD_FLAG_INDEX:
            penalties[index] += Gwei(base_reward * weight // WEIGHT_DENOMINATOR)
    return rewards, penalties
```

這個函式在紀元處理期間被使用，基於個別驗證者在先前紀元的投票紀錄，為它們分派獎勵與懲罰。「區塊提議者因納入證明而獲得的獎勵」是[在區塊處理期間](/part3/transition/block/#def_process_attestation)計算的。函式名稱中的「deltas」（增減量）指的是回傳的「獎勵」與「懲罰」兩個分開的串列。獎勵與懲罰始終分開處理，以避免負數。

這個函式為「對應於正確證明投票」的每一種[旗標型別](/part3/config/constants/#participation-flag-indices)各被呼叫一次：及時來源、及時目標、及時鏈頭。

[`get_unslashed_participating_indices()`](/part3/helper/accessors/#def_get_unslashed_participating_indices) 回傳的驗證者串列，包含「將因『以及時且正確的方式做出這種投票』而被獎勵」的那些驗證者。那個常式使用「區塊處理期間 [`process_attestation()`](/part3/transition/block/#def_process_attestation) 為每個驗證者在狀態中所設定的旗標」，並回傳「對應旗標被設定」的驗證者。

每個活躍驗證者每個紀元被預期正好做出一筆證明，所以我們接著循環走遍整個活躍驗證者集合，只要我們不處於怠惰洩漏，就在它們出現於 `unslashed_participating_indices` 時獎勵它們。如果我們處於洩漏，就沒有驗證者的任何投票會被獎勵，但懲罰仍套用於不參與的驗證者。

請注意，獎勵以 `unslashed_participating_increments` 加權，後者與「以此旗標做出正確投票之驗證者」的總質押成比例。這意味著，如果其他驗證者的參與度較低，那麼即使我完美地履行我的職責，我的獎勵也會較低。這麼做的原因與[勸阻攻擊](https://raw.githubusercontent.com/ethereum/research/master/papers/discouragement/discouragement.pdf)（discouragement attack）有關（亦見這篇[不錯的說明](https://web.archive.org/web/20221225163839/https://hackingresear.ch/discouragement-attacks/)[^fn-discouragement-link]）。簡言之，有了這個機制，驗證者就被激勵去互相幫忙（例如轉發 gossip 訊息、或好好聚合證明），而不是去攻擊或審查彼此。

[^fn-discouragement-link]: 很遺憾，原本的頁面 `https://hackingresear.ch/discouragement-attacks/` 現在似乎已無法存取。內文中的連結指向 archive.org，但他們的版本有點壞掉。

未做出「正確且及時投票」的驗證者，會因它們所錯失的每個旗標而被處以一筆完整的加權基礎獎勵，但錯失鏈頭投票除外。鏈頭投票只有單一一個時段可以被納入，所以下一個時段缺少一個區塊就足以造成錯失，但這完全在證明者的控制之外。因此，鏈頭投票只會被獎勵，不會被懲罰。這也讓表現完美的驗證者在怠惰洩漏期間能損益兩平——那時我們預期至少三分之一的區塊會缺失：它們收不到獎勵，但理想上也收不到懲罰。

把算術理清楚，一個紀元中「證明者獎勵所造成的最大總發行量」$I_A$ 結果如下，使用稍後所描述的[符號](/part3/transition/epoch/#reward-and-penalty-calculations)。

$$
I_A = \frac{W_s + W_t + W_h}{W_{\Sigma}}NB
$$

|||
|-|------|
| 使用&nbsp;者 | [`process_rewards_and_penalties()`](/part3/transition/epoch/#def_process_rewards_and_penalties) |
| 使用 | [`get_unslashed_participating_indices()`](/part3/helper/accessors/#def_get_unslashed_participating_indices), [`get_total_balance()`](/part3/helper/accessors/#def_get_total_balance), [`get_total_active_balance()`](/part3/helper/accessors/#get_total_active_balance), [`get_eligible_validator_indices()`](/part3/transition/epoch/#def_get_eligible_validator_indices), [`get_base_reward()`](/part3/transition/epoch/#def_get_base_reward), [`is_in_inactivity_leak()`](/part3/transition/epoch/#def_is_in_inactivity_leak) |
| 亦見 | [`process_attestation()`](/part3/transition/block/#def_process_attestation), [participation flag indices](/part3/config/constants/#participation-flag-indices), [rewards and penalties](/part3/transition/epoch/#reward-and-penalty-calculations) |

### 信標狀態變更器 <!-- /part3/helper/mutators/ -->

#### `increase_balance`

<a id="def_increase_balance"></a>

```python
def increase_balance(state: BeaconState, index: ValidatorIndex, delta: Gwei) -> None:
    """
    Increase the validator balance at index ``index`` by ``delta``.
    """
    state.balances[index] += delta
```

在以一個驗證者的存款餘額建立該驗證者之後，這個函式與 [`decrease_balance()`](#decrease_balance) 是規格中唯二會修改驗證者餘額的地方。

我們需要兩個分開的函式來改變驗證者餘額，一個用來增加、一個用來減少，因為我們只使用無號整數。

有趣的小知識：這附近的一個錯字導致了 Teku 在最初的[客戶端互通活動](https://web.archive.org/web/20221129214218/https://media.consensys.net/how-30-eth-2-0-devs-locked-themselves-in-to-achieve-interoperability-175e4a807d92?gi=cbf4f6b2df72)上唯一的一次[共識失敗](https://github.com/ConsenSys/teku/pull/885/files)。無號整數[誘發臭蟲](https://critical.eschertech.com/2010/04/07/danger-unsigned-types-used-here/)！

|||
|-|------|
| 使用&nbsp;者 | [`slash_validator()`](#def_slash_validator), [`process_rewards_and_penalties()`](/part3/transition/epoch/#def_process_rewards_and_penalties), [`process_attestation()`](/part3/transition/block/#def_process_attestation), [`process_deposit()`](/part3/transition/block/#def_process_deposit), [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate) |
| 亦見 | [`decrease_balance()`](#def_decrease_balance) |

#### `decrease_balance`

<a id="def_decrease_balance"></a>

```python
def decrease_balance(state: BeaconState, index: ValidatorIndex, delta: Gwei) -> None:
    """
    Decrease the validator balance at index ``index`` by ``delta``, with underflow protection.
    """
    state.balances[index] = 0 if delta > state.balances[index] else state.balances[index] - delta
```

[`increase_balance()`](#increase_balance) 的對應物。它有一點額外的工作要做，以檢查無號整數的下溢，因為餘額不可變為負。

|||
|-|------|
| 使用&nbsp;者 | [`slash_validator()`](#def_slash_validator), [`process_rewards_and_penalties()`](/part3/transition/epoch/#def_process_rewards_and_penalties), [`process_slashings()`](/part3/transition/epoch/#def_process_slashings), [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate) |
| 亦見 | [`increase_balance()`](#increase_balance) |

#### `initiate_validator_exit`

<a id="def_initiate_validator_exit"></a>

```python
def initiate_validator_exit(state: BeaconState, index: ValidatorIndex) -> None:
    """
    Initiate the exit of the validator with index ``index``.
    """
    # Return if validator already initiated exit
    validator = state.validators[index]
    if validator.exit_epoch != FAR_FUTURE_EPOCH:
        return

    # Compute exit queue epoch
    exit_epochs = [v.exit_epoch for v in state.validators if v.exit_epoch != FAR_FUTURE_EPOCH]
    exit_queue_epoch = max(exit_epochs + [compute_activation_exit_epoch(get_current_epoch(state))])
    exit_queue_churn = len([v for v in state.validators if v.exit_epoch == exit_queue_epoch])
    if exit_queue_churn >= get_validator_churn_limit(state):
        exit_queue_epoch += Epoch(1)

    # Set validator exit epoch and withdrawable epoch
    validator.exit_epoch = exit_queue_epoch
    validator.withdrawable_epoch = Epoch(validator.exit_epoch + MIN_VALIDATOR_WITHDRAWABILITY_DELAY)
```

退出可能被[自願地](/part3/transition/block/#voluntary-exits)發起、作為[被罰沒](/part3/helper/mutators/#slash_validator)的結果、或藉由[跌到](/part3/transition/epoch/#registry-updates) [`EJECTION_BALANCE`](/part3/config/configuration/#ejection_balance) 門檻而發起。

在所有情況下，一個動態的「變動上限」為每個紀元可退出的驗證者數設了上限。它由 [`get_validator_churn_limit()`](/part3/helper/accessors/#get_validator_churn_limit) 計算。強制執行這一點的機制是退出佇列：該驗證者的 `exit_epoch` 被設定成它位於佇列的末端。

退出佇列不是以一個獨立的資料結構維護的，而是不斷地從所有驗證者的退出紀元重新計算出來，並容許每個紀元有固定數目退出。我預期在實際的實作中，這附近有一些可做的最佳化。

一個正在退出的驗證者，被預期繼續其提議與作證的職責，直到它的 `exit_epoch` 過去為止，並會繼續相應地收到獎勵與懲罰。

此外，一個已退出的驗證者，在它的 `withdrawable_epoch` 之前仍符合被罰沒的資格——`withdrawable_epoch` 被設在它的 `exit_epoch` 之後 [`MIN_VALIDATOR_WITHDRAWABILITY_DELAY`](/part3/config/configuration/#min_validator_withdrawability_delay) 個紀元。這是為了留一些額外時間，讓該驗證者的任何可罰沒過錯能被偵測並回報。

|||
|-|------|
| 使用&nbsp;者 | [`slash_validator()`](/part3/helper/mutators/#def_slash_validator), [`process_registry_updates()`](/part3/transition/epoch/#def_process_registry_updates), [`process_voluntary_exit()`](/part3/transition/block/#def_process_voluntary_exit) |
| 使用 | [`compute_activation_exit_epoch()`](/part3/helper/misc/#compute_activation_exit_epoch), [`get_validator_churn_limit()`](/part3/helper/accessors/#get_validator_churn_limit)|
| 亦見 | [自願退出](/part3/transition/block/#voluntary-exits)、[`MIN_VALIDATOR_WITHDRAWABILITY_DELAY`](/part3/config/configuration/#min_validator_withdrawability_delay) |

#### `slash_validator`

<a id="def_slash_validator"></a>

```python
def slash_validator(state: BeaconState,
                    slashed_index: ValidatorIndex,
                    whistleblower_index: ValidatorIndex=None) -> None:
    """
    Slash the validator with index ``slashed_index``.
    """
    epoch = get_current_epoch(state)
    initiate_validator_exit(state, slashed_index)
    validator = state.validators[slashed_index]
    validator.slashed = True
    validator.withdrawable_epoch = max(validator.withdrawable_epoch, Epoch(epoch + EPOCHS_PER_SLASHINGS_VECTOR))
    state.slashings[epoch % EPOCHS_PER_SLASHINGS_VECTOR] += validator.effective_balance
    slashing_penalty = validator.effective_balance // MIN_SLASHING_PENALTY_QUOTIENT_BELLATRIX
    decrease_balance(state, slashed_index, slashing_penalty)

    # Apply proposer and whistleblower rewards
    proposer_index = get_beacon_proposer_index(state)
    if whistleblower_index is None:
        whistleblower_index = proposer_index
    whistleblower_reward = Gwei(validator.effective_balance // WHISTLEBLOWER_REWARD_QUOTIENT)
    proposer_reward = Gwei(whistleblower_reward * PROPOSER_WEIGHT // WEIGHT_DENOMINATOR)
    increase_balance(state, proposer_index, proposer_reward)
    increase_balance(state, whistleblower_index, Gwei(whistleblower_reward - proposer_reward))
```

當一份可罰沒過錯的回報在區塊處理期間被驗證過後，[提議者罰沒](/part3/transition/block/#proposer-slashings)與[證明者罰沒](/part3/transition/block/#attester-slashings)兩者都會落到這裡。

當一個驗證者被罰沒時，有幾件事立即發生：

  - 該驗證者透過 [`initiate_validator_exit()`](#initiate_validator_exit) 被處理以退出，所以它加入退出佇列。
  - 該驗證者被標記為已被罰沒。這個資訊在計算獎勵與懲罰時被用到：在被退出的期間，無論一個被罰沒的驗證者做什麼，它都會收到「彷彿它未能提議或作證」般的懲罰，包括適用時的怠惰洩漏。
  - 通常，作為退出過程的一部分，一個驗證者的 `withdrawable_epoch`（一個驗證者的質押原則上被解鎖的時點）被設在它退出之後 [`MIN_VALIDATOR_WITHDRAWABILITY_DELAY`](/part3/config/configuration/#min_validator_withdrawability_delay) 個紀元。當一個驗證者被罰沒時，會套用一段長得多的鎖定期，即 [`EPOCHS_PER_SLASHINGS_VECTOR`](/part3/config/preset/#epochs_per_slashings_vector)。這是為了讓「一筆進一步、潛在大得多的罰沒懲罰」能在「鏈得知大約同一時間有多少驗證者一起被罰沒」之後[稍後被套用](/part3/transition/epoch/#slashings)。可提領紀元被推遲的時長，是「套用額外懲罰所需時長」的兩倍——額外懲罰在這段期間的[一半處](/part3/transition/epoch/#slashings)被套用。這純粹意味著被罰沒的驗證者繼續累積證明懲罰，比必要時長多了約 18 天。公平對待被罰沒的驗證者，對協定而言不是什麼大優先事項。
  - 該驗證者的有效餘額被加到「本紀元被罰沒驗證者之累積有效餘額」上，並儲存在環狀串列 `state.slashings` 中。這稍後會被前一點所提到的罰沒懲罰計算所使用。
  - 一筆初始的「打手心」罰沒懲罰被套用，數額為「該驗證者的有效餘額（以 Gwei 計）除以 [`MIN_SLASHING_PENALTY_QUOTIENT_BELLATRIX`](/part3/config/preset/#min_slashing_penalty_quotient)」。對一個有完整 32&nbsp;ETH 有效餘額的驗證者，這筆初始懲罰是 1&nbsp;ETH。
  - 納入該罰沒證明的區塊提議者收到一筆獎勵。

簡言之，一個被罰沒的驗證者收到一筆初始的輕微懲罰，可預期稍後收到一筆進一步的懲罰，並被標記以退出。

請注意，`whistleblower_index` 在參數列中預設為 `None`。這在 Phase&nbsp;0 中從未被使用，結果是納入該罰沒的提議者拿到全部的告密者獎勵；對於提議者或證明者罰沒的發現者，沒有單獨的告密者獎勵。原因之一純粹是回報太容易被偷：如果我把一個可罰沒事件回報給一個區塊提議者，沒有任何東西能阻止那個提議者把該回報宣稱為自己的。我們可以引入某種花俏的 ZK 協定來使這變得無須信任，但目前我們先這樣做。後續的發展，例如[保管證明遊戲](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/_features/custody_game/beacon-chain.md#early-derived-secret-reveals)，可能會直接獎勵告密者。

|||
|-|------|
| 使用&nbsp;者 | [`process_proposer_slashing()`](/part3/transition/block/#def_process_proposer_slashing), [`process_attester_slashing()`](/part3/transition/block/#def_process_attester_slashing) |
| 使用 | [`initiate_validator_exit()`](#def_initiate_validator_exit), [`get_beacon_proposer_index()`](/part3/helper/accessors/#def_get_beacon_proposer_index), [`decrease_balance()`](#def_decrease_balance), [`increase_balance()`](#def_increase_balance) |
| 亦見 | [`EPOCHS_PER_SLASHINGS_VECTOR`](/part3/config/preset/#epochs_per_slashings_vector), [`MIN_SLASHING_PENALTY_QUOTIENT_BELLATRIX`](/part3/config/preset/#min_slashing_penalty_quotient), [`process_slashings()`](/part3/transition/epoch/#def_process_slashings) |

## 信標鏈狀態轉換函式 <!-- /part3/transition/ -->

### 前言

#### 狀態轉換

狀態轉換函式（state transition function）是區塊鏈所做之事的核心。網路上的每個節點維護一個[狀態](/part3/containers/state/#beaconstate)，它對應於該節點對世界狀態的觀點。

傳統上，節點的狀態藉由以「狀態轉換函式」依序套用區塊而更新。狀態轉換函式是「純」的，意思是它的輸出只取決於輸入，而它沒有副作用。這使它具確定性：如果每個節點都以相同的狀態（[創世](/part3/initialise/#initialise-state)狀態）開始，並套用相同序列的區塊，那麼所有節點必定會得出相同的結果狀態。如果它們因為某個原因沒有，那麼我們就有了一個共識失敗。

如果 $S$ 是一個信標狀態，而 $B$ 是一個信標區塊，那麼狀態轉換函式 $f$ 可以寫成

$$
S' \equiv f(S, B)
$$

在這個方程式中，我們把 $S$ 稱為前狀態（pre-state，套用區塊 $B$ 之前的狀態），把 $S'$ 稱為後狀態（post-state）。隨著我們收到新的區塊，函式 $f$ 接著被迭代，以不斷地更新狀態。

那就是區塊鏈進程最純粹形式下的精髓，如同它在工作量證明之下存在的那樣；在工作量證明之下，狀態轉換函式專一地由處理區塊所驅動。

然而，信標鏈不是由區塊驅動的。它是由時段驅動的。對狀態的更新取決於時段的進展，無論那個時段是否有一個區塊與之相關。

因此，信標鏈的狀態轉換函式由三個元素構成。

1. 一個每時段轉換函式 $S' \equiv f_s(S)$。（狀態包含時段號，所以我們不需要提供它。）
2. 一個每區塊轉換函式 $S' \equiv f_b(S, B)$。
3. 一個每紀元轉換函式 $S' \equiv f_e(S)$。

在更新鏈時，這些狀態轉換函式中的每一個都需要在適當的時點被運行，而精確地定義這一切，正是信標鏈規格這個部分的職責。

#### 有效性條件

<a id="assert"></a>

> 對應於一個前狀態 `state` 與一個經簽署區塊 `signed_block` 的後狀態，被定義為 `state_transition(state, signed_block)`。觸發一個未被處理之例外（例如一個失敗的 `assert` 或一次超出範圍的串列存取）的狀態轉換被視為無效。造成 `uint64` 溢位或下溢的狀態轉換也被視為無效。

這是「規格如何處理無效狀況與錯誤」的一個非常重要的陳述。基本上，如果處理任何一個區塊會在規格的 Python 程式碼中觸發任何種類的例外，那麼那個區塊就無效、必須被拒絕。那意味著必須撤銷在處理該區塊過程中已做出的任何狀態修改。

對規格做[形式驗證](https://github.com/ConsenSys/eth2.0-dafny)的人[不太喜歡這一點](https://github.com/ethereum/consensus-specs/issues/1797)，因為在執行中的程式碼裡有 assert 陳述句是一種反模式：確保你的程式碼根本永遠不會失敗，會更好。

#### 規格

無論如何，如上文所討論的，信標鏈狀態轉換有三個元素：

  1. [時段處理](#def_process_slots)，它為每個時段執行，不論還有什麼別的事在發生；
  2. [紀元處理](/part3/transition/epoch/#epoch-processing)，它每 [`SLOTS_PER_EPOCH`](/part3/config/preset/#slots_per_epoch)（32）個時段發生一次，同樣不論還有什麼別的事在發生；以及，
  3. [區塊處理](/part3/transition/block/#block-processing)，它只在「收到了一個信標區塊」的時段中發生。

<a id="def_state_transition"></a>

```python
def state_transition(state: BeaconState, signed_block: SignedBeaconBlock, validate_result: bool=True) -> None:
    block = signed_block.message
    # Process slots (including those with no blocks) since block
    process_slots(state, block.slot)
    # Verify signature
    if validate_result:
        assert verify_block_signature(state, signed_block)
    # Process block
    process_block(state, block)
    # Verify state root
    if validate_result:
        assert block.state_root == hash_tree_root(state)
```

雖然信標鏈的狀態轉換在概念上是由時段驅動的，但依規格的寫法，一次狀態轉換是由「收到一個區塊要處理」所觸發的。那意味著我們首先需要從我們在狀態中的當前時段號（即我們上次處理一個區塊所在的時段），快轉到我們正在處理之區塊的時段。我們把中間的時段（如果有的話）視為空的。這項「快轉」由 [`process_slots()`](#def_process_slots) 完成，它也會在需要時觸發紀元處理。

在實際的客戶端實作中，狀態更新通常會是基於時間的，在「尚未收到一個區塊」時藉由移動到下一個時段而觸發。然而，快轉功能會在探索區塊樹中不同分叉時被使用。

`validate_result` 參數預設為 `True`，意味著區塊的簽章會被檢查，並且「把區塊套用於狀態的結果」會得出「與區塊所宣稱相同的狀態根」（「後狀態」必須相符）。然而，在建立區塊時，提議者可以把 `validate_result` 設為 `False`，以容許狀態根被計算出來，否則我們會有一個循環依賴。涵蓋初始候選區塊的簽章被省略，以避免在一個時段中簽署兩次時與罰沒保護產生不良的交互作用。

|||
|-|------|
| 使用 | [`process_slots()`](#def_process_slots), [`verify_block_signature`](#def_verify_block_signature), [`process_block`](/part3/transition/block/#def_process_block) |

<a id="def_verify_block_signature"></a>

```python
def verify_block_signature(state: BeaconState, signed_block: SignedBeaconBlock) -> bool:
    proposer = state.validators[signed_block.message.proposer_index]
    signing_root = compute_signing_root(signed_block.message, get_domain(state, DOMAIN_BEACON_PROPOSER))
    return bls.Verify(proposer.pubkey, signing_root, signed_block.signature)
```

檢查區塊上的簽章與「區塊的內容」以及「該區塊所宣稱提議者的公鑰」相符。這確保了區塊不能被偽造、或在傳輸途中被竄改。驗證者的所有公鑰都儲存在狀態中的 [`Validator`](/part3/containers/dependencies/#validator) 串列裡。

|||
|-|------|
| 使用&nbsp;者 | [`state_transition()`](#def_state_transition) |
| 使用 | [`compute_signing_root()`](/part3/helper/misc/#def_compute_signing_root), [`get_domain()`](/part3/helper/accessors/#def_get_domain), [`bls.Verify()`](/part3/helper/crypto/#bls-signatures) |
| 亦見 | [`DOMAIN_BEACON_PROPOSER`](/part3/config/constants/#domain-types) |

<a id="def_process_slots"></a>

```python
def process_slots(state: BeaconState, slot: Slot) -> None:
    assert state.slot < slot
    while state.slot < slot:
        process_slot(state)
        # Process epoch on the start slot of the next epoch
        if (state.slot + 1) % SLOTS_PER_EPOCH == 0:
            process_epoch(state)
        state.slot = Slot(state.slot + 1)
```

把狀態從它的當前時段更新到給定的時段號，假定所有中間的時段都是空的（它們不含區塊）。迭代地呼叫 [`process_slot()`](#def_process_slot) 以套用空時段的狀態轉換。

這就是「需要時觸發紀元處理」之處。空時段處理是輕量的，但任何需要被處理的紀元轉換，都需要完整的獎勵與懲罰、以及證成—最終確定的機制。

|||
|-|------|
| 使用&nbsp;者 | [`state_transition()`](#def_state_transition) |
| 使用 | [`process_slot()`](#def_process_slot), [`process_epoch()`](/part3/transition/epoch/#def_process_epoch) |
| 亦見 | [`SLOTS_PER_EPOCH`](/part3/config/preset/#slots_per_epoch) |

<a id="def_process_slot"></a>

```python
def process_slot(state: BeaconState) -> None:
    # Cache state root
    previous_state_root = hash_tree_root(state)
    state.state_roots[state.slot % SLOTS_PER_HISTORICAL_ROOT] = previous_state_root
    # Cache latest block header state root
    if state.latest_block_header.state_root == Bytes32():
        state.latest_block_header.state_root = previous_state_root
    # Cache block root
    previous_block_root = hash_tree_root(state.latest_block_header)
    state.block_roots[state.slot % SLOTS_PER_HISTORICAL_ROOT] = previous_block_root
```

套用單一一個時段的狀態轉換（但更新時段號、以及任何所需的紀元處理，是由 [`process_slots()`](#def_process_slots) 處理的）。這在每個時段都會做，無論是否有一個區塊在場；如果沒有區塊在場，那麼它就是唯一被做的事。

時段處理幾乎是瑣碎的，只包含計算更新後的狀態與區塊雜湊樹根（視需要），並把它們儲存在狀態中的歷史串列裡。以一種循環的方式，狀態根只在空時段狀態轉換中、由於更新狀態根與區塊根的串列而改變。

[`SLOTS_PER_HISTORICAL_ROOT`](/part3/config/preset/#slots_per_historical_root) 是 [`SLOTS_PER_EPOCH`](/part3/config/preset/#slots_per_epoch) 的倍數，所以沒有覆寫 `state_roots` 與 `block_roots` 環狀串列的危險。這些會在紀元處理期間被正確地處理。

這裡唯一的奇特之處是這幾行：

```none
    if state.latest_block_header.state_root == Bytes32():
        state.latest_block_header.state_root = previous_state_root
```

這段邏輯[被引入](https://github.com/ethereum/consensus-specs/pull/711)，以避免一個循環依賴，同時也保持狀態轉換的乾淨。我們收到的每個區塊都包含一個後狀態根，但作為狀態處理的一部分，我們把該區塊儲存在狀態中（在 `state.latest_block_header` 裡），因此改變了後狀態根。

因此，為了能驗證狀態轉換，我們採用一個慣例：「進來之區塊的狀態根」與「我們把區塊插入狀態之後所計算的狀態根」兩者，都基於一個帶有存根狀態根（即 `Bytes32()`）的「暫時」區塊標頭。這讓區塊所宣稱的後狀態根能被驗證，而不帶循環性。下一次 `process_slots()` 被呼叫時，區塊的存根狀態根會被更新為實際的後狀態根，如上文所述。

|||
|-|------|
| 使用&nbsp;者 | [`process_slots()`](#def_process_slots) |
| 使用 | [`hash_tree_root`](/part3/helper/crypto/#hash_tree_root) |
| 亦見 | [`SLOTS_PER_HISTORICAL_ROOT`](/part3/config/preset/#slots_per_historical_root) |

### 執行引擎 <!-- /part3/transition/execution/ -->

以太坊轉向權益證明的「合併」發生於 2022 年 9 月 15 日。就信標鏈而言，最重大的變更是：如今多套用了一個區塊有效性條件。合併之後的信標區塊包含一個新的 [`ExecutionPayload`](/part3/containers/execution/#executionpayload) 物件，它基本上是一個 Eth1 區塊。要讓信標區塊有效，它的執行酬載的內容必須依以太坊長期以來的區塊與交易執行規則（減去任何工作量證明條件）而言是有效的。

信標鏈不知道如何驗證以太坊交易。合併的全部重點，就是讓信標鏈客戶端能把執行酬載的驗證交接給一個在本地連接的執行客戶端（從前的 Eth1 客戶端）。信標鏈共識客戶端透過下方所描述的 `notify_new_payload()` 函式進行這項交接。

在架構上，`notify_new_payload()` 函式透過一個稱為 Engine API 的新介面被存取，[Bellatrix 規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/bellatrix/beacon-chain.md)把它刻劃如下。

> 與實作相關的 `ExecutionEngine` 協定，透過以下各項封裝執行子系統的邏輯：
>
>   - 一個型別為 `ExecutionState` 的狀態物件 `self.execution_state`
>   - 一個通知函式 `self.notify_new_payload`，它可能對 `self.execution_state` 套用變更
>
> _注意_：`notify_new_payload` 是一個透過 `EXECUTION_ENGINE` 模組存取的函式，該模組實例化 `ExecutionEngine` 協定。
>
> 這個函式的主體與實作相關。
> Engine API 可被用來透過一個外部執行引擎，實作這個函式以及類似定義的函式。

[TODO - link to execution API chapter when written]::

#### `notify_new_payload`

<a id="def_notify_new_payload"></a>

```python
def notify_new_payload(self: ExecutionEngine, execution_payload: ExecutionPayload) -> bool:
    """
    Return ``True`` if and only if ``execution_payload`` is valid with respect to ``self.execution_state``.
    """
    ...
```

這個函式在[區塊處理](/part3/transition/block/)期間被呼叫，以驗證一個信標區塊執行酬載的有效性。執行酬載的內容對共識層而言大致上是不透明的（因此函式定義中有 `...`），而執行酬載的驗證幾乎完全仰賴執行客戶端。如果有幫助的話，你可以把它想成只是一次外部的黑箱函式庫呼叫。

|||
|-|------|
| 使用&nbsp;者 | [`process_execution_payload()`](/part3/transition/block/#def_process_execution_payload) |

### 紀元處理 <!-- /part3/transition/epoch/ -->

<a id="def_process_epoch"></a>

```python
def process_epoch(state: BeaconState) -> None:
    process_justification_and_finalization(state)  # [Modified in Altair]
    process_inactivity_updates(state)  # [New in Altair]
    process_rewards_and_penalties(state)  # [Modified in Altair]
    process_registry_updates(state)
    process_slashings(state)  # [Modified in Altair]
    process_eth1_data_reset(state)
    process_effective_balance_updates(state)
    process_slashings_reset(state)
    process_randao_mixes_reset(state)
    process_historical_summaries_update(state)  # [Modified in Capella]
    process_participation_flag_updates(state)  # [New in Altair]
    process_sync_committee_updates(state)  # [New in Altair]
```

在一個紀元結束時需要做的事情，那長長的一張清單。你可以從註解看出，Altair 升級加入了一堆額外的工作。

|||
|-|------|
| 使用&nbsp;者 | [`process_slots()`](/part3/transition/#def_process_slots) |
| 使用 | 下面的所有東西 |

#### 證成與最終確定

<a id="def_process_justification_and_finalization"></a>

```python
def process_justification_and_finalization(state: BeaconState) -> None:
    # Initial FFG checkpoint values have a `0x00` stub for `root`.
    # Skip FFG updates in the first two epochs to avoid corner cases that might result in modifying this stub.
    if get_current_epoch(state) <= GENESIS_EPOCH + 1:
        return
    previous_indices = get_unslashed_participating_indices(state, TIMELY_TARGET_FLAG_INDEX, get_previous_epoch(state))
    current_indices = get_unslashed_participating_indices(state, TIMELY_TARGET_FLAG_INDEX, get_current_epoch(state))
    total_active_balance = get_total_active_balance(state)
    previous_target_balance = get_total_balance(state, previous_indices)
    current_target_balance = get_total_balance(state, current_indices)
    weigh_justification_and_finalization(state, total_active_balance, previous_target_balance, current_target_balance)
```

我相信註解中所提到的角落案例，與 [Issue 849](https://github.com/ethereum/consensus-specs/issues/849) 有關[^fn-ugly-integers]。無論如何，在前兩個紀元期間跳過證成與最終確定的計算，確實簡化了事情。

[^fn-ugly-integers]: 值得一訪，哪怕只是為了對 Jacek 把 `uint` 描述為「醜陋的整數」會心一笑。

為了 Casper FFG 最終性計算的目的，我們想要「來源投票與目標投票兩者我們都同意」的證明。如果來源投票不正確，那麼這筆證明就絕不會被處理進狀態，所以我們只需要「依其[參與旗標索引](/part3/config/constants/#participation-flag-indices)而為正確目標投票」的驗證者。

由於正確的目標投票在被做出後最晚 32 個時段內都能被納入，我們從先前紀元與當前紀元兩者收集投票，以確保我們把它們全部收齊了。

一旦我們知道哪些驗證者在當前與先前紀元為正確的來源與鏈頭投票，我們就把它們的有效餘額（不是實際餘額）加起來。`total_active_balance` 是「所有本應在當前紀元期間投票之驗證者」的有效餘額總和。已被罰沒、但未退出的驗證者不被納入這些計算。

這些聚合餘額被傳給 [`weigh_justification_and_finalization()`](#def_weigh_justification_and_finalization)，以做「更新證成與最終確定」的實際工作。

|||
|-|------|
| 使用&nbsp;者 | [`process_epoch()`](#def_process_epoch), [`compute_pulled_up_tip`](/part3/forkchoice/phase0/#compute_pulled_up_tip) |
| 使用 | [`get_unslashed_participating_indices()`](/part3/helper/accessors/#def_get_unslashed_participating_indices), [`get_total_active_balance()`](/part3/helper/accessors/#def_get_total_active_balance), [`get_total_balance()`](/part3/helper/accessors/#def_get_total_balance), [`weigh_justification_and_finalization()`](#def_weigh_justification_and_finalization) |
| 亦見 | [participation flag indices](/part3/config/constants/#participation-flag-indices) |

<a id="def_weigh_justification_and_finalization"></a>

```python
def weigh_justification_and_finalization(state: BeaconState,
                                         total_active_balance: Gwei,
                                         previous_epoch_target_balance: Gwei,
                                         current_epoch_target_balance: Gwei) -> None:
    previous_epoch = get_previous_epoch(state)
    current_epoch = get_current_epoch(state)
    old_previous_justified_checkpoint = state.previous_justified_checkpoint
    old_current_justified_checkpoint = state.current_justified_checkpoint

    # Process justifications
    state.previous_justified_checkpoint = state.current_justified_checkpoint
    state.justification_bits[1:] = state.justification_bits[:JUSTIFICATION_BITS_LENGTH - 1]
    state.justification_bits[0] = 0b0
    if previous_epoch_target_balance * 3 >= total_active_balance * 2:
        state.current_justified_checkpoint = Checkpoint(epoch=previous_epoch,
                                                        root=get_block_root(state, previous_epoch))
        state.justification_bits[1] = 0b1
    if current_epoch_target_balance * 3 >= total_active_balance * 2:
        state.current_justified_checkpoint = Checkpoint(epoch=current_epoch,
                                                        root=get_block_root(state, current_epoch))
        state.justification_bits[0] = 0b1

    # Process finalizations
    bits = state.justification_bits
    # The 2nd/3rd/4th most recent epochs are justified, the 2nd using the 4th as source
    if all(bits[1:4]) and old_previous_justified_checkpoint.epoch + 3 == current_epoch:
        state.finalized_checkpoint = old_previous_justified_checkpoint
    # The 2nd/3rd most recent epochs are justified, the 2nd using the 3rd as source
    if all(bits[1:3]) and old_previous_justified_checkpoint.epoch + 2 == current_epoch:
        state.finalized_checkpoint = old_previous_justified_checkpoint
    # The 1st/2nd/3rd most recent epochs are justified, the 1st using the 3rd as source
    if all(bits[0:3]) and old_current_justified_checkpoint.epoch + 2 == current_epoch:
        state.finalized_checkpoint = old_current_justified_checkpoint
    # The 1st/2nd most recent epochs are justified, the 1st using the 2nd as source
    if all(bits[0:2]) and old_current_justified_checkpoint.epoch + 1 == current_epoch:
        state.finalized_checkpoint = old_current_justified_checkpoint
```

這個常式先處理證成，然後處理最終確定。

##### 證成

超多數連結（supermajority link）是一個「帶有已證成來源檢查點 $C_m$ 與目標檢查點 $C_n$」的投票，由控制超過三分之二質押的驗證者所做出。如果一個檢查點有一個指向它的超多數連結，那麼我們就認為它已被證成。所以，如果超過三分之二的驗證者同意「檢查點 3 已被證成」（它們的來源投票），並以檢查點 4 作為它們的目標投票，那麼我們就證成檢查點 4。

我們知道所有證明都有「我們同意的來源投票」。第一個 `if` 陳述句試圖證成前一個紀元的檢查點，看看（來源, 目標）這一對是否為一個超多數。第二個 `if` 陳述句試圖證成當前紀元的檢查點。請注意，前一個紀元的檢查點可能已經被證成過了；這一點不會被檢查，但不影響邏輯。

最近四個紀元的證成狀態，儲存在狀態中的一個位元陣列裡。在常式開頭把這些位元往前移一位之後，當前紀元的證成狀態儲存在元素 0，前一個儲存在元素 1，依此類推。

請注意，`total_active_balance` 是當前紀元的總餘額，所以對於計算前一個紀元的超多數而言，它可能不是嚴格正確的。然而，驗證者集合在各紀元之間能改變的速率受到[嚴格約束](/part3/config/configuration/#min_per_epoch_churn_limit)，所以這不是一個顯著的問題。

##### 最終確定

[Gasper 論文](https://arxiv.org/abs/2003.03052)所描述的 Casper FFG 版本，使用 $k$-最終性，它擴展了[原本的 Casper FFG 論文](https://arxiv.org/abs/1710.09437)對最終性的處理。關於它如何與 Casper FFG 的安全性保證互動，更多內容見「共識」那一章的 [k-最終性那一節](/part2/consensus/casper_ffg/#k-finality)。

在 $k$-最終性中，如果我們有一組連續的 $k$ 個已證成檢查點 ${C_j, \ldots, C_{j+k-1}}$，以及一個從 $C_j$ 到 $C_{j+k}$ 的超多數連結，那麼 $C_j$ 就被最終確定。也請注意，依上述規則，這會證成 $C_{j+k}$。

這在 Casper FFG 中的版本是 $1$-最終性。所以，一個從已證成檢查點 $C_n$ 到緊接的下一個檢查點 $C_{n+1}$ 的超多數連結，既證成 $C_{n+1}$，也最終確定 $C_n$。

在信標鏈上我們使用 $2$-最終性，因為目標投票最晚可能延遲一個紀元才被納入。在 $2$-最終性中，我們保留四個紀元的檢查點證成狀態紀錄，並有以下的最終確定條件，其中當前紀元的檢查點是 $C_n$。請注意，我們在這個常式中已經更新了 $C_n$ 與 $C_{n-1}$ 的證成狀態，這意味著：如果對應的位元分別被設定了，就存在指向它們的超多數連結。

 1. 檢查點 $C_{n-3}$ 與 $C_{n-2}$ 已被證成，且有一個從 $C_{n-3}$ 到 $C_{n-1}$ 的超多數連結：最終確定 $C_{n-3}$。
 2. 檢查點 $C_{n-2}$ 已被證成，且有一個從 $C_{n-2}$ 到 $C_{n-1}$ 的超多數連結：最終確定 $C_{n-2}$。這等同於把 $1$-最終性套用於前一個紀元。
 3. 檢查點 $C_{n-2}$ 與 $C_{n-1}$ 已被證成，且有一個從 $C_{n-2}$ 到 $C_n$ 的超多數連結：最終確定 $C_{n-2}$。
 4. 檢查點 $C_{n-1}$ 已被證成，且有一個從 $C_{n-1}$ 到 $C_n$ 的超多數連結：最終確定 $C_{n-1}$。這等同於把 $1$-最終性套用於當前紀元。

<a id="img_consensus_2_finality"></a>
<figure class="diagram" style="width: 65%">

![A diagram of the four 2-finality scenarios.](images/diagrams/consensus-2-finality.svg)

<figcaption>

2-最終性的四種情況。在每種情況中，超多數連結使其起點處的檢查點（來源）變為已最終確定，使其終點處的檢查點（目標）變為已證成。檢查點編號標在底部。

</figcaption>
</figure>

幾乎總是，我們會預期只見到 $1$-最終性的情況，尤其是情況 4。$2$-最終性的情況只會在「許多證明被延遲」、或「我們非常接近 2/3 參與門檻」的情形下發生。請注意，這些評估會疊加，所以舉例來說，規則 2 有可能最終確定 $C_{n-2}$，然後規則 4 立即最終確定 $C_{n-1}$。

對不熟悉的人說明：在 Python 的陣列切片語法中，`bits[1:4]` 指的是位元 1、2、3（但不含 4）。這個我老是搞錯。

|||
|-|------|
| 使用&nbsp;者 | [`process_justification_and_finalization()`](#def_process_justification_and_finalization) |
| 使用 | [`get_block_root()`](/part3/helper/accessors/#def_get_block_root) |
| 亦見 | [`JUSTIFICATION_BITS_LENGTH`](/part3/config/constants/#justification_bits_length)、[`Checkpoint`](/part3/containers/dependencies/#checkpoint) |

#### 怠惰分數

<a id="def_process_inactivity_updates"></a>

```python
def process_inactivity_updates(state: BeaconState) -> None:
    # Skip the genesis epoch as score updates are based on the previous epoch participation
    if get_current_epoch(state) == GENESIS_EPOCH:
        return

    for index in get_eligible_validator_indices(state):
        # Increase the inactivity score of inactive validators
        if index in get_unslashed_participating_indices(state, TIMELY_TARGET_FLAG_INDEX, get_previous_epoch(state)):
            state.inactivity_scores[index] -= min(1, state.inactivity_scores[index])
        else:
            state.inactivity_scores[index] += INACTIVITY_SCORE_BIAS
        # Decrease the inactivity score of all eligible validators during a leak-free epoch
        if not is_in_inactivity_leak(state):
            state.inactivity_scores[index] -= min(INACTIVITY_SCORE_RECOVERY_RATE, state.inactivity_scores[index])
```

自 Altair 升級以來，每個驗證者在信標狀態中都有一個各自的怠惰分數，它依如下方式更新。

  - 在紀元 $N$ 結束時，不論是否處於怠惰洩漏，
    - 當該驗證者在紀元 $N-1$ 期間做出了一個正確且[及時的目標投票](/part3/config/constants/#participation-flag-indices)時，把分數減一，
    - 否則把分數加上 [`INACTIVITY_SCORE_BIAS`](/part3/config/configuration/#inactivity_score_bias)。請注意，[`get_eligible_validator_indices()`](#def_get_eligible_validator_indices) 包含「已被罰沒但尚未可提領」的驗證者：被罰沒的驗證者被當成不參與來對待，無論它們實際上做了什麼。
  - 當「不」處於怠惰洩漏時
    - 把所有驗證者的分數減去 [`INACTIVITY_SCORE_RECOVERY_RATE`](/part3/config/configuration/#inactivity_score_recovery_rate)。

<a id="img_incentives_inactivity_scores_flow"></a>
<figure class="diagram">

![Flowchart showing how inactivity score updates are calculated.](images/diagrams/incentives-inactivity_scores_flow.svg)

<figcaption>

每個驗證者的怠惰分數如何被更新。順利的流程正好從中間貫穿。在紀元 $N$ 結束時更新分數時，「Active（活躍）」意指在紀元 $N-1$ 做出了一個正確且及時的目標投票。

</figcaption>
</figure>

分數有一個零的下限。所以，在洩漏之外，驗證者的分數會迅速回到零並停留在那裡，因為 `INACTIVITY_SCORE_RECOVERY_RATE` 大於 `INACTIVITY_SCORE_BIAS`。

|||
|-|------|
| 使用&nbsp;者 | [`process_epoch()`](#def_process_epoch) |
| 使用 | [`get_eligible_validator_indices()`](#def_get_eligible_validator_indices)、[`get_unslashed_participating_indices()`](/part3/helper/accessors/#get_unslashed_participating_indices)、[`is_in_inactivity_leak()`](/part3/transition/epoch/#def_is_in_inactivity_leak) |
| 亦見 | [`INACTIVITY_SCORE_BIAS`](/part3/config/configuration/#inactivity_score_bias)、[`INACTIVITY_SCORE_RECOVERY_RATE`](/part3/config/configuration/#inactivity_score_recovery_rate) |

#### 獎勵與懲罰計算

我不想對你來一整套[黃皮書](https://ethereum.github.io/yellowpaper/paper.pdf)那樣的論述，但我會採用一點符號，以幫助分析獎勵。

我們會定義一個基礎獎勵 $B$，我們將會看到它結果是「一個表現最佳的驗證者每個紀元的長期預期平均收入」（忽略驗證者集合大小的變化）。活躍驗證者的總數是 $N$。

基礎獎勵是從一個[每增量基礎獎勵](#def_get_base_reward_per_increment) $b$ 計算出來的。一個「增量」（increment）是以 [`EFFECTIVE_BALANCE_INCREMENT`](/part3/config/preset/#effective_balance_increment) 為單位的一單位有效餘額。$B = 32b$，因為 [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance) = `32` ` * ` `EFFECTIVE_BALANCE_INCREMENT`。

我們在獎勵計算中會用到的其他量，是[激勵權重](/part3/config/constants/#incentivization-weights)：$W_s$、$W_t$、$W_h$ 與 $W_y$ 分別是正確來源、目標、鏈頭與同步委員會投票的權重；$W_p$ 是提議者權重；而權重分母 $W_{\Sigma}$ 是各權重的總和。

常規獎勵的發行以四種方式發生：

  - $I_A$ 是「一個紀元中所有作證驗證者」的最大總獎勵；
  - $I_{A_P}$ 是「一個紀元中發給提議者、用於納入證明」的最大獎勵；
  - $I_S$ 是「一個紀元中所有同步委員會參與者」的最大總獎勵；以及
  - $I_{S_P}$ 是「一個紀元中發給提議者、用於納入同步聚合」的最大獎勵；

在 [`get_flag_index_deltas()`](/part3/helper/accessors/#def_get_flag_index_deltas)、[`process_attestation()`](/part3/transition/block/#def_process_attestation) 與 [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate) 之下，我們發現這些以 $B$ 與 $N$ 表示的結果如下：

$$
\begin{aligned}
&I_A = \frac{W_s + W_t + W_h}{W_{\Sigma}}NB \\
&I_{A_P} = \frac{W_p}{W_{\Sigma} - W_p}I_A \\
&I_S = \frac{W_y}{W_{\Sigma}}NB \\
&I_{S_P} = \frac{W_p}{W_{\Sigma} - W_p}I_S
\end{aligned}
$$

要找出每個紀元的最佳總發行量，我們可以先把 $I_A$ 與 $I_S$ 相加，

$$
I_A + I_S = \frac{W_s + W_t + W_h + W_y}{W_{\Sigma}}NB = \frac{W_{\Sigma} - W_p}{W_{\Sigma}}NB
$$

現在把提議者獎勵加進來，

$$
I_A + I_S + I_{A_P} + I_{S_P} = \frac{W_{\Sigma} - W_p}{W_{\Sigma}}(1 + \frac{W_p}{W_{\Sigma} - W_p})NB = (\frac{W_{\Sigma} - W_p}{W_{\Sigma}} + \frac{W_p}{W_{\Sigma}})NB = NB
$$

所以，我們看到每個紀元都有 $NB$ Gwei 被頒發給 $N$ 個驗證者。每個驗證者都參與作證，而提議與同步委員會職責是均勻隨機的，所以「每個表現最佳的驗證者每個紀元」的長期預期收入是 $B$ Gwei。

##### 輔助函式

<a id="def_get_base_reward_per_increment"></a>

```python
def get_base_reward_per_increment(state: BeaconState) -> Gwei:
    return Gwei(EFFECTIVE_BALANCE_INCREMENT * BASE_REWARD_FACTOR // integer_squareroot(get_total_active_balance(state)))
```

每增量基礎獎勵是獎勵的基本單位，所有其他常規獎勵與懲罰都以它為基準來計算。我們把每增量基礎獎勵記為 $b$。

如我在 [`BASE_REWARD_FACTOR`](/part3/config/preset/#base_reward_factor) 之下所指出的，如果我們希望增加或減少「參與 Eth2 的總獎勵」（亦稱為新以太幣的發行率），這就是要轉的那個大旋鈕。

一個增量是一個驗證者有效餘額的單一一個單位，以 [`EFFECTIVE_BALANCE_INCREMENT`](/part3/config/preset/#effective_balance_increment) 為計值單位，而後者恰好是一以太幣。所以，一個增量是 1 以太幣的有效餘額，而一個有效性最大的驗證者有 32 個增量。

每增量基礎獎勵與「所有活躍驗證者總餘額的平方根」成反比。這意味著，隨著驗證者數目 $N$ 增加，每驗證者的獎勵以 $\frac{1}{\sqrt{N}}$ 遞減，而每紀元的整體發行量以 $\sqrt{N}$ 遞增。

每驗證者獎勵隨 $N$ 增加而遞減，提供了一個價格發現機制：其構想是，會找到一個均衡點，在那裡「驗證者的總數所造成的獎勵」與「別處在相似風險下可得的報酬」相似。獎勵曲線本可選擇一條不同的曲線。舉例來說，採用總餘額的倒數而非其平方根，會讓總發行量維持恆定。[發行那一節](/part2/incentives/issuance/)對這些主題有更深入的探討。

|||
|-|------|
| 使用&nbsp;者 | [`get_base_reward()`](#def_get_base_reward), [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate) |
| 使用 | [`integer_squareroot()`](/part3/helper/math/#def_integer_squareroot), [`get_total_active_balance()`](/part3/helper/accessors/#def_get_total_active_balance) |

<a id="def_get_base_reward"></a>

```python
def get_base_reward(state: BeaconState, index: ValidatorIndex) -> Gwei:
    """
    Return the base reward for the validator defined by ``index`` with respect to the current ``state``.
    """
    increments = state.validators[index].effective_balance // EFFECTIVE_BALANCE_INCREMENT
    return Gwei(increments * get_base_reward_per_increment(state))
```

基礎獎勵是「一個表現最佳的驗證者，長期下來每個紀元平均可預期賺取」的獎勵。它與該驗證者的有效餘額成比例；一個有 [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance) 的驗證者，可預期長期平均每個紀元收到完整的基礎獎勵 $B = 32b$。

|||
|-|------|
| 使用&nbsp;者 | [`get_flag_index_deltas()`](/part3/helper/accessors/#def_get_flag_index_deltas), [`process_attestation()`](/part3/transition/block/#def_process_attestation) |
| 使用 | [`get_base_reward_per_increment()`](#def_get_base_reward_per_increment) |
| 亦見 | [`EFFECTIVE_BALANCE_INCREMENT`](/part3/config/preset/#effective_balance_increment) |

<a id="def_get_finality_delay"></a>

```python
def get_finality_delay(state: BeaconState) -> uint64:
    return get_previous_epoch(state) - state.finalized_checkpoint.epoch
```

回傳自上一個已最終確定檢查點以來的紀元數（再減一）。在理想的運行中這應該是零：在紀元處理期間，我們的目標是已證成當前紀元的檢查點、並已最終確定前一個紀元的檢查點。最終確定的延遲，暗示著一次鏈分裂、或一大部分驗證者離線。

|||
|-|------|
| 使用&nbsp;者 | [`is_in_inactivity_leak()`](#def_is_in_inactivity_leak) |

<a id="def_is_in_inactivity_leak"></a>

```python
def is_in_inactivity_leak(state: BeaconState) -> bool:
    return get_finality_delay(state) > MIN_EPOCHS_TO_INACTIVITY_PENALTY
```

如果信標鏈有 [`MIN_EPOCHS_TO_INACTIVITY_PENALTY`](/part3/config/preset/#min_epochs_to_inactivity_penalty) 個紀元（也就是四個紀元）未能最終確定一個檢查點，那麼這條鏈就進入[怠惰洩漏](/part3/config/preset/#inactivity_penalty_quotient)。在這個模式中，不參與的懲罰被大幅增加，目標是減少「不參與者所掌控之質押」的比例，並最終重新取得最終性。

|||
|-|------|
| 使用&nbsp;者 | [`get_flag_index_deltas()`](/part3/helper/accessors/#get_flag_index_deltas), [`process_inactivity_updates()`](#def_process_inactivity_updates) |
| 使用 | [`get_finality_delay()`](#def_get_finality_delay) |
| 亦見 | [inactivity leak](/part3/config/preset/#inactivity_penalty_quotient), [`MIN_EPOCHS_TO_INACTIVITY_PENALTY`](/part3/config/preset/#min_epochs_to_inactivity_penalty) |

<a id="def_get_eligible_validator_indices"></a>

```python
def get_eligible_validator_indices(state: BeaconState) -> Sequence[ValidatorIndex]:
    previous_epoch = get_previous_epoch(state)
    return [
        ValidatorIndex(index) for index, v in enumerate(state.validators)
        if is_active_validator(v, previous_epoch) or (v.slashed and previous_epoch + 1 < v.withdrawable_epoch)
    ]
```

這些是在前一個紀元中受到獎勵與懲罰的驗證者。

這個串列與 [`get_active_validator_indices()`](/part3/helper/accessors/#def_get_active_validator_indices) 回傳的活躍驗證者集合不同之處在於：除了被標記為活躍的驗證者之外，它還包含「已被罰沒但尚未完全退出」的驗證者。被罰沒的驗證者一直到它們變為可提領、因而完全退出為止，都會受到懲罰。

|||
|-|------|
| 使用&nbsp;者 | [`get_flag_index_deltas()`](/part3/helper/accessors/#def_get_flag_index_deltas)、[`process_inactivity_updates()`](#def_process_inactivity_updates)、[`get_inactivity_penalty_deltas()`](#def_get_inactivity_penalty_deltas) |
| 使用 | [`is_active_validator()`](/part3/helper/predicates/#def_is_active_validator) |

##### 怠惰懲罰增減量

<a id="def_get_inactivity_penalty_deltas"></a>

```python
def get_inactivity_penalty_deltas(state: BeaconState) -> Tuple[Sequence[Gwei], Sequence[Gwei]]:
    """
    Return the inactivity penalty deltas by considering timely target participation flags and inactivity scores.
    """
    rewards = [Gwei(0) for _ in range(len(state.validators))]
    penalties = [Gwei(0) for _ in range(len(state.validators))]
    previous_epoch = get_previous_epoch(state)
    matching_target_indices = get_unslashed_participating_indices(state, TIMELY_TARGET_FLAG_INDEX, previous_epoch)
    for index in get_eligible_validator_indices(state):
        if index not in matching_target_indices:
            penalty_numerator = state.validators[index].effective_balance * state.inactivity_scores[index]
            penalty_denominator = INACTIVITY_SCORE_BIAS * INACTIVITY_PENALTY_QUOTIENT_BELLATRIX
            penalties[index] += Gwei(penalty_numerator // penalty_denominator)
    return rewards, penalties
```

驗證者收到的懲罰與它們各自的怠惰分數成比例，即使信標鏈並未處於[怠惰洩漏](/part3/transition/epoch/#def_is_in_inactivity_leak)。然而，這些分數在洩漏之外會相當迅速地減到零。這與 Phase&nbsp;0 不同——在 Phase&nbsp;0 中怠惰懲罰只在洩漏期間被套用。

所有「在前一個紀元做出了正確且及時[目標投票](/part3/config/constants/#participation-flag-indices)」的未被罰沒驗證者，都由 [`get_unslashed_participating_indices()`](/part3/helper/accessors/#get_unslashed_participating_indices) 識別出來，而所有其他活躍驗證者收到一筆懲罰，包括被罰沒的驗證者。

懲罰與該驗證者的有效餘額及其怠惰分數成比例。計算的更多細節見 [`INACTIVITY_PENALTY_QUOTIENT_BELLATRIX`](/part3/config/preset/#inactivity_penalty_quotient)，懲罰如何累積的一些圖表見 [`INACTIVITY_SCORE_RECOVERY_RATE`](/part3/config/configuration/#inactivity_score_recovery_rate)。

回傳的 `rewards` 陣列始終只含零。它在這裡只是為了讓呼叫端常式的 Python 語法更簡單。

|||
|-|------|
| 使用&nbsp;者 | [`process_rewards_and_penalties()`](#def_process_rewards_and_penalties) |
| 使用 | [`get_unslashed_participating_indices()`](/part3/helper/accessors/#get_unslashed_participating_indices), [`get_eligible_validator_indices()`](/part3/transition/epoch/#def_get_eligible_validator_indices) |
| 亦見 | [Inactivity Scores](#inactivity-scores), [`INACTIVITY_PENALTY_QUOTIENT_BELLATRIX`](/part3/config/preset/#inactivity_penalty_quotient), [`INACTIVITY_SCORE_RECOVERY_RATE`](/part3/config/configuration/#inactivity_score_recovery_rate) |

##### 處理獎勵與懲罰

<a id="def_process_rewards_and_penalties"></a>

```python
def process_rewards_and_penalties(state: BeaconState) -> None:
    # No rewards are applied at the end of `GENESIS_EPOCH` because rewards are for work done in the previous epoch
    if get_current_epoch(state) == GENESIS_EPOCH:
        return

    flag_deltas = [get_flag_index_deltas(state, flag_index) for flag_index in range(len(PARTICIPATION_FLAG_WEIGHTS))]
    deltas = flag_deltas + [get_inactivity_penalty_deltas(state)]
    for (rewards, penalties) in deltas:
        for index in range(len(state.validators)):
            increase_balance(state, ValidatorIndex(index), rewards[index])
            decrease_balance(state, ValidatorIndex(index), penalties[index])
```

這就是「驗證者依其證明紀錄而被獎勵與懲罰」之處。

納入信標區塊的證明，在區塊被收到時由 [`process_attestation`](/part3/transition/block/#def_process_attestation) 處理，並依其及時性與正確性在信標狀態中設定[旗標](/part3/config/types/#participationflags)。這些旗標現在藉由為每一種[旗標型別](/part3/config/constants/#participation-flag-indices)各呼叫一次 [`get_flag_index_deltas()`](/part3/helper/accessors/#def_get_flag_index_deltas)，而被處理成每個驗證者的獎勵與懲罰。

一旦正常的證明獎勵與懲罰被計算出來，基於驗證者怠惰分數的[額外懲罰](#def_get_inactivity_penalty_deltas)就被累加。

如別處所指出的，獎勵與懲罰彼此分開處理，因為我們不處理負數。

供參考，唯二其他套用獎勵與懲罰的地方如下：

  - 在區塊處理期間：用於[同步委員會參與](/part3/transition/block/#def_process_sync_aggregate)、套用[提議者獎勵](/part3/transition/block/#def_process_attestation)時、以及套用初始[罰沒獎勵與懲罰](/part3/helper/mutators/#def_slash_validator)時。
  - 在紀元處理期間：套用[擴展罰沒懲罰](/part3/transition/epoch/#def_process_slashings)時。

|||
|-|------|
| 使用&nbsp;者 | [`process_epoch()`](#def_process_epoch) |
| 使用 | [`get_flag_index_deltas()`](/part3/helper/accessors/#def_get_flag_index_deltas), [`get_inactivity_penalty_deltas()`](#def_get_inactivity_penalty_deltas), [`increase_balance()`](/part3/helper/mutators/#def_increase_balance), [`decrease_balance()`](/part3/helper/mutators/#def_decrease_balance) |
| 亦見 | [`ParticipationFlags`](/part3/config/types/#participationflags), [`PARTICIPATION_FLAG_WEIGHTS`](/part3/config/constants/#participation_flag_weights) |

#### 註冊表更新

<a id="def_process_registry_updates"></a>

```python
def process_registry_updates(state: BeaconState) -> None:
    # Process activation eligibility and ejections
    for index, validator in enumerate(state.validators):
        if is_eligible_for_activation_queue(validator):
            validator.activation_eligibility_epoch = get_current_epoch(state) + 1

        if (
            is_active_validator(validator, get_current_epoch(state))
            and validator.effective_balance <= EJECTION_BALANCE
        ):
            initiate_validator_exit(state, ValidatorIndex(index))

    # Queue validators eligible for activation and not yet dequeued for activation
    activation_queue = sorted([
        index for index, validator in enumerate(state.validators)
        if is_eligible_for_activation(state, validator)
        # Order by the sequence of activation_eligibility_epoch setting and then index
    ], key=lambda index: (state.validators[index].activation_eligibility_epoch, index))
    # Dequeued validators for activation up to churn limit
    for index in activation_queue[:get_validator_churn_limit(state)]:
        validator = state.validators[index]
        validator.activation_epoch = compute_activation_exit_epoch(get_current_epoch(state))
```

[`Registry`](/part3/containers/state/#registry)（註冊表）是信標狀態中儲存 [`Validator`](/part3/containers/dependencies/#validator) 紀錄的部分。這些特定的更新，大體上關乎讓驗證者通過啟用佇列。

[`is_eligible_for_activation_queue()`](/part3/helper/predicates/#def_is_eligible_for_activation_queue) 找出「有足夠存款數額、但其 `activation_eligibility_epoch` 仍被設為 [`FAR_FUTURE_EPOCH`](/part3/config/constants/#far_future_epoch)」的驗證者。這些至多是「上一個紀元期間處理了其存款」的驗證者，潛在地多達 `MAX_DEPOSITS * SLOTS_PER_EPOCH`，即 512（減去任何尚未累積成一整筆完整存款的部分存款）。這些驗證者的 `activation_eligibility_epoch` 被設為下一個紀元。一旦那個紀元被最終確定，它們就變為符合啟用資格——「符合啟用資格」只意味著它們能被加入啟用佇列；它們要到抵達佇列末端時才會變為啟用。

接著，任何「有效餘額已跌到 [`EJECTION_BALANCE`](/part3/config/configuration/#ejection_balance)」的驗證者，它們的退出被發起。

[`is_eligible_for_activation()`](/part3/helper/predicates/#is_eligible_for_activation) 選出「其 `activation_eligibility_epoch` 剛被最終確定」的驗證者。這些驗證者的串列依資格紀元、然後依索引排序。如果最終確定因為某個原因被延遲，串列中可能會有多個資格紀元。

最後，串列中最前面的 [`get_validator_churn_limit()`](/part3/helper/accessors/#def_get_validator_churn_limit) 個驗證者，它們的啟用紀元被設為 [`compute_activation_exit_epoch()`](/part3/helper/misc/#def_compute_activation_exit_epoch)。

乍看之下，你會以為這裡可以設定整個佇列的啟用紀元，而不只是單一一個紀元份。但在某個時點，`get_validator_churn_limit()` 會以無法預測的方式改變（我們不知道驗證者何時會退出），這使得那樣做不可行。不過，奇怪的是，那正是 [`initiate_validator_exit()`](/part3/helper/mutators/#def_initiate_validator_exit) 所做的。無論如何，客戶端可以藉由持久保存已排序的啟用佇列、而非重新計算它，來最佳化這一點。

|||
|-|------|
| 使用&nbsp;者 | [`process_epoch()`](#def_process_epoch) |
| 使用 | [`is_eligible_for_activation_queue()`](/part3/helper/predicates/#def_is_eligible_for_activation_queue), [`is_active_validator()`](/part3/helper/predicates/#def_is_active_validator), [`initiate_validator_exit()`](/part3/helper/mutators/#initiate_validator_exit), [`is_eligible_for_activation()`](/part3/helper/predicates/#def_is_eligible_for_activation), [`get_validator_churn_limit()`](/part3/helper/accessors/#def_get_validator_churn_limit), [`compute_activation_exit_epoch()`](/part3/helper/misc/#def_compute_activation_exit_epoch) |
| 亦見 | [`Validator`](/part3/containers/dependencies/#validator), [`EJECTION_BALANCE`](/part3/config/configuration/#ejection_balance) |

#### 罰沒

<a id="def_process_slashings"></a>

```python
def process_slashings(state: BeaconState) -> None:
    epoch = get_current_epoch(state)
    total_balance = get_total_active_balance(state)
    adjusted_total_slashing_balance = min(
        sum(state.slashings) * PROPORTIONAL_SLASHING_MULTIPLIER_BELLATRIX,
        total_balance
    )
    for index, validator in enumerate(state.validators):
        if validator.slashed and epoch + EPOCHS_PER_SLASHINGS_VECTOR // 2 == validator.withdrawable_epoch:
            increment = EFFECTIVE_BALANCE_INCREMENT  # Factored out from penalty numerator to avoid uint64 overflow
            penalty_numerator = validator.effective_balance // increment * adjusted_total_slashing_balance
            penalty = penalty_numerator // total_balance * increment
            decrease_balance(state, ValidatorIndex(index), penalty)
```

罰沒懲罰分兩個階段套用：第一個階段在 [`slash_validator()`](/part3/helper/mutators/#def_slash_validator) 中，於偵測到時立即進行；第二個階段在這裡。

在 `slash_validator()` 中，可提領紀元被設在未來 [`EPOCHS_PER_SLASHINGS_VECTOR`](/part3/config/preset/#epochs_per_slashings_vector) 處，所以在這個函式中，我們考量的是所有「離可提領已走到一半」（也就是已完全退出協定一半）的被罰沒驗證者。等價地說，它們是在 `EPOCHS_PER_SLASHINGS_VECTOR` ` // ` `2` 個紀元前（約 18 天前）被罰沒的。

要計算額外的罰沒懲罰，我們做以下事情：

 1. 找出「在前 `EPOCHS_PER_SLASHINGS_VECTOR` 個紀元（36 天）內被罰沒之所有驗證者」的有效餘額總和（在罰沒當時的有效餘額）。這些被以一個向量儲存在狀態中。
 2. 把這個總和乘以 [`PROPORTIONAL_SLASHING_MULTIPLIER_BELLATRIX`](/part3/config/preset/#proportional_slashing_multiplier)，但把結果上限設為 `total_balance`，即所有驗證者的總活躍餘額。
 3. 對於每個被考量的被罰沒驗證者，把它的有效餘額乘以第 2 步的結果，然後除以 `total_balance`。這得出一個介於零與「該驗證者完整有效餘額」之間的數額。那個數額作為懲罰從它的實際餘額中被扣除。請注意，在奇特的角落案例中有效餘額可能超出實際餘額，但 [`decrease_balance()`](/part3/helper/mutators/#def_decrease_balance) 確保餘額不會變為負。

如果在那 36 天內只有單一一個驗證者被罰沒，那麼這筆次級懲罰是微小的（實際上是零，見下文）。如果三分之一的驗證者被罰沒（最終確定相衝突區塊所需的最小數量），那麼，在 `PROPORTIONAL_SLASHING_MULTIPLIER_BELLATRIX` 設為三的情況下，一次成功的鏈攻擊會導致攻擊者失去它們的全部有效餘額。

有趣的是，由於這個常式中整數算術被建構的方式，特別是把 `increment` 因式分解提出，如果 `validator.effective_balance * adjusted_total_slashing_balance` 小於 `total_balance`，那麼這項計算的結果就會是零。實際上，懲罰被向下取整到最接近的整數以太幣數額。Issue [1322](https://github.com/ethereum/consensus-specs/issues/1322) 與 [2161](https://github.com/ethereum/consensus-specs/issues/2161) 討論了這一點。最終，其後果是：當罰沒數量很少時，根本沒有額外的關聯式罰沒懲罰，這大概是件好事。

|||
|-|------|
| 使用&nbsp;者 | [`process_epoch()`](#def_process_epoch) |
| 使用 | [`get_total_active_balance()`](/part3/helper/accessors/#def_get_total_active_balance), [`decrease_balance()`](/part3/helper/mutators/#def_decrease_balance) |
| 亦見 | [`slash_validator()`](/part3/helper/mutators/#def_slash_validator), [`EPOCHS_PER_SLASHINGS_VECTOR`](/part3/config/preset/#epochs_per_slashings_vector), [`PROPORTIONAL_SLASHING_MULTIPLIER_BELLATRIX`](/part3/config/preset/#proportional_slashing_multiplier) |

#### Eth1 資料投票更新

<a id="def_process_eth1_data_reset"></a>

```python
def process_eth1_data_reset(state: BeaconState) -> None:
    next_epoch = Epoch(get_current_epoch(state) + 1)
    # Reset eth1 data votes
    if next_epoch % EPOCHS_PER_ETH1_VOTING_PERIOD == 0:
        state.eth1_data_votes = []
```

有一段固定的期間，在這段期間信標區塊提議者對它們對 Eth1 存款合約的觀點投票，並試圖達成一個簡單多數的協議。在這段期間結束時，投票的紀錄被清空、投票重新開始，無論在這段期間內是否達成了協議。

|||
|-|------|
| 使用&nbsp;者 | [`process_epoch()`](#def_process_epoch) |
| 亦見 | [`EPOCHS_PER_ETH1_VOTING_PERIOD`](/part3/config/preset/#epochs_per_eth1_voting_period), [`Eth1Data`](/part3/containers/dependencies/#eth1data) |

#### 有效餘額更新

<a id="def_process_effective_balance_updates"></a>

```python
def process_effective_balance_updates(state: BeaconState) -> None:
    # Update effective balances with hysteresis
    for index, validator in enumerate(state.validators):
        balance = state.balances[index]
        HYSTERESIS_INCREMENT = uint64(EFFECTIVE_BALANCE_INCREMENT // HYSTERESIS_QUOTIENT)
        DOWNWARD_THRESHOLD = HYSTERESIS_INCREMENT * HYSTERESIS_DOWNWARD_MULTIPLIER
        UPWARD_THRESHOLD = HYSTERESIS_INCREMENT * HYSTERESIS_UPWARD_MULTIPLIER
        if (
            balance + DOWNWARD_THRESHOLD < validator.effective_balance
            or validator.effective_balance + UPWARD_THRESHOLD < balance
        ):
            validator.effective_balance = min(balance - balance % EFFECTIVE_BALANCE_INCREMENT, MAX_EFFECTIVE_BALANCE)
```

每個驗證者的餘額在狀態中被表示兩次：一次精確地在一個與驗證者紀錄分開的串列中，一次以一種[粗粒度的格式](/part3/config/preset/#effective_balance_increment)在該驗證者的紀錄之內。在規格內的計算中只使用有效餘額，但獎勵與懲罰套用於實際餘額。這個常式就是「有效餘額每個紀元被更新一次以跟隨實際餘額」之處。

在「一個驗證者的實際餘額改變時計算它的有效餘額」時，會使用一個遲滯（hysteresis）機制。關於這的更多討論、以及相關常數的值，見[遲滯參數](/part3/config/preset/#hysteresis-parameters)。在當前的值下，一個驗證者的有效餘額在其實際餘額跌到 `X.75`&nbsp;ETH 以下時降到 `X`&nbsp;ETH，並在其實際餘額升到 `Y.25`&nbsp;ETH 以上時升到 `Y`&nbsp;ETH。遲滯機制確保有效餘額不頻繁地改變，這意味著在計算狀態根時，驗證者紀錄的串列只需不頻繁地被重新雜湊，大幅節省工作。

|||
|-|------|
| 使用&nbsp;者 | [`process_epoch()`](#def_process_epoch) |
| 亦見 | [Hysteresis Parameters](/part3/config/preset/#hysteresis-parameters) |

#### 罰沒餘額更新

<a id="def_process_slashings_reset"></a>

```python
def process_slashings_reset(state: BeaconState) -> None:
    next_epoch = Epoch(get_current_epoch(state) + 1)
    # Reset slashings
    state.slashings[next_epoch % EPOCHS_PER_SLASHINGS_VECTOR] = Gwei(0)
```

`state.slashings` 是一個長度為 [`EPOCHS_PER_SLASHINGS_VECTOR`](/part3/config/preset/#epochs_per_slashings_vector) 的環狀串列，它包含「每個紀元被罰沒之所有驗證者」的有效餘額總計。這些被用來在被罰沒的驗證者退出之前，對它們套用一筆關聯式罰沒懲罰。每個紀元我們用零覆寫最舊的條目，而它就成為當前的條目。

|||
|-|------|
| 使用&nbsp;者 | [`process_epoch()`](#def_process_epoch) |
| 亦見 | [`process_slashings()`](/part3/transition/epoch/#def_process_slashings), [`EPOCHS_PER_SLASHINGS_VECTOR`](/part3/config/preset/#epochs_per_slashings_vector) |

#### Randao 混合值更新

<a id="def_process_randao_mixes_reset"></a>

```python
def process_randao_mixes_reset(state: BeaconState) -> None:
    current_epoch = get_current_epoch(state)
    next_epoch = Epoch(current_epoch + 1)
    # Set randao mix
    state.randao_mixes[next_epoch % EPOCHS_PER_HISTORICAL_VECTOR] = get_randao_mix(state, current_epoch)
```

`state.randao_mixes` 是一個長度為 [`EPOCHS_PER_HISTORICAL_VECTOR`](/part3/config/preset/#epochs_per_historical_vector) 的環狀串列。RANDAO 的當前值——它隨著每個抵達的區塊而更新——依 [`get_randao_mix()`](/part3/helper/accessors/#def_get_randao_mix) 被儲存在位置 `state.randao_mixes[current_epoch % EPOCHS_PER_HISTORICAL_VECTOR]`。

在每個紀元結束時，這個紀元的 RANDAO 最終值被複製過去，成為下一個紀元 randao 的起始值，並把其餘的條目作為歷史值保留下來。

|||
|-|------|
| 使用&nbsp;者 | [`process_epoch()`](#def_process_epoch) |
| 使用 | [`get_randao_mix()`](/part3/helper/accessors/#def_get_randao_mix) |
| 亦見 | [`process_randao()`](/part3/transition/block/#def_process_randao), [`EPOCHS_PER_HISTORICAL_VECTOR`](/part3/config/preset/#epochs_per_historical_vector) |

#### 歷史摘要更新

<a id="def_process_historical_summaries_update"></a>

```python
def process_historical_summaries_update(state: BeaconState) -> None:
    # Set historical block root accumulator.
    next_epoch = Epoch(get_current_epoch(state) + 1)
    if next_epoch % (SLOTS_PER_HISTORICAL_ROOT // SLOTS_PER_EPOCH) == 0:
        historical_summary = HistoricalSummary(
            block_summary_root=hash_tree_root(state.block_roots),
            state_summary_root=hash_tree_root(state.state_roots),
        )
        state.historical_summaries.append(historical_summary)
```

這個常式在 [Capella 升級](/part4/history/capella/)時取代了 [`process_historical_roots_update()`](/../bellatrix/part3/transition/epoch/#def_process_historical_roots_update)。

先前，`state.block_roots` 與 `state.state_roots` 兩個串列被一起 Merkle 化成單一一個根，然後才被加入 `state.historical_roots` [雙重批次累加器](https://ethresear.ch/t/double-batched-merkle-log-accumulator/571?u=benjaminion)。現在它們被分開 Merkle 化，並透過 [`HistoricalSummary`](/part3/containers/dependencies/#historicalsummary) 容器被附加到 `state.historical_summaries`。Capella 升級[改變了這一點](https://github.com/ethereum/consensus-specs/pull/2649)，使得驗證過去的區塊歷史成為可能，而無須知道狀態歷史。

摘要每 [`SLOTS_PER_HISTORICAL_ROOT`](/part3/config/preset/#slots_per_historical_root) 個時段被附加到串列一次。以每個摘要 64 位元組計，這個串列會以每年 20&nbsp;KB 的速率成長。信標狀態中對應的區塊根與狀態根串列是環狀的，在下一個週期就被覆寫掉。

被這個函式取代的 `process_historical_roots_update()` 函式，仍[在 Bellatrix 版中有記載](/../bellatrix/part3/transition/epoch/#def_process_historical_roots_updates)。

|||
|-|------|
| 使用&nbsp;者 | [`process_epoch()`](#def_process_epoch) |
| 亦見 | [`HistoricalSummary`](/part3/containers/dependencies/#historicalsummary), [`SLOTS_PER_HISTORICAL_ROOT`](/part3/config/preset/#slots_per_historical_root) |

#### 參與旗標更新

<a id="def_process_participation_flag_updates"></a>

```python
def process_participation_flag_updates(state: BeaconState) -> None:
    state.previous_epoch_participation = state.current_epoch_participation
    state.current_epoch_participation = [ParticipationFlags(0b0000_0000) for _ in range(len(state.validators))]
```

會儲存兩個紀元份的驗證者參與旗標（它們記錄驗證者的證明活動）。在每個紀元結束時，當前的變為先前的，而一個新的空串列變為當前的。

|||
|-|------|
| 使用&nbsp;者 | [`process_epoch()`](#def_process_epoch) |
| 亦見 | [`ParticipationFlags`](/part3/config/types/#participationflags) |

#### 同步委員會更新

<a id="def_process_sync_committee_updates"></a>

```python
def process_sync_committee_updates(state: BeaconState) -> None:
    next_epoch = get_current_epoch(state) + Epoch(1)
    if next_epoch % EPOCHS_PER_SYNC_COMMITTEE_PERIOD == 0:
        state.current_sync_committee = state.next_sync_committee
        state.next_sync_committee = get_next_sync_committee(state)
```

同步委員會每 [`EPOCHS_PER_SYNC_COMMITTEE_PERIOD`](/part3/config/preset/#epochs_per_sync_committee_period) 輪替一次。下一個同步委員會已準備好並等候著，使得驗證者能藉由訂閱必要的子網來預先準備。那個委員會變為當前的同步委員會，而下一個被計算出來。

|||
|-|------|
| 使用&nbsp;者 | [`process_epoch()`](#def_process_epoch) |
| 使用 | [`get_next_sync_committee()`](/part3/helper/accessors/#def_get_next_sync_committee) |
| 亦見 | [`EPOCHS_PER_SYNC_COMMITTEE_PERIOD`](/part3/config/preset/#epochs_per_sync_committee_period) |

### 區塊處理 <!-- /part3/transition/block/ -->

<a id="def_process_block"></a>

```python
def process_block(state: BeaconState, block: BeaconBlock) -> None:
    process_block_header(state, block)
    if is_execution_enabled(state, block.body):
        process_withdrawals(state, block.body.execution_payload)  # [New in Capella]
        process_execution_payload(state, block.body.execution_payload, EXECUTION_ENGINE)  # [Modified in Capella]
    process_randao(state, block.body)
    process_eth1_data(state, block.body)
    process_operations(state, block.body)  # [Modified in Capella]
    process_sync_aggregate(state, block.body.sync_aggregate)
```

這些是信標節點為了處理一個區塊並更新狀態而執行的工作。如果任何一個被呼叫的函式觸發了一個 `assert` 陳述句的失敗、或任何其他種類的例外，那麼[整個區塊就無效](/part3/transition/#assert)，而任何狀態變更都必須被回滾。

> _注意_：對 `process_execution_payload` 的呼叫必須發生在對 `process_randao` 的呼叫之前，因為前者取決於「以前一個區塊的 reveal 計算出的 `randao_mix`」。

對 [`process_execution_payload()`](#def_process_execution_payload) 的呼叫是在合併前的 Bellatrix 升級中加入的。[`EXECUTION_ENGINE` 物件](/part3/transition/execution/)其實並未在信標鏈規格中被定義，而是對應於一個 API，它呼叫出去給一個附接的執行客戶端（從前的 Eth1 客戶端），由後者做大部分的酬載驗證。

[`process_operations()`](#def_process_operations) 涵蓋對「區塊中任何罰沒回報（提議者與證明者）、任何證明、任何存款、以及任何自願退出」的處理。

|||
|-|------|
| 使用&nbsp;者 | [`state_transition()`](/part3/transition/#def_state_transition) |
| 使用 | [`process_block_header()`](#def_process_block_header), [`is_execution_enabled()`](/part3/helper/predicates/#def_is_execution_enabled), [`process_execution_payload()`](#def_process_execution_payload), [`process_randao()`](#def_process_randao), [`process_eth1_data()`](#def_process_eth1_data), [`process_operations()`](#def_process_operations), [`process_sync_aggregate()`](#def_process_sync_aggregate) |

#### 區塊標頭

<a id="def_process_block_header"></a>

```python
def process_block_header(state: BeaconState, block: BeaconBlock) -> None:
    # Verify that the slots match
    assert block.slot == state.slot
    # Verify that the block is newer than latest block header
    assert block.slot > state.latest_block_header.slot
    # Verify that proposer index is the correct index
    assert block.proposer_index == get_beacon_proposer_index(state)
    # Verify that the parent matches
    assert block.parent_root == hash_tree_root(state.latest_block_header)
    # Cache current block as the new latest block
    state.latest_block_header = BeaconBlockHeader(
        slot=block.slot,
        proposer_index=block.proposer_index,
        parent_root=block.parent_root,
        state_root=Bytes32(),  # Overwritten in the next process_slot call
        body_root=hash_tree_root(block.body),
    )

    # Verify proposer is not slashed
    proposer = state.validators[block.proposer_index]
    assert not proposer.slashed
```

[區塊標頭](/part3/containers/dependencies/#beaconblockheader)資料的一組直截了當的有效性條件。

這個常式儲存在狀態中的區塊標頭物件版本，是進來之區塊標頭的一個複本，但它的 `state_root` 被設為它的預設空 `Bytes32()` 值。這一點的解釋見 [`process_slot()`](/part3/transition/#def_process_slot)。

|||
|-|------|
| 使用&nbsp;者 | [`process_block()`](#def_process_block) |
| 使用 | [`get_beacon_proposer_index()`](/part3/helper/accessors/#def_get_beacon_proposer_index), [`hash_tree_root()`](/part3/helper/crypto/#hash_tree_root) |
| 亦見 | [BeaconBlockHeader](/part3/containers/dependencies/#beaconblockheader), [`process_slot()`](/part3/transition/#def_process_slot) |

#### 提領

##### `get_expected_withdrawals`

<a id="def_get_expected_withdrawals"></a>

```python
def get_expected_withdrawals(state: BeaconState) -> Sequence[Withdrawal]:
    epoch = get_current_epoch(state)
    withdrawal_index = state.next_withdrawal_index
    validator_index = state.next_withdrawal_validator_index
    withdrawals: List[Withdrawal] = []
    bound = min(len(state.validators), MAX_VALIDATORS_PER_WITHDRAWALS_SWEEP)
    for _ in range(bound):
        validator = state.validators[validator_index]
        balance = state.balances[validator_index]
        if is_fully_withdrawable_validator(validator, balance, epoch):
            withdrawals.append(Withdrawal(
                index=withdrawal_index,
                validator_index=validator_index,
                address=ExecutionAddress(validator.withdrawal_credentials[12:]),
                amount=balance,
            ))
            withdrawal_index += WithdrawalIndex(1)
        elif is_partially_withdrawable_validator(validator, balance):
            withdrawals.append(Withdrawal(
                index=withdrawal_index,
                validator_index=validator_index,
                address=ExecutionAddress(validator.withdrawal_credentials[12:]),
                amount=balance - MAX_EFFECTIVE_BALANCE,
            ))
            withdrawal_index += WithdrawalIndex(1)
        if len(withdrawals) == MAX_WITHDRAWALS_PER_PAYLOAD:
            break
        validator_index = ValidatorIndex((validator_index + 1) % len(state.validators))
    return withdrawals
```

這在區塊處理與區塊建構兩者中都被使用，以建構「我們預期在區塊中見到的自動驗證者提領」串列。

最多 [`MAX_VALIDATORS_PER_WITHDRAWALS_SWEEP`](/part3/config/preset/#max_validators_per_withdrawals_sweep) 個驗證者會被考慮進行提領。如該標題之下所描述的，這作用是在「符合資格的驗證者寥寥無幾、彼此相距甚遠」時約束節點的負載。

從上一次掃描停下之處（`state.next_withdrawal_validator_index`）接續下去，我們依驗證者索引遞增的順序，輪流考量驗證者。如果一個驗證者[符合完整提領的資格](/part3/helper/predicates/#def_is_fully_withdrawable_validator)，那麼一筆「針對它整個餘額」的提領交易就被加入串列。如果一個驗證者[符合部分提領的資格](/part3/helper/predicates/#def_is_partially_withdrawable_validator)，那麼一筆「針對它在 [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance) 之上之多餘餘額」的提領交易就被加入串列。

每筆[提領交易](/part3/containers/dependencies/#withdrawal)都與一個唯一、連續的[提領索引](/part3/config/types/#withdrawalindex)相關，該索引就是先前提領的總數。

一旦 [`MAX_WITHDRAWALS_PER_PAYLOAD`](/part3/config/preset/#max_withdrawals_per_payload) 筆交易已被組裝出來、或 [`MAX_VALIDATORS_PER_WITHDRAWALS_SWEEP`](/part3/config/preset/#max_validators_per_withdrawals_sweep) 個驗證者已被考量過，掃描就終止並回傳交易的串列。

信標狀態中的 `next_withdrawal_index` 與 `next_withdrawal_validator_index` 計數器不在這裡更新，而在呼叫端函式中更新。

|||
|-|------|
| 使用&nbsp;者 | [`process_withdrawals()`](#def_process_withdrawals) |
| 使用 | [`is_fully_withdrawable_validator()`](/part3/helper/predicates/#def_is_fully_withdrawable_validator), [`is_partially_withdrawable_validator()`](/part3/helper/predicates/#def_is_partially_withdrawable_validator) |
| 亦見 | [`MAX_WITHDRAWALS_PER_PAYLOAD`](/part3/config/preset/#max_withdrawals_per_payload), [`MAX_VALIDATORS_PER_WITHDRAWALS_SWEEP`](/part3/config/preset/#max_validators_per_withdrawals_sweep), [Withdrawal](/part3/containers/dependencies/#withdrawal) |

##### `process_withdrawals`

<a id="def_process_withdrawals"></a>

```python
def process_withdrawals(state: BeaconState, payload: ExecutionPayload) -> None:
    expected_withdrawals = get_expected_withdrawals(state)
    assert len(payload.withdrawals) == len(expected_withdrawals)

    for expected_withdrawal, withdrawal in zip(expected_withdrawals, payload.withdrawals):
        assert withdrawal == expected_withdrawal
        decrease_balance(state, withdrawal.validator_index, withdrawal.amount)

    # Update the next withdrawal index if this block contained withdrawals
    if len(expected_withdrawals) != 0:
        latest_withdrawal = expected_withdrawals[-1]
        state.next_withdrawal_index = WithdrawalIndex(latest_withdrawal.index + 1)

    # Update the next validator index to start the next withdrawal sweep
    if len(expected_withdrawals) == MAX_WITHDRAWALS_PER_PAYLOAD:
        # Next sweep starts after the latest withdrawal's validator index
        next_validator_index = ValidatorIndex((expected_withdrawals[-1].validator_index + 1) % len(state.validators))
        state.next_withdrawal_validator_index = next_validator_index
    else:
        # Advance sweep by the max length of the sweep if there was not a full set of withdrawals
        next_index = state.next_withdrawal_validator_index + MAX_VALIDATORS_PER_WITHDRAWALS_SWEEP
        next_validator_index = ValidatorIndex(next_index % len(state.validators))
        state.next_withdrawal_validator_index = next_validator_index
```

一個區塊中的提領交易出現在它的 [`ExecutionPayload`](/part3/containers/execution/#executionpayload) 中，因為它們橫跨共識層與執行層兩者。在處理提領時，我們首先檢查它們與我們預期見到的相符。這是由「對 [`get_expected_withdrawals()`](#def_get_expected_withdrawals) 的呼叫」以及「`for` 迴圈內的成對比較」處理的[^fn-withdrawals-zip]。如果任何 `assert` 測試失敗，那麼整個區塊就無效，所有變更——包括已做出的餘額更新——都必須被回滾。對於每筆提領，對應驗證者的餘額被減少；執行客戶端會在執行層把相同的數額加到該驗證者的 Eth1 提領位址上。

[^fn-withdrawals-zip]: 此處對 [`zip()`](https://docs.python.org/3/library/functions.html#zip) 的使用相當有 Python 風格，但只是意味著：有兩個長度相等的串列，我們輪流成對地取它們的元素。

在那之後，我們有一些花招用於更新信標狀態中 `next_withdrawal_index` 與 `next_withdrawal_validator_index` 的值。

對於 `next_withdrawal_index`——它只是計算曾做出之提領的數目——我們取串列中最後一筆提領的索引並加一。把串列的長度加到我們的當前值上會是等價的。

對於 `next_withdrawal_validator_index`，我們有兩種情況。如果我們有一個含 [`MAX_WITHDRAWALS_PER_PAYLOAD`](/part3/config/preset/#max_withdrawals_per_payload) 筆提領交易的完整串列，那麼我們知道這就是終止掃描的那個條件。因此，我們下次需要考量的第一個驗證者，就是「最後一筆提領交易中那個驗證者」的下一個。否則，掃描是因為抵達 [`MAX_VALIDATORS_PER_WITHDRAWALS_SWEEP`](/part3/config/preset/#max_validators_per_withdrawals_sweep) 而終止的，而我們下次需要考量的第一個驗證者，就是那之後的那一個。

我不禁覺得，從 [`get_expected_withdrawals()`](#def_get_expected_withdrawals) 把這兩者都回傳回來會更容易些——它們才剛在那裡被獨立地計算過。

|||
|-|------|
| 使用&nbsp;者 | [`process_block()`](#def_process_block) |
| 使用 | [`get_expected_withdrawals()`](#def_get_expected_withdrawals), [`decrease_balance()`](/part3/helper/mutators/#def_decrease_balance) |
| 亦見 | [WithdrawalIndex](/part3/config/types/#withdrawalindex), [ValidatorIndex](/part3/config/types/#validatorindex), [`MAX_WITHDRAWALS_PER_PAYLOAD`](/part3/config/preset/#max_withdrawals_per_payload), [`MAX_VALIDATORS_PER_WITHDRAWALS_SWEEP`](/part3/config/preset/#max_validators_per_withdrawals_sweep) |

#### 執行酬載

##### `process_execution_payload`

<a id="def_process_execution_payload"></a>

```python
def process_execution_payload(state: BeaconState, payload: ExecutionPayload, execution_engine: ExecutionEngine) -> None:
    # Verify consistency of the parent hash with respect to the previous execution payload header
    if is_merge_transition_complete(state):
        assert payload.parent_hash == state.latest_execution_payload_header.block_hash
    # Verify prev_randao
    assert payload.prev_randao == get_randao_mix(state, get_current_epoch(state))
    # Verify timestamp
    assert payload.timestamp == compute_timestamp_at_slot(state, state.slot)
    # Verify the execution payload is valid
    assert execution_engine.notify_new_payload(payload)
    # Cache execution payload header
    state.latest_execution_payload_header = ExecutionPayloadHeader(
        parent_hash=payload.parent_hash,
        fee_recipient=payload.fee_recipient,
        state_root=payload.state_root,
        receipts_root=payload.receipts_root,
        logs_bloom=payload.logs_bloom,
        prev_randao=payload.prev_randao,
        block_number=payload.block_number,
        gas_limit=payload.gas_limit,
        gas_used=payload.gas_used,
        timestamp=payload.timestamp,
        extra_data=payload.extra_data,
        base_fee_per_gas=payload.base_fee_per_gas,
        block_hash=payload.block_hash,
        transactions_root=hash_tree_root(payload.transactions),
        withdrawals_root=hash_tree_root(payload.withdrawals),  # [New in Capella]
    )
```

自合併以來，執行酬載（從前的 Eth1 區塊）如今構成信標區塊的一部分。

對執行酬載而言並沒有太多信標鏈處理要做，因為它們大體上是「只對執行客戶端有意義」的不透明資料團塊。然而，信標鏈確實需要知道執行酬載在執行客戶端的觀點下是否有效。一個依執行（Eth1）鏈規則而言無效的執行酬載，會使含有它的信標區塊無效。

會進行一些初步的合理性檢查：

  - 除非這是我們所見過最初的那個執行酬載，否則它的 `parent_hash` 必須與「我們在信標狀態中持有的 `block_hash`」（即我們上一個處理之執行酬載的）相符。這確保了執行酬載的鏈是連續的，因為它本質上是區塊鏈中的一條區塊鏈。
  - 我們檢查 `prev_randao` 值被正確地設定，否則一個區塊提議者能輕而易舉地控制執行層上的隨機性。
  - 執行酬載上的時間戳必須與時段時間戳相符。同樣地，這防止提議者為任何依賴於執行層時間的智慧合約而操縱該時間。

接著我們透過 Engine&nbsp;API、使用執行引擎提供的 [`notify_new_payload()`](/part3/transition/execution/#def_notify_new_payload) 函式，把酬載送過去給它。這發揮兩項用途：第一，它請求執行客戶端檢查酬載的有效性；第二，如果酬載有效，它讓執行層能藉由運行酬載中所含的交易來更新它自己的狀態。

最後，執行酬載的標頭被儲存在[信標狀態](/part3/containers/state/#beaconstate)中，主要是為了讓 `block_hash`&ndash;`parent_hash` 檢查能在這個函式下次被呼叫時進行。執行標頭資料的其餘部分目前並未在信標鏈規格中被使用，儘管它被儲存著。

這個函式是在合併前的 Bellatrix 升級中加入的。

|||
|-|------|
| 使用&nbsp;者 | [`process_block()`](#def_process_block) |
| 使用 | [`is_merge_transition_complete()`](/part3/helper/predicates/#def_is_merge_transition_complete), [`get_randao_mix()`](/part3/helper/accessors/#def_get_randao_mix), [`compute_timestamp_at_slot()`](/part3/helper/misc/#def_compute_timestamp_at_slot), [`notify_new_payload()`](/part3/transition/execution/#def_notify_new_payload), [`hash_tree_root()`](/part3/helper/crypto/#hash_tree_root) |
| 亦見 | [`ExecutionPayloadHeader`](/part3/containers/execution/#executionpayloadheader) |

#### RANDAO

<a id="def_process_randao"></a>

```python
def process_randao(state: BeaconState, body: BeaconBlockBody) -> None:
    epoch = get_current_epoch(state)
    # Verify RANDAO reveal
    proposer = state.validators[get_beacon_proposer_index(state)]
    signing_root = compute_signing_root(epoch, get_domain(state, DOMAIN_RANDAO))
    assert bls.Verify(proposer.pubkey, signing_root, body.randao_reveal)
    # Mix in RANDAO reveal
    mix = xor(get_randao_mix(state, epoch), hash(body.randao_reveal))
    state.randao_mixes[epoch % EPOCHS_PER_HISTORICAL_VECTOR] = mix
```

一個良好的隨機性來源，對信標鏈的運作而言是基礎性的。協定的安全性顯著地取決於「能否無法預測且均勻地選出區塊提議者與委員會成員」。事實上，「信標鏈」這個名稱本身就是受到 Dfinity 的[隨機性信標](https://arxiv.org/abs/1805.04548)概念所啟發。

目前提供隨機性的機制是一個 RANDAO，其中每個區塊提議者提供一些隨機性，而所有的貢獻在一個紀元的過程中被混合在一起。這並非不可偏倚的（一個惡意的提議者若略過一個區塊對它有利，它可能會選擇這麼做），但[已經夠好](https://ethresear.ch/t/rng-exploitability-analysis-assuming-pure-randao-based-main-chain/1825?u=benjaminion)。在未來，以太坊可能會使用一個可驗證延遲函式（[VDF](https://www.vdfalliance.org/)）來提供不可偏倚的隨機性。

[早期的設計](https://github.com/ethereum/consensus-specs/pull/33/files)讓驗證者預先承諾於「雜湊洋蔥」，在每次區塊提議時剝掉一層雜湊。這[被改為](https://github.com/ethereum/consensus-specs/pull/483)使用「涵蓋[紀元號](https://github.com/ethereum/consensus-specs/pull/498)的一個 BLS 簽章」作為熵的來源。使用簽章既是一項簡化，也是多方（分散式）驗證者的一項使能要素。其（合理的）假設是：足夠多的驗證者以良好的熵產生了它們的私鑰，以確保 RANDAO 的熵是足夠的。

[TODO: link to DVT ^^^]::

`process_randao()` 函式單純地使用提議者的公鑰來驗證「區塊中的 RANDAO reveal 確實是『以提議者私鑰簽署的紀元號』」。然後它把該 reveal 的雜湊混入當前紀元的 RANDAO 累加器。使用雜湊是為了把簽章從 96 位元組縮減到 32 位元組，並使它均勻。RANDAO 累加器在各紀元結束時的 [`EPOCHS_PER_HISTORICAL_VECTOR`](/part3/config/preset/#epochs_per_historical_vector) 個過去的值被儲存在狀態中。

出自 Justin Drake 的[筆記](https://notes.ethereum.org/@JustinDrake/rkPjB1_xr)：
> 在 `process_randao` 中使用 `xor` 比使用 `hash`（略微）更安全。為了說明原因，想像一個攻擊者能在當前紀元中碾磨隨機性，使得在「下一個紀元的兩種結果抽樣」中，他的兩個驗證者以不同的順序成為最後的提議者。`xor` 的交換性使那兩種抽樣等價，因此相較於 `hash`（它不具交換性）而言，減少了攻擊者對下一個紀元的碾磨機會。這項嚴格的安全性改善，可能會簡化 RANDAO 安全性形式下界的推導。

請注意，`assert` 陳述句意味著：如果 RANDAO reveal 形成得不正確，整個區塊就無效。

|||
|-|------|
| 使用&nbsp;者 | [`process_block()`](#def_process_block) |
| 使用 | [`get_beacon_proposer_index()`](/part3/helper/accessors/#def_get_beacon_proposer_index), [`compute_signing_root()`](/part3/helper/misc/#def_compute_signing_root), [`get_domain()`](/part3/helper/accessors/#def_get_domain), [`bls.Verify()`](/part3/helper/crypto/#bls-signatures), [`hash()`](/part3/helper/crypto/#hash), [`xor()`](/part3/helper/math/#def_xor), [`get_randao_mix()`](/part3/helper/accessors/#def_get_randao_mix) |
| 亦見 | [`EPOCHS_PER_HISTORICAL_VECTOR`](/part3/config/preset/#epochs_per_historical_vector) |

#### Eth1 資料

<a id="def_process_eth1_data"></a>

```python
def process_eth1_data(state: BeaconState, body: BeaconBlockBody) -> None:
    state.eth1_data_votes.append(body.eth1_data)
    if state.eth1_data_votes.count(body.eth1_data) * 2 > EPOCHS_PER_ETH1_VOTING_PERIOD * SLOTS_PER_EPOCH:
        state.eth1_data = body.eth1_data
```

區塊可能包含 [`Eth1Data`](/part3/containers/dependencies/#eth1data)，它應是提議者當時對 Eth1 鏈與存款合約的最佳觀點。把這份資料弄正確沒有激勵，弄不正確也沒有懲罰。

如果在每段 [`EPOCHS_PER_ETH1_VOTING_PERIOD`](/part3/config/preset/#epochs_per_eth1_voting_period) 個紀元（6.8 小時）的投票期間，提議者投出的相同投票有一個簡單多數，那麼這份 Eth1 資料就被提交到信標狀態。這更新了鏈對存款合約的觀點，而自上次更新以來的新存款會開始被處理。

這個機制過去[證明是脆弱的](https://github.com/ethereum/consensus-specs/issues/2018)，但看來即使不完美也還行得通。

|||
|-|------|
| 使用&nbsp;者 | [`process_block()`](#def_process_block) |
| 亦見 | [`Eth1Data`](/part3/containers/dependencies/#eth1data), [`EPOCHS_PER_ETH1_VOTING_PERIOD`](/part3/config/preset/#epochs_per_eth1_voting_period) |

#### 操作

<a id="def_process_operations"></a>

```python
def process_operations(state: BeaconState, body: BeaconBlockBody) -> None:
    # Verify that outstanding deposits are processed up to the maximum number of deposits
    assert len(body.deposits) == min(MAX_DEPOSITS, state.eth1_data.deposit_count - state.eth1_deposit_index)

    def for_ops(operations: Sequence[Any], fn: Callable[[BeaconState, Any], None]) -> None:
        for operation in operations:
            fn(state, operation)

    for_ops(body.proposer_slashings, process_proposer_slashing)
    for_ops(body.attester_slashings, process_attester_slashing)
    for_ops(body.attestations, process_attestation)
    for_ops(body.deposits, process_deposit)
    for_ops(body.voluntary_exits, process_voluntary_exit)
    for_ops(body.bls_to_execution_changes, process_bls_to_execution_change)  # [New in Capella]
```

只是一個用於處理區塊中各種可選內容的調度器。

存款之為可選，只是在「有些區塊有、有些沒有」的意義上。然而，依 `assert` 陳述句而言，如果依信標鏈對 Eth1 鏈的觀點有存款待處理，那麼區塊就「必須」納入它們，否則區塊無效。

關於區塊提議者納入這些元素中每一個的激勵：

  - 提議者因納入任何可得的證明與罰沒回報而被明確地獎勵。
  - 有一個與「納入存款訊息」相關的有效性條件，因而有一個隱含的獎勵。
  - 納入自願退出的激勵是：較小的驗證者集合意味著其餘驗證者有較高的獎勵。
  - 納入 BLS 提領憑證變更訊息沒有激勵，無論隱含或明確。這些是純粹基於利他的基礎而被處理的。

|||
|-|------|
| 使用&nbsp;者 | [`process_block()`](#def_process_block) |
| 使用 | [`process_proposer_slashing()`](#def_process_proposer_slashing), [`process_attester_slashing()`](#def_process_attester_slashing), [`process_attestation()`](#def_process_attestation), [`process_deposit()`](#def_process_deposit), [`process_voluntary_exit()`](#def_process_voluntary_exit), [`process_bls_to_execution_change()`](#def_process_bls_to_execution_change) |
| 亦見 | [`BeaconBlockBody`](/part3/containers/blocks/#beaconblockbody) |

##### 提議者罰沒

<a id="def_process_proposer_slashing"></a>

```python
def process_proposer_slashing(state: BeaconState, proposer_slashing: ProposerSlashing) -> None:
    header_1 = proposer_slashing.signed_header_1.message
    header_2 = proposer_slashing.signed_header_2.message

    # Verify header slots match
    assert header_1.slot == header_2.slot
    # Verify header proposer indices match
    assert header_1.proposer_index == header_2.proposer_index
    # Verify the headers are different
    assert header_1 != header_2
    # Verify the proposer is slashable
    proposer = state.validators[header_1.proposer_index]
    assert is_slashable_validator(proposer, get_current_epoch(state))
    # Verify signatures
    for signed_header in (proposer_slashing.signed_header_1, proposer_slashing.signed_header_2):
        domain = get_domain(state, DOMAIN_BEACON_PROPOSER, compute_epoch_at_slot(signed_header.message.slot))
        signing_root = compute_signing_root(signed_header.message, domain)
        assert bls.Verify(proposer.pubkey, signing_root, signed_header.signature)

    slash_validator(state, header_1.proposer_index)
```

一個 [`ProposerSlashing`](/part3/containers/operations/#proposerslashing) 是「一個提議者在同一高度簽署了兩個區塊」的證明。一個區塊中最多可納入 [`MAX_PROPOSER_SLASHINGS`](/part3/config/preset/#max_proposer_slashings) 個。它以一對 [`SignedBeaconBlockHeader`](/part3/containers/envelopes/#signedbeaconblockheader) 的形式包含證據。

證明很簡單：那兩個提議來自同一個時段、有相同的提議者，但在 `parent_root`、`state_root` 或 `body_root` 中的一者或多者上有所不同。此外，它們兩者都由該提議者簽署。相衝突的區塊不需要有效：任何符合判準的標頭對，不論區塊的內容為何，都該被罰沒。

一如既往，`assert` 陳述句確保：如果含有它的區塊包含任何無效的罰沒主張，那個區塊就無效。

有趣的小知識：信標鏈上發生的[第一筆罰沒](https://beaconcha.in/slot/138731#proposer-slashings)是一筆提議者罰沒。兩個以相同金鑰並排運行的客戶端，往往會產生相同的證明，因為協定就是被設計來鼓勵那樣的。獨立地產生相同的區塊則非常不可能，因為區塊包含多得多的資料。

|||
|-|------|
| 使用&nbsp;者 | [`process_block()`](#def_process_block) |
| 使用 | [`is_slashable_validator()`](/part3/helper/predicates/#def_is_slashable_validator), [`get_domain()`](/part3/helper/accessors/#def_get_domain), [`compute_signing_root()`](/part3/helper/misc/#def_compute_signing_root), [`bls.Verify()`](/part3/helper/crypto/#bls-signatures), [`slash_validator()`](/part3/helper/mutators/#def_slash_validator) |
| 亦見 | [`ProposerSlashing`](/part3/containers/operations/#proposerslashing) |

##### 證明者罰沒

<a id="def_process_attester_slashing"></a>

```python
def process_attester_slashing(state: BeaconState, attester_slashing: AttesterSlashing) -> None:
    attestation_1 = attester_slashing.attestation_1
    attestation_2 = attester_slashing.attestation_2
    assert is_slashable_attestation_data(attestation_1.data, attestation_2.data)
    assert is_valid_indexed_attestation(state, attestation_1)
    assert is_valid_indexed_attestation(state, attestation_2)

    slashed_any = False
    indices = set(attestation_1.attesting_indices).intersection(attestation_2.attesting_indices)
    for index in sorted(indices):
        if is_slashable_validator(state.validators[index], get_current_epoch(state)):
            slash_validator(state, index)
            slashed_any = True
    assert slashed_any
```

[`AttesterSlashing`](/part3/containers/operations/#attesterslashing) 與提議者罰沒類似，它們只提供「兩個彼此衝突的聚合 [`IndexedAttestation`](/part3/containers/dependencies/#indexedattestation)」的證據。一個區塊中最多可納入 [`MAX_ATTESTER_SLASHINGS`](/part3/config/preset/#max_attester_slashings) 個。

有效性檢查由 [`is_slashable_attestation_data()`](/part3/helper/predicates/#is_slashable_attestation_data) 完成——它檢查雙重投票與環繞投票條件——以及由 [`is_valid_indexed_attestation()`](/part3/helper/predicates/#def_is_valid_indexed_attestation) 完成，後者驗證證明上的簽章。

任何同時出現在兩筆證明中的驗證者都會被罰沒。如果沒有驗證者被罰沒，那麼這個證明者罰沒主張畢竟是無效的，因此含有它的區塊就無效。

例子：一筆[雙重投票](https://beaconcha.in/slot/43920#attester-slashings)證明者罰沒；[環繞投票](https://beaconcha.in/slot/17184#attester-slashings)證明者罰沒。

|||
|-|------|
| 使用&nbsp;者 | [`process_block()`](#def_process_block) |
| 使用 | [`is_slashable_attestation_data()`](/part3/helper/predicates/#is_slashable_attestation_data), [`is_valid_indexed_attestation()`](/part3/helper/predicates/#def_is_valid_indexed_attestation), [`is_slashable_validator()`](/part3/helper/predicates/#def_is_slashable_validator), [`slash_validator()`](/part3/helper/mutators/#def_slash_validator) |
| 亦見 | [`AttesterSlashing`](/part3/containers/operations/#attesterslashing) |

##### 證明

<a id="def_process_attestation"></a>

```python
def process_attestation(state: BeaconState, attestation: Attestation) -> None:
    data = attestation.data
    assert data.target.epoch in (get_previous_epoch(state), get_current_epoch(state))
    assert data.target.epoch == compute_epoch_at_slot(data.slot)
    assert data.slot + MIN_ATTESTATION_INCLUSION_DELAY <= state.slot <= data.slot + SLOTS_PER_EPOCH
    assert data.index < get_committee_count_per_slot(state, data.target.epoch)

    committee = get_beacon_committee(state, data.slot, data.index)
    assert len(attestation.aggregation_bits) == len(committee)

    # Participation flag indices
    participation_flag_indices = get_attestation_participation_flag_indices(state, data, state.slot - data.slot)

    # Verify signature
    assert is_valid_indexed_attestation(state, get_indexed_attestation(state, attestation))

    # Update epoch participation flags
    if data.target.epoch == get_current_epoch(state):
        epoch_participation = state.current_epoch_participation
    else:
        epoch_participation = state.previous_epoch_participation

    proposer_reward_numerator = 0
    for index in get_attesting_indices(state, data, attestation.aggregation_bits):
        for flag_index, weight in enumerate(PARTICIPATION_FLAG_WEIGHTS):
            if flag_index in participation_flag_indices and not has_flag(epoch_participation[index], flag_index):
                epoch_participation[index] = add_flag(epoch_participation[index], flag_index)
                proposer_reward_numerator += get_base_reward(state, index) * weight

    # Reward proposer
    proposer_reward_denominator = (WEIGHT_DENOMINATOR - PROPOSER_WEIGHT) * WEIGHT_DENOMINATOR // PROPOSER_WEIGHT
    proposer_reward = Gwei(proposer_reward_numerator // proposer_reward_denominator)
    increase_balance(state, get_beacon_proposer_index(state), proposer_reward)
```

區塊提議者在這裡因「於區塊處理期間納入證明」而被獎勵，而作證的驗證者在[紀元處理](/part3/transition/epoch/#process-rewards-and-penalties)期間收到它們的獎勵與懲罰。

這個常式處理區塊中所納入的每一筆證明。首先會進行一堆有效性檢查。如果其中任何一個失敗，那麼整個區塊就無效（它最可能來自一個不同分叉上的提議者，因此對我們無用）：

  - 該證明的目標投票必須是前一個紀元的檢查點、或當前紀元的檢查點。
  - 目標檢查點與該證明的時段必須屬於同一個紀元。
  - 該證明不可比 [`MIN_ATTESTATION_INCLUSION_DELAY`](/part3/config/preset/#min_attestation_inclusion_delay)（即一）個時段更新。所以這個條件排除了來自當前或未來時段的證明。
  - 該證明不可比 [`SLOTS_PER_EPOCH`](/part3/config/preset/#slots_per_epoch)（即 32）個時段更舊。[^fn-eip7045]
  - 該證明必須來自一個「在該證明被建立時就存在」的委員會。
  - 委員會的大小與聚合的大小必須相符（`aggregation_bits`）。
  - 證明上的（聚合）簽章必須有效，且必須對應於「它所宣稱由其簽署之驗證者」的聚合公鑰。這（以及其他判準）由 [`is_valid_indexed_attestation()`](/part3/helper/predicates/#def_is_valid_indexed_attestation) 檢查。

[^fn-eip7045]: 這在 [EIP-7045](https://eips.ethereum.org/EIPS/eip-7045) 中會有所改變，預定納入 [Deneb 升級](/part4/history/deneb/)。這項變更會容許從整個當前與先前紀元納入證明。

一旦該證明通過了檢查，它就藉由「把它所含之來自驗證者的投票轉換成狀態中的旗標」而被處理。

在所有的檢查之中很容易略過它，但實際的證明處理是由 [`get_attestation_participation_flag_indices()`](/part3/helper/accessors/#def_get_attestation_participation_flag_indices) 完成的。它取該證明的來源、目標與鏈頭投票，連同它的納入延遲（它被納入一個區塊時遲了幾個時段），並在 `participation_flag_indices` 中回傳一個串列，含有最多[三個旗標](/part3/config/constants/#participation-flag-indices)，對應於「既正確又及時」的投票。

對於每個簽署了該證明的驗證者，如果 `participation_flag_indices` 中的每個旗標尚未在它的 `epoch_participation` 紀錄中為它被設定，那麼該旗標就被設定，而提議者被獎勵。請記得，做出該證明的驗證者要到紀元結束時才被獎勵。如果一個驗證者在對應的紀元中該旗標已被設定，就不累加提議者獎勵：這個驗證者的證明已被納入一個較早的區塊。

提議者獎勵被累加，並依「指派給每個旗標（及時來源、及時目標、及時鏈頭）的[權重](/part3/config/constants/#participation_flag_weights)」加權。

如果一個提議者只納入某一個時段的所有證明，而所有相關的驗證者都投票，那麼它的獎勵會是（以稍早建立的[符號](/part3/transition/epoch/#reward-and-penalty-calculations)表示）：

$$
I_{A_P} = \frac{W_p}{32(W_{\Sigma} - W_p)}I_A
$$

其中 $I_A$ 是「每個紀元給證明者的最大總獎勵」，在 [`get_flag_index_deltas()`](/part3/helper/accessors/#def_get_flag_index_deltas) 中計算。一個紀元中「給納入證明之提議者」的總可得獎勵，是這個值的 32 倍。

|||
|-|------|
| 使用&nbsp;者 | [`process_operations()`](#def_process_operations) |
| 使用 | [`get_committee_count_per_slot()`](/part3/helper/accessors/#def_get_committee_count_per_slot), [`get_beacon_committee()`](/part3/helper/accessors/#def_get_beacon_committee), [`get_attestation_participation_flag_indices()`](/part3/helper/accessors/#def_get_attestation_participation_flag_indices), [`is_valid_indexed_attestation()`](/part3/helper/predicates/#def_is_valid_indexed_attestation), [`get_indexed_attestation()`](/part3/helper/accessors/#def_get_indexed_attestation), [`get_attesting_indices()`](/part3/helper/accessors/#def_get_attesting_indices), [`has_flag()`](/part3/helper/participation/#def_has_flag), [`add_flag()`](/part3/helper/participation/#def_add_flag), [`get_base_reward()`](/part3/transition/epoch/#def_get_base_reward), [`increase_balance()`](/part3/helper/mutators/#def_increase_balance) |
| 亦見 | [Participation flag indices](/part3/config/constants/#participation-flag-indices), [`PARTICIPATION_FLAG_WEIGHTS`](/part3/config/constants/#participation_flag_weights), [`get_flag_index_deltas()`](/part3/helper/accessors/#def_get_flag_index_deltas) |

##### 存款

本節的程式碼處理「被納入一個區塊」的存款交易。當一個使用者把一個或多個 ETH 轉移到[存款合約](/part2/deposits-withdrawals/contract/)時，就建立了一筆存款。我們需要檢查隨存款送出的資料是否有效。如果有效，我們就建立一筆新的驗證者紀錄（針對一個驗證者的首筆存款），或更新一筆既有的紀錄。

<a id="def_get_validator_from_deposit"></a>

```python
def get_validator_from_deposit(pubkey: BLSPubkey, withdrawal_credentials: Bytes32, amount: uint64) -> Validator:
    effective_balance = min(amount - amount % EFFECTIVE_BALANCE_INCREMENT, MAX_EFFECTIVE_BALANCE)

    return Validator(
        pubkey=pubkey,
        withdrawal_credentials=withdrawal_credentials,
        activation_eligibility_epoch=FAR_FUTURE_EPOCH,
        activation_epoch=FAR_FUTURE_EPOCH,
        exit_epoch=FAR_FUTURE_EPOCH,
        withdrawable_epoch=FAR_FUTURE_EPOCH,
        effective_balance=effective_balance,
    )
```

基於存款資料建立一個全新初始化的驗證者物件。這從 `process_deposit()` 中[被因式分解提出](https://github.com/ethereum/consensus-specs/commit/1623086088e6f0496566ab7d50d16a8c78cdebf0)，以在 Phase&nbsp;0 規格與（現已棄用的）分片規格之間有更好的程式碼重用。

`pubkey` 在初始的存款交易中被提供。存款者從驗證者的私鑰產生它的公鑰。

|||
|-|------|
| 使用&nbsp;者 | [`apply_deposit()`](#def_apply_deposit) |
| 亦見 | [`Validator`](/part3/containers/dependencies/#validator), [`FAR_FUTURE_EPOCH`](/part3/config/constants/#far_future_epoch), [`EFFECTIVE_BALANCE_INCREMENT`](/part3/config/preset/#effective_balance_increment), [`MAX_EFFECTIVE_BALANCE`](/part3/config/preset/#max_effective_balance) |

<a id="def_apply_deposit"></a>

```python
def apply_deposit(state: BeaconState,
                  pubkey: BLSPubkey,
                  withdrawal_credentials: Bytes32,
                  amount: uint64,
                  signature: BLSSignature) -> None:
    validator_pubkeys = [validator.pubkey for validator in state.validators]
    if pubkey not in validator_pubkeys:
        # Verify the deposit signature (proof of possession) which is not checked by the deposit contract
        deposit_message = DepositMessage(
            pubkey=pubkey,
            withdrawal_credentials=withdrawal_credentials,
            amount=amount,
        )
        domain = compute_domain(DOMAIN_DEPOSIT)  # Fork-agnostic domain since deposits are valid across forks
        signing_root = compute_signing_root(deposit_message, domain)
        # Initialize validator if the deposit signature is valid
        if bls.Verify(pubkey, signing_root, signature):
            state.validators.append(get_validator_from_deposit(pubkey, withdrawal_credentials, amount))
            state.balances.append(amount)
            # [New in Altair]
            state.previous_epoch_participation.append(ParticipationFlags(0b0000_0000))
            state.current_epoch_participation.append(ParticipationFlags(0b0000_0000))
            state.inactivity_scores.append(uint64(0))
    else:
        # Increase balance by deposit amount
        index = ValidatorIndex(validator_pubkeys.index(pubkey))
        increase_balance(state, index, amount)
```

`apply_deposit()` 函式在 Capella 發布版中從 `process_deposit()` 中[被因式分解提出](https://github.com/ethereum/consensus-specs/pull/3177)，以在 Phase&nbsp;0 規格與 [EIP-6110 規格](https://github.com/ethereum/consensus-specs/tree/v1.3.0/specs/_features/eip6110)之間有更好的程式碼重用[^fn-eip-6110]。

[^fn-eip-6110]: [EIP-6110](https://eips.ethereum.org/EIPS/eip-6110) 是一個潛在的未來升級，它會容許存款或多或少即時地被處理，而不必像現在這樣經過 [Eth1 追隨距離](/part3/config/configuration/#eth1_follow_distance)與 [Eth1 投票期間](/part3/config/preset/#epochs_per_eth1_voting_period)。

存款是以存款驗證者的私鑰簽署的，而對應的公鑰被納入存款資料中。這構成了對該私鑰的一個「持有證明」（proof of possession），並防止諸如[流氓金鑰攻擊](/part2/building_blocks/signatures/#proof-of-possession)這類的惡行。請注意，此處在驗證存款的簽章時直接使用 [`compute_domain()`](/part3/helper/misc/#def_compute_domain)，而非比較常用的 [`get_domain()`](/part3/helper/accessors/#def_get_domain) 包裝器。這是因為存款訊息跨越信標鏈升級（例如 Phase&nbsp;0、Altair 與 Bellatrix）都有效，所以我們不想把分叉版本混入域中。此外，存款可以在 `genesis_validators_root` 已知之前就做出。

`if pubkey not in validator_pubkeys` 測試把新存款與加值存款區分開來。當與存款相關的公鑰不存在於既有的驗證者集合中時，一筆新的驗證者紀錄就被建立。當該公鑰已經存在時，既有驗證者紀錄的餘額就被加值。一個驗證者的公鑰是它的唯一身分。（它的驗證者索引目前也是唯一的，但那在未來[可能會改變](https://eips.ethereum.org/EIPS/eip-6914)。）

這個常式一個有趣的怪癖是：只有針對一個驗證者的首筆存款需要被簽署。針對同一個公鑰的後續存款，它們的簽章不會被檢查。這可能讓一個質押者（金鑰持有者）做出一筆初始存款（比如說 1 ETH），然後讓那筆存款被「沒有該私鑰的其他人」加值。我不知道這項功能有任何實際用途，但若聽到有任何用途會很高興。它略微降低了「為同一個驗證者做出多筆存款」之質押者的風險，因為它們不需要擔心錯誤地簽署除首筆之外的任何存款。

類似地，一旦一個驗證者的提領憑證已被初始存款交易設定，針對同一個驗證者之後續存款的提領憑證就被忽略。只有出現在初始存款上的憑證被儲存在信標鏈上。這是一項重要的安全措施。如果一個攻擊者偷走了一個驗證者的簽署金鑰（它簽署存款交易），我們不希望他們能夠改變提領憑證，以便把質押據為己有。然而，這是雙向的，而且有人為質押池找出了[一個漏洞](https://medium.com/immunefi/rocketpool-lido-frontrunning-bug-fix-postmortem-e701f26d7971)：一個惡意的運營者可能潛在地用一筆 1&nbsp;ETH 的存款搶先（front-run）一筆存款交易，把提領憑證設成他們自己的。

請注意，存款資料中的 `withdrawal_credential` 不會以任何方式被檢查。要使用[正確的前綴](/part3/config/constants/#withdrawal-prefixes)與內容，以便在退出共識層之後能收到其獎勵並取回其質押，這由存款者自行確保。

|||
|-|------|
| 使用&nbsp;者 | [`process_deposit()`](#def_process_deposit) |
| 使用 | [`compute_domain()`](/part3/helper/misc/#def_compute_domain), [`compute_signing_root()`](/part3/helper/misc/#def_compute_signing_root), [`bls.Verify()`](/part3/helper/crypto/#bls-signatures), [`get_validator_from_deposit()`](#def_get_validator_from_deposit) |
| 亦見 | [`DepositMessage`](/part3/containers/dependencies/#depositmessage), [`DOMAIN_DEPOSIT`](/part3/config/constants/#domain_deposit) |

<a id="def_process_deposit"></a>

```python
def process_deposit(state: BeaconState, deposit: Deposit) -> None:
    # Verify the Merkle branch
    assert is_valid_merkle_branch(
        leaf=hash_tree_root(deposit.data),
        branch=deposit.proof,
        depth=DEPOSIT_CONTRACT_TREE_DEPTH + 1,  # Add 1 for the List length mix-in
        index=state.eth1_deposit_index,
        root=state.eth1_data.deposit_root,
    )

    # Deposits must be processed in order
    state.eth1_deposit_index += 1

    apply_deposit(
        state=state,
        pubkey=deposit.data.pubkey,
        withdrawal_credentials=deposit.data.withdrawal_credentials,
        amount=deposit.data.amount,
        signature=deposit.data.signature,
    )
```

在這裡，我們處理來自一個區塊的一筆存款。如果該存款有效，就建立一個新的驗證者，或把存款數額加到一個既有的驗證者上。

對 [`is_valid_merkle_branch()`](/part3/helper/predicates/#def_is_valid_merkle_branch) 的呼叫，確保了偽造一筆存款是不可能的。來自存款合約的 `eth1data.deposit_root` 已被信標鏈[協議](/part3/transition/block/#eth1-data)，並包含所有「信標鏈可見之待處理存款」。存款本身包含一個 Merkle 證明，證明它被納入在那個根中。`state.eth1_deposit_index` 計數器確保存款依序被處理。簡言之，提議者提供 `leaf` 與 `branch`，但 `index` 與 `root` 兩者都不提供。

如果 Merkle 分支檢查失敗，那麼整個區塊就無效。然而，個別的存款可以未通過簽章檢查而不使區塊無效。

存款必須依序被處理，而所有可得的存款都必須被納入區塊（最多 [`MAX_DEPOSITS`](/part3/config/preset/#max_deposits)——在 [`process_operations()`](#def_process_operations) 中檢查）。這確保了信標鏈無法審查存款交易，除非以「完全停止出塊」為代價。

|||
|-|------|
| 使用&nbsp;者 | [`process_operations()`](#def_process_operations) |
| 使用 | [`is_valid_merkle_branch()`](/part3/helper/predicates/#def_is_valid_merkle_branch), [`hash_tree_root()`](/part3/helper/crypto/#hash_tree_root), [`apply_deposit()`](#def_apply_deposit) |
| 亦見 | [`Deposit`](/part3/containers/operations/#deposit), [`DEPOSIT_CONTRACT_TREE_DEPTH`](/part3/config/constants/#deposit_contract_tree_depth) |

##### 自願退出

<a id="def_process_voluntary_exit"></a>

```python
def process_voluntary_exit(state: BeaconState, signed_voluntary_exit: SignedVoluntaryExit) -> None:
    voluntary_exit = signed_voluntary_exit.message
    validator = state.validators[voluntary_exit.validator_index]
    # Verify the validator is active
    assert is_active_validator(validator, get_current_epoch(state))
    # Verify exit has not been initiated
    assert validator.exit_epoch == FAR_FUTURE_EPOCH
    # Exits must specify an epoch when they become valid; they are not valid before then
    assert get_current_epoch(state) >= voluntary_exit.epoch
    # Verify the validator has been active long enough
    assert get_current_epoch(state) >= validator.activation_epoch + SHARD_COMMITTEE_PERIOD
    # Verify signature
    domain = get_domain(state, DOMAIN_VOLUNTARY_EXIT, voluntary_exit.epoch)
    signing_root = compute_signing_root(voluntary_exit, domain)
    assert bls.Verify(validator.pubkey, signing_root, signed_voluntary_exit.signature)
    # Initiate exit
    initiate_validator_exit(state, voluntary_exit.validator_index)
```

一個自願退出訊息由一個驗證者提交，以表明它希望不再當一個活躍的驗證者。一個提議者透過 gossip 或透過它自己的 API 收到[自願退出訊息](/part3/containers/operations/#voluntaryexit)，然後把該訊息納入一個區塊，使它能被網路處理。

大部分的檢查是直截了當的，如程式碼中的註解所述。請注意以下幾點。

  - 如果自願退出在給定的 `epoch` 之前就被納入區塊，它們就是無效的，所以節點在把它們放進一個區塊之前，應緩衝它們所見到的任何未來日期的退出。
  - 一個驗證者必定已啟用了至少 [`SHARD_COMMITTEE_PERIOD`](/part3/config/configuration/#shard_committee_period) 個紀元（27 小時）。理路見[那裡](/part3/config/configuration/#shard_committee_period)。
  - 自願退出是以驗證者平常的簽署金鑰簽署的。有一些討論談到[改變這一點](https://github.com/ethereum/consensus-specs/issues/1578)，使得自願退出也能用驗證者的提領金鑰來簽署。

如果自願退出訊息有效，那麼該驗證者就藉由呼叫 [`initiate_validator_exit()`](/part3/helper/mutators/#initiate_validator_exit) 被加入退出佇列。

目前，一個驗證者要退出又重新進入是[不可能的](https://notes.ethereum.org/elDvTNrbRqmgP6np_YWc2g#Concerns-that-motivated-removing-re-activation-functionality-in-2017)，但這項功能在未來[可能會被引入](https://hackmd.io/@HWeNw8hNRimMm2m2GH56Cw/HkTzLKOov#Exit-and-re-entry)。

|||
|-|------|
| 使用&nbsp;者 | [`process_operations()`](/part3/transition/block/#def_process_operations) |
| 使用 | [`is_active_validator()`](/part3/helper/predicates/#def_is_active_validator), [`get_domain()`](/part3/helper/accessors/#def_get_domain), [`compute_signing_root()`](/part3/helper/misc/#def_compute_signing_root), [`bls.Verify()`](/part3/helper/crypto/#bls-signatures), [`initiate_validator_exit()`](/part3/helper/mutators/#def_initiate_validator_exit) |
| 亦見 | [`VoluntaryExit`](/part3/containers/operations/#voluntaryexit), [`SHARD_COMMITTEE_PERIOD`](/part3/config/configuration/#shard_committee_period) |

##### `process_bls_to_execution_change`

<a id="def_process_bls_to_execution_change"></a>

```python
def process_bls_to_execution_change(state: BeaconState,
                                    signed_address_change: SignedBLSToExecutionChange) -> None:
    address_change = signed_address_change.message

    assert address_change.validator_index < len(state.validators)

    validator = state.validators[address_change.validator_index]

    assert validator.withdrawal_credentials[:1] == BLS_WITHDRAWAL_PREFIX
    assert validator.withdrawal_credentials[1:] == hash(address_change.from_bls_pubkey)[1:]

    # Fork-agnostic domain since address changes are valid across forks
    domain = compute_domain(DOMAIN_BLS_TO_EXECUTION_CHANGE, genesis_validators_root=state.genesis_validators_root)
    signing_root = compute_signing_root(address_change, domain)
    assert bls.Verify(address_change.from_bls_pubkey, signing_root, signed_address_change.signature)

    validator.withdrawal_credentials = (
        ETH1_ADDRESS_WITHDRAWAL_PREFIX
        + b'\x00' * 11
        + address_change.to_execution_address
    )
```

[Capella 升級](/part4/history/capella/)提供一個一次性的操作，容許質押者把它們的提領憑證從 BLS 型（[`BLS_WITHDRAWAL_PREFIX`](/part3/config/constants/#bls_withdrawal_prefix)，不容許提領）改為 Eth1 式（[`ETH1_ADDRESS_WITHDRAWAL_PREFIX`](/part3/config/constants/#eth1_address_withdrawal_prefix)，啟用自動提領）。

質押者可以藉由簽署一個 [`BLSToExecutionChange`](/part3/containers/operations/#blstoexecutionchange) 訊息並把它廣播到網路，來做出這項變更。在某個時點，一個提議者會把該變更訊息納入一個區塊，而它會在狀態轉換中抵達這個函式。

對於 [BLS 憑證](/part3/config/constants/#bls_withdrawal_prefix)，提領憑證包含「一個公鑰之 SHA256 雜湊」的最後 31 個位元組。那個公鑰是該驗證者的提領金鑰，有別於它的簽署金鑰，雖然它常[衍生自同一個助記詞](https://eips.ethereum.org/EIPS/eip-2334#validator-keys)。藉由檢查它的雜湊，我們確認「變更訊息中所提供的公鑰」與「在初始存款中建立提領憑證的那個公鑰」是同一個。

一旦我們確信公鑰與先前承諾的相同，我們就能用它來驗證提領交易上的簽章。再次強調，這筆交易必須以驗證者的提領私鑰、而非其平常的簽署金鑰來簽署。

驗證過簽章之後，我們終於能夠、且不可逆轉地，把該驗證者的提領憑證從 BLS 式更新為 Eth1 式。

|||
|-|------|
| 使用&nbsp;者 | [`process_operations()`](/part3/transition/block/#def_process_operations) |
| 使用 | [`compute_signing_root()`](/part3/helper/misc/#def_compute_signing_root), [`compute_domain()`](/part3/helper/misc/#def_compute_domain), [`bls.Verify()`](/part3/helper/crypto/#bls-signatures) |
| 亦見 | [`BLS_WITHDRAWAL_PREFIX`](/part3/config/constants/#bls_withdrawal_prefix), [`BLSToExecutionChange`](/part3/containers/operations/#blstoexecutionchange) |

#### 同步聚合處理

<a id="def_process_sync_aggregate"></a>

```python
def process_sync_aggregate(state: BeaconState, sync_aggregate: SyncAggregate) -> None:
    # Verify sync committee aggregate signature signing over the previous slot block root
    committee_pubkeys = state.current_sync_committee.pubkeys
    participant_pubkeys = [pubkey for pubkey, bit in zip(committee_pubkeys, sync_aggregate.sync_committee_bits) if bit]
    previous_slot = max(state.slot, Slot(1)) - Slot(1)
    domain = get_domain(state, DOMAIN_SYNC_COMMITTEE, compute_epoch_at_slot(previous_slot))
    signing_root = compute_signing_root(get_block_root_at_slot(state, previous_slot), domain)
    assert eth_fast_aggregate_verify(participant_pubkeys, signing_root, sync_aggregate.sync_committee_signature)

    # Compute participant and proposer rewards
    total_active_increments = get_total_active_balance(state) // EFFECTIVE_BALANCE_INCREMENT
    total_base_rewards = Gwei(get_base_reward_per_increment(state) * total_active_increments)
    max_participant_rewards = Gwei(total_base_rewards * SYNC_REWARD_WEIGHT // WEIGHT_DENOMINATOR // SLOTS_PER_EPOCH)
    participant_reward = Gwei(max_participant_rewards // SYNC_COMMITTEE_SIZE)
    proposer_reward = Gwei(participant_reward * PROPOSER_WEIGHT // (WEIGHT_DENOMINATOR - PROPOSER_WEIGHT))

    # Apply participant and proposer rewards
    all_pubkeys = [v.pubkey for v in state.validators]
    committee_indices = [ValidatorIndex(all_pubkeys.index(pubkey)) for pubkey in state.current_sync_committee.pubkeys]
    for participant_index, participation_bit in zip(committee_indices, sync_aggregate.sync_committee_bits):
        if participation_bit:
            increase_balance(state, participant_index, participant_reward)
            increase_balance(state, get_beacon_proposer_index(state), proposer_reward)
        else:
            decrease_balance(state, participant_index, participant_reward)
```

與證明的處理方式類似，信標區塊提議者在它的區塊中納入「與它對鏈之本地觀點相符」的同步委員會投票的一個聚合。具體而言，同步委員會投票是針對「提議者在前一個時段所見到的鏈頭區塊」。（如果前一個時段是空的，那麼鏈頭區塊會是來自一個更早的時段。）

我們把這些投票對照我們對鏈的本地觀點加以驗證，如果它們相符，我們就獎勵投了票的參與者。如果它們與我們的本地觀點不符，那麼整個區塊就無效：它在另一個分支上。

為了進行驗證，我們形成前一個時段之區塊的簽署根，並混入 `DOMAIN_SYNC_COMMITTEE`。然後我們檢查「[`SyncAggregate`](/part3/containers/operations/#syncaggregate) 中收到的聚合簽章」是否能對照它驗證通過，使用「宣稱簽署了它之驗證者」的聚合公鑰。如果簽署根（也就是鏈頭區塊）有誤、或參與者的串列有誤，那麼驗證就會失敗，而區塊無效。

與提議者獎勵一樣、但與證明獎勵不同，同步委員會獎勵不以參與者的有效餘額加權。這已經由委員會選取過程處理掉了——該過程以驗證者的有效餘額為「被選取的機率」加權。

逐一檢視這些計算：

  - `total_active_increments`：整個活躍驗證者集合的有效餘額總和，以 [`EFFECTIVE_BALANCE_INCREMENT`](/part3/config/preset/#effective_balance_increment) 正規化，以給出增量的總數。
  - `total_base_rewards`：本紀元所有驗證者因所有職責而將被頒發的最大獎勵。以稍早建立的[符號](/part3/transition/epoch/#reward-and-penalty-calculations)而言，它至多是 $NB$。
  - `max_participant_rewards`：在這個時段中將給予整個同步委員會的總獎勵數額。
  - `participant_reward`：每個參與驗證者的獎勵，以及每個不參與驗證者的懲罰。
  - `proposer_reward`：參與者獎勵的七分之一。

每個投了票的委員會成員收到一筆 `participant_reward` 的獎勵，而提議者另外收到這的七分之一。

每個未能投票的委員會成員收到一筆 `participant_reward` 的懲罰，而提議者什麼都收不到。

以我們的[符號](/part3/transition/epoch/#reward-and-penalty-calculations)而言，每個時段同步委員會所造成的最大發行量（獎勵）如下。

$$
I_S = \frac{W_y}{32 \cdot W_{\Sigma}}NB
$$

每紀元的獎勵是這的三十二倍。提議者就同步聚合而言的最大獎勵：

$$
I_{S_P} = \frac{W_p}{W_{\Sigma} - W_p}I_S
$$

|||
|-|------|
| 使用&nbsp;者 | [`process_operations()`](/part3/transition/block/#def_process_operations) |
| 使用 | [`get_domain()`](/part3/helper/accessors/#def_get_domain), [`compute_signing_root()`](/part3/helper/misc/#def_compute_signing_root), [`eth_fast_aggregate_verify()`](/part3/helper/crypto/#def_eth_fast_aggregate_verify), [`get_total_active_balance()`](/part3/helper/accessors/#def_get_total_active_balance), [`get_base_reward_per_increment()`](/part3/transition/epoch/#def_get_base_reward_per_increment), [`increase_balance()`](/part3/helper/mutators/#def_increase_balance), [`decrease_balance()`](/part3/helper/mutators/#decrease_balance) |
| 亦見 | [Incentivization weights](/part3/config/constants/#incentivization-weights), [`SYNC_COMMITTEE_SIZE`](/part3/config/preset/#sync_committee_size) |

## 初始化狀態 <!-- /part3/initialise/ -->

### 引言

TODO: rework and synthesis - this text is from the original Genesis.

在以太坊信標鏈創世被觸發之前，對每個以太坊工作量證明區塊，令 `candidate_state = initialize_beacon_state_from_eth1(eth1_block_hash, eth1_timestamp, deposits)`，其中：

  - `eth1_block_hash` 是該以太坊工作量證明區塊的雜湊
  - `eth1_timestamp` 是對應於 `eth1_block_hash` 的 Unix 時間戳
  - `deposits` 是所有存款的序列，依時間順序排列，直到（並含）雜湊為 `eth1_block_hash` 的區塊

工作量證明區塊只有在「至少 `SECONDS_PER_ETH1_BLOCK` ` * ` `ETH1_FOLLOW_DISTANCE` 秒之久」之後才可被考量（即 `eth1_timestamp` ` + ` `SECONDS_PER_ETH1_BLOCK` ` * ` `ETH1_FOLLOW_DISTANCE` ` <= ` `current_unix_time`）。由於這項約束，如果 `GENESIS_DELAY` ` < ` `SECONDS_PER_ETH1_BLOCK` ` * ` `ETH1_FOLLOW_DISTANCE`，那麼 `genesis_time` 就可能發生在「時間/狀態首次被知曉」之前。各個值應被配置以避免這種情況。

### 初始化

又稱創世。

這個輔助函式只用於為純粹的 Capella 測試網與測試初始化狀態。

<a id="def_initialize_beacon_state_from_eth1"></a>

```python
def initialize_beacon_state_from_eth1(eth1_block_hash: Hash32,
                                      eth1_timestamp: uint64,
                                      deposits: Sequence[Deposit],
                                      execution_payload_header: ExecutionPayloadHeader=ExecutionPayloadHeader()
                                      ) -> BeaconState:
    fork = Fork(
        previous_version=CAPELLA_FORK_VERSION,  # [Modified in Capella] for testing only
        current_version=CAPELLA_FORK_VERSION,  # [Modified in Capella]
        epoch=GENESIS_EPOCH,
    )
    state = BeaconState(
        genesis_time=eth1_timestamp + GENESIS_DELAY,
        fork=fork,
        eth1_data=Eth1Data(block_hash=eth1_block_hash, deposit_count=uint64(len(deposits))),
        latest_block_header=BeaconBlockHeader(body_root=hash_tree_root(BeaconBlockBody())),
        randao_mixes=[eth1_block_hash] * EPOCHS_PER_HISTORICAL_VECTOR,  # Seed RANDAO with Eth1 entropy
    )

    # Process deposits
    leaves = list(map(lambda deposit: deposit.data, deposits))
    for index, deposit in enumerate(deposits):
        deposit_data_list = List[DepositData, 2**DEPOSIT_CONTRACT_TREE_DEPTH](*leaves[:index + 1])
        state.eth1_data.deposit_root = hash_tree_root(deposit_data_list)
        process_deposit(state, deposit)

    # Process activations
    for index, validator in enumerate(state.validators):
        balance = state.balances[index]
        validator.effective_balance = min(balance - balance % EFFECTIVE_BALANCE_INCREMENT, MAX_EFFECTIVE_BALANCE)
        if validator.effective_balance == MAX_EFFECTIVE_BALANCE:
            validator.activation_eligibility_epoch = GENESIS_EPOCH
            validator.activation_epoch = GENESIS_EPOCH

    # Set genesis validators root for domain separation and chain versioning
    state.genesis_validators_root = hash_tree_root(state.validators)

    # Fill in sync committees
    # Note: A duplicate committee is assigned for the current and next committee at genesis
    state.current_sync_committee = get_next_sync_committee(state)
    state.next_sync_committee = get_next_sync_committee(state)

    # Initialize the execution payload header
    state.latest_execution_payload_header = execution_payload_header

    return state
```

每個狀態欄位都以它的 [SSZ 預設值](/part2/building_blocks/ssz/#default-values)開始，除非明確地提供了一個值。所以，舉例來說，`state.next_withdrawal_index` 會被初始化為零，而 `state.historical_summaries` 被初始化為一個空串列。

### 創世狀態

每當 `is_valid_genesis_state(candidate_state)` 第一次為 `True` 時，就令 `genesis_state = candidate_state`。

<a id="def_is_valid_genesis_state"></a>

```python
def is_valid_genesis_state(state: BeaconState) -> bool:
    if state.genesis_time < MIN_GENESIS_TIME:
        return False
    if len(get_active_validator_indices(state, GENESIS_EPOCH)) < MIN_GENESIS_ACTIVE_VALIDATOR_COUNT:
        return False
    return True
```

TODO

### 創世區塊

令 `genesis_block = BeaconBlock(state_root=hash_tree_root(genesis_state))`。

TODO

## 分叉選擇 <!-- /part3/forkchoice/ -->

### 引言

信標鏈的分叉選擇與主狀態轉換規格分開記載。和主規格一樣，分叉選擇規格是增量式的，較晚的版本只指明「自前一個版本以來的變更」。在註解主規格時，我把各個增量版本合併成單一一份最新的文件。然而在以下內容中，我會分開處理原本的 [Phase 0 分叉選擇](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/fork-choice.md)與增量的 [Bellatrix 分叉選擇](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/bellatrix/fork-choice.md)更新，因為後者主要引入的是合併過渡特有的一次性功能。

#### 什麼是分叉選擇？

如[共識引言](/part2/consensus/preliminaries/#fork-choice-rules)所描述，分叉選擇規則（fork choice rule）是「一個節點在給定它可得的資訊之下，決定哪個區塊是鏈的『最佳』鏈頭」的手段。一個良好的分叉選擇規則，會使節點的網路最終收斂到同一條正典鏈：它能一致地解決分叉，即使在某種程度的故障或敵對行為之下也是如此。

以太坊的權益證明共識引入了一個 [`Store`](/part3/forkchoice/phase0/#store) 物件，它包含「判定一個最佳鏈頭所必需的所有資料」。一個節點的 Store 是它分叉選擇規則的「真理來源」（source of truth）。以古典共識的術語來說，它是一個節點的本地觀點：一個節點對網路狀態所擁有的所有相關資訊。分叉選擇規則可被刻劃為一個函式 $\text{GetHead}(\text{Store}) \rightarrow \text{HeadBlock}$。

在合併事件期間，信標鏈的分叉選擇被臨時擴增，使其能考量 Eth1 鏈上的區塊，以協議哪一個（在潛在的多個候選者之中）會成為終端工作量證明區塊。

#### 概觀

以太坊的分叉選擇由 LMD GHOST 分叉選擇規則構成，並被 Casper FFG 分叉選擇規則所修改（約束）。Casper FFG 規則藉由「只容許『後裔自上一個已最終確定[^fn-last-finalised]檢查點』的區塊作為鏈頭的候選者」來修改 LMD GHOST 分叉選擇。所有更早的分支實際上都被從一個節點對網路狀態的本地觀點中修剪掉。

[^fn-last-finalised]: 我在這裡做了簡化。LMD GHOST 在任何一個時刻只能考量「上一個已證成檢查點」的後裔。但上一個已證成檢查點可以改變。LMD GHOST 絕不會考量上一個已最終確定檢查點之前的分支。關於這稍後會多談。

<a id="img_annotated_forkchoice_gasper"></a>
<figure class="diagram" style="width: 90%">

![Diagram of a block tree showing that Casper FFG finalises the early chain up to a checkpoint and LMD GHOST handles fork choice after that.](images/diagrams/annotated-forkchoice-gasper.svg)

<figcaption>

Casper FFG 的角色是最終確定一個檢查點。已最終確定檢查點之前的歷史，是一條線性的區塊鏈，所有分支都被修剪掉。LMD GHOST 被用來在任何時候選出最佳的鏈頭區塊。LMD GHOST 受 Casper FFG 約束，意思是它只在已最終確定檢查點之後的區塊樹上運作。

</figcaption>
</figure>

這個組合[後來被稱為](https://arxiv.org/abs/2003.03052)「Gasper」，[乍看之下](https://ethresear.ch/t/beacon-chain-casper-mini-spec/2760?u=benjaminion)顯得相對簡單。然而，各種邊界案例的出現、以及一連串源源不絕的潛在攻擊，已導致第三方研究人員[宣稱](https://arxiv.org/pdf/2009.04987.pdf)「Gasper 協定是複雜的」。而那番話，還是在實作我們將在以下各節檢視的許多修正之前說的。Vitalik 本人[曾寫道](https://notes.ethereum.org/@vbuterin/single_slot_finality#Bad-news-hybrid-consensus-mechanisms-actually-have-many-unavoidable-problems)：

> Casper FFG 最終確定與 LMD GHOST 分叉選擇之間的「介面」是顯著複雜性的一個來源，導致了若干攻擊——這些攻擊需要相當複雜的修補才能修復，而更多的弱點仍定期被發現。

儘管有這一切，我們今天仍愉快地在 Gasper 協定之上運行以太坊。我們繼續增量式地加入「對抗已知攻擊」的防禦，而有朝一日我們可能完全脫離 Gasper——也許轉向一個[單時段最終性](https://ethresear.ch/t/reorg-resilience-and-security-in-post-ssf-lmd-ghost/14164?u=benjaminion)協定，或轉向 [Casper CBC](https://medium.com/@jonchoi/ethereum-casper-101-7a851a4f1eb0#c979)。同時，Gasper 在實務上正證明自己「夠好」。[^fn-gasper-weaknesses]

[^fn-gasper-weaknesses]: Goldfish 那篇〈No More Attacks on Proof-of-Stake Ethereum?〉[論文](https://arxiv.org/pdf/2209.03255.pdf)的附錄 C.1，對 Gasper 共識的已知弱點是一個有用的概觀。

#### 範圍與術語

這些分叉選擇規格文件並不涵蓋整個機制。它們大體上只關乎 LMD GHOST 分叉選擇；Casper FFG 那一面的事情（證成與最終確定）[在主狀態轉換規格中](/part3/transition/epoch/#justification-and-finalization)處理。

證明（attestation）、投票（vote）與訊息（message）這幾個詞經常出現。一筆證明是[三個投票](/part3/containers/dependencies/#attestationdata)的集合：一個為來源檢查點的投票、一個為目標檢查點的投票，以及一個為鏈頭區塊的投票。來源與目標投票被 Casper FFG 使用，而鏈頭投票被 LMD GHOST 使用。在以下各節中我們主要關注鏈頭投票，除非另有說明。LMD GHOST 鏈頭投票也稱為訊息，即「LMD」中的「M」。

我們討論證明之處，它們可以是來自一個驗證者的單一一筆證明，也可以是「包含多個做出相同那組投票之驗證者的證明」的聚合證明。從脈絡會清楚看出適用的是哪一種。

#### 解讀開發者黑話

有時你會聽到協定開發者說一些略為晦澀的話，像是「我們可以在分叉選擇中處理那個」。例如「我們可以透過分叉選擇來處理審查」。

當我們理解「一個節點的分叉選擇規則是它對『偏好追隨、或偏好不追隨哪一條鏈』的表達」時，這種說法就說得通了。沒有任何誠實的節點想要追隨「包含無效區塊（依狀態轉換而言）」的一條鏈，所以所有誠實節點的分叉選擇，絕不會選出一個「祖先中有一個無效區塊」的鏈頭區塊。

類似地，節點可以修改它們的分叉選擇規則，使得「帶有看似審查交易之區塊」的分支絕不會被選中。如果擁有足夠多驗證者的節點這麼做，那麼任何這樣的區塊都會被孤立，強烈地勸阻審查。當然，這是雙向的。一個政府可以宣布分叉選擇必須忽略「帶有『「不」審查交易之區塊』」的任何分支。如果有足夠多的驗證者——超過半數——選擇遵從，那麼整條鏈就會變得會審查。

分叉選擇的目標是讓網路收斂到單一一個歷史，所以有一個強烈的激勵去試圖與自己的對等節點達成一致。然而，它也提供了一個機制，可被用來（也許作為社會協調的一個結果）對「哪種區塊最終被納入那個歷史」抱持立場。

#### 歷史

[TODO: insert link to history of PoS]::

權益證明以太坊有一段悠久的歷史，我們會在別處回顧它。以下里程碑對於當前的 Casper FFG 加 LMD GHOST 實作是重要的。

Vitalik 在 2018 年 7 月 31 日發布了信標鏈權益證明共識最初的[迷你規格](https://ethresear.ch/t/beacon-chain-casper-mini-spec/2760?u=benjaminion)，那是在我們放棄「把以太坊轉向 PoS」的先前設計之後不久。最初的設計使用 IMD GHOST（即時訊息驅動 GHOST），其中證明在分叉選擇中有一段有限的存續期[^fn-imd-ghost]。由於對 IMD 穩定性特質的疑慮，IMD GHOST 在 2018 年 11 月[被改為](https://ethresear.ch/t/beacon-chain-casper-mini-spec/2760/17?u=benjaminion) LMD GHOST（最新訊息驅動 GHOST）。

[^fn-imd-ghost]: 如果我理解正確的話。IMD GHOST 的痕跡如今很難找到，這大概是好事。

[最初的分叉選擇規格](https://github.com/ethereum/consensus-specs/blob/a103e79e676ca08cac0040f60c90fecf7e2ea3f2/specs/core/0_fork-choice.md)在 2019 年 4 月被發布到 GitHub，僅僅 96 行。[當前的 Phase 0 分叉選擇規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/fork-choice.md)有 576 行。

各種議題已使分叉選擇規格在複雜性上膨脹起來。

2019 年 8 月，有人[發現](https://ethresear.ch/t/decoy-flip-flop-attack-on-lmd-ghost/6001?u=benjaminion)了對 LMD GHOST 的一種「誘餌翻轉攻擊」（decoy flip-flop attack），可被一個對手用來延遲最終確定（延遲一段有限的時間）。對抗這的防禦，是[加上一個檢查](https://github.com/ethereum/consensus-specs/pull/1466/files)，確認新被考量的證明只來自當前或先前紀元。我們會在 [`validate_on_attestation()`](/part3/forkchoice/phase0/#attestation-timeliness) 之下涵蓋這一點。

2019 年 9 月，有人[發現](https://ethresear.ch/t/analysis-of-bouncing-attack-on-ffg/6113?u=benjaminion)了對 Casper FFG 的一種「彈跳攻擊」（bouncing attack），可以無限期地延遲最終確定。直到 Capella 規格發布之前，我們對此有[一個修正](https://ethresear.ch/t/prevention-of-bouncing-attack-on-ffg/6114?u=benjaminion)，它只容許分叉選擇的已證成檢查點在一個紀元的早期部分被更新。這個修正在 Capella 升級中被移除，因為它為分叉選擇增添了顯著的複雜性，而且無論如何都可以藉由分裂誠實驗證者的觀點而被[繞過](https://notes.ethereum.org/@fradamt/Sy6PzcRdt)。彈跳攻擊非常難以設置，而有能力做這件事的對手大概能以更有趣的方式攻擊鏈。彈跳攻擊及其原本的修正，仍[在 Bellatrix 版中有記載](/../bellatrix/part3/forkchoice/phase0/#the-bouncing-attack)。

大約在 2019 年 11 月，[人們明白了](https://notes.ethereum.org/Fj-gVkOSTpOyUx-zkWjuwg?view)：為了把 Casper FFG 正確地套用到 LMD GHOST，有必要從分叉選擇中過濾掉「不可行的分支」。這在[為何要修剪不可行的分支？](/part3/forkchoice/phase0/#why-prune-unviable-branches)那一節中詳細討論。

2021 年 7 月，有人[發現](https://notes.ethereum.org/@hww/fork-choice-store-inconsistency)了一個邊界案例，其中（如果 1/3 的驗證者準備好被罰沒）「store 的已證成檢查點必須是已最終確定檢查點之後裔」這項不變式可能變得被違反。對 [`on_tick()`](/part3/forkchoice/phase0/#on_tick) 處理器的[一個修正](https://github.com/ethereum/consensus-specs/pull/2518)被實作出來，以維持這項不變式。

2021 年 11 月，有人在 [`on_block()`](/part3/forkchoice/phase0/#on_block) 處理器中[發現](https://notes.ethereum.org/@djrtwo/S1ZGAXhwK)了一些過度複雜的邏輯，它可能導致 Store 保留不一致的已最終確定與已證成檢查點，這進而會使 [`filter_block_tree()`](/part3/forkchoice/phase0/#filter_block_tree) 失敗。要觸發這個故障，本來得有超過三分之一的驗證者被罰沒，但[隨之而來的修正](https://github.com/ethereum/consensus-specs/pull/2727)結果無論如何都是個不錯的簡化。

[提議者增益](/part3/forkchoice/phase0/#proposer-boost)（proposer boost）也在 2021 年 11 月[被加入](https://github.com/ethereum/consensus-specs/pull/2730)。這是對抗「對 LMD GHOST 之潛在[平衡攻擊](https://ethresear.ch/t/a-balancing-attack-on-gasper-the-current-candidate-for-eth2s-beacon-chain/8079?u=benjaminion)」的一項防禦——平衡攻擊可能阻止 Casper FFG 達成最終確定。我們會在[提議者增益](/part3/forkchoice/phase0/#proposer-boost)那一節詳細涵蓋這一點。

2022 年 1 月發布了[一種新型](https://ethresear.ch/t/balancing-attack-lmd-edition/11853?u=benjaminion)的平衡攻擊，它仰賴攻擊者的驗證者做出模稜兩可的證明（在同一個時段做出多筆不同的證明）。為了對抗這，2022 年 3 月加入了一項[對抗模稜兩可索引的防禦](https://github.com/ethereum/consensus-specs/pull/2845)。我們會在講到 [`on_attester_slashing()`](/part3/forkchoice/phase0/#equivocation_balancing_attack) 處理器時討論這一點。這項防禦在 Capella 規格更新中得到強化，做法是把所有被罰沒的驗證者排除在「對分叉選擇有影響力」之外。

2022 年上半年發現了數個涉及「未實現之證成」（unrealised justification）的議題，它們源自 2019 年 11 月「過濾可行區塊」的修正。第一，一種[未實現證成鏈重組](https://notes.ethereum.org/@adiasg/unrealized-justification)攻擊，它容許一個紀元第一個區塊的提議者，輕易地把前一個紀元末尾多達九個區塊分叉掉。那個攻擊的一個變體也被發現能導致驗證者做出可罰沒的證明。第二，一種[證成扣留攻擊](https://hackmd.io/o9tGPQL2Q4iH3Mg7Mma9wQ)，一個對手可用它在一個紀元的開頭重組任意數目的區塊。這些議題在 Capella 規格更新中藉由它所引入的「拉起末梢」（pull up tips）與[未實現證成邏輯](/part3/forkchoice/phase0/#unrealised-justification)而被處理。

讀者可能從這份議題清單推斷出，分叉選擇是棘手難纏、極難推理的，而讀者不會錯。對分叉選擇規則的一些早該進行的[形式驗證](/part3/forkchoice/phase0/#formal-proofs)工作最近已完成。它力求證明某些理想的特質，例如「一個遵循規則的誠實驗證者絕不可能做出可罰沒的證明」。

我們會在以下兩節逐步講解分叉選擇規格時，更詳細地研究上述每一個議題。

  - [Phase 0 分叉選擇](/part3/forkchoice/phase0/)是主要的分叉選擇規格。
  - [Bellatrix 分叉選擇](/part3/forkchoice/bellatrix/)涵蓋合併前後對分叉選擇的變更。

請注意，[Capella 升級](/part4/history/capella/)包含了對分叉選擇規格的一次[大幅改寫](https://github.com/ethereum/consensus-specs/pull/3290)。這次改寫移除了彈跳攻擊修正，並引入了對抗一種新攻擊的「拉起末梢」防禦，諸如此類。以下各節基於更新後的 Capella 版本，但先前的註解版分叉選擇[仍然可得](/../bellatrix/part3/forkchoice/)。所有這些變更都在 Capella 之前悄悄地推出，埋藏在各種客戶端軟體更新之中，而更新後的規格被按住，直到 Capella 升級本身才釋出[^fn-fork-choice-updates]。這些議題的一次[公開揭露](https://notes.ethereum.org/@djrtwo/2023-fork-choice-reorg-disclosure)，在 Capella 升級數週後做出。

[^fn-fork-choice-updates]: 當分叉選擇被發現有議題時，常見的做法是在它們被公開之前，於客戶端發布版中「悄悄地」修正它們。弔詭的是，對分叉選擇規則的變更不會破壞共識，而且通常不需要在客戶端中同時啟用。像 Capella 這樣的硬分叉升級確保所有節點運營者出於必要都升級到了最新的軟體版本，屆時公布問題與修正的細節就是安全的。即使在強制升級之間，也要讓你的軟體保持最新——這是其中一個好理由。

### Phase 0 分叉選擇 <!-- /part3/forkchoice/phase0/ -->

本節涵蓋 [Phase 0 分叉選擇](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/fork-choice.md)文件。它基於 Capella、[v1.3.0](https://github.com/ethereum/consensus-specs/tree/v1.3.0) 規格發布版本。若想看另一種講法，我推薦 [Vitalik 的註解版分叉選擇](https://github.com/ethereum/annotated-spec/blob/master/phase0/fork-choice.md)文件。

下方以區塊引言呈現的內容（帶有側邊欄）是從 specs 儲存庫一字不差地複製過來的，所有函式程式碼也是如此。

> 與一個 `store` 相關的鏈頭區塊根，被定義為 `get_head(store)`。在創世時，令 `store = get_forkchoice_store(genesis_state, genesis_block)`，並藉由運行以下各項來更新 `store`：
>
>   - 每當 `time > store.time` 時（其中 `time` 是當前 Unix 時間）運行 `on_tick(store, time)`
>   - 每當一個區塊 `block: SignedBeaconBlock` 被收到時運行 `on_block(store, block)`
>   - 每當一筆證明 `attestation` 被收到時運行 `on_attestation(store, attestation)`
>   - 每當一筆證明者罰沒 `attester_slashing` 被收到時運行 `on_attester_slashing(store, attester_slashing)`
>
> 以上任何處理器若觸發一個未被處理的例外（例如一個失敗的 assert 或一次超出範圍的串列存取），都被視為無效。對處理器的無效呼叫絕不可修改 `store`。

對 Store 的更新只透過這四個處理器函式產生：[`on_tick()`](#on_tick)、[`on_block()`](#on_block)、[`on_attestation()`](#on_attestation) 與 [`on_attester_slashing()`](#on_attester_slashing)。這是分叉選擇用以獲得它對世界之知識的四種感官。

> _注意_：
><!-- markdownlint-disable ol-prefix -->
> 1) **閏秒**：在閏秒前後，時段會持續 `SECONDS_PER_SLOT` `+ 1` 或 `SECONDS_PER_SLOT` `- 1` 秒。這由 [UNIX 時間](https://en.wikipedia.org/wiki/Unix_time)自動處理。

閏秒[在 2035 年之後](https://www.timeanddate.com/news/astronomy/end-of-leap-seconds-2022)將不再發生。我們在那之後可以移除這條注記。

> 2) **誠實的時鐘**：誠實的節點被假定為彼此的時鐘同步在 `SECONDS_PER_SLOT` 秒之內。

在實務上，同步性假設比這更強。任何時鐘漂移超過 `SECONDS_PER_SLOT` `/` `INTERVALS_PER_SLOT`（四秒）的節點，都會遭受效能降級，並且可被視為拜占庭式的（故障的），至少對 LMD GHOST 分叉選擇而言如此。

> 3) **Eth1 資料**：[誠實驗證者文件](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md)中所指定的大 `ETH1_FOLLOW_DISTANCE`，應確保正典信標鏈的 `state.latest_eth1_data` 與正典的以太坊工作量證明鏈維持一致。若非如此，就會需要緊急的手動介入。

合併之後，執行層與共識層之間的一致性不再是個議題，雖然我們目前保留 [`ETH1_FOLLOW_DISTANCE`](/part3/config/configuration/#eth1_follow_distance)。

> 4) **手動分叉**：手動分叉可以任意地改變分叉選擇規則，但被預期在紀元轉換時施行，分叉細節反映在 `state.fork` 中。

手動分叉有時被稱為硬分叉或升級，它們是預先計畫並協調好的。它們不同於「分叉選擇規則被設計來解決」的那種非預期分叉。

> 5) **實作**：這份規格中所見的實作，是為了易於理解而建構的，而非為了在運算、空間或任何其他資源上的最佳化。若干最佳化過的替代方案可在[這裡](https://github.com/protolambda/lmd-ghost)找到。
<!-- markdownlint-enable ol-prefix -->

讀過規格之後，你可能會對「易於理解」這個說法感到困惑。然而，有好幾個演算法確實遠非高效，而切實的實作需要大量的最佳化，這點是確鑿無疑的。

### 常數

<a id="intervals_per_slot"></a>

| Name                 | Value       |
| -------------------- | ----------- |
| `INTERVALS_PER_SLOT` | `uint64(3)` |

只有在「一個時段持續時間的最初 `1 /` `INTERVALS_PER_SLOT`」期間抵達的區塊，才有資格加上[提議者分數增益](#proposer-boost)。這個時刻是時段中「驗證者被預期[發布證明](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#attesting)、宣告它們對鏈頭觀點」的時點。

在以太坊共識規格中，`INTERVALS_PER_SLOT` 恰好整除 `SECONDS_PER_SLOT`，而所有時間量都嚴格是 `uint64` 的秒數。然而，運行「與以太坊相同之基本協定」的其他鏈，可能不具備這項特質。舉例來說，[Gnosis 信標鏈](https://docs.gnosischain.com/specs)有五秒的時段。我們為了支援這一點，把 Teku 的內部時鐘[從秒改為](https://github.com/ConsenSys/teku/pull/5321)毫秒，這在技術上偏離了規格，但沒有任何東西壞掉。

### 配置

<a id="proposer_score_boost"></a>

| Name                   | Value        |
| ---------------------- | ------------ |
| `PROPOSER_SCORE_BOOST` | `uint64(40)` |

>   - 提議者分數增益的價值是委員會權重的 `PROPOSER_SCORE_BOOST` 個百分點，亦即，對於委員會權重為 `committee_weight` 的時段，增益權重等於 `(committee_weight * PROPOSER_SCORE_BOOST) // 100`。

[提議者增益](#proposer-boost)是對分叉選擇規則的一項修改，它對抗所謂的[平衡攻擊](https://ethresear.ch/t/a-balancing-attack-on-gasper-the-current-candidate-for-eth2s-beacon-chain/8079?u=benjaminion)。當一個及時的區塊提議被收到時，提議者增益在分叉選擇計算中，臨時地為那個區塊的分支加上一個巨大的權重，即「被指派在那個時段作證之所有驗證者」總有效餘額的 `PROPOSER_SCORE_BOOST` 個百分點。

`PROPOSER_SCORE_BOOST` 的值隨著平衡攻擊被更徹底地分析，而隨時間有所改變。

  - Vitalik 原本[提議的緩解措施](https://notes.ethereum.org/@vbuterin/lmd_ghost_mitigation)討論使用 25% 的值。
  - 2021 年 11 月 23 日的最初實作把它[改為 70%](https://github.com/ethereum/consensus-specs/pull/2730/files)（沒有任何關於那個數字之理路的紀錄）。
  - 2022 年 5 月 9 日，作為一份詳細得多的[分析](https://notes.ethereum.org/@casparschwa/H1T0k7b85)的結果，它被[改為 33%](https://github.com/ethereum/consensus-specs/pull/2888/files)。
  - 2022 年 5 月 20 日，由於上述分析中的一個差一錯誤計算，它被[改為 40%](https://github.com/ethereum/consensus-specs/pull/2895/files)。

為 `PROPOSER_SCORE_BOOST` 選擇一個值時的基本權衡取捨，是介於「容許一個對手進行『事前』（ex-ante）或『事後』（ex-post）鏈重組」之間。把 `PROPOSER_SCORE_BOOST` 設得太高，會使一個敵對的提議者更容易進行事後重組——它給了提議者相較於驗證者投票而言不成比例的權力。把 `PROPOSER_SCORE_BOOST` 設得太低，會使一個對手更容易進行事前重組。Caspar Schwarz-Schilling 在他的 Liscon 演講〈[The game of reorgs in PoS Ethereum](https://vimeo.com/637529564)〉中很好地涵蓋了這些權衡取捨。[^fn-ex-ante-ex-post]

[^fn-ex-ante-ex-post]: 「事後」重組發生在一個提議者藉由建構於一個祖先之上、而把前一個時段的區塊孤立掉時。「事前」重組發生在一個提議者安排好「藉由遲交它自己的提議而把下一個區塊孤立掉」時。Caspar Schwarz-Schilling 做了一則不錯的 [Twitter 討論串](https://web.archive.org/web/20230630135719/https://nitter.it/casparschwa/status/1454511850821931017)說明。

### 輔助函式

#### `LatestMessage`

```python
class LatestMessage(object):
    epoch: Epoch
    root: Root
```

這只是一個便利類別，用於追蹤來自每個驗證者最近的鏈頭投票——LMD&nbsp;GHOST 中的「LM」（最新訊息）。[`Epoch`](/part3/config/types/#epoch) 是一個 `uint64` 型別，而 [`Root`](/part3/config/types/#root) 是一個 `Bytes32` 型別。Store 持有一個「驗證者索引到它們最新訊息」的對應。

#### `Store`

> `Store` 負責追蹤分叉選擇演算法所需的資訊。被追蹤的重要欄位描述如下：
>
>   - `justified_checkpoint`：用作 LMD GHOST 分叉選擇演算法起點的已證成檢查點。
>   - `finalized_checkpoint`：已知的最高已最終確定檢查點。分叉選擇只考量「不與這個檢查點相衝突」的區塊。
>   - `unrealized_justified_checkpoint` 與 `unrealized_finalized_checkpoint`：這兩者分別追蹤最高的已證成與已最終確定檢查點，不論鏈上的「**實現**」（realization）是否已發生——亦即不論狀態轉換函式內對新證明的 FFG 處理是否已發生。這與 `justified_checkpoint` 及 `finalized_checkpoint` 有一個重要的區別，因為後兩者只會追蹤「在鏈上被實現」的檢查點。請注意，對 FFG 資訊的鏈上處理只在紀元邊界發生。
>   - `unrealized_justifications`：儲存一個「區塊根到『在那個區塊中觀察到的未實現已證成檢查點』」的對應。

這些解釋性的要點是在 Capella 升級中加入的[^fn-explanatory-points]。我們會在下文適當的地方對它們加以闡述。

[^fn-explanatory-points]: 看到一些解釋如今找到了回到規格文件之路，挺有意思的——在不久前它全都被勤勉地剝除掉之後。看來人們是欣賞解釋的，我猜。

```python
class Store(object):
    time: uint64
    genesis_time: uint64
    justified_checkpoint: Checkpoint
    finalized_checkpoint: Checkpoint
    unrealized_justified_checkpoint: Checkpoint
    unrealized_finalized_checkpoint: Checkpoint
    proposer_boost_root: Root
    equivocating_indices: Set[ValidatorIndex]
    blocks: Dict[Root, BeaconBlock] = field(default_factory=dict)
    block_states: Dict[Root, BeaconState] = field(default_factory=dict)
    checkpoint_states: Dict[Checkpoint, BeaconState] = field(default_factory=dict)
    latest_messages: Dict[ValidatorIndex, LatestMessage] = field(default_factory=dict)
    unrealized_justifications: Dict[Root, Checkpoint] = field(default_factory=dict)
```

一個節點的 Store 記錄它對外部世界所擁有的所有分叉選擇相關資訊。以較古典的術語來說，Store 是該節點對網路的觀點。Store 只由[四個處理器函式](#handlers)更新。

基本欄位如下。

  - `time`：上次呼叫 [`on_tick()`](#on_tick) 處理器時的牆鐘時間（Unix 時間）。理論上這是連續地更新的；在實務上每個時段只更新至少兩三次。
  - `justified_checkpoint`：我們節點對當前已證成檢查點的觀點。
  - `finalized_checkpoint`：我們節點對當前已最終確定檢查點的觀點。
  - `blocks`：我們所知道、後裔自 `finalized_checkpoint` 的所有區塊。分叉選擇規格並未描述如何修剪 Store，所以如果我們精確地遵循它，最後就會有自創世以來的所有區塊。然而，分叉選擇中只會考量「後裔自上一個已最終確定檢查點」的區塊，而已最終確定檢查點只會在高度上增加。所以對客戶端實作而言，把「屬於『不後裔自上一個已最終確定檢查點之分支』」的所有區塊（及其相關狀態）從 Store 中移除是安全的。
  - `block_states`：對 Store 中的每個區塊，我們也保留它對應的（後）狀態。這些狀態大多被用於關於證成與最終確定的資訊。
  - `checkpoint_states`：如果一個檢查點之前緊鄰著空時段，那麼該檢查點狀態就不會對應於一個區塊狀態，所以我們也儲存檢查點狀態，以 [`Checkpoint`](/part3/containers/dependencies/#checkpoint)、而非區塊根為索引。上一個已證成檢查點處的狀態，被用於驗證者餘額，以及在 [`on_attester_slashing()`](#on_attester_slashing) 處理器中驗證證明。
  - `latest_messages`：來自驗證者的最新鏈頭投票集合。當 [`on_attestation()`](#on_attestation) 處理器為一個驗證者處理一個新的鏈頭投票時，它就被加入這個集合，而舊的投票被丟棄。

以下欄位是隨著新的攻擊與防禦被發現，而在不同時間被加入的。

  - `proposer_boost_root` 是在「提議者增益作為對抗 [LMD 平衡攻擊](#proposer-boost)的防禦而被實作」時[被加入](https://github.com/ethereum/consensus-specs/pull/2730)的。只要當前區塊在一個時段的最初三分之一內抵達，它就在一個時段的持續時間內被設為該區塊的根。
  - `equivocating_indices` 集合[被加入](https://github.com/ethereum/consensus-specs/pull/2845)以對抗[模稜兩可平衡攻擊](#equivocation_balancing_attack)。它包含「被回報為犯了一項證明者罰沒違規」之任何驗證者的索引。這些驗證者必須被從分叉選擇規則的考量中移除，直到上一個已證成檢查點狀態追上「這些驗證者已被罰沒」這個事實為止。
  - `unrealized_justified_checkpoint` 與 `unrealized_finalized_checkpoint` 欄位是在 Capella 更新中[被加入](https://github.com/ethereum/consensus-specs/pull/3290)的。它們被用來避免舊版 `filter_block_tree()` 所遭受的某些[未實現證成](#unrealised-justification)問題。
  - 同樣在 Capella 更新中被加入的是 `unrealized_justifications`，它是一個「區塊根到未實現證成檢查點」的對應。它由 [`compute_pulled_up_tip()`](#compute_pulled_up_tip) 維護。對每個區塊，它儲存「對該區塊的後狀態運行 [`process_justification_and_finalization()`](/part3/transition/epoch/#def_process_justification_and_finalization) 所得出的已證成檢查點」。在信標狀態中，那項計算只在紀元邊界進行，所以在分叉選擇之內，我們把那個結果稱為「未實現的」。

對非 Python 行家：[`Set`](https://docs.python.org/3/library/typing.html#typing.Set) 與 [`Dict`](https://docs.python.org/3/library/typing.html#typing.Dict) 是 Python 的泛型型別。`Set` 是一個無序的物件集合；`Dict` 提供鍵—值查找。

#### `is_previous_epoch_justified`

```python
def is_previous_epoch_justified(store: Store) -> bool:
    current_slot = get_current_slot(store)
    current_epoch = compute_epoch_at_slot(current_slot)
    return store.justified_checkpoint.epoch + 1 == current_epoch
```

基於 Store 中的當前時間，如果前一個紀元起始處的檢查點已被證成——也就是已收到一個超多數的 Casper FFG 投票——這個函式就回傳 `True`。

|||
|-|------|
| 使用&nbsp;者 | [`filter_block_tree()`](#filter_block_tree) |

#### `get_forkchoice_store`

> 所提供的錨定狀態（anchor-state）會被視為一個受信任的狀態，不會回滾到它之前。對一個全客戶端而言，這應該是創世狀態。
>
> _注意_ 就分叉選擇而言，區塊標頭可與區塊互換。規格很可能會轉用標頭，以減少測試向量的開銷並有更好的封裝。完整的實作把區塊作為其資料庫的一部分儲存，並且在處理正式環境的分叉選擇時往往會使用完整的區塊。

```python
def get_forkchoice_store(anchor_state: BeaconState, anchor_block: BeaconBlock) -> Store:
    assert anchor_block.state_root == hash_tree_root(anchor_state)
    anchor_root = hash_tree_root(anchor_block)
    anchor_epoch = get_current_epoch(anchor_state)
    justified_checkpoint = Checkpoint(epoch=anchor_epoch, root=anchor_root)
    finalized_checkpoint = Checkpoint(epoch=anchor_epoch, root=anchor_root)
    proposer_boost_root = Root()
    return Store(
        time=uint64(anchor_state.genesis_time + SECONDS_PER_SLOT * anchor_state.slot),
        genesis_time=anchor_state.genesis_time,
        justified_checkpoint=justified_checkpoint,
        finalized_checkpoint=finalized_checkpoint,
        unrealized_justified_checkpoint=justified_checkpoint,
        unrealized_finalized_checkpoint=finalized_checkpoint,
        proposer_boost_root=proposer_boost_root,
        equivocating_indices=set(),
        blocks={anchor_root: copy(anchor_block)},
        block_states={anchor_root: copy(anchor_state)},
        checkpoint_states={justified_checkpoint: copy(anchor_state)},
        unrealized_justifications={anchor_root: justified_checkpoint}
    )
```

`get_forkchoice_store()` 從一個錨定狀態及其對應的區塊（標頭）初始化分叉選擇 Store 物件。如前所述，錨定狀態可以是創世狀態。同樣地，當使用[檢查點同步](https://docs.teku.consensys.net/get-started/checkpoint-start)時，錨定狀態會是節點運營者所提供的已最終確定檢查點狀態，它會[被當成彷彿](https://github.com/ethereum/consensus-specs/issues/2566)是一個創世狀態來對待。無論哪一種情況，`latest_messages` 儲存一開始都會是空的。

#### `get_slots_since_genesis`

```python
def get_slots_since_genesis(store: Store) -> int:
    return (store.time - store.genesis_time) // SECONDS_PER_SLOT
```

不言自明。這是唯二使用 `store.time` 的地方之一，另一個是在 [`on_block()`](#on_block) 處理器中的提議者增益邏輯裡。

|||
|-|------|
| 使用&nbsp;者 | [`get_current_slot()`](#get_current_slot) |

#### `get_current_slot`

```python
def get_current_slot(store: Store) -> Slot:
    return Slot(GENESIS_SLOT + get_slots_since_genesis(store))
```

不言自明。[`GENESIS_SLOT`](/part3/config/constants/#genesis_slot) 通常是零。

|||
|-|------|
| 使用&nbsp;者 | [`get_voting_source()`](#get_voting_source), [`filter_block_tree()`](#filter_block_tree), [`compute_pulled_up_tip()`](#compute_pulled_up_tip), [`on_tick_per_slot`](#on_tick_per_slot), [`validate_target_epoch_against_current_time()`](#validate_target_epoch_against_current_time), [`validate_on_attestation()`](#validate_on_attestation), [`on_tick()`](#on_tick), [`on_block()`](#on_block) |
| 使用 | [`get_slots_since_genesis()`](#get_slots_since_genesis) |

#### `compute_slots_since_epoch_start`

```python
def compute_slots_since_epoch_start(slot: Slot) -> int:
    return slot - compute_start_slot_at_epoch(compute_epoch_at_slot(slot))
```

不言自明。

|||
|-|------|
| 使用&nbsp;者 | [`on_tick_per_slot()`](#on_tick_per_slot) |
| 使用 | [`compute_epoch_at_slot()`](/part3/helper/misc/#def_compute_epoch_at_slot)、[`compute_start_slot_at_epoch()`](/part3/helper/misc/#def_compute_start_slot_at_epoch) |

#### `get_ancestor`

```python
def get_ancestor(store: Store, root: Root, slot: Slot) -> Root:
    block = store.blocks[root]
    if block.slot > slot:
        return get_ancestor(store, block.parent_root, slot)
    return root
```

給定一個區塊根 `root`，`get_ancestor()` 回傳「在時段 `slot` 被發布的祖先區塊」（在同一個分支上）。如果在 `slot` 沒有區塊被發布，那麼就回傳「`slot` 之前最近被發布的祖先區塊」。

這個函式有時只被用來確認「根為 `root` 的區塊」後裔自「時段 `slot` 的某個特定區塊」，有時則實際被用來取得那個祖先區塊的根。

|||
|-|------|
| 使用 | `get_ancestor()` (recursively) |
| 使用&nbsp;者 | [`get_weight()`](#get_weight), [`filter_block_tree()`](#filter_block_tree), [`validate_on_attestation()`](#validate_on_attestation), [`on_block()`](#on_block), `get_ancestor()` (recursively) |

#### `get_weight`

```python
def get_weight(store: Store, root: Root) -> Gwei:
    state = store.checkpoint_states[store.justified_checkpoint]
    unslashed_and_active_indices = [
        i for i in get_active_validator_indices(state, get_current_epoch(state))
        if not state.validators[i].slashed
    ]
    attestation_score = Gwei(sum(
        state.validators[i].effective_balance for i in unslashed_and_active_indices
        if (i in store.latest_messages
            and i not in store.equivocating_indices
            and get_ancestor(store, store.latest_messages[i].root, store.blocks[root].slot) == root)
    ))
    if store.proposer_boost_root == Root():
        # Return only attestation score if ``proposer_boost_root`` is not set
        return attestation_score

    # Calculate proposer score if ``proposer_boost_root`` is set
    proposer_score = Gwei(0)
    # Boost is applied if ``root`` is an ancestor of ``proposer_boost_root``
    if get_ancestor(store, store.proposer_boost_root, store.blocks[root].slot) == root:
        committee_weight = get_total_active_balance(state) // SLOTS_PER_EPOCH
        proposer_score = (committee_weight * PROPOSER_SCORE_BOOST) // 100
    return attestation_score + proposer_score
```

在這裡我們找到了 GHOST[^fn-ghost-acronym] 協定的精髓：一個區塊的權重，是「為那個區塊投的票」之總和，「_加上_」「為它所有後裔區塊投的票」。我們在計算一個區塊的權重時納入「為後裔投的票」，因為「為一個區塊投的票」也隱含地是「為那個區塊所有祖先投的票」——如果一個特定的區塊被納入鏈上，它所有的祖先也必定被納入。換個方式說，我們把驗證者視為在為整個分支投票，而非只為它們的葉投票。

[^fn-ghost-acronym]: 「貪婪最重觀察子樹」（Greedy Heaviest-Observed Sub-Tree），由 [Sompolinsky 與 Zohar](https://eprint.iacr.org/2013/881.pdf) 命名。

暫時忽略提議者增益的部分，所進行的主要計算如下。

```none
    state = store.checkpoint_states[store.justified_checkpoint]
    unslashed_and_active_indices = [
        i for i in get_active_validator_indices(state, get_current_epoch(state))
        if not state.validators[i].slashed
    ]
    attestation_score = Gwei(sum(
        state.validators[i].effective_balance for i in unslashed_and_active_indices
        if (i in store.latest_messages
            and i not in store.equivocating_indices
            and get_ancestor(store, store.latest_messages[i].root, store.blocks[root].slot) == root)
    ))
```

我們只考量活躍且未被罰沒之驗證者的投票。（被罰沒的驗證者可能仍在退出佇列中，技術上是「活躍的」，至少依 [`is_active_validator()`](/part3/helper/predicates/#def_is_active_validator) 而言如此。）「排除『在上一個已證成檢查點已於協定內被罰沒』之驗證者」這一點，是在 Capella 規格中加入的，以補足 [`on_attester_slashing()`](#on_attester_slashing) 處理器。它額外會排除「透過提議者罰沒被罰沒的驗證者」、以及「很久以前被罰沒（當退出佇列很長時）、且我們已從 Store 中丟棄其證明者罰沒」的驗證者。

給定一個區塊根 `root`，這把「為『後裔自那個區塊』之區塊投的所有票」加起來。更精確地說，它計算「所有『最新鏈頭投票是為 `root` 之後裔、或為 `root` 本身』的驗證者」的有效餘額總和。正是「我們只基於每個驗證者的『_最新_』投票來進行權重計算」這一事實，使這成為「LMD」（最新訊息驅動）GHOST。

<a id="img_annotated_forkchoice_get_weight_0"></a>
<figure class="diagram" style="width: 90%">

![Diagram of a block tree with weights and latest attesting balances shown for each block.](images/diagrams/annotated-forkchoice-get-weight-0.svg)

<figcaption>

$B_N$ 是「最近的鏈頭投票是為區塊 $N$ 之驗證者」的有效餘額總和，而 $W_N$ 是「始於區塊 $N$ 之分支」的權重。

</figcaption>
</figure>

在區塊的權重 $W_x$ 與區塊的最新作證餘額 $B_x$ 之間，存在一些顯而易見的關係。

  - 對一個葉區塊 $N$（一個沒有子代的區塊），$W_N = B_N$。
  - 一個區塊的權重，是它自己的最新作證餘額，加上它直接子代之權重的總和。所以在圖中，$W_1 = B_1 + W_2 + W_3$。

這些關係可被用來藉由把結果記憶化，而避免重複大量的工作。

##### 提議者增益

2020 年 9 月，在主網創世前不久，有人發布了對 LMD GHOST 共識機制的一種理論上的「[平衡攻擊](https://arxiv.org/abs/2009.04987)」，並附有一篇 [Ethresear.ch 貼文](https://ethresear.ch/t/a-balancing-attack-on-gasper-the-current-candidate-for-eth2s-beacon-chain/8079?u=benjaminion)。

平衡攻擊容許「一個對手所控制的極少量驗證者」永久地維持一個分叉的網路，所有驗證者中有一半追隨一個分叉、一半追隨另一個。這會無限期地延遲最終確定，是一種活性失敗。由於這個攻擊仰賴「關於對手對網路擁有多少權力」的一些不切實際的假設——即對「誰能在何時看到什麼」的細粒度控制——我們覺得這個潛在攻擊對信標鏈的上線不是一個顯著的威脅。然而，對這個攻擊的[後續精進](https://arxiv.org/abs/2110.10086)看來已使它更切實可行。

「修改分叉選擇以緩解平衡攻擊」最先[由 Vitalik 提議](https://notes.ethereum.org/@vbuterin/lmd_ghost_mitigation)。這後來被稱為提議者增益，它的一個版本在 2021 年末[被採納](https://github.com/ethereum/consensus-specs/pull/2730)進共識層規格，各個客戶端團隊在 2022 年 4 月與 5 月發布了「帶有主網提議者增益支援」的版本。

對分叉選擇的變更可以在重大協定升級之外做出；並非嚴格必要讓所有客戶端實作同時做出變更，不像硬分叉升級那樣必須如此。鑑於此，支援提議者增益的主網客戶端發布版在 2022 年 4 月與 5 月的[不同時間](https://kyrianalex.substack.com/p/ethereums-7-block-reorg)做出，而使用者並未被強迫依固定的時程升級。很不幸地，網路上有混雜的節點——大約一半套用提議者增益、一半沒有——導致了信標鏈在 2022 年 5 月 25 日發生一次[七個區塊的鏈重組](https://barnabe.substack.com/p/pos-ethereum-reorg)。其結果是，後續對分叉選擇的更新，在客戶端團隊之間傾向於更緊密地協調。

##### 提議者增益細節

提議者增益修改了我們那個「只基於最新投票」、漂亮而直觀的分支權重計算，做法是為「在當前時段準時被收到的一個區塊」加上額外的權重。以這種方式，它引入了一種同步性加權。Vitalik [稱這](https://notes.ethereum.org/@vbuterin/lmd_ghost_mitigation#Proposed-solution)為「一個明確的『同步瓶頸』裝置」。簡言之，它把一個及時的區塊視為「一個帶有巨大權重的投票」，這個權重被臨時加到「它所延伸的那個分支」上。

提議者增益背後的簡單直覺，Barnabé Monnot [把它總結](https://barnabe.substack.com/p/pos-ethereum-reorg)為：「一個及時的區塊不應預期被重組掉」。就平衡攻擊而言，提議者增益被設計來壓倒「來自對手所控制驗證者」的投票，轉而容許那個及時區塊的提議者選擇將會勝出的分叉。引用 [Francesco D'Amato](https://ethresear.ch/t/view-merge-as-a-replacement-for-proposer-boost/13739?u=benjaminion#high-level-mitigation-idea-3) 的話：「總體策略是賦予誠實的提議者權力，去把它們對分叉選擇的觀點強加上去，但不給它們太多權力、不使委員會變得無關緊要。」

`store.proposer_boost_root` 的預設設定是 `Root()`。也就是「空」或「null」的 [SSZ 預設](/part2/building_blocks/ssz/#default-values)根值，所有位元組都設為零。每當一個區塊在「一個時段的最初 `1 /` `INTERVALS_PER_SLOT` 部分」期間被收到時——也就是當該區塊是及時的時候——`store.proposer_boost_root` 就被 [`on_block()`](/part3/forkchoice/phase0/#on_block) 處理器設為那個區塊的雜湊樹根。在每個時段結束時，它被 [`on_tick()`](/part3/forkchoice/phase0/#on_block) 處理器重設為 `Root()`。因此，提議者增益從「一個及時的區塊被收到」的時點起、到那個時段結束為止，對分叉選擇計算有影響，而「及時」在以太坊信標鏈上意指「在最初四秒之內」。

當分支末梢的區塊是及時的時候，提議者增益會使整個分支受到偏好。當提議者增益生效、且當前時段中那個及時的區塊（其根為 `store.proposer_boost_root`）後裔自「我們正在計算其權重的區塊」時，那個區塊的權重也會被增加，因為計算包含它所有後裔的權重。以這種方式，提議者增益加權與投票權重一樣[傳播到被增益區塊的祖先](https://github.com/ethereum/consensus-specs/pull/2760)。

提議者增益為該區塊分支加上的權重，是「被指派在那個時段作證之所有驗證者」總有效餘額的 `PROPOSER_SCORE_BOOST` 個百分點。更確切地說，它是對那個時段總有效餘額的一個近似值，由「所有驗證者的總有效餘額除以每個紀元的時段數」導出。

`PROPOSER_SCORE_BOOST` 的值隨時間有所改變，才定案於它目前的 40%。歷史、以及「目前的值如何被計算」的連結，見[那裡的描述](#proposer_score_boost)。

##### 提議者增益與遲到的區塊

提議者增益的一個副作用是：它讓客戶端能可靠地把「太晚發布的區塊」重組掉（孤立掉）。提議者可以選擇建構於遲到區塊的父代之上，而非建構於遲到的區塊之上。

一個區塊提議者本應在時段的開頭發布它的區塊，使它有時間在最初四秒內被整個委員會收到並作證。然而，合併之後，把區塊提議延遲幾秒鐘可能是有利可圖的，以收集更多的交易收入與更好的可榨取價值機會。雖然「在進入一個時段五六秒時發布」的區塊不會獲得很多票，它們在基本共識規格之下仍[很可能維持正典](https://notes.ethereum.org/@casparschwa/ByHu1XZUq)。只要下一個區塊提議者在時段結束前收到了遲到的區塊，它通常就會把它當成最佳可得鏈頭來建構於其上。[^fn-legend-late-blocks]這是不可取的，因為它懲罰了絕大多數誠實的驗證者——那些（正確地）為一個空時段投票的驗證者——剝奪了它們「正確鏈頭投票」的獎勵，甚至可能在一個紀元的開頭因「不正確的目標投票」而懲罰它們。

[^fn-legend-late-blocks]: 舉例來說，[時段 4939809](https://beaconcha.in/slot/4939809#votes) 與[時段 4939815](https://beaconcha.in/slot/4939815#votes) 的區塊幾乎沒有票，卻成為了正典。它們幾乎肯定是太晚發布的——顯然是由同一個運營者 [Legend](https://beaconcha.in/slots?q=Legend) 發布的——但發布得及時，讓下一個提議者來得及建構於它們之上。太晚發布可能是由於單純的時鐘設定錯誤，也可能是一個刻意的策略，以在合併之後獲得更多的交易收入。無論哪一種情況，它都是不可取的。

沒有提議者增益的話，下一個提議者「不建構於它太晚收到的一個區塊上」是一個會輸的策略。雖然遲到的區塊可能只有少量的票，但它一開始的票比你的區塊多，所以驗證者仍會把遲到的區塊作證為鏈頭，讓它維持正典，並把「你建構於它父代之上的替代區塊」孤立掉。

有了提議者增益，只要遲到的區塊票數少於提議者增益的百分比，誠實的提議者就能有信心：它的替代區塊會在分叉選擇中勝出夠久，使得下一個提議者會建構於那個區塊上，而非建構於它略過的那個遲到區塊上。

<a id="img_annotated_forkchoice_late_block_0"></a>
<figure class="diagram" style="width: 90%">
<div style="width: 80%">

![Diagram showing a proposer choosing whether to build on a late block or its parent.](images/diagrams/annotated-forkchoice-late-block-0.svg)

</div>
<figcaption>

區塊 $B$ 太晚發布了，遠在 4 秒的證明截止時間之後。然而，由於不誠實或設定錯誤的驗證者，它仍設法取得了少數幾筆證明（比如說，委員會的 10%）。下一個提議者應該在遲到的區塊之上建構 $C_1$，還是在它的父代之上建構 $C_2$？

</figcaption>
</figure>

<a id="img_annotated_forkchoice_late_block_1"></a>
<figure class="diagram" style="width: 90%">
<div style="width: 80%">

![Diagram showing that without proposer score boosting a proposer should build on the late block.](images/diagrams/annotated-forkchoice-late-block-1.svg)

</div>
<figcaption>

沒有提議者增益的話，唯一說得通的是建構 $C_1$，在遲到的區塊 $B$ 之上。由於 $B$ 有一些權重（儘管很小），上方的分支會在分叉選擇中勝出（如果網路在那時表現得同步）。區塊 $C_2$ 會被孤立。

</figcaption>
</figure>

<a id="img_annotated_forkchoice_late_block_2"></a>
<figure class="diagram" style="width: 90%">
<div style="width: 80%">

![Diagram showing that with proposer score boosting a proposer may build on the late block's parent.](images/diagrams/annotated-forkchoice-late-block-2.svg)

</div>
<figcaption>

有了提議者增益，$C$ 的提議者可以安全地發布 $C_1$ 或 $C_2$。由於 40% 的提議者分數增益，發布「把 $B$ 孤立掉」的區塊 $C_2$ 是安全的，因為下方的分支在該時段期間會有較大的權重。

</figcaption>
</figure>

這個策略在 Lighthouse 客戶端中的一個[實作](https://github.com/sigp/lighthouse/pull/2860)，看來在減少網路上遲到區塊的數量方面是有效的。當遲到的區塊很可能被孤立時，發布它們就被強烈地反激勵。它在某個時點可能會被[採納](https://github.com/ethereum/consensus-specs/pull/3034)為共識規格中的標準行為，但目前仍是可選的。為了避免活性失敗，有數個防護措施在場。

請注意，提議者增益一般而言並不容許驗證者把及時的區塊重組掉（也就是一次事後重組）。一個及時的區塊本應從委員會獲得足夠的票，使它永遠維持正典。

##### 提議者增益的替代方案

提議者增益並非對平衡攻擊或事前重組的一個完美解法。它使事後重組更容易達成；它不隨參與度而擴展，意味著如果只有 40% 的驗證者在線，那麼提議者就能隨意重組；當一個攻擊者控制了好幾個連續的時段、可在其上累積投票時，它可能會失效。

有人提議了一些「對 LMD GHOST 的變更或替代方案」，它們不需要提議者分數增益。

[視圖合併](https://ethresear.ch/t/view-merge-as-a-replacement-for-proposer-boost/13739?u=benjaminion)（View-merge）[^fn-view-merge-first]是一個機制，其中證明者在一個時段結束前某段時間 $\Delta$ 凍結它們的分叉選擇。然而，下一個提議者不凍結它的分叉選擇。假定的最大網路延遲是 $\Delta$，所以提議者會及時看到所有投票，而它會把它們的一份摘要——包含在它的區塊內——傳遞給所有驗證者。這讓整個網路能在一個共同的觀點上同步。平衡攻擊仰賴給網路的兩半不同的觀點，會被視圖合併所防止。

[^fn-view-merge-first]: 視圖合併，雖然不是用這個名稱，最早在 2021 年 10 月於 Ethresear.ch 貼文〈[Change fork choice rule to mitigate balancing and reorging attacks](https://ethresear.ch/t/change-fork-choice-rule-to-mitigate-balancing-and-reorging-attacks/11127?u=benjaminion)〉中為以太坊提出。關於視圖合併的更多解釋，亦見[這則 Twitter 討論串](https://web.archive.org/web/20230630135730/https://nitter.it/fradamt/status/1572884967461474306)。

Goldfish 協定——描述於論文〈[No More Attacks on Proof-of-Stake Ethereum?](https://arxiv.org/abs/2209.03255)〉中——建構於視圖合併（在那裡稱為「訊息緩衝」）之上，並加入了投票過期，使得鏈頭區塊投票幾乎立即過期（名稱由此而來——不論對錯，金魚以記性短而聞名）。所得的協定可被證明具有重組韌性，並支援快速確認。

視圖合併與 Goldfish 兩者都帶有「它們在同步條件下之特質」的漂亮證明，在相同條件下優於 Gasper。然而，它們在較為實際的非同步條件下可能表現得不那麼好。原本的視圖合併文章對「大於 2 秒的延遲」[說](https://ethresear.ch/t/change-fork-choice-rule-to-mitigate-balancing-and-reorging-attacks/11127?u=benjaminion#musings-on-latency-13)：「這很糟。」Goldfish 論文的一位作者[曾說](https://ethresear.ch/t/reorg-resilience-and-security-in-post-ssf-lmd-ghost/14164?u=benjaminion) Goldfish「對非同步極其脆弱，容許諸如任意長重組這類災難性的失敗」[^fn-goldfish-brittle]，並在[別處](https://ethresear.ch/t/a-simple-single-slot-finality-protocol/14920?u=benjaminion)說「即使單一一個時段的非同步，都可能導致一次災難性的失敗，危及任何先前已確認區塊的安全性」。至少對提議者增益而言，我們知道它在高延遲的條件下只會退化成正常的 Gasper。

[^fn-goldfish-brittle]: 要找到這段引文所指的 6.3 節，你需要看 Goldfish 論文的[原本 v1 版本](https://arxiv.org/pdf/2209.03255v1.pdf)。那一節在論文較晚的版本中被省略了。

Francesco D'Amato 在〈[Reorg resilience and security in post-SSF LMD-GHOST](https://ethresear.ch/t/reorg-resilience-and-security-in-post-ssf-lmd-ghost/14164?u=benjaminion)〉中論證：LMD GHOST 重組議題真正的根源，是我們當前基於委員會的投票：「議題的癥結在於，一個時段委員會的誠實多數，不等於『符合資格之分叉選擇權重』的多數」，因為一個對手能以來自其他時段的投票影響分叉選擇。對此的終極解方會是[單時段最終性](https://notes.ethereum.org/@vbuterin/single_slot_finality)（SSF），其中所有驗證者在每個時段都投票。SSF 距今天的切實可行還很遙遠，但它的分叉選擇的一個候選者是 [RLMD-GHOST](https://ethresear.ch/t/a-simple-single-slot-finality-protocol/14920?u=benjaminion)（最近最新訊息驅動 GHOST），它在一段可配置的時間之後把投票過期。

|||
|-|------|
| 使用&nbsp;者 | [`get_head()`](#get_head) |
| 使用 | [`get_active_validator_indices()`](/part3/helper/accessors/#def_get_active_validator_indices)、[`get_ancestor()`](#get_ancestor)、[`get_total_active_balance()`](/part3/helper/accessors/#def_get_total_active_balance) |
| 亦見 | [`on_tick()`](#on_tick)、[`on_block()`](#on_block)、[`PROPOSER_SCORE_BOOST`](#proposer_score_boost) |

#### `get_voting_source`

```python
def get_voting_source(store: Store, block_root: Root) -> Checkpoint:
    """
    Compute the voting source checkpoint in event that block with root ``block_root`` is the head block
    """
    block = store.blocks[block_root]
    current_epoch = compute_epoch_at_slot(get_current_slot(store))
    block_epoch = compute_epoch_at_slot(block.slot)
    if current_epoch > block_epoch:
        # The block is from a prior epoch, the voting source will be pulled-up
        return store.unrealized_justifications[block_root]
    else:
        # The block is not from a prior epoch, therefore the voting source is not pulled up
        head_state = store.block_states[block_root]
        return head_state.current_justified_checkpoint
```

如果給定的區塊（它是 Store 區塊樹中的一個葉區塊）來自一個較早的紀元，那麼就回傳它的[未實現證成](#unrealised-justification)。否則就回傳它後狀態中的已證成檢查點（它的已實現證成）。

回傳未實現證成被稱為「拉起」（pulling up）該區塊（或「拉一個分支的末梢」），因為它等同於對該區塊的後狀態運行紀元結束時的狀態轉換會計處理：該區塊在概念上被從它實際的時段拉起到下一個紀元的第一個時段。

Casper FFG 來源投票是「一個驗證者在投票當時相信為最高已證成」的檢查點。因此，這個函式回傳「以這個區塊為鏈頭的驗證者，在當前紀元投出一個 Casper FFG 投票時將會使用」的來源檢查點。這在 [`filter_block_tree()`](#filter_block_tree) 中有一個重要的角色，並用於[「不自我罰沒性」的形式證明](#formal-proofs)。

|||
|-|------|
| 使用&nbsp;者 | [`filter_block_tree()`](#filter_block_tree) |
| 使用 | [`compute_epoch_at_slot()`](/part3/helper/misc/#def_compute_epoch_at_slot) |

#### `filter_block_tree`

> _注意_：對 `filter_block_tree` 的外部呼叫（亦即，任何不是由這個函式中遞迴邏輯所做出的呼叫）「必須」把 `block_root` 設為 `store.justified_checkpoint`。

對 `filter_block_tree()` 唯一的外部呼叫，來自 [`get_filtered_block_tree()`](#get_filtered_block_tree)，它使用 `store.justified_checkpoint.root`。所以我們沒問題。這是[混合式 LMD GHOST](#hybrid-lmd-ghost) 的一項要求——它強制執行 Casper FFG 的分叉選擇規則。

```python
def filter_block_tree(store: Store, block_root: Root, blocks: Dict[Root, BeaconBlock]) -> bool:
    block = store.blocks[block_root]
    children = [
        root for root in store.blocks.keys()
        if store.blocks[root].parent_root == block_root
    ]

    # If any children branches contain expected finalized/justified checkpoints,
    # add to filtered block-tree and signal viability to parent.
    if any(children):
        filter_block_tree_result = [filter_block_tree(store, child, blocks) for child in children]
        if any(filter_block_tree_result):
            blocks[block_root] = block
            return True
        return False

    current_epoch = compute_epoch_at_slot(get_current_slot(store))
    voting_source = get_voting_source(store, block_root)

    # The voting source should be at the same height as the store's justified checkpoint
    correct_justified = (
        store.justified_checkpoint.epoch == GENESIS_EPOCH
        or voting_source.epoch == store.justified_checkpoint.epoch
    )

    # If the previous epoch is justified, the block should be pulled-up. In this case, check that unrealized
    # justification is higher than the store and that the voting source is not more than two epochs ago
    if not correct_justified and is_previous_epoch_justified(store):
        correct_justified = (
            store.unrealized_justifications[block_root].epoch >= store.justified_checkpoint.epoch and
            voting_source.epoch + 2 >= current_epoch
        )

    finalized_slot = compute_start_slot_at_epoch(store.finalized_checkpoint.epoch)
    correct_finalized = (
        store.finalized_checkpoint.epoch == GENESIS_EPOCH
        or store.finalized_checkpoint.root == get_ancestor(store, block_root, finalized_slot)
    )
    # If expected finalized/justified, add to viable block-tree and signal viability to parent.
    if correct_justified and correct_finalized:
        blocks[block_root] = block
        return True

    # Otherwise, branch not viable
    return False
```

`filter_block_tree()` 函式處在「LMD GHOST 與 Casper FFG 如何被栓接在一起」的核心。

基本結構相當簡單。給定一個區塊，`filter_block_tree()` 遞迴地走訪 Store 的區塊樹，以深度優先的方式造訪該區塊的後裔。當它抵達一個葉區塊（一個分支的末梢）時，如果該葉區塊作為鏈頭是「可行的」，那麼它與它所有的祖先（整個分支）都會被加入 `blocks` 串列，否則該分支會被忽略。

換句話說，這個演算法把「終止於一個不可行鏈頭區塊」的分支修剪掉，並保留「終止於一個可行鏈頭區塊」的分支。

<a id="img_annotated_viable_nonviable"></a>
<figure class="diagram" style="width: 80%">

![A diagram showing the pruning of nonviable branches.](images/diagrams/annotated-forkchoice-viable-nonviable.svg)

<figcaption>

區塊 $J$ 是 Store 的已證成檢查點。有四個後裔自它的候選鏈頭區塊。兩個是可行的（$V$），兩個是不可行的（$NV$）。「終止於可行鏈頭」之分支中的區塊由過濾器回傳；「終止於不可行鏈頭」之分支中的區塊被過濾掉。

</figcaption>
</figure>

##### 可行性

是什麼決定了一個葉區塊可行與否？

Capella 之前，「一個葉區塊要成為一個可行的鏈頭區塊」有一個相當直截了當的要求：可行的鏈頭區塊有一個「在已證成與已最終確定檢查點上與 Store 一致」的後狀態。這被封裝在以下這段來自 [Bellatrix 規格](/../bellatrix/part3/forkchoice/phase0/#filter_block_tree)的程式碼中：

```none
    correct_justified = (
        store.justified_checkpoint.epoch == GENESIS_EPOCH
        or head_state.current_justified_checkpoint == store.justified_checkpoint
    )
    correct_finalized = (
        store.finalized_checkpoint.epoch == GENESIS_EPOCH
        or head_state.finalized_checkpoint == store.finalized_checkpoint
    )
    # If expected finalized/justified, add to viable block-tree and signal viability to parent.
    if correct_justified and correct_finalized:
        blocks[block_root] = block
        return True
```

我們在 Capella 更新中所擁有的程式碼，複雜得多、也較不直觀。但在我們講到那個之前，我們需要退一步，討論為什麼我們究竟應該過濾區塊樹。

##### 為何要修剪不可行的分支？

像這樣過濾區塊樹，確保了 Casper FFG 分叉選擇規則——「追隨『包含最高高度之已證成檢查點』的鏈」——在 LMD GHOST 分叉選擇被評估之前，就被套用於區塊樹。

非常早期版本的規格，把「後裔自 Store 已證成檢查點」之任何分支的末梢，視為一個潛在的鏈頭區塊。然而，有人[發現](https://notes.ethereum.org/Fj-gVkOSTpOyUx-zkWjuwg?view)了一個情境，其中這可能導致一個死鎖，最終性在這個死鎖中將無法前進，除非驗證者讓自己被罰沒——一種活性失敗[^fn-plausible-liveness]。

[^fn-plausible-liveness]: 這個情境並不嚴格破壞 Casper FFG 的「貌似活性」（plausible liveness）特質，因為原則上，投票者可以安全地忽略 LMD GHOST 分叉選擇、切換回原本的鏈，以推進最終性。但它確實在 LMD GHOST 分叉選擇規則與「推進最終性」之間製造了一個衝突。

`filter_block_tree()` 函式[被加入](https://github.com/ethereum/consensus-specs/pull/1495)作為對這個議題的一個修正。給定一個 Store 與一個區塊根，`filter_block_tree()` 回傳「我們在『後裔自給定區塊之樹』中所知道的所有區塊」的串列，並已把「終止於某種意義上不可行之葉區塊」的任何分支修剪掉。

為了說明這個問題，考量以下各圖所示的情況，它基於該議題的[原本描述](https://notes.ethereum.org/Fj-gVkOSTpOyUx-zkWjuwg?view)。脈絡是：有一個控制 18% 驗證者的對手，利用（或造成）一次臨時的網路分區。我們主要會以檢查點來說明這個議題，並省略「攜帶證明的中間區塊」——你可以視需要在心裡把這些插入進去。

我們以一個所有節點都同意的已證成檢查點 $A$ 開始。

由於網路分區，只有 49% 的驗證者、加上對手的 18%，看到檢查點 $B$。它們全都做出 Casper FFG 投票 $[A \rightarrow B]$，因而證成 $B$。在這個分支上產生了一個進一步的檢查點 $C_1$，而那 49% 的誠實驗證者盡責地做出 Casper FFG 投票 $[B \rightarrow C_1]$，但對手不做，意味著 $C_1$ 未被證成。這個分支上的驗證者把 $h_1$ 視為鏈頭區塊，並有一個 $B$ 的最高已證成檢查點。

<a id="img_annotated_forkchoice_filter_0"></a>
<figure class="diagram" style="width: 90%">

![A diagram illustrating the first step in a liveness attack on the unfiltered chain, making the first branch.](images/diagrams/annotated-forkchoice-filter-0.svg)

<figcaption>

大區塊代表檢查點。在檢查點 $A$ 之後有一次網路分區：49% 的驗證者加上對手看到檢查點 $B$ 與 $C_1$。Casper 投票以虛線箭頭表示。對手為 $B$ 投票，但不為 $C_1$ 投票。

</figcaption>
</figure>

其餘 33% 的驗證者沒看到檢查點 $B$，而是看到 $C_2$，並為它做出 Casper FFG 投票 $[A \rightarrow C_2]$。但這不是足以證成 $C_2$ 的票數。在 $C_2$ 之上產生了檢查點 $D_2$，以及一個進一步的區塊 $h_2$。在這個分支上，依 LMD GHOST 而言 $h_2$ 是鏈頭，而 $A$ 仍是最高的已證成檢查點。

<a id="img_annotated_forkchoice_filter_1"></a>
<figure class="diagram" style="width: 90%">

![A diagram illustrating the second step in a liveness attack on the unfiltered chain, making the second branch.](images/diagrams/annotated-forkchoice-filter-1.svg)

<figcaption>

與此同時，其餘 33% 的驗證者沒看到始於 $B$ 的分支，而是開始一個「包含 $C_2$ 及其後裔」的新分支。它們沒有足夠的集體權重來證成任何一個檢查點。

</figcaption>
</figure>

現在來到狡猾的部分。對手把它的 LMD GHOST 投票（以及隱含地，它的 Casper FFG 投票，雖然那對這個演練無關緊要）從第一個分支切換到第二個分支，並讓第一個分支中的驗證者看到第二個分支上的區塊與投票。

區塊 $h_2$ 現在有來自驗證者多數的票——33% 加上對手的 18%——所以所有誠實的驗證者都應把它作為它們的鏈頭區塊。

然而，$h_2$ 分支上的已證成檢查點仍是 $A$。這意味著，那 49% 做出了 Casper FFG 投票 $[B \rightarrow C]$ 的驗證者，「不能」把它們的鏈頭從 $h_1$ 切換到 $h_2$，否則就會犯下一個 Casper FFG 環繞投票、因而被罰沒。切換分支會使它們的最高已證成檢查點倒退。由於它們先前投了 $[B \rightarrow C_1]$，它們現在不能投 $[A \rightarrow X]$（其中 $X$ 的高度大於 $C_1$）——而如果它們要切換到 $h_2$ 分支，就必須這麼投。

<a id="img_annotated_forkchoice_filter_2"></a>
<figure class="diagram" style="width: 90%">

![A diagram illustrating the third step in a liveness attack on the unfiltered chain, changing the chain head.](images/diagrams/annotated-forkchoice-filter-2.svg)

<figcaption>

對手切換到第二個分支，給予 $h_2$ 多數的 LMD GHOST 投票。這使最終確定陷入死鎖：那 49% 做出了 Casper FFG 投票 $[B \rightarrow C_1]$ 的驗證者，不被罰沒就無法切換到 $h_2$。

</figcaption>
</figure>

總而言之，這條鏈無法再最終確定（藉由建立更高的已證成檢查點），除非有相當大比例的驗證者（至少 16%）願意讓自己被罰沒。

這條鏈絕不應有可能落入「誠實的驗證者在遵循協定規則的情況下，最終陷入被罰沒之危險」的處境。這裡的處境之所以出現，是由於 Casper FFG 分叉選擇（追隨「包含最高高度之已證成檢查點」的鏈）與 LMD GHOST 分叉選擇（在這個情況中它忽略了那項規則）之間的一個衝突。它是「這兩者被栓接在一起的笨拙方式」的一個徵狀。

對這一切所選擇的修正，是在套用 LMD GHOST 分叉選擇之前先過濾區塊樹，以便把所有「不可行」的分支從考量中移除。也就是說，所有「其鏈頭區塊的狀態在『證成與最終確定的當前狀態』上與我不一致」的分支。

<a id="img_annotated_forkchoice_filter_3"></a>
<figure class="diagram" style="width: 90%">

![A diagram showing that filter block tree prunes out the conflicting branch for validators following the first branch.](images/diagrams/annotated-forkchoice-filter-3.svg)

<figcaption>

當追隨分支 1 的驗證者套用 `filter_block_tree()` 時，分支 2 被修剪掉（如虛線所示）。這是因為它們的 Store 以 $B$ 作為最佳已證成檢查點，而分支 2 的葉區塊有一個「以 $A$ 作為已證成檢查點」的狀態。對這些驗證者而言，$h_2$ 不再是一個候選鏈頭區塊。

</figcaption>
</figure>

有了這個修正，當第二個分支上的驗證者最終察覺到第一個分支時，這條鏈就會恢復最終確定的能力。在看到 $h_1$ 及其祖先時，它們會把它們 Store 的已證成檢查點更新為 $B$，並把 $h_2$ 分支標記為不可行。

##### 未實現證成

Capella [對分叉選擇規格的更新](https://github.com/ethereum/consensus-specs/pull/3290)的一個主要特點，是在過濾區塊樹時「處理『未實現證成』」的邏輯。

[先前的分叉選擇規格](/../bellatrix/part3/forkchoice/phase0/)中曾出現數個議題。第一，一種[未實現證成鏈重組](https://notes.ethereum.org/@adiasg/unrealized-justification)攻擊，它容許一個紀元第一個區塊的提議者，輕易地把前一個紀元末尾多達九個區塊分叉掉。那個攻擊的一個變體也被發現能導致驗證者做出可罰沒的證明——正是這個過濾器意在防止的議題。第二，一種[證成扣留攻擊](https://hackmd.io/o9tGPQL2Q4iH3Mg7Mma9wQ)，一個對手可用它在一個紀元的開頭重組任意數目的區塊。

根本的議題在於：在共識層的狀態轉換之內，「更新證成與最終性」的計算只在紀元邊界進行。一個對手有幾種方式可以利用這一點，在 `filter_block_tree()` 之內把競爭的分支過濾掉。本質上，由於沒有把未實現的證成納入考量，過濾被套用得太過激進。

說清楚一點，這裡所描述的兩種攻擊都適用於 [`filter_block_tree()` 的舊版本](/../bellatrix/part3/forkchoice/phase0/#filter_block_tree)，並已在當前的發布版中被矯正。這是「評估 `correct_justified` 與 `correct_finalized`」的舊的、簡單得多的程式碼：

```none
    correct_justified = (
        store.justified_checkpoint.epoch == GENESIS_EPOCH
        or head_state.current_justified_checkpoint == store.justified_checkpoint
    )
    correct_finalized = (
        store.finalized_checkpoint.epoch == GENESIS_EPOCH
        or head_state.finalized_checkpoint == store.finalized_checkpoint
    )
```

這意味著，一個分支的末梢在以下情況被納入考量：（a）它後狀態中的已證成檢查點與 store 中的相符，且（b）它後狀態中的已最終確定檢查點與 store 中的相符。這些漂亮而簡單的判準已被改成我們今天所擁有的這團亂麻，我們稍後會看它。但首先，讓我們看看舊的判準有什麼問題。

###### 未實現證成鏈重組

[未實現證成鏈重組](https://notes.ethereum.org/@adiasg/unrealized-justification)容許「一個被指派在一個紀元第一個時段提議區塊」的對手，把前一個紀元末尾多達九個區塊的一段鏈重組掉。

這的關鍵是「_未實現證成_」這個概念。在一個紀元接近結束時（在一個紀元的最後三分之一內，也就是最後九個時段），信標鏈可能已收集到足夠的 Casper FFG 投票，足以證成那個紀元起始處的檢查點。然而，證成與最終確定的計算只在紀元邊界進行，所以已達成的證成是「未實現的」：直到那個紀元結束為止，所有的區塊都會繼續有一個「指向一個更早檢查點」的後狀態證成。

<a id="img_annotated_forkchoice_unrealised_justification-reorg_0"></a>
<figure class="diagram" style="width: 90%">

![A diagram showing the setup for an unrealised justification reorg scenario.](images/diagrams/annotated-forkchoice-unrealised-justification-reorg-0.svg)

<figcaption>

實心的垂直線是紀元邊界，而方塊 $C_1$ 與 $C_2$ 是它們的檢查點。一個區塊的 $J$ 值顯示它後狀態中的已證成檢查點。它的 $U$ 值是假想的未實現證成。在一個紀元期間，鏈可能收集到足夠的 Casper FFG 投票來證成一個新的檢查點，但信標狀態中的證成只在紀元邊界發生，所以在過渡期間它是未實現的。區塊 $Y$ 顯然是鏈頭區塊。

</figcaption>
</figure>

當對手是一個紀元第一個時段的提議者時，它本可利用前一個紀元中的未實現證成，來把那個紀元的最後幾個區塊分叉掉——多達約九個，視對手的區塊所包含的 FFG 投票而定。藉由建構一個競爭的鏈頭區塊，對手可以誘騙 `filter_block_tree()` 把先前的鏈頭分支從考量中過濾掉。

<a id="img_annotated_forkchoice_unrealised_justification_reorg_1"></a>
<figure class="diagram" style="width: 90%">

![A diagram showing how the adversary executes the unrealised justification reorg.](images/diagrams/annotated-forkchoice-unrealised-justification-reorg-1.svg)

<figcaption>

對手在下一個紀元的第一個時段加上一個區塊 $Z$。它建構於 $W$ 之上，而 $W$ 有未實現證成。在紀元邊界，狀態的已證成檢查點被計算出來，所以 $W$ 的後狀態有 $C_2$。在先前的分叉選擇中，只有「末梢在已證成檢查點上與 Store 一致」的分支才能被考量。在那個基礎上，終止於 $Y$ 的分支本會被過濾器排除，使 $Z$ 成為鏈頭，即使它可能有零個 LMD GHOST 支持。區塊 $X$ 與 $Y$ 本會被孤立（重組掉）。

</figcaption>
</figure>

###### 未實現證成死鎖

同樣明顯起來的是：Capella 之前那個版本的 `filter_block_tree()` 並未完全防止死鎖的可能性——而死鎖正是過濾區塊樹[意在防止](#why-prune-unviable-branches)的東西。死鎖是「誠實的驗證者被迫在『做出一筆可罰沒的證明』與『完全不投票』之間選擇」的處境。

這個設置與攻擊在 [Aditya Asgaonkar 的文件](https://notes.ethereum.org/@adiasg/unrealized-justification)中描述，是上述重組的一個變體。原本的死鎖攻擊仰賴網路被分區，使得驗證者有分裂的觀點。這個較新的死鎖攻擊不需要網路分區，但在一些相當特定的未實現證成條件之下，對手能使已證成檢查點倒退。在「一些誠實的驗證者已用較高的檢查點作為它們的 Casper FFG 來源投票」之後這麼做，會迫使它們後續要麼做出一個環繞投票，要麼不投票。

###### 證成扣留攻擊

[證成扣留攻擊](https://hackmd.io/o9tGPQL2Q4iH3Mg7Mma9wQ)與[未實現證成鏈重組](#unrealised-justification-reorg)類似，它涉及「利用未實現證成來讓 `filter_block_tree()` 把『對手分支以外的其他分支』排除掉」。

在這個攻擊中，對手需要在一個紀元結束時連續有好幾個提議——多到：如果對手不發布這些區塊，那麼那個紀元到它結束時就不會被證成。也就是說，沒有對手的區塊，就沒有未實現證成；有對手的區塊，就會有未實現證成。

<a id="img_annotated_forkchoice_justification_withholding_0"></a>
<figure class="diagram" style="width: 90%">

![A diagram showing how an adversary sets up a justification withholding attack.](images/diagrams/annotated-forkchoice-justification-withholding-0.svg)

<figcaption>

對手在一個紀元結束時有一連串的提議。這些區塊包含足夠的 FFG 投票來證成該紀元的檢查點 $C_2$，但對手目前把它們扣住。

</figcaption>
</figure>

鏈的其餘部分不知道對手的區塊，所以繼續建構，彷彿那些是被略過的時段。

<a id="img_annotated_forkchoice_justification_withholding_1"></a>
<figure class="diagram" style="width: 90%">

![A diagram showing the chain progressing after the setup of the justification withholding attack, but before its execution.](images/diagrams/annotated-forkchoice-justification-withholding-1.svg)

<figcaption>

其餘的驗證者在下一個紀元的開頭繼續建構區塊 $A$ 與 $B$。沒有對手的區塊，檢查點 2 未被證成，所以 $A$ 與 $B$ 在它們的後狀態中以 $C_1$ 作為已證成（它們的未實現證成在此無關緊要）。區塊 $B$ 是鏈的鏈頭。

</figcaption>
</figure>

對手在紀元 3 的某個時點有一個區塊提議——何時無關緊要。

<a id="img_annotated_forkchoice_justification_withholding_2"></a>
<figure class="diagram" style="width: 90%">

![A diagram showing the execution of the justification withholding attack.](images/diagrams/annotated-forkchoice-justification-withholding-2.svg)

<figcaption>

當對手在紀元 3 發布區塊 $Z$ 時，它同時釋出它扣住的區塊。區塊 $Z$ 有一個 $C_2$ 的後狀態已證成檢查點（在紀元邊界更新）。在舊的 `filter_block_tree()` 之下，那本會把 $B$ 排除在「作為鏈頭被考量」之外，而對手的區塊 $Z$ 本會成為鏈頭，即使沒有 LMD 支持。

</figcaption>
</figure>

##### 可行與不可行的分支

區塊樹過濾的進行方式，是檢查「分支末梢的區塊」在某種意義上有「正確的」證成與最終確定。`correct_justified` 與 `correct_finalised` 兩個旗標都必須為真，該分支才被視為可行。

###### `correct_justified`

來自 Capella 更新、較新且較複雜的 `correct_justified` 評估如下。

```none
    current_epoch = compute_epoch_at_slot(get_current_slot(store))
    voting_source = get_voting_source(store, block_root)

    # The voting source should be at the same height as the store's justified checkpoint
    correct_justified = (
        store.justified_checkpoint.epoch == GENESIS_EPOCH
        or voting_source.epoch == store.justified_checkpoint.epoch # A
    )

    # If the previous epoch is justified, the block should be pulled-up. In this case, check that unrealized
    # justification is higher than the store and that the voting source is not more than two epochs ago
    if not correct_justified and is_previous_epoch_justified(store): # B
        correct_justified = (
            store.unrealized_justifications[block_root].epoch >= store.justified_checkpoint.epoch and # C
            voting_source.epoch + 2 >= current_epoch # D
        )
```

我不會假裝我完全理解這個——它似乎遠非直觀，它的正確性也遠非顯而易見[^fn-fc-fv]。目前我會引用 Aditya 直接與我分享的一些解釋。

[^fn-fc-fv]: 「分叉選擇有多麼難以推理」的一些證據，由 Consensys 的 Roberto Saltini 與團隊所建立的[正確性形式證明](https://docs.google.com/document/d/1PnhDMij6w_fjLGicSF-I9sQcSWgaj5fjtGlRPIgYnVA/edit)提供。[光是其中一個證明](https://docs.google.com/document/d/1V0sabk-DKnIl3BKgt-GkEFSFq-K-Ie8gmuezHRnVn0c/edit#)印出來就有 28 頁長。

> `correct_justified` 條件確保：
> （a）我們挑選一個「在其鏈中有『良好』證成」的鏈頭區塊，且
> （b）驗證者能為所選的鏈頭區塊投票，而沒有「製造可罰沒訊息」的風險。
>
> 我在此非正式地描述（a），但你可以把分叉選擇想成一個啟發法，用以選擇要在哪裡投票，使得我們盡可能快地推進我們的已最終確定檢查點。一般而言，這意味著我們為「我們所知道的最高已證成檢查點」投票，但「我們所知道的」這部分是棘手的，因為未實現證成的微妙之處、以及相關的重組攻擊。
>
> 現在，如果你忽略未實現證成與重組攻擊，`correct_justified` 的這第一次出現〔行 `A`〕就足以處理（a）與（b）。然後，為了修正重組攻擊，我們為被拉起的區塊加上一個額外版本的 `correct_justified`，其中第一行〔行 `C`〕處理（a），而第二行〔行 `D`〕處理（b）。

回想一下，過濾區塊樹的首要目標，是避免誠實的驗證者被迫在 Casper FFG 中做出環繞投票，因為這些是可罰沒的。然而，先前對此的矯正措施在過濾掉候選鏈頭時太過急切，而一個對手能利用未實現證成來強迫重組，甚至強迫「我們想避免的那種自我罰沒」。

當前的分叉選擇機制保有兩項關鍵特質[^fn-fc-mikhail]。

[^fn-fc-mikhail]: 我感謝 Mikhail Kalinin 以他非常清晰而審慎的解釋幫助我。我的解釋基於他的；任何錯誤與過度簡化全是我自己的手筆。

1. 一個候選鏈頭區塊的 `voting_source.epoch` 始終小於或等於 `store.justified_checkpoint.epoch`。
   - 這是因為 [`on_block()`](#on_block) 總是呼叫 [`update_checkpoints()`](#update_checkpoints)，以及 [`get_voting_source()`](#get_voting_source) 函式被建構的方式。
   - `voting_source.epoch` 是「以那個區塊為鏈頭的驗證者，在當前紀元做出一個 Casper FFG 投票時將會使用」的 Casper FFG 來源投票。
2. `store.justified_checkpoint.epoch` 絕不會減少（它是單調遞增的）。
   - 它只在 [`update_checkpoints()`](#update_checkpoints) 中被寫入，而從那裡很容易看出這是真的。

就我在原始碼中標記為 `A` 的那一行而言，如果投票來源與 Store 的已證成檢查點相符，那麼一切都好，我們沒有理由不把該區塊當成鏈頭考量，我們可以把其餘的邏輯短路掉。依特質 2，Store 的已證成檢查點絕不會減少，所以一個驗證者基於此的 Casper FFG 投票，絕不可能是一個環繞投票。（由於目標投票嚴格遞增，它也不可能是一個被環繞的投票。）

<a id="img_annotated_forkchoice_correct_justified_0"></a>
<figure class="diagram" style="width: 85%">

![A diagram showing that it is always safe to vote when the voting source is the same as the store's justified checkpoint.](images/diagrams/annotated-forkchoice-correct-justified-0.svg)

<figcaption>

當投票來源與 store 的已證成檢查點相同時，投票永遠是安全的。store 的已證成檢查點絕不會減少，所以我們不可能犯下一個環繞投票。

</figcaption>
</figure>

如果該區塊依第一個判準不是一個可行的鏈頭，它仍可能依第二個判準（行 `D`）是一個可行的鏈頭。回想一下，上述的重組攻擊仰賴對手利用未實現證成來更新 Store 的已證成檢查點，使鏈先前的鏈頭就其已實現證成而言變得「過時」，雖然基於它的未實現證成它仍會是可行的。為了避免這一點，我們希望安全地納入盡可能多的可行鏈頭。

我們知道，依特質 1、且由於我們已處理了相等的情況，我們此時做出的任何 Casper FFG 投票，其 `voting_source.epoch` 都會嚴格小於 `store.justified_checkpoint.epoch`。

原始碼中的行 `D` 說，容許 `voting_source.epoch == current_epoch - 2` 與 `voting_source.epoch == current_epoch - 1` 的投票是安全的。任何誠實投票的目標紀元都會是 `current_epoch`，所以來源與目標之間的間隔最多是兩個紀元，這不足以環繞一個先前的投票。也就是說，一個環繞先前投票 $[s_1 \rightarrow t_1]$ 的投票 $[s_2 \rightarrow t_2]$，要求 $s_2 < s_1 < t_1 < t_2$。如果 $t_2 - s_2 \le 2$，這就不可能。這個例外是[安全區塊確認規則](/part3/safe-block/)的分析所需要的，並在[確認規則論文](https://ethresear.ch/uploads/short-url/fV7zyTggJtMn8xlUUNVXTOB532G.pdf)的 3.3 節中討論。

<a id="img_annotated_forkchoice_correct_justified_1"></a>
<figure class="diagram" style="width: 85%">

![A diagram showing that it is safe to vote from two epochs ago.](images/diagrams/annotated-forkchoice-correct-justified-1.svg)

<figcaption>

當投票來源在當前紀元的兩個紀元之內時，投票就是安全的，因為一個環繞投票必定涵蓋至少兩個位於其間的檢查點。

</figcaption>
</figure>

行 `B`（關於前一個紀元之證成的條件）與行 `C` 似乎都是不必要的，可能[在未來被移除](https://github.com/ethereum/consensus-specs/pull/3339/files#diff-f58759020c0d7542f963e2b88fef66c2179d740beb5af45b7e2c90913477be11L277-L290)。關於這的討論，見（草案）論文〈[A Confirmation Rule for the Ethereum Consensus Protocol](https://ethresear.ch/uploads/short-url/fV7zyTggJtMn8xlUUNVXTOB532G.pdf)〉的 3.3 與 3.4 節。不過請注意，[下文](#formal-proofs)所描述的[誠實可行鏈頭](https://docs.google.com/document/d/1riyJxPPCuTwxmpKWqUD9noGMPB5FtvUW81JN9kaUQBo/edit)特質的證明，仰賴一個較弱的條件 `store.justified_checkpoint.epoch >= current_epoch - 2`（即前一個或再前一個紀元已被證成）。

###### `correct_finalized`

Capella 更新對 `correct_finalized` 的變更較為有限，也較為直觀。

```none
    finalized_slot = compute_start_slot_at_epoch(store.finalized_checkpoint.epoch)
    correct_finalized = (
        store.finalized_checkpoint.epoch == GENESIS_EPOCH
        or store.finalized_checkpoint.root == get_ancestor(store, block_root, finalized_slot)
    )
```

這單純地確保一個可行的區塊後裔自 Store 的已最終確定檢查點。

[先前的版本](https://github.com/ethereum/consensus-specs/blob/v1.2.0/specs/phase0/fork-choice.md?plain=1#L231-L234)使用了「正被考量其可行性之區塊」的後狀態，這使它就未實現最終性而言遭受與 `correct_justified` 類似的複雜情況。我們其實不在乎該區塊後狀態對最終確定的觀點，因為最終性是一個全域特質：只要該區塊後裔自已最終確定檢查點，它就應符合「被考量以變為可行」的資格。

`correct_finalized` 檢查乍看之下可能顯得多餘，因為我們總是基於「一棵以上一個已證成檢查點為根的樹」來過濾，而那個檢查點（在沒有大規模罰沒的情況下）必定後裔自上一個已最終確定檢查點。然而，這個檢查保證了一個進一步的條件：一個節點自己對已最終確定檢查點的觀點是不可逆的，即使發生了一次大規模罰沒——這就是下一節中的[不可逆本地最終性](https://docs.google.com/document/d/194dC7UmDSY5pDsrqi2B4VWpF1ORCkftHXhmtxtEaHT4/edit)形式特質。維持這項不變式對建構高效的客戶端是一大幫助——我們可以自由地忘掉上一個已最終確定檢查點之前的一切。

###### 形式證明

如以太坊基金會關於 Capella 分叉選擇規格更新的[揭露](https://notes.ethereum.org/@djrtwo/2023-fork-choice-reorg-disclosure)所提及的，新分叉選擇的一些特質已由 Consensys 的 Roberto Saltini 與他的團隊[形式驗證](https://docs.google.com/document/d/1PnhDMij6w_fjLGicSF-I9sQcSWgaj5fjtGlRPIgYnVA/edit)過。

這個形式驗證過程，涉及選定一些「我們希望對分叉選擇為真」的特質，並手動建構「它們始終被規格所保持」的證明。它是一個比手動測試、模糊測試、或迄今一直是主要做法的籠統含糊論述更為穩健、更為嚴謹的過程。

[那些文件](https://docs.google.com/document/d/1PnhDMij6w_fjLGicSF-I9sQcSWgaj5fjtGlRPIgYnVA/edit)中證明了四項特質。

  - [不自我罰沒性](https://docs.google.com/document/d/12dF-84w6G62KH68L2dO_ym7RGXEZ0k9d7mOksgzp3Ls/edit)
    - 任何遵循[誠實驗證者指南](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md)的驗證者，絕不會罰沒它自己。
  - [誠實可行鏈頭](https://docs.google.com/document/d/1riyJxPPCuTwxmpKWqUD9noGMPB5FtvUW81JN9kaUQBo/edit)
    - 假設一個同步的網路、`current_epoch - 2` 已被證成、且誠實節點已收到足夠的證明來證成「可能的最高已證成檢查點」，那麼「一個誠實節點在當前紀元提議、且後裔自『可能的最高已證成檢查點』」的任何區塊，都被納入 [`get_filtered_block_tree()`](#get_filtered_block_tree) 的輸出中。
  - [無死鎖](https://docs.google.com/document/d/1V0sabk-DKnIl3BKgt-GkEFSFq-K-Ie8gmuezHRnVn0c/edit)
    - 一個運行以太坊協定的分散式系統，絕不會落入「不可能最終確定一個新紀元」的狀態。
  - [不可逆本地最終性](https://docs.google.com/document/d/194dC7UmDSY5pDsrqi2B4VWpF1ORCkftHXhmtxtEaHT4/edit)
    - 一個區塊，一旦在一個誠實驗證者的本地觀點中被最終確定，就絕不會在本地觀點中被從正典鏈回退。

考量到推理分叉選擇的複雜性、以及它相當斑駁的歷史，如今有了[這些](https://docs.google.com/document/d/1PnhDMij6w_fjLGicSF-I9sQcSWgaj5fjtGlRPIgYnVA/edit)正確性證明，是極大的安心保證[^fn-fv-assumptions]。

[^fn-fv-assumptions]: 然而，證明中仍有一些假設是過度簡化的，例如「一個區塊中可納入的證明數量沒有上界」、以及「誠實節點不丟棄它們所收到的任何證明，無論它有多舊」。圍繞分叉選擇有過一些失敗證明的歷史，它們基於太過寬泛的假設。但願這些證明站得住腳；我沒有能力評斷。

##### 結論

這是關於一個短函式的一長節。如我在本節開頭所說，`filter_block_tree()` 處在「LMD GHOST 與 Casper FFG 如何被栓接在一起」的核心，而我想這裡潛藏著多少複雜性，讓每個人都吃了一驚。

作為給讀者的一個練習，我們可以想像「無須過濾區塊樹」的人生。Potuz 在〈[Fork choice without on-state FFG filtering](https://hackmd.io/@potuz/rkB25feBi)〉中記下了一些對此的想法。

最終，與[提議者增益](#proposer-boost)一樣，圍繞 Gasper 分叉選擇的複雜性，大體上源自我們基於時段的投票——投票在一個紀元中逐漸累積。這導致了未實現證成以及諸如此類的東西。長期的修正大概也是相同的：轉向[單時段最終性](#alternatives-to-proposer-boost)。

|||
|-|------|
| 使用&nbsp;者 | [`get_filtered_block_tree()`](#get_filtered_block_tree)、[`filter_block_tree()`](#filter_block_tree)（遞迴） |
| 使用 | [`filter_block_tree()`](#filter_block_tree)（遞迴）、[`compute_epoch_at_slot()`](/part3/helper/misc/#def_compute_epoch_at_slot)、[`get_voting_source()`](#get_voting_source)、[`is_previous_epoch_justified()`](#is_previous_epoch_justified)、[`compute_start_slot_at_epoch()`](/part3/helper/misc/#def_compute_start_slot_at_epoch)、[`get_ancestor()`](#get_ancestor) |

#### `get_filtered_block_tree`

```python
def get_filtered_block_tree(store: Store) -> Dict[Root, BeaconBlock]:
    """
    Retrieve a filtered block tree from ``store``, only returning branches
    whose leaf state's justified/finalized info agrees with that in ``store``.
    """
    base = store.justified_checkpoint.root
    blocks: Dict[Root, BeaconBlock] = {}
    filter_block_tree(store, base, blocks)
    return blocks
```

一個便利包裝器，把 Store 的已證成檢查點傳給 [`filter_block_tree()`](#filter_block_tree)。回傳時，`blocks` 字典結構會包含「所有以那個檢查點為根之可行分支」的區塊，而不包含任何不後裔自那個檢查點的東西。「可行」的意義見[上文](#viable-and-unviable-branches)。

|||
|-|------|
| 使用&nbsp;者 | [`get_head()`](#get_head) |
| 使用 | [`filter_block_tree()`](#filter_block_tree) |

#### `get_head`

```python
def get_head(store: Store) -> Root:
    # Get filtered block tree that only includes viable branches
    blocks = get_filtered_block_tree(store)
    # Execute the LMD-GHOST fork choice
    head = store.justified_checkpoint.root
    while True:
        children = [
            root for root in blocks.keys()
            if blocks[root].parent_root == head
        ]
        if len(children) == 0:
            return head
        # Sort by latest attesting balance with ties broken lexicographically
        # Ties broken by favoring block with lexicographically higher root
        head = max(children, key=lambda root: (get_weight(store, root), root))
```

`get_head()` 封裝了分叉選擇規則：給定一個 Store，它回傳一個鏈頭區塊。

分叉選擇規則是客觀的，意思是給定相同的 Store，它總是會回傳相同的鏈頭區塊。但整體的過程是主觀的，意思是網路上的每個節點往往會有一個不同的觀點，亦即一個不同的 Store，原因是收到證明或區塊的延遲、或由於網路非同步或一次攻擊而見過不同組的證明或區塊。

先看 `while True` 迴圈，這以最純粹的形式實作了 LMD GHOST。從一個給定的區塊開始（在未經修改的 LMD GHOST 中那會是創世區塊），我們找出那個區塊各子代的權重。我們選出權重最大的子區塊，並重複這個過程，直到我們落在一個葉區塊（一個分支的末梢）。也就是說，我們貪婪地取最重觀察子樹，GHOST。兩個權重相同的子區塊之間的任何平手，藉由比較它們的區塊雜湊來打破，所以我們落在一個唯一的葉區塊——我們所回傳的鏈頭。

<a id="img_annotated_forkchoice_lmd_ghost_0"></a>
<figure class="diagram" style="width: 85%">

![Diagram of a block tree showing the weight of each block.](images/diagrams/annotated-forkchoice-lmd-ghost-0.svg)

<figcaption>

`get_head()` 從一棵區塊樹的根區塊 $A$ 開始。數字顯示每個區塊的權重，即它的最新作證餘額——「把最新投票投給那個區塊之驗證者」的有效餘額總和。[提議者增益](#proposer-boost)能臨時地增加最新區塊的分數（未顯示）。

</figcaption>
</figure>

<a id="img_annotated_forkchoice_lmd_ghost_1"></a>
<figure class="diagram" style="width: 85%">

![Diagram of a block tree showing the weight of each block and the weight of each subtree.](images/diagrams/annotated-forkchoice-lmd-ghost-1.svg)

<figcaption>

`get_weight()` 函式套用於一個區塊時，回傳「該區塊與它所有後裔之子樹」的總權重。這些權重顯示在子區塊與父區塊之間的線上。

</figcaption>
</figure>

<a id="img_annotated_forkchoice_lmd_ghost_2"></a>
<figure class="diagram" style="width: 85%">

![Diagram of a block tree showing the branch chosen by the GHOST rule.](images/diagrams/annotated-forkchoice-lmd-ghost-2.svg)

<figcaption>

給定一個區塊，`get_head()` 中的迴圈考量它的各子代，並選出「以最高權重之子樹為根」的那一個。它以最重的子區塊重複這個過程[^fn-get-head-recursive]，直到它抵達一個沒有子代的區塊。在這個例子中，它會選出分支 $A \leftarrow C \leftarrow E$，回傳 $E$ 作為鏈頭區塊。

</figcaption>
</figure>

[^fn-get-head-recursive]: 這個演算法是遞迴的，雖然它在此處不是以遞迴的方式寫成。

##### 混合式 LMD GHOST

我們剛剛描述的是純粹的 LMD GHOST 演算法。從創世區塊開始，它走訪整個區塊樹，在每個分叉處取最重的分支，直到它抵達一個葉區塊。

然而，`get_head()` 中所實作的，是這個演算法的一個修改形式，[Gasper 論文](https://arxiv.org/pdf/2003.03052.pdf)[^fn-hlmd-ghost-definition]把它稱為「混合式 LMD GHOST」（hybrid LMD GHOST，HLMD GHOST）。它不是純粹的 LMD GHOST，而是被 Casper FFG 共識所修改的 LMD GHOST。

[^fn-hlmd-ghost-definition]: 見那篇論文的 4.6 節。

```none
    # Get filtered block tree that only includes viable branches
    blocks = get_filtered_block_tree(store)
    # Execute the LMD-GHOST fork choice
    head = store.justified_checkpoint.root
```

具體而言，我們不從創世區塊開始走訪樹，而是從上一個已證成檢查點開始；而且我們不考量 Store 所知道的所有區塊，而是先用 [`get_filtered_block_tree()`](#get_filtered_block_tree) 把「不可行」的分支過濾掉。

這就是 Casper FFG 分叉選擇規則——「追隨『包含最高高度之已證成檢查點』的鏈」——與 LMD GHOST 分叉選擇規則相會的時點。前者修改後者，給了我們 HLMD GHOST 分叉選擇規則。

|||
|-|------|
| 使用 | [`get_filtered_block_tree()`](#get_filtered_block_tree), [`get_weight()`](#get_weight) |

#### `update_checkpoints`

```python
def update_checkpoints(store: Store, justified_checkpoint: Checkpoint, finalized_checkpoint: Checkpoint) -> None:
    """
    Update checkpoints in store if necessary
    """
    # Update justified checkpoint
    if justified_checkpoint.epoch > store.justified_checkpoint.epoch:
        store.justified_checkpoint = justified_checkpoint

    # Update finalized checkpoint
    if finalized_checkpoint.epoch > store.finalized_checkpoint.epoch:
        store.finalized_checkpoint = finalized_checkpoint
```

如果給定的已證成或已最終確定檢查點中任一者較新，就更新 store 中的檢查點。

證成與最終確定本應是鏈的「全域」特質，不特定於任何一個分支，所以我們讓我們的 Store 與「我們所見過的最高檢查點」保持同步。

請注意，依其建構方式，Store 的已證成與已最終確定檢查點只能單調遞增。前者對[「不自我罰沒性」的形式證明](#formal-proofs)很重要。

|||
|-|------|
| 使用&nbsp;者 | [`compute_pulled_up_tip()`](#compute_pulled_up_tip), [`on_tick_per_slot()`](#on_tick_per_slot), [`on_block()`](#on_block) |

#### `update_unrealized_checkpoints`

```python
def update_unrealized_checkpoints(store: Store, unrealized_justified_checkpoint: Checkpoint,
                                  unrealized_finalized_checkpoint: Checkpoint) -> None:
    """
    Update unrealized checkpoints in store if necessary
    """
    # Update unrealized justified checkpoint
    if unrealized_justified_checkpoint.epoch > store.unrealized_justified_checkpoint.epoch:
        store.unrealized_justified_checkpoint = unrealized_justified_checkpoint

    # Update unrealized finalized checkpoint
    if unrealized_finalized_checkpoint.epoch > store.unrealized_finalized_checkpoint.epoch:
        store.unrealized_finalized_checkpoint = unrealized_finalized_checkpoint
```

[`update_checkpoints()`](#update_checkpoints) 對應於未實現之已證成與已最終確定檢查點的對應物。

|||
|-|------|
| 使用&nbsp;者 | [`compute_pulled_up_tip()`](#compute_pulled_up_tip) |

#### 拉起末梢的輔助函式

##### `compute_pulled_up_tip`

```python
def compute_pulled_up_tip(store: Store, block_root: Root) -> None:
    state = store.block_states[block_root].copy()
    # Pull up the post-state of the block to the next epoch boundary
    process_justification_and_finalization(state)

    store.unrealized_justifications[block_root] = state.current_justified_checkpoint
    update_unrealized_checkpoints(store, state.current_justified_checkpoint, state.finalized_checkpoint)

    # If the block is from a prior epoch, apply the realized values
    block_epoch = compute_epoch_at_slot(store.blocks[block_root].slot)
    current_epoch = compute_epoch_at_slot(get_current_slot(store))
    if block_epoch < current_epoch:
        update_checkpoints(store, state.current_justified_checkpoint, state.finalized_checkpoint)
```

`compute_pulled_up_tip()` 為每個被處理的區塊被呼叫，以維護 `update_unrealized_checkpoints` 對應。它是在 Capella 規格更新中加入的。

這個常式中的主要工作，在於對 [`process_justification_and_finalization()`](/part3/transition/epoch/#def_process_justification_and_finalization) 的呼叫。在狀態轉換中，這每個紀元被呼叫一次。現在我們每個區塊呼叫它一次，如果樸素地實作，這會增添顯著的負載。

由於狀態轉換只在紀元邊界呼叫 `process_justification_and_finalization()`，信標狀態的證成與最終確定資訊不可能在紀元中途改變。然而，Casper FFG 投票在整個紀元的進展過程中累積，而在那個紀元結束之前的某個時點，通常會有足夠的投票被納入鏈上，足以證成一個新的檢查點。當這發生時，我們把它稱為「未實現證成」，因為它尚未反映在鏈上（在信標狀態中）。未實現證成反映「如果紀元結束時的會計處理立即對該區塊運行，信標狀態會是什麼樣子」——「拉起末梢」的命名由此而來。

我們模擬把該區塊「拉起」到下一個紀元邊界，以查出證成與最終確定的狀態會是什麼。當下一個紀元開始時，未實現的值就會變為已實現。

<a id="img_annotated_forkchoice_pull_up_tip"></a>
<figure class="diagram" style="width: 80%">

![A diagram showing how unrealised justification becomes realised when a block is "pulled up" to the next epoch.](images/diagrams/annotated-forkchoice-pull-up-tip.svg)

<figcaption>

每個區塊有一個 $J$ 值，即它後狀態所知道的已證成檢查點。$J$ 只在紀元邊界被更新。我們在概念上加上一個 $U$ 值，即「如果該區塊被『拉起』到下一個紀元邊界（信標狀態的證成與最終確定計算在那裡進行，顯示為 $W'$），它後狀態中會有」的已證成檢查點。

</figcaption>
</figure>

如圖所示，未實現證成 $U$ 可能與已實現證成 $J$ 不同，原因是未被處理的 Casper FFG 投票在一個紀元期間累積。然而，一個紀元自己的檢查點，要到至少走過一個紀元的 2/3（23 個時段，因為證明是在它們所作證之時段的後一個時段被納入的）時，才可能取得未實現證成。也就是說，區塊 $W$ 最早可能出現的時間，是在紀元 2 的時段 22（時段計數以零起算）。

在把該區塊及其未實現證成檢查點加入 `store.unrealized_justifications` 對應之後，如果該區塊的值較新，Store 的 `unrealized_justified_checkpoint` 與 `unrealized_finalized_checkpoint` 就被更新。

如果該區塊來自一個先前的紀元，那麼它的證成與最終確定就不再是未實現的，因為信標狀態自那時以來已經過了一次實際的紀元轉換，所以如果該區塊有較新的，我們就可以更新 Store 的 `justified_checkpoint` 與 `finalized_checkpoint`。

|||
|-|------|
| 使用&nbsp;者 | [`on_block()`](#on_block) |
| 使用 | [`process_justification_and_finalization()`](/part3/transition/epoch/#def_process_justification_and_finalization), [`update_unrealized_checkpoints()`](#update_unrealized_checkpoints), [`compute_epoch_at_slot()`](/part3/helper/misc/#def_compute_epoch_at_slot), [`update_checkpoints()`](#update_checkpoints) |

#### `on_tick` 的輔助函式

##### `on_tick_per_slot`

```python
def on_tick_per_slot(store: Store, time: uint64) -> None:
    previous_slot = get_current_slot(store)

    # Update store time
    store.time = time

    current_slot = get_current_slot(store)

    # If this is a new slot, reset store.proposer_boost_root
    if current_slot > previous_slot:
        store.proposer_boost_root = Root()

    # If a new epoch, pull-up justification and finalization from previous epoch
    if current_slot > previous_slot and compute_slots_since_epoch_start(current_slot) == 0:
        update_checkpoints(store, store.unrealized_justified_checkpoint, store.unrealized_finalized_checkpoint)
```

`on_tick_per_slot()` 輔助函式每個時段至少被呼叫一次。如果有多個時段沒有 tick 被處理，那麼 [`on_tick()`](#on_tick) 處理器就反覆呼叫它，為那些時段處理（合成的）tick。這確保了：當一個紀元第一個時段期間沒有 tick 被處理時，`update_checkpoints()` 仍會被呼叫。

`on_tick_per_slot()` 輔助函式有三項職責：

  - 更新時間，
  - 重設提議者增益，以及
  - 在紀元邊界更新檢查點。

###### 更新時間

```none
    # update store time
    store.time = time
```

store 有一個當前時間的概念，它在計算[當前時段](#get_current_slot)時、以及套用提議者增益時被使用。時間參數不需要非常細粒度。要不是因為提議者增益，以整數個時段來度量時間是沒問題的，至少在分叉選擇之內如此[^fn-time-in-slots]。

[^fn-time-in-slots]: 把分叉選擇中的 `time` 從秒改為時段，曾[有人建議](https://github.com/ethereum/consensus-specs/issues/1502)，但從未被採納。

###### 重設提議者增益

```none
    # Reset store.proposer_boost_root if this is a new slot
    if current_slot > previous_slot:
        store.proposer_boost_root = Root()
```

[提議者增益](#proposer-boost)是對抗「對 LMD GHOST 之平衡攻擊」的一項防禦。它在分叉選擇中以額外的權重獎勵及時的區塊，使一個誠實提議者的區塊不太可能被孤立。

Store 的 `proposer_boost_root` 欄位，在一個區塊被及時地（在它的時段最初四秒內）收到並處理時，於 [`on_block()`](#on_block) 處理器中被設定。在該時段的其餘時間裡，這容許在 [`get_weight()`](#get_weight) 中為該區塊加上額外的權重。

這裡的邏輯在下一個時段的開頭把 `proposer_boost_root` 重設為一個預設值，因而移除額外的提議者增益權重，直到下一個及時的區塊被處理為止。

###### 更新檢查點

```none
    # If a new epoch, pull-up justification and finalization from previous epoch
    if current_slot > previous_slot and compute_slots_since_epoch_start(current_slot) == 0:
        update_checkpoints(store, store.unrealized_justified_checkpoint, store.unrealized_finalized_checkpoint)
```

如果這是一個紀元的第一個時段，那麼我們自上一個 tick 以來已經過了一個紀元邊界，而我們的未實現證成與最終確定已變為已實現。它們現在應與信標狀態中的已證成與已最終確定檢查點同步。

|||
|-|------|
| 使用&nbsp;者 | [`on_tick()`](#on_tick) |
| 使用 | [`get_current_slot()`](#get_current_slot)、[`compute_slots_since_epoch_start()`](#compute_slots_since_epoch_start)、[`update_checkpoints()`](#update_checkpoints) |

#### `on_attestation` 的輔助函式

##### `validate_target_epoch_against_current_time`

```python
def validate_target_epoch_against_current_time(store: Store, attestation: Attestation) -> None:
    target = attestation.data.target

    # Attestations must be from the current or previous epoch
    current_epoch = compute_epoch_at_slot(get_current_slot(store))
    # Use GENESIS_EPOCH for previous when genesis to avoid underflow
    previous_epoch = current_epoch - 1 if current_epoch > GENESIS_EPOCH else GENESIS_EPOCH
    # If attestation target is from a future epoch, delay consideration until the epoch arrives
    assert target.epoch in [current_epoch, previous_epoch]
```

這個函式單純地基於一筆證明的目標檢查點投票，檢查它來自當前或先前紀元。Store 有一個由 [`on_tick()`](#on_tick) 處理器維護的當前時間概念，所以這是一個直截了當的計算。這個及時性檢查的引入，是為了對抗[下文所描述](#attestation-timeliness)的「誘餌翻轉」攻擊。

請注意，這裡有一個小小的不一致。證明只在「它們被發布之時段之後的 32 個時段」內可被[納入區塊](/part3/transition/block/#attestations)。然而，它們在分叉選擇中可被考量的有效期是兩個紀元，即最多 64 個時段。

|||
|-|------|
| 使用&nbsp;者 | [`validate_on_attestation()`](#validate_on_attestation) |
| 使用 | [`get_current_slot()`](#get_current_slot), [`compute_epoch_at_slot()`](/part3/helper/misc/#def_compute_epoch_at_slot) |

##### `validate_on_attestation`

```python
def validate_on_attestation(store: Store, attestation: Attestation, is_from_block: bool) -> None:
    target = attestation.data.target

    # If the given attestation is not from a beacon block message, we have to check the target epoch scope.
    if not is_from_block:
        validate_target_epoch_against_current_time(store, attestation)

    # Check that the epoch number and slot number are matching
    assert target.epoch == compute_epoch_at_slot(attestation.data.slot)

    # Attestation target must be for a known block. If target block is unknown, delay consideration until block is found
    assert target.root in store.blocks

    # Attestations must be for a known block. If block is unknown, delay consideration until the block is found
    assert attestation.data.beacon_block_root in store.blocks
    # Attestations must not be for blocks in the future. If not, the attestation should not be considered
    assert store.blocks[attestation.data.beacon_block_root].slot <= attestation.data.slot

    # LMD vote must be consistent with FFG vote target
    target_slot = compute_start_slot_at_epoch(target.epoch)
    assert target.root == get_ancestor(store, attestation.data.beacon_block_root, target_slot)

    # Attestations can only affect the fork choice of subsequent slots.
    # Delay consideration in the fork choice until their slot is in the past.
    assert get_current_slot(store) >= attestation.data.slot + 1
```

這是 [`on_attestation()`](#on_attestation) 處理器的一個公用函式，它把「我們在對 Store 做出任何變更之前，想對一筆證明進行的各種有效性檢查」收集在一起。回想一下，一個失敗的斷言意味著處理器會退出，而對 Store 做出的任何變更都必須被回滾。

###### 證明的及時性

```none
    # If the given attestation is not from a beacon block message, we have to check the target epoch scope.
    if not is_from_block:
        validate_target_epoch_against_current_time(store, attestation)
```

首先，我們檢查證明的及時性。新收到的證明只有在「我們聽聞它們時，它們來自[當前或先前紀元](#validate_target_epoch_against_current_time)」的情況下，才被考量插入 Store。

這個檢查的[引入](https://github.com/ethereum/consensus-specs/pull/1466)，是為了對抗對 LMD GHOST 的一種「[誘餌翻轉攻擊](https://ethresear.ch/t/decoy-flip-flop-attack-on-lmd-ghost/6001?u=benjaminion)」。這個攻擊取決於「由於某個網路故障，已出現兩個競爭的分支」。一個擁有某一比例質押（但少於 33%）的對手，能把較早紀元的投票累積儲存起來，並在精心計時的時刻釋放它們，以切換勝出的分支（依 LMD GHOST 分叉選擇而言），使得兩個分支都無法取得最終確定所需的 2/3 權重。這個攻擊能持續到對手用盡儲存的投票為止。

「只容許來自當前與先前紀元的證明對 Store 的更新有效」似乎是一項有效的防禦，因為它防止攻擊者把先前紀元的證明累積儲存起來。實作這一點的 PR 把它描述為「FMD GHOST」（fresh message driven GHOST，新訊息驅動 GHOST）。然而，分叉選擇仍仰賴 Store 中來自每個驗證者的最新訊息（「LMD」），無論它有多舊。我們在實務上似乎最後得到了一種混合式的 FMD/LMD GHOST[^fn-lmd-fmd-ghost]。

[^fn-lmd-fmd-ghost]: FMD 對 LMD GHOST 在 Ethresear.ch 文章〈[Saving strategy and FMD GHOST](https://ethresear.ch/t/saving-strategy-and-fmd-ghost/6226?u=benjaminion)〉中有進一步的討論。[後續的工作](#alternatives-to-proposer-boost)，例如 Goldfish 協定與 RLMD GHOST，把投票過期推進得更遠。

至於 `if not is_from_block` 測試，如果舊的證明是在一個區塊中被收到的，這就容許 `on_attestation` 處理器處理它們。它似乎是為了幫助測試的產生而引入的，而非正常運作中所需要的東西。這是引入它的那個 [PR 中的一則評論](https://github.com/ethereum/consensus-specs/pull/2727#pullrequestreview-812756853)。

> 目前繼續推進「處理來自區塊的舊證明」也是好的——那是在我們當前的測試設置中讓「對 store 的原子式更新」運作的唯一方式。如果這在未來改變，這段邏輯應經過安全性分析（尤其是針對翻轉攻擊）。

證明只有在「不到 32 個時段舊」時，才有效可被納入一個區塊。這些會是「當時所做之『新鮮』投票」的一個子集（「當前加先前紀元」的新鮮判準可能涵蓋多達 64 個時段）。

###### 紀元與時段相符

```none
    # Check that the epoch number and slot number are matching
    assert target.epoch == compute_epoch_at_slot(attestation.data.slot)
```

這個檢查處理一個[邊界案例](https://github.com/ethereum/consensus-specs/issues/1501)，其中驗證者可能為一個較早或較晚的紀元捏造投票。這對分叉選擇而言大概不是大問題，比較是對信標鏈狀態轉換的會計處理而言。儘管如此，這個檢查在兩個地方都[被實作](https://github.com/ethereum/consensus-specs/pull/1509)了。

###### 不為未知區塊的證明

```none
    # Attestations target be for a known block. If target block is unknown, delay consideration until the block is found
    assert target.root in store.blocks
    # Attestations must be for a known block. If block is unknown, delay consideration until the block is found
    assert attestation.data.beacon_block_root in store.blocks
```

這似乎是一個自然的檢查——如果我們不知道一個區塊（無論是一個目標檢查點或鏈頭區塊），處理任何為它投的票就沒有意義。這些條件[被加入](https://github.com/ethereum/consensus-specs/pull/1477)規格時沒有進一步的理路。如註解所述，這類證明在未來可能變為有效，屆時應重新考量。當客戶端收到「為它們尚不知道之區塊」的證明時，它們通常會請求它們的對等節點直接把該區塊送給它們。

###### 不為未來區塊的證明

```none
    # Attestations must not be for blocks in the future. If not, the attestation should not be considered
    assert store.blocks[attestation.data.beacon_block_root].slot <= attestation.data.slot
```

這個檢查與上述「不為未知區塊」的檢查一起[被引入](https://github.com/ethereum/consensus-specs/pull/1477)。容許「為『發布得比該證明所指派時段更晚之區塊』投的票」，會[增加誘餌翻轉攻擊的可行性](https://github.com/ethereum/consensus-specs/issues/1406)，因為它移除了「需要先有一段網路非同步期間才能設置攻擊」這項條件。

###### LMD 與 FFG 投票的一致性

```none
    # LMD vote must be consistent with FFG vote target
    target_slot = compute_start_slot_at_epoch(target.epoch)
    assert target.root == get_ancestor(store, attestation.data.beacon_block_root, target_slot)
```

這個檢查確保「該證明鏈頭投票中的區塊」後裔自「它目標投票中的區塊」。

這個檢查的[引入](https://github.com/ethereum/consensus-specs/pull/1742)，是為了修正三個浮現出來的議題。

1. 分叉選擇對證明的驗證與狀態轉換對證明的驗證之間的[不一致](https://github.com/ethereum/consensus-specs/issues/1408)。議題在於，如果某些證明就分叉選擇而言有效、但對納入區塊而言無效，這就是「驗證者之間網路觀點不同」的一個潛在來源，可能妨礙分叉選擇收斂。驗證者既透過證明 gossip、也透過區塊收到證明。理想上，這些管道中的每一個會包含或多或少相同的資訊。[^fn-inconsistency-of-attestations-blocks-gossip]

2. [來自不相容分叉的證明](https://github.com/ethereum/consensus-specs/issues/1456)。由於委員會洗牌只在[前一個紀元的開頭](/part2/building_blocks/randomness/#lookahead)被決定，這在「處理目標區塊來自不同分叉之證明」時可能導致實作上的挑戰。過一陣子，分叉最後會有不同的洗牌。客戶端常把洗牌快取起來，而必須處理這些邊界案例可能是臭蟲的一個來源。這個檢查移除了「驗證證明時要使用哪個狀態」的任何含混。它也防止驗證者在多個分叉的情況下，利用「[影響它們自己委員會指派](https://github.com/ethereum/consensus-specs/issues/1636)」的能力。

3. [故障或惡意的驗證者](https://github.com/ethereum/consensus-specs/issues/1636)不應能藉由利用這個不一致來影響分叉選擇。一筆未通過這個測試的證明，不會是由一個正確運作、誠實的驗證者所產生的。因此忽略它是最安全的。

[^fn-inconsistency-of-attestations-blocks-gossip]: 有一個這樣的不一致仍然存在：證明[在 gossip 中有效](#validate_target_epoch_against_current_time)的期間是最多兩個紀元，但在區塊中只有 32 個時段。

###### 只接受未來的時段

```none
    # Attestations can only affect the fork choice of subsequent slots.
    # Delay consideration in the fork choice until their slot is in the past.
    assert get_current_slot(store) >= attestation.data.slot + 1
```

這個判準在 [Gasper 論文](https://arxiv.org/abs/2003.03052)的 8.4 節中討論：在時段 $N$，只有來自「直到並含時段 $N-1$」之時段的證明，才可出現在 Store 中。

如果證明一被收到就被納入 Store，一個擁有若干不誠實驗證者的對手就能利用那一點，以機率方式分裂誠實驗證者的投票。不誠實的驗證者會在時段早期作證，把它們的投票分散在競爭的鏈頭區塊之間。由於網路延遲，當誠實的驗證者在「適當時間作證之前」運行它們自己的分叉選擇時，它們很可能會基於「它們到那時為止所收到的不誠實證明子集」而為每個候選者看到不同的權重。在那種情況下，誠實驗證者的投票最後可能被分裂。這可能使這條鏈無法收斂到單一一個鏈頭區塊。

引入這個「考量證明時延遲一個時段」的做法，使誠實的驗證者在時段 $N$ 全都為同一個鏈頭區塊投票的可能性大大增加，因為它們會全都看過直到時段 $N-1$ 為止的一組類似的證明，而不會被「對手在當前時段早期的證明」所影響。

|||
|-|------|
| 使用&nbsp;者 | [`on_attestation()`](#on_attestation) |
| 使用 | [`validate_target_epoch_against_current_time()`](#validate_target_epoch_against_current_time), [`compute_epoch_at_slot()`](/part3/helper/misc/#def_compute_epoch_at_slot), [`compute_start_slot_at_epoch()`](/part3/helper/misc/#def_compute_start_slot_at_epoch), [`get_ancestor()`](#get_ancestor), [`get_ancestor()`](#get_ancestor) |

##### `store_target_checkpoint_state`

```python
def store_target_checkpoint_state(store: Store, target: Checkpoint) -> None:
    # Store target checkpoint state if not yet seen
    if target not in store.checkpoint_states:
        base_state = copy(store.block_states[target.root])
        if base_state.slot < compute_start_slot_at_epoch(target.epoch):
            process_slots(base_state, compute_start_slot_at_epoch(target.epoch))
        store.checkpoint_states[target] = base_state
```

我們需要檢查點狀態，既為了提供驗證者餘額（用於在分叉選擇中為投票加權），也為了驗證者洗牌（在驗證證明時使用）。

<a id="checkpoint_block_epoch"></a>

一個 [`Checkpoint`](/part3/containers/dependencies/#checkpoint) 是對「一個紀元第一個時段」的指涉，是證明中 Casper FFG 投票所指向的東西。當一筆證明的目標是「之前緊鄰著空時段」的一個檢查點時，該檢查點的狀態不會與它所指向之區塊的狀態相符。因此，我們取那個區塊的狀態（`base_state`），並對它運行簡單的[空時段 `process_slots()`](/part3/transition/#def_process_slots) 狀態轉換，以把狀態更新到與該檢查點同步。

<a id="img_annotated_forkchoice_processSlots"></a>
<figure class="diagram" style="width: 70%">

![A diagram showing the state being updated to the checkpoint by process_slots.](images/diagrams/annotated-forkchoice-processSlots.svg)

<figcaption>

考量一個指向 $[N, B]$ 的檢查點，其中 $N$ 是檢查點高度（紀元號），$B$ 是最近區塊的區塊根。帶有虛線輪廓的形狀表示被略過的時段。`process_slots()` 函式取與該區塊相關的狀態 $S$，並藉由把空時段套到它上面，把它更新到該檢查點的時段，得出狀態 $S'$。

</figcaption>
</figure>

|||
|-|------|
| 使用&nbsp;者 | [`on_attestation()`](#on_attestation) |
| 使用 | [`compute_start_slot_at_epoch()`](/part3/helper/misc/#def_compute_start_slot_at_epoch), [`process_slots()`](/part3/transition/#def_process_slots),  |

##### `update_latest_messages`

```python
def update_latest_messages(store: Store, attesting_indices: Sequence[ValidatorIndex], attestation: Attestation) -> None:
    target = attestation.data.target
    beacon_block_root = attestation.data.beacon_block_root
    non_equivocating_attesting_indices = [i for i in attesting_indices if i not in store.equivocating_indices]
    for i in non_equivocating_attesting_indices:
        if i not in store.latest_messages or target.epoch > store.latest_messages[i].epoch:
            store.latest_messages[i] = LatestMessage(epoch=target.epoch, root=beacon_block_root)
```

一個[訊息](#latestmessage)由一個時間戳與一個區塊根（鏈頭）投票構成。這些分別以「該證明目標檢查點的紀元號」與「LMD GHOST 鏈頭區塊投票」的形式，從含有它的證明中擷取出來。等到我們到達這裡時，[`validate_on_attestation()`](#validate_on_attestation) 已經檢查過「鏈頭投票所針對的時段」屬於「對應於目標投票的紀元」。驗證者每個紀元正好投票一次，所以紀元號的粒度足以追蹤它們的最新投票。

`attesting_indices` 中的所有驗證者都做出了這同一筆證明。這筆證明會以單一一筆[聚合證明](/part3/containers/operations/#attestation)的形式走遍世界，但它在被傳給這個函式之前，已在 [`on_attestation()`](#on_attestation) 中被拆開了。我們那份[模稜兩可者](#on_attester_slashing)的搗蛋名單上的驗證者被過濾掉，而留下來的任何驗證者都被考量進行更新。

如果該驗證者索引尚未在 `store.latest_messages` 集合中，就插入它的投票；如果我們所擁有的投票比已儲存的投票更新，就更新它。每個驗證者在 `latest_messages` 集合中最多有一個條目。

|||
|-|------|
| 使用&nbsp;者 | [`on_attestation()`](#on_attestation) |
| 亦見 | [`Attestation`](/part3/containers/operations/#attestation), [`LatestMessage`](#latestmessage) |

### 處理器

下面的四個處理器——`on_tick()`、`on_block()`、`on_attestation()` 與 `on_attester_slashing()`——是分叉選擇規則的四種感官。它們是分叉選擇用以獲得它對外部世界之知識的手段，也是 Store 被更新的唯一手段。

這些處理器中沒有一個是被「規格中任何地方出現的程式碼」明確呼叫的。預期客戶端實作會在需要時呼叫每個處理器。依照分叉選擇規格頂端的引言材料，它們應依如下方式被呼叫。

  - 每當 `time > store.time` 時（其中 `time` 是當前 Unix 時間）呼叫 `on_tick(store, time)`。
  - 每當一個區塊 `block` 被收到時呼叫 `on_block(store, block)`。
  - 每當一筆證明 `attestation` 被收到時呼叫 `on_attestation(store, attestation)`。
  - 每當一筆證明者罰沒 `attester_slashing` 被收到時呼叫 `on_attester_slashing(store, attester_slashing)`。

#### `on_tick`

```python
def on_tick(store: Store, time: uint64) -> None:
    # If the ``store.time`` falls behind, while loop catches up slot by slot
    # to ensure that every previous slot is processed with ``on_tick_per_slot``
    tick_slot = (time - store.genesis_time) // SECONDS_PER_SLOT
    while get_current_slot(store) < tick_slot:
        previous_time = store.genesis_time + (get_current_slot(store) + 1) * SECONDS_PER_SLOT
        on_tick_per_slot(store, previous_time)
    on_tick_per_slot(store, time)
```

「tick」在規格中沒有被定義。在概念上，tick 被用來持續地讓分叉選擇的內部時鐘（`store.time`）保持更新。在實務上，呼叫 `on_tick()` 真正必要的時機只在一個時段的開頭、在進入一個時段 `SECONDS_PER_SLOT` `/` `INTERVALS_PER_SLOT` 時、以及[在提議一個區塊之前](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/phase0/validator.md#block-proposal)。然而，`on_tick()` 的處理是輕量的，更頻繁地呼叫它可能是方便的。

Teku 客戶端規律地[每秒兩次](https://github.com/ConsenSys/teku/blob/727e734e2d7c31112e1e313ef3cd2c0a004f81b2/services/timer/src/main/java/tech/pegasys/teku/services/timer/TimerService.java#L37)呼叫 `on_tick()`，因為它在內部被用來驅動分叉選擇以外的其他東西。此外，Teku 為它的 tick 間隔使用毫秒、而非秒為單位，這嚴格說來偏離了規格，但對於支援諸如 [Gnosis 信標鏈](https://docs.gnosischain.com/specs)（其 `SECONDS_PER_SLOT` 不是 `INTERVALS_PER_SLOT` 的倍數）這類其他鏈是必要的。

`while` 迴圈是在 Capella 規格中引入的。它確保 [`on_tick_per_slot()`](#on_tick_per_slot) 中的處理每個時段都被進行。當「自上一個 tick 被處理以來已經過了多個時段」時，這個迴圈為它們各自呼叫 `on_tick_per_slot()`，以便趕上。這唯一造成差別的，是在紀元邊界更新檢查點。先前，如果一個 tick 沒有在一個紀元第一個時段期間被處理，那麼檢查點更新可能會被不正確地略過。請注意，`on_tick_per_slot()` 更新 `store.time`，這進而更新 `get_current_slot()` 的輸出，所以迴圈會終止。

我預期，`time` 之所以作為一個參數提供、而非透過機器的時鐘查找，原因是這樣可簡化測試。

|||
|-|------|
| 使用 | [`get_current_slot()`](#get_current_slot), [`on_tick_per_slot()`](#on_tick_per_slot) |
| 亦見 | [`SECONDS_PER_SLOT`](/part3/config/configuration/#seconds_per_slot) |

#### `on_block`

```python
def on_block(store: Store, signed_block: SignedBeaconBlock) -> None:
    block = signed_block.message
    # Parent block must be known
    assert block.parent_root in store.block_states
    # Make a copy of the state to avoid mutability issues
    pre_state = copy(store.block_states[block.parent_root])
    # Blocks cannot be in the future. If they are, their consideration must be delayed until they are in the past.
    assert get_current_slot(store) >= block.slot

    # Check that block is later than the finalized epoch slot (optimization to reduce calls to get_ancestor)
    finalized_slot = compute_start_slot_at_epoch(store.finalized_checkpoint.epoch)
    assert block.slot > finalized_slot
    # Check block is a descendant of the finalized block at the checkpoint finalized slot
    assert get_ancestor(store, block.parent_root, finalized_slot) == store.finalized_checkpoint.root

    # Check the block is valid and compute the post-state
    state = pre_state.copy()
    block_root = hash_tree_root(block)
    state_transition(state, signed_block, True)
    # Add new block to the store
    store.blocks[block_root] = block
    # Add new state for this block to the store
    store.block_states[block_root] = state

    # Add proposer score boost if the block is timely
    time_into_slot = (store.time - store.genesis_time) % SECONDS_PER_SLOT
    is_before_attesting_interval = time_into_slot < SECONDS_PER_SLOT // INTERVALS_PER_SLOT
    if get_current_slot(store) == block.slot and is_before_attesting_interval:
        store.proposer_boost_root = hash_tree_root(block)

    # Update checkpoints in store if necessary
    update_checkpoints(store, state.current_justified_checkpoint, state.finalized_checkpoint)

    # Eagerly compute unrealized justification and finality
    compute_pulled_up_tip(store, block_root)
```

每當一個新的經簽署信標區塊被收到時，就應呼叫 `on_block()` 處理器。它做以下事情。

  - 進行一些有效性檢查。
  - 用該區塊及其相關的信標狀態更新 store。
  - 處理提議者增益（區塊及時性）。
  - 在被容許且需要時，更新 Store 的已證成與已最終確定檢查點。

`on_block()` 處理器不會為它所含的證明呼叫 `on_attestation()` 處理器，所以客戶端需要為每筆證明分別做那件事。

##### 有效性檢查

```none
    # Parent block must be known
    assert block.parent_root in store.block_states
    # Make a copy of the state to avoid mutability issues
    pre_state = copy(store.block_states[block.parent_root])
    # Blocks cannot be in the future. If they are, their consideration must be delayed until they are in the past.
    assert get_current_slot(store) >= block.slot

    # Check that block is later than the finalized epoch slot (optimization to reduce calls to get_ancestor)
    finalized_slot = compute_start_slot_at_epoch(store.finalized_checkpoint.epoch)
    assert block.slot > finalized_slot
    # Check block is a descendant of the finalized block at the checkpoint finalized slot
    assert get_ancestor(store, block.parent_root, finalized_slot) == store.finalized_checkpoint.root

    # Check the block is valid and compute the post-state
    state = pre_state.copy()
    block_root = hash_tree_root(block)
    state_transition(state, signed_block, True)
```

首先我們做一些相當不言自明的檢查。為了在分叉選擇中被考量，該區塊必須接合到我們已經擁有的區塊樹上（也就是，它的父代必須在 Store 中），依我們 Store 的時鐘而言它不可來自一個未來的時段，而且它必須來自一個後裔自我們已最終確定檢查點的分支。依「已最終確定」的定義，正典鏈先前的所有分支都被修剪掉。

最後的檢查是對該區塊運行一次完整的狀態轉換。這有兩個目的：（1）它檢查該區塊就共識規則而言是有效的，且（2）它給了我們該區塊的後狀態，這是我們需要加入 Store 的。我們從該區塊的父代取得它的前狀態，而我們知道父代已經在 store 中。傳給 [`state_transition()`](/part3/transition/#def_state_transition) 的 `True` 參數確保該區塊的簽章被檢查，並確保「把該區塊套用於狀態的結果」會得出「與該區塊所宣稱相同的狀態根」（「後狀態」必須相符）。客戶端在進行狀態轉換時會在別處運行這項操作，所以在一個最佳的實作中，`state_transition()` 呼叫的結果很可能會被快取在某處。

##### 更新 Store

```none
    # Add new block to the store
    store.blocks[block_root] = block
    # Add new state for this block to the store
    store.block_states[block_root] = state
```

一旦該區塊通過了有效性檢查，它與它的後狀態就能被加入 Store。

##### 處理提議者增益

```none
    # Add proposer score boost if the block is timely
    time_into_slot = (store.time - store.genesis_time) % SECONDS_PER_SLOT
    is_before_attesting_interval = time_into_slot < SECONDS_PER_SLOT // INTERVALS_PER_SLOT
    if get_current_slot(store) == block.slot and is_before_attesting_interval:
        store.proposer_boost_root = hash_tree_root(block)
```

[提議者增益](#proposer-boost)是對抗「對 LMD GHOST 之平衡攻擊」的一項防禦。它在分叉選擇中以額外的權重獎勵及時的區塊，使一個誠實提議者的區塊不太可能被孤立。

這裡，在 `on_block()` 處理器中，就是「區塊的及時性被評估並記錄」之處。如果在該區塊被處理時，Store 的時間（由 [`on_tick()`](#on_tick) 處理器所設定）在該時段的最初三分之一（`1 /` `INTERVALS_PER_SLOT`，亦即 4 秒）內，那麼我們就把 `store.proposer_boost_root` 設為該區塊的根。

`store.proposer_boost_root` 欄位只能在一個時段的最初四秒期間被設定，而它在下一個時段的開頭被 [`on_tick()`](#on_tick) 處理器清除。它在 [`get_weight()`](#get_weight) 函式中被用來判定是否加上額外的提議者增益權重。

請注意，如果該時段中有一次提議者模稜兩可，這段程式碼會把提議者增益套用於「收到的第二個區塊」、而非「收到的第一個區塊」。這對於使用 [MEV-Boost](https://github.com/flashbots/mev-boost/) 的第三方出塊之安全性變得重要——它可能[容許一個提議者](https://lighthouse-blog.sigmaprime.io/mev-unbundling-rpc.html)「偷走」一個區塊建構者區塊中的交易（代價是被罰沒），這被認為是一件壞事。比較好的做法是只把提議者增益套用於收到的第一個區塊，而有人提議了對 `on_block()` 的一個[小修補](https://github.com/ethereum/consensus-specs/pull/3352)來實作這一點。

##### 更新已證成與已最終確定

```none
    # Update checkpoints in store if necessary
    update_checkpoints(store, state.current_justified_checkpoint, state.finalized_checkpoint)

    # Eagerly compute unrealized justification and finality
    compute_pulled_up_tip(store, block_root)
```

如果該區塊後狀態中的已證成與已最終確定檢查點較好（也就是較高、較近），[`update_checkpoints()`](#update_checkpoints) 就單純地更新 Store 的已證成與已最終確定檢查點。Store 始終追蹤「它有能力驗證的、已知最佳的」已證成與已最終確定檢查點。

[`compute_pulled_up_tip()`](#compute_pulled_up_tip) 對該區塊運行紀元轉換的 Casper FFG 會計處理——在概念上把它從它的當前時段「拉起」到下一個紀元的第一個時段——以看看它是否已達成[未實現證成](#unrealised-justification)。該區塊的未實現證成會被儲存起來，供 [`filter_block_tree()`](#filter_block_tree) 稍後使用，而 Store 的未實現證成與未實現最終確定追蹤器可能會被更新。如果該區塊來自一個先前的紀元，那麼未實現的檢查點就變為已實現，而 [`update_checkpoints()`](#update_checkpoints) 會被再次呼叫，可能覆寫掉我們剛剛在上一行所做的更新。

|||
|-|------|
| 使用 | [`get_current_slot()`](#get_current_slot), [`compute_start_slot_at_epoch()`](/part3/helper/misc/#def_compute_start_slot_at_epoch), [`get_ancestor()`](#get_ancestor), [`hash_tree_root()`](/part3/helper/crypto/#hash_tree_root), [`state_transition()`](/part3/transition/#def_state_transition), [`update_checkpoints()`](#update_checkpoints), [`compute_pulled_up_tip()`](#compute_pulled_up_tip) |
| 亦見 | [`INTERVALS_PER_SLOT`](#intervals_per_slot) |

#### `on_attestation`

```python
def on_attestation(store: Store, attestation: Attestation, is_from_block: bool=False) -> None:
    """
    Run ``on_attestation`` upon receiving a new ``attestation`` from either within a block or directly on the wire.

    An ``attestation`` that is asserted as invalid may be valid at a later time,
    consider scheduling it for later processing in such case.
    """
    validate_on_attestation(store, attestation, is_from_block)

    store_target_checkpoint_state(store, attestation.data.target)

    # Get state at the `target` to fully validate attestation
    target_state = store.checkpoint_states[attestation.data.target]
    indexed_attestation = get_indexed_attestation(target_state, attestation)
    assert is_valid_indexed_attestation(target_state, indexed_attestation)

    # Update latest messages for attesting indices
    update_latest_messages(store, indexed_attestation.attesting_indices, attestation)
```

不論我們是怎麼聽聞證明的，它們都可能有用：它們可能被包含在一個區塊中、或透過 gossip 個別地被收到、或透過一隻信鴿[^fn-view-merge-attestations]。

[^fn-view-merge-attestations]: 若我們採用[視圖合併](https://ethresear.ch/t/view-merge-as-a-replacement-for-proposer-boost/13739?u=benjaminion)，這就會改變。屆時分叉選擇中只會考量「已被特別指定的聚合者所處理過」的證明。

如果該證明是從一個區塊中拆出來的，那麼旗標 `is_from_block` 就應被設為 `True`。這會使 [`validate_on_attestation()`](#validate_on_attestation) 中的及時性檢查被略過：不來自區塊的證明，為了影響分叉選擇，必須在它們被產生的那個紀元、或下一個紀元被收到。（所以，一隻信鴿會需要相當迅捷。）

[`validate_on_attestation()`](#validate_on_attestation) 函式對該證明進行一組全面的有效性檢查，以對抗各種攻擊。

假設該證明通過了檢查，我們就把它的目標檢查點狀態加入 Store 供稍後使用，同時也立即使用它。[`store_target_checkpoint_state()`](#store_target_checkpoint_state) 函式是冪等的，所以如果該狀態已經存在，就什麼都不會發生。

有了目標檢查點狀態，我們就能用它來查找驗證者的正確洗牌。手裡有了洗牌，呼叫 [`get_indexed_attestation()`](/part3/helper/accessors/#def_get_indexed_attestation) 就把 [`Attestation`](/part3/containers/operations/#attestation) 物件（包含一個位元串列）轉成一個 [`IndexedAttestation`](/part3/containers/dependencies/#indexedattestation) 物件（包含一個驗證者索引串列）。

最後，我們可以用 [`is_valid_indexed_attestation()`](/part3/helper/predicates/#def_is_valid_indexed_attestation) 驗證這個索引化證明，這相當於把它的聚合 BLS 簽章對照「這些被索引驗證者的公鑰集合」加以檢查。相較於其他的檢查，檢查簽章是相對昂貴的，這是把它延後到最後的原因之一（我們也不想對照一個[不一致的目標](#lmd-and-ffg-vote-consistency)來檢查它們）。

若且唯若一切都成功了，我們才呼叫 [`update_latest_messages()`](#update_latest_messages)，為「參與了這次投票的驗證者」刷新 Store 的最新訊息串列。

|||
|-|------|
| 使用 | [`validate_on_attestation()`](#validate_on_attestation), [`store_target_checkpoint_state()`](#store_target_checkpoint_state), [`get_indexed_attestation()`](/part3/helper/accessors/#def_get_indexed_attestation), [`is_valid_indexed_attestation()`](/part3/helper/predicates/#def_is_valid_indexed_attestation), [`update_latest_messages()`](#update_latest_messages) |

#### `on_attester_slashing`

> _注意_：`on_attester_slashing` 在同步期間應被呼叫，而一個客戶端「必須」維護「至少自最近的已最終確定檢查點以來」的 `AttesterSlashing` 模稜兩可集合。

```python
def on_attester_slashing(store: Store, attester_slashing: AttesterSlashing) -> None:
    """
    Run ``on_attester_slashing`` immediately upon receiving a new ``AttesterSlashing``
    from either within a block or directly on the wire.
    """
    attestation_1 = attester_slashing.attestation_1
    attestation_2 = attester_slashing.attestation_2
    assert is_slashable_attestation_data(attestation_1.data, attestation_2.data)
    state = store.block_states[store.justified_checkpoint.root]
    assert is_valid_indexed_attestation(state, attestation_1)
    assert is_valid_indexed_attestation(state, attestation_2)

    indices = set(attestation_1.attesting_indices).intersection(attestation_2.attesting_indices)
    for index in indices:
        store.equivocating_indices.add(index)
```

<a id="equivocation_balancing_attack"></a>

`on_attester_slashing()` 處理器[被加入](https://github.com/ethereum/consensus-specs/pull/2845)以對抗[模稜兩可平衡攻擊](https://ethresear.ch/t/balancing-attack-lmd-edition/11853?u=benjaminion)（在〈[Two Attacks On Proof-of-Stake GHOST/Ethereum](https://arxiv.org/abs/2203.01315)〉中有更正式的描述）。這個攻擊仰賴對手的驗證者對它們的證明模稜兩可——也就是每個紀元發布多筆不同的證明——而它無法由提議者分數增益所解決。

當然，模稜兩可的證明依 Casper FFG 戒律而言是可罰沒的。當攻擊最終結束時，那些驗證者會被懲罰並被逐出驗證者集合。然而與此同時，由於分叉選擇計算基於「上一個已證成紀元時的驗證者集合」，對手的驗證者可能讓攻擊無限期地持續下去。

這個機制不在分叉選擇之內加上大量的機制來追蹤並偵測相衝突的證明，而是仰賴「以[證明者罰沒訊息](/part3/containers/operations/#attesterslashing)的形式、透過區塊或直接從對等節點收到」的第三方罰沒主張。有效性檢查與狀態轉換的 [`process_attester_slashing()`](/part3/transition/block/#def_process_attester_slashing) 方法中的相同，包括 [`is_slashable_attestation_data()`](/part3/helper/predicates/#is_slashable_attestation_data) 的使用。這比我們在此處的目的所需更為寬廣，因為它既會排除模稜兩可的驗證者，也會排除做出環繞投票的驗證者。但排除所有行為不端的驗證者大概是個好主意。

任何被證明做出了相衝突證明的驗證者，都被加入 `store.equivocating_indices` 集合[^fn-python-set-add]。它們不再參與[分支權重](#get_weight)的計算，而它們未來的證明[在分叉選擇中會被忽略](#update_latest_messages)。我們被容許清除「上一個已最終確定檢查點之前」的任何模稜兩可證明資訊，但那些驗證者到那時應已被狀態轉換罰沒了，所以這個禁令是永久的。

[^fn-python-set-add]: `store.equivocating_indices` 是一個 Python Set。再次加入一個既有的元素是一個無操作，所以它不可能無界地成長。

|||
|-|------|
| 使用 | [`is_slashable_attestation_data()`](/part3/helper/predicates/#def_is_slashable_attestation_data)、[`is_valid_indexed_attestation()`](/part3/helper/predicates/#def_is_valid_indexed_attestation) |
| 亦見 | [`AttesterSlashing`](/part3/containers/operations/#attesterslashing)、[`process_attester_slashing()`](/part3/transition/block/#def_process_attester_slashing) |

### Bellatrix 分叉選擇 <!-- /part3/forkchoice/bellatrix/ -->

### 引言

本節涵蓋額外的 Bellatrix 分叉選擇文件，[v1.3.0](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/bellatrix/fork-choice.md)。若想看一個相輔相成的講法，見 Vitalik 的[註解版 Bellatrix 分叉選擇](https://github.com/ethereum/annotated-spec/blob/master/merge/fork-choice.md)（基於一個略舊的版本）。

一如往常，帶有側邊欄的文字是直接從規格引用的。

> 這是依「可執行信標鏈提案」對分叉選擇的修改。
>
> _注意_：它引入了「從最後一個 PoW 區塊過渡到第一個 PoS 區塊」的過程。

「可執行信標鏈提案」[^fn-executable-beacon-chain-name]就是後來被稱為合併的東西，由 [EIP-3675](https://eips.ethereum.org/EIPS/eip-3675) 連同信標鏈上的 Bellatrix 升級所規範。

[^fn-executable-beacon-chain-name]: 這個名稱來自 Mikhail Kalinin 在 [Ethresear.ch 上的原本文章](https://ethresear.ch/t/executable-beacon-chain/8271?u=benjaminion)。

對以太坊協定的升級，通常計畫在預先決定的區塊高度發生。基於安全理由，合併升級使用了一個不同的觸發條件，具體而言是工作量證明挖礦的一個[終端總難度](/part3/config/configuration/#transition-settings)。第一個達到那個累積難度量的工作量證明區塊，成為了最後一個工作量證明區塊：所有後續的執行區塊如今都以執行酬載的形式被合併進權益證明信標鏈。

Bellatrix 升級對分叉選擇引入的唯一功能性變更，是關於「確保信標鏈在合併的時點挑出一個有效的終端工作量證明區塊」。因此，這一節如今大體上只有歷史上的趣味。

本節其餘的材料（大多與 Engine API 相關）其實與分叉選擇規則根本無關。它主要描述「把分叉選擇決定單向傳達給執行層」。整體而言，這是一堆有點古怪的東西的集合，我猜是因為找不到更好的地方放它。

### 自訂型別

| 名稱 | SSZ 等價型別 | 描述 |
| - | - | - |
| `PayloadId` | `Bytes8` | 一個酬載建構過程的識別碼 |

`PayloadId` 被用來追蹤「從共識客戶端發給執行客戶端的有狀態請求」。具體而言，共識客戶端可以透過 [`notify_forkchoice_updated()`](#notify_forkchoice_updated) 命令（它對應到 Engine API 文件中的 [`engine_forkchoiceUpdatedV1`](https://github.com/ethereum/execution-apis/blob/main/src/engine/paris.md#engine_forkchoiceupdatedv1) RPC 方法），要求執行客戶端開始建立一個新的執行酬載。執行客戶端會回傳一個 `PayloadId` 參照，並繼續非同步地建構該酬載。稍後，共識客戶端可以藉由把同一個 `PayloadId` 傳給 engine API 的 [`engine_getPayloadV1`](https://github.com/ethereum/execution-apis/blob/main/src/engine/paris.md#engine_getpayloadv1) 方法，來取得該酬載。

### 協定

一如往常，帶有側邊欄的文字是直接從規格引用的。

#### `ExecutionEngine`

> _注意_：`notify_forkchoice_updated` 函式被加入 `ExecutionEngine` 協定，以示意分叉選擇更新。
>
> 這個函式的主體與實作相關。Engine API 可被用來以一個外部執行引擎實作它。

合併之後，每個共識客戶端（信標鏈客戶端）都必須與一個執行客戶端（`ExecutionEngine`；從前的 Eth1 客戶端）配對。執行客戶端有數個角色。

1. 它驗證執行酬載。
2. 它執行執行酬載，以維護以太坊的狀態（帳戶、合約、餘額、收據等等）。
3. 它透過它的 RPC API 為應用程式提供資料。
4. 它維護一個交易的記憶體池（mempool），從中它建構執行酬載，並把它們提供給共識層以散布。

這些角色中的第一個與最後一個，是在共識端讓我們感興趣的。第一個角色之所以重要，是因為信標區塊只有在「包含有效的執行酬載」時才有效。最後一個之所以重要，是因為共識端不直接處理一般的以太坊交易，無法建構它自己的執行酬載。

這兩端之間的介面稱為 [Engine API](https://github.com/ethereum/execution-apis/tree/main/src/engine)。Engine API 是執行客戶端提供給它的伴隨共識客戶端的 RPC（遠端程序呼叫）介面。它是單向的，意思是共識客戶端可以呼叫 Engine API 上的方法，但執行客戶端不會呼叫共識客戶端上的任何方法。

[TODO: link to `EngineAPI` section when written]::

Engine API 所提供最有意思的方法，是以下這三個。

  - [`engine_newPayloadV1`](https://github.com/ethereum/execution-apis/blob/main/src/engine/paris.md#engine_newpayloadv1)
    - 當共識客戶端收到一個新的信標區塊時，它擷取該區塊的執行酬載，並使用這個方法把它送給執行客戶端。執行客戶端會驗證該酬載並執行它所含的交易。這個方法的回傳值指明該酬載是否有效。
  - [`engine_forkchoiceUpdatedV1`](https://github.com/ethereum/execution-apis/blob/main/src/engine/paris.md#engine_forkchoiceupdatedv1)
    - 下方的函式 [`notify_forkchoice_updated()`](#notify_forkchoice_updated) 為兩個目的使用這個方法。第一，它被例行性地用來以最新的共識資訊更新執行客戶端：鏈頭區塊、安全鏈頭區塊與已最終確定區塊。第二，它可被用來提示執行客戶端開始從它的記憶體池建構一個執行酬載。共識客戶端在它即將提議一個信標區塊時會這麼做。
  - [`engine_getPayloadV1`](https://github.com/ethereum/execution-apis/blob/main/src/engine/paris.md#engine_getpayloadv1)
    - 這被用來取回先前透過 `engine_forkchoiceUpdatedV1` 請求的一個執行酬載，以一個 `PayloadId` 作為參照。

##### `notify_forkchoice_updated`

> 這個函式「原子地」進行三個動作：
>
>   - 重組執行酬載鏈與相應的狀態，以使 `head_block_hash` 成為鏈頭。
>   - 用 `safe_block_hash` 參數所提供的值更新安全區塊雜湊。
>   - 對執行狀態套用最終性：它不可逆轉地持久保存「所有執行酬載與相應狀態的鏈，直到並含 `finalized_block_hash`」。
>
> 此外，如果提供了 `payload_attributes`，這個函式就在 `head_block_hash` 之上啟動一個酬載建構過程，並回傳「已發起之過程」的一個識別碼。

```python
def notify_forkchoice_updated(self: ExecutionEngine,
                              head_block_hash: Hash32,
                              safe_block_hash: Hash32,
                              finalized_block_hash: Hash32,
                              payload_attributes: Optional[PayloadAttributes]) -> Optional[PayloadId]:
    ...
```

這是如上文所述、圍繞 Engine API 的 [`engine_forkchoiceUpdatedV1`](https://github.com/ethereum/execution-apis/blob/main/src/engine/paris.md#engine_forkchoiceupdatedv1) RPC 方法的一個包裝器。我們用它讓執行客戶端與最新的分叉選擇資訊保持同步，並（可選地）不時請求它為我們建構一個新的執行酬載。

> _注意_：`notify_forkchoice_updated` 函式呼叫的 `(head_block_hash, finalized_block_hash)` 值，對應到 [EIP-3675](https://eips.ethereum.org/EIPS/eip-3675#definitions) 中所定義的 `POS_FORKCHOICE_UPDATED` 事件。依照 EIP-3675，在一個過渡後區塊被最終確定之前，`notify_forkchoice_updated` 「必須」以 `finalized_block_hash = Hash32()` 被呼叫。

[EIP-3675](https://eips.ethereum.org/EIPS/eip-3675) 是合併在執行層端（Eth1 端）的規格。那裡所描述的 `POS_FORKCHOICE_UPDATED` 事件，由共識層呼叫 Engine API 的 `engine_forkchoiceUpdatedV1` 方法所觸發，而後者又由共識客戶端呼叫 `notify_forkchoice_updated()` 所觸發。共識客戶端會週期性地這麼做，特別是每當信標鏈上發生一次重組時，使得建構於執行層之上的應用程式能知道哪個狀態是當前的。

在合併與「合併之後第一個已最終確定紀元」之間，執行鏈上沒有最終性的保證，因此我們無法送給它一個已最終確定區塊雜湊，只得改用佔位用的預設值。

> _注意_：客戶端軟體「絕不可」在 PoW 網路上的過渡條件被滿足之前呼叫這個函式，亦即在「存在一個使 `is_valid_terminal_pow_block` 函式回傳 `True` 之區塊」之前。

在合併之後以前，工作量證明鏈對權益證明鏈對世界的觀點不感興趣。

> _注意_：客戶端軟體「必須」呼叫這個函式來發起酬載建構過程，以產生合併過渡區塊；在這種情況下，`head_block_hash` 參數「必須」被設為一個終端 PoW 區塊的雜湊。

在終端工作量證明區塊被偵測到之後，第一個信標鏈提議者會以 `payload_attributes` 參數呼叫 `notify_forkchoice_updated()`，以請求為第一個合併後的區塊建構一個執行酬載。

如果曾有多個候選的終端 PoW 區塊（就像 Goerli 測試網的合併那樣），信標區塊提議者本可自由選擇要請它的執行客戶端建構於它們當中的哪一個之上。

###### `safe_block_hash`

> `safe_block_hash` 參數「必須」被設為 [`get_safe_execution_payload_hash(store: Store)`](https://github.com/ethereum/consensus-specs/blob/v1.3.0/fork_choice/safe-block.md#get_safe_execution_payload_hash) 函式的回傳值。

「安全區塊」（safe block）功能是共識協定向執行層示意「一個區塊極不可能曾被回退」的一種方式。應用程式開發者可以使用安全區塊資訊，以一種偽快速最終性的形式，為它們的使用者提供更好的使用者體驗。關於這的更多內容，見後面的[安全區塊](/part3/safe-block/)那一節。

### 輔助函式

#### `PayloadAttributes`

> 用於透過 `notify_forkchoice_updated` 示意發起酬載建構過程。

```python
@dataclass
class PayloadAttributes(object):
    timestamp: uint64
    prev_randao: Bytes32
    suggested_fee_recipient: ExecutionAddress
    withdrawals: Sequence[Withdrawal]  # [New in Capella]
```

這個類別對應到 Engine API 的 [`PayloadAttributesV2`](https://github.com/ethereum/execution-apis/blob/main/src/engine/shanghai.md#payloadattributesv2) 類別，在請求執行客戶端開始建構一個執行酬載時被使用。

`prev_randao` 欄位是信標狀態當前的 [RANDAO](/part2/building_blocks/randomness/) 值，它已被前一個信標區塊中的 RANDAO reveal 所更新。它透過 EVM 新的 [`PREVRANDAO`](https://eips.ethereum.org/EIPS/eip-4399) 操作碼提供給執行層的應用程式。

`suggested_fee_recipient` 是「在酬載被執行時，任何來自交易小費的費用收入應被送往」的以太坊帳戶（從前稱為 `COINBASE`）。如果執行客戶端有它自己的費用收受者設定，它可能會覆寫這一項，因此叫「建議的」（suggested）。但容許它透過 Engine API 被設定，使得「託管多個驗證者的一個信標節點」有可能為每個驗證者使用一個不同的費用收受者位址，而若在執行端設定它，就會迫使它們全都使用同一個費用收受者位址。

`withdrawals` 欄位是在 [Capella 升級](/part4/history/capella/)中加入的。它容許共識層把一個提領串列傳給執行層，以納入一個執行酬載。它們最多會有 [`MAX_WITHDRAWALS_PER_PAYLOAD`](/part3/config/preset/#max_withdrawals_per_payload) 筆。當含有該酬載的區塊被處理時，對於每筆提領，該數額會從信標鏈上驗證者的餘額中被扣除，並會被加到 [`Withdrawal`](/part3/containers/dependencies/#withdrawal) 物件 `ExecutionAddress` 欄位中那個以太坊帳戶的餘額上。`ExecutionAddress` 衍生自該驗證者的[提領憑證](/part3/config/constants/#eth1_address_withdrawal_prefix)。

### `PowBlock`

```python
class PowBlock(Container):
    block_hash: Hash32
    parent_hash: Hash32
    total_difficulty: uint256
```

這個類別只是一種簡潔的方式，用以包裝我們在合併前後檢查工作量證明區塊所需的資訊。它由 [`get_pow_block()`](#get_pow_block) 回傳，由 [`is_valid_terminal_pow_block()`](#is_valid_terminal_pow_block) 取用。

#### `get_pow_block`

> 令 `get_pow_block(block_hash: Hash32) -> Optional[PowBlock]` 為這樣一個函式：給定 PoW 區塊的雜湊，它回傳該區塊的資料。如果所請求的區塊尚不可得，它可能得出 `None`。
>
> _注意_：`eth_getBlockByHash` JSON-RPC 方法可被用來從一個執行客戶端拉取這項資訊。

如前所述，`get_pow_block()` 是圍繞以太坊 [`eth_getBlockByHash`](https://ethereum.org/en/developers/docs/apis/json-rpc/#eth_getblockbyhash) JSON-RPC 方法的一個包裝器。給定一個區塊雜湊（不是它的雜湊樹根！——Eth1 區塊是用 RLP、而非 SSZ 編碼的），它回傳 [`PowBlock`](#powblock) 結構中的資訊。

`eth_getBlockByHash` 是一個標準的 Eth1 客戶端 RPC 方法，而非一個特定的 Engine API 方法。為了方便，執行客戶端除了標準的 RPC API 連接埠之外，往往也透過 Engine API 連接埠提供對這個方法的存取，使得共識客戶端能被配置成只連接到執行客戶端上的一個連接埠。

#### `is_valid_terminal_pow_block`

> 被分叉選擇處理器 `on_block` 使用。

```python
def is_valid_terminal_pow_block(block: PowBlock, parent: PowBlock) -> bool:
    is_total_difficulty_reached = block.total_difficulty >= TERMINAL_TOTAL_DIFFICULTY
    is_parent_total_difficulty_valid = parent.total_difficulty < TERMINAL_TOTAL_DIFFICULTY
    return is_total_difficulty_reached and is_parent_total_difficulty_valid
```

給定兩個 [`PowBlock`](#powblock) 物件（分別對應於一個工作量證明區塊與它的父工作量證明區塊），這個函式檢查該區塊是否符合「成為終端工作量證明區塊」的判準。也就是說，它的總難度超出終端總難度，而它父代的總難度沒有。

#### `validate_merge_block`

```python
def validate_merge_block(block: BeaconBlock) -> None:
    """
    Check the parent PoW block of execution payload is a valid terminal PoW block.

    Note: Unavailable PoW block(s) may later become available,
    and a client software MAY delay a call to ``validate_merge_block``
    until the PoW block(s) become available.
    """
    if TERMINAL_BLOCK_HASH != Hash32():
        # If `TERMINAL_BLOCK_HASH` is used as an override, the activation epoch must be reached.
        assert compute_epoch_at_slot(block.slot) >= TERMINAL_BLOCK_HASH_ACTIVATION_EPOCH
        assert block.body.execution_payload.parent_hash == TERMINAL_BLOCK_HASH
        return

    pow_block = get_pow_block(block.body.execution_payload.parent_hash)
    # Check if `pow_block` is available
    assert pow_block is not None
    pow_parent = get_pow_block(pow_block.parent_hash)
    # Check if `pow_parent` is available
    assert pow_parent is not None
    # Check if `pow_block` is a valid terminal PoW block
    assert is_valid_terminal_pow_block(pow_block, pow_parent)
```

這被 Bellatrix 的 `on_block()` 處理器使用。`block` 參數是一個「宣稱自己是第一個合併後區塊」的信標區塊。也就是說，它是（當前分支上）第一個包含非預設 [`ExecutionPayload`](/part3/containers/execution/#executionpayload) 的信標區塊。

[`TERMINAL_BLOCK_HASH`](/part3/config/configuration/#transition-settings) 是一個參數，客戶端運營者本可協議在必要時用它來覆寫終端總難度機制。舉例來說，如果合併導致了信標鏈分叉，那麼這些分叉本可藉由「手動協議一個 Eth1 合併區塊、並透過客戶端命令列參數把 `TERMINAL_BLOCK_HASH` 設為它的值」來解決。實際上並不需要這麼做，而 `TERMINAL_BLOCK_HASH` 仍維持它的預設值 `Hash32()`。

這個函式其餘的部分檢查：（a）「身為執行酬載之父代的 PoW 區塊」存在，且總難度大於 [`TERMINAL_TOTAL_DIFFICULTY`](/part3/config/configuration/#transition-settings)，以及（b）那個區塊的父代存在，且總難度小於 `TERMINAL_TOTAL_DIFFICULTY`。（難度檢查在 [`is_valid_terminal_pow_block()`](#is_valid_terminal_pow_block) 中進行。）

<a id="img_annotated_forkchoice_the_merge_block"></a>
<figure class="diagram" style="width: 80%">

![A diagram showing the relationship between the merge block and the terminal proof of work block.](images/diagrams/annotated-forkchoice-the-merge-block.svg)

<figcaption>

第一個信標鏈合併後區塊，包含「其父 PoW 區塊曾是終端 PoW 區塊」的執行酬載。終端 PoW 區塊是第一個「總難度超出 [`TERMINAL_TOTAL_DIFFICULTY`](/part3/config/configuration/#transition-settings)」的 PoW 區塊。

</figcaption>
</figure>

父 PoW 區塊與祖父 PoW 區塊透過 [`get_pow_block()`](#get_pow_block) 函式被取回，這在實務上涉及對附接的 Eth1／執行客戶端發出 RPC 呼叫。如果這些呼叫中任一者失敗，一個 `assert` 就會被觸發，而 `on_block()` 處理器會放棄退出，不做出任何變更。

### 更新後的分叉選擇處理器

#### `on_block`

> _注意_：唯一的修改是加上對「過渡區塊條件」的驗證。

```python
def on_block(store: Store, signed_block: SignedBeaconBlock) -> None:
    """
    Run ``on_block`` upon receiving a new block.

    A block that is asserted as invalid due to unavailable PoW block may be valid at a later time,
    consider scheduling it for later processing in such case.
    """
    block = signed_block.message
    # Parent block must be known
    assert block.parent_root in store.block_states
    # Make a copy of the state to avoid mutability issues
    pre_state = copy(store.block_states[block.parent_root])
    # Blocks cannot be in the future. If they are, their consideration must be delayed until they are in the past.
    assert get_current_slot(store) >= block.slot

    # Check that block is later than the finalized epoch slot (optimization to reduce calls to get_ancestor)
    finalized_slot = compute_start_slot_at_epoch(store.finalized_checkpoint.epoch)
    assert block.slot > finalized_slot
    # Check block is a descendant of the finalized block at the checkpoint finalized slot
    assert get_ancestor(store, block.parent_root, finalized_slot) == store.finalized_checkpoint.root

    # Check the block is valid and compute the post-state
    state = pre_state.copy()
    block_root = hash_tree_root(block)
    state_transition(state, signed_block, True)

    # [New in Bellatrix]
    if is_merge_transition_block(pre_state, block.body):
        validate_merge_block(block)

    # Add new block to the store
    store.blocks[block_root] = block
    # Add new state for this block to the store
    store.block_states[block_root] = state

    # Add proposer score boost if the block is timely
    time_into_slot = (store.time - store.genesis_time) % SECONDS_PER_SLOT
    is_before_attesting_interval = time_into_slot < SECONDS_PER_SLOT // INTERVALS_PER_SLOT
    if get_current_slot(store) == block.slot and is_before_attesting_interval:
        store.proposer_boost_root = hash_tree_root(block)

    # Update checkpoints in store if necessary
    update_checkpoints(store, state.current_justified_checkpoint, state.finalized_checkpoint)

    # Eagerly compute unrealized justification and finality.
    compute_pulled_up_tip(store, block_root)
```

如前所述，此處對正常 [`on_block()`](/part3/forkchoice/phase0/#on_block) 處理器唯一的增添，是這幾行：

```none
    # [New in Bellatrix]
    if is_merge_transition_block(pre_state, block.body):
        validate_merge_block(block)
```

當給定的區塊是第一個包含執行酬載的信標區塊時，[`is_merge_transition_block()`](/part3/helper/predicates/#def_is_merge_transition_block) 函式會回傳 `True`，否則回傳 `False`。

為了確保執行鏈與信標鏈在合併時的一致性，這第一個合併後的信標區塊需要一些額外的處理。我們必須檢查「它的執行酬載所衍生自的 PoW 區塊」確實符合了[合併的判準](#is_valid_terminal_pow_block)。本質上，它的總難度必須超出終端總難度，而它父代的總難度必須沒有。如果這個測試失敗，那麼就有什麼出了錯，這個信標區塊必須被排除在分叉選擇之外。

萬一在合併的時點發生 PoW 分叉，可能會有好幾個候選的執行區塊符合這個判準——[這在合併其中一個測試網時發生過](https://web.archive.org/web/20230630134924/https://nitter.it/vdWijden/status/1557555377314701312)[^fn-teku-besu-goerli-merge]——但那沒關係。「成為正典的第一個合併後信標區塊[^fn-first-merged-beacon-block]」的提議者，可決定哪個終端執行區塊勝出。

[^fn-teku-besu-goerli-merge]: 並對一些客戶端實作觸發了[一個議題](https://hackmd.io/@ajsutton/SJJYWezC9)。

[^fn-first-merged-beacon-block]: 記錄一下，主網上第一個合併後的信標區塊在[時段 4700013](https://beaconcha.in/slot/4700013)。

## 安全區塊 <!-- /part3/safe-block/ -->

### 引言

[分叉選擇安全區塊規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/fork_choice/safe-block.md)其實不是信標鏈分叉選擇的一部分，它位於 consensus 儲存庫中一份不同的文件裡。它是一個啟發法，用以利用分叉選擇的 Store 資料，在一些合理的假設之下識別出一個「不會被回退」的區塊。舉例來說，它可被應用程式用來為交易實作一個結算期。這與一個假設有個類比：在工作量證明之下、沒有 51% 攻擊的情況下，一個區塊在「特定數目的區塊（比如說十五個）已被建構於它之上」之後，就變得免於重組。

> 在誠實多數與某些網路同步性假設之下，存在一個免於重組的區塊。通常這個區塊相當接近正典鏈的鏈頭，這使得向使用者揭露一個安全區塊很有價值。
>
> 本節描述一個找出一個安全區塊的演算法。

當然，終極的安全區塊是上一個已最終確定檢查點。但那可能是幾分鐘之前，即使在理想的網路條件下也是如此。如果我們假設（a）有一個誠實多數的驗證者，且（b）它們的訊息被及時地收到，那麼我們原則上能識別出一個更近的、不會有回退風險的區塊。

#### `get_safe_beacon_block_root`

```python
def get_safe_beacon_block_root(store: Store) -> Root:
    # Use most recent justified block as a stopgap
    return store.justified_checkpoint.root
```

> _注意_：目前的安全區塊演算法單純地回傳 `store.justified_checkpoint.root`，並且預計在未來被改進。

在上述假設之下，回傳已證成檢查點確實是安全的，但我們幾乎肯定能做得更好。最近在「提供一個更有用的安全區塊」方面已有大幅的進展。關於這的更多內容，在「共識」那一章的[確認規則](/part2/consensus/lmd_ghost/#confirmation-rule)那一節。

#### `get_safe_execution_payload_hash`

```python
def get_safe_execution_payload_hash(store: Store) -> Hash32:
    safe_block_root = get_safe_beacon_block_root(store)
    safe_block = store.blocks[safe_block_root]

    # Return Hash32() if no payload is yet justified
    if compute_epoch_at_slot(safe_block.slot) >= BELLATRIX_FORK_EPOCH:
        return safe_block.body.execution_payload.block_hash
    else:
        return Hash32()
```

> _注意_：這個輔助函式使用在 [Bellatrix](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/bellatrix/beacon-chain.md) 中擴充的信標區塊容器。

Bellatrix 是合併前的升級，它為信標區塊加上了執行酬載雜湊，以為合併本身做準備。以太坊上的應用程式大體上不知道信標鏈，會使用執行酬載雜湊、而非信標區塊根，作為它們在 Eth1 區塊鏈中的參考點。

# 第四部分：升級 <!-- /part4/ -->

<!-- Protocol upgrades, sometimes called hard forks, are backward-incompatible changes to the specification. This is how Ethereum has historically delivered improvements and extra capabilities to the Eth1 chain, and now to the Eth2 beacon chain. -->

TODO

## 硬分叉 <!-- /part4/forks/* -->

TODO

### 分叉摘要（Fork Digest）

TODO

## 升級歷史 <!-- /part4/history/ -->

### 引言

透過 2021 年 2 月的一個公開過程，我們決定信標鏈（共識層）升級會[以恆星命名](https://github.com/ethereum/eth2.0-pm/issues/202#issuecomment-775789449)。我們依英文字母順序取用它們，第一個是 [Altair](https://github.com/ethereum/consensus-specs/issues/2218)。創世配置仍叫 Phase&nbsp;0，源於現已廢止的「交付以太坊&nbsp;2.0 的[三階段計畫](https://web.archive.org/web/20220916204934/https://docs.ethhub.io/ethereum-roadmap/ethereum-2.0/eth-2.0-phases/)」。

迄今升級的一份摘要在下方，更詳細的描述在以下各節。[^fn-upgrade-config]

[^fn-upgrade-config]: [客戶端配置檔](https://github.com/Consensys/teku/blob/master/ethereum/spec/src/main/resources/tech/pegasys/teku/spec/config/configs/mainnet.yaml#L42)是升級時間與日期的一個有用參考。

| 名稱 | 紀元 | 日期&nbsp;(UTC) | 主要主題 | 規格&nbsp;標籤 | 發布&nbsp;名稱 |
| - | - | -- | -- | - | -- |
| [Phase&nbsp;0](/part4/history/phase0/) | 0      | 2020-12-01 12:00:23 | 創世配置 | [v1.0.0](https://github.com/ethereum/consensus-specs/releases/tag/v1.0.0) | Cosmic Egg |
| [Altair](/part4/history/altair/)       | 74240  | 2021-10-27 10:56:23 | 同步委員會與經濟改革 | [v1.1.0](https://github.com/ethereum/consensus-specs/releases/tag/v1.1.0) |  The Great Machine |
| [Bellatrix](/part4/history/bellatrix/) | 144896 | 2022-09-06 11:34:47 | 合併就緒升級 | [v1.2.0](https://github.com/ethereum/consensus-specs/releases/tag/v1.2.0) | Ailuropoda melanoleuca[^fn-giant-panda] |
| [Capella](/part4/history/capella/)     | 194048 | 2023-04-12 22:27:35 | 啟用提領 | [v1.3.0](https://github.com/ethereum/consensus-specs/releases/tag/v1.3.0) | Gamlum[^fn-gamlum] |
| [Deneb](/part4/history/deneb/)         | 待定    | 待定                 | EIP-4844 資料可用性 | 待定  | 待定 |
| [Electra](/part4/history/electra/)     | 待定    | 待定                 | 待定 | 待定  | 待定 |

[^fn-giant-panda]: Ailuropoda melanoleuca 是[大貓熊](https://en.wikipedia.org/wiki/Giant_panda)的正式名稱。

[^fn-gamlum]: Gamlum 可能曾是 [Capella](https://en.wikipedia.org/wiki/Capella)（五車二）一個與山羊相關的古名。

合併是一種特殊的升級，因為它不是一次手動的硬分叉。支援合併所需的協定變更，在 Bellatrix 升級中完成。合併本身在九天後發生，沒有任何進一步的介入，與執行層的 [Paris 升級](https://github.com/ethereum/execution-specs/blob/master/network-upgrades/mainnet-upgrades/paris.md)同時發生。

[TODO: link to Merge section when done]::

共識層規格是增量式撰寫的。每個版本（例如當前的 Bellatrix [v1.3.0](https://github.com/ethereum/consensus-specs/tree/v1.3.0/specs) 版本）都包含先前版本未改變的規格，再加上「詳述新版本變更」的一組分開的文件。因此，舉例來說，要建構 Bellatrix，你需要 [Phase&nbsp;0](https://github.com/ethereum/consensus-specs/tree/v1.3.0/specs/phase0) 規格、疊在它之上的 [Altair](https://github.com/ethereum/consensus-specs/tree/v1.3.0/specs/altair)「差異」規格、以及再疊在它之上的 [Bellatrix](https://github.com/ethereum/consensus-specs/tree/v1.3.0/specs/bellatrix)「差異」規格，全部都帶有相同的 GitHub 發布標籤（在這個情況下是 v1.3.0）。

共識規格儲存庫包含一些其他的、未發布的版本，例如 [das](https://github.com/ethereum/consensus-specs/tree/dev/specs/_features/das)（資料可用性抽樣）、[custody_game](https://github.com/ethereum/consensus-specs/tree/dev/specs/_features/custody_game) 與 [sharding](https://github.com/ethereum/consensus-specs/tree/dev/specs/_features/sharding)。這些反映了不同的研究方向，處於各種不同的時效狀態。

#### 升級時機

在工作量證明之下，升級（合併除外）在「預先數週選定」的區塊高度進行。由於雜湊算力的變化，預測它們的時機是困難的——它們可能會偏離目標時間數小時、甚至一兩天。

在權益證明之下，我們有能精確到秒地為網路升級計時的奢侈。儘管如此，我們的目標是在 256 個紀元的邊界進行升級。這些邊界既對應於區塊根與狀態根的[批次間隔](/part3/transition/epoch/#historical-summaries-updates)（[`SLOTS_PER_HISTORICAL_ROOT`](/part3/config/preset/#slots_per_historical_root) 個時段），也對應於同步委員會週期（[`EPOCHS_PER_SYNC_COMMITTEE_PERIOD`](/part3/config/preset/#sync-committee) 個紀元）。讓協定不在這些週期的中途改變，會使「之後用它們的資料驗證證明」變得更容易。

256 個紀元的一段週期約為 27 小時，所以我們每天大約得到一次進行升級的機會。

### Phase 0 <!-- /part4/history/phase0/ -->

基於歷史的原因，信標鏈在它創世時的初始配置被稱為 Phase&nbsp;0。

信標鏈創世發生於 2020 年 12 月 1 日 UTC 12:00:23。多出來的 23 秒，來自第一個符合[創世判準](/part3/initialise/#genesis-state)之 Eth1 區塊的時間戳，即[區塊 11320899](https://etherscan.io/block/11320899)。它是工作量證明的一小點殘餘，永遠嵌在信標鏈的歷史之中。

|||
| - | - |
| `MIN_GENESIS_TIME` | `uint64(1606824000)` (Dec 1, 2020, 12pm UTC) |
| `GENESIS_FORK_VERSION` | `Version('0x00000000')` |

完整的描述見 [Phase 0 規格](https://github.com/ethereum/consensus-specs/tree/v1.3.0/specs/phase0)。這些規格今天仍適用於信標鏈，除了「它們被 [Altair](/part4/history/altair/)、[Bellatrix](/part4/history/bellatrix/) 或更晚的升級取代」之處。

我的 [Phase&nbsp;0 註解版規格](https://benjaminion.xyz/eth2-annotated-spec/phase0/beacon-chain/)仍然可得。

### Altair <!-- /part4/history/altair/ -->

Altair 升級發生於 2021 年 10 月 27 日 UTC 10:56:23。

|||
| - | - |
| `ALTAIR_FORK_VERSION` | `Version('0x01000000')` |
| `ALTAIR_FORK_EPOCH` | `Epoch(74240)` (Oct 27, 2021, 10:56:23am UTC) |

Altair 升級的主要目標是：

1. 引入同步委員會以支援輕客戶端，
2. 大幅重新設計信標鏈的獎勵與懲罰會計處理，以及
3. 開始把一些懲罰參數朝它們的最終值增加。

為了支援同步委員會，做出了以下變更。

  - 為同步委員會函式設立的新[加密域](/part3/config/constants/#domain-types)。
  - 支援同步委員會的新資料結構。即 [`SyncAggregate`](/part3/containers/operations/#syncaggregate) 與 [`SyncCommittee`](/part3/containers/dependencies/#synccommittee)。
  - 管理同步委員會的函式：
    - [`get_next_sync_committee_indices()`](/part3/helper/accessors/#def_get_next_sync_committee_indices)；
    - [`get_next_sync_committee()`](/part3/helper/accessors/#def_get_next_sync_committee)；
    - [`process_sync_aggregate()`](/part3/transition/block/#def_process_sync_aggregate)，它負責處理同步委員會參與的獎勵與懲罰會計處理；以及
    - [`process_sync_committee_updates()`](/part3/transition/epoch/#def_process_sync_committee_updates)。
  - [P2P 規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/altair/p2p-interface.md)中加入了 gossip 主題，以支援同步委員會的活動。

對會計處理的改革是廣泛的，我不會在此把它們全部列出，因為它們在註解版規格與本書的別處有徹底的涵蓋。但總結而言，

  - 有一個[轉變](https://github.com/ethereum/consensus-specs/pull/2176#issue-779590549)：從「在紀元邊界做完所有證明納入的會計處理」，轉為「在紀元期間持續地進行大部分的工作」。紀元轉換無論如何都相當沉重；這分散了工作負載，整體而言也較簡單。
  - 不同行為的激勵被微調，例如遲到的證明與區塊提議獎勵。我們也藉機簡化了獎勵與懲罰的計算。
  - [怠惰洩漏](/part2/incentives/inactivity/)被更改，使它現在以每驗證者、而非全域的方式被套用。

至於懲罰參數，以下參數被更新。隨著我們對運行信標鏈漸漸熟悉，這些參數在創世時曾被放寬：

  - [`INACTIVITY_PENALTY_QUOTIENT`](/part3/config/preset/#inactivity_penalty_quotient_bellatrix) 從 $2^{26}$ 減為 $3 \times 2^{24}$。這在怠惰洩漏期間更快地減少質押。
  - [`MIN_SLASHING_PENALTY_QUOTIENT`](/part3/config/preset/#min_slashing_penalty_quotient_bellatrix) 從 128 減為 64。這把「持有完整質押之驗證者」的初始罰沒懲罰設為 0.5&nbsp;ETH，而非 Phase&nbsp;0 的 0.25&nbsp;ETH。
  - [`PROPORTIONAL_SLASHING_MULTIPLIER`](/part3/config/preset/#proportional_slashing_multiplier_bellatrix) 從 1 增為 2，使得萬一超過三分之一的驗證者一起被罰沒，完整的懲罰會是移除它們質押的三分之二、而非 Phase&nbsp;0 的三分之一。

Phase&nbsp;0 與 Altair 之間變更的整體描述，在 [Altair 規格](https://github.com/ethereum/consensus-specs/tree/v1.3.0/specs/altair)中。

我的 [Altair 註解版規格](/../altair/part3/)仍然可得。

### Bellatrix <!-- /part4/history/bellatrix/ -->

Bellatrix 升級發生於 2022 年 9 月 6 日 UTC 11:34:47。

|||
| - | - |
| `BELLATRIX_FORK_VERSION` | `Version('0x02000000')` |
| `BELLATRIX_FORK_EPOCH` | `Epoch(144896)` (Sept 6, 2022, 11:34:47am UTC) |

Bellatrix 的首要目標，是讓信標鏈為九天後發生的[合併](/part4/merge/)做好準備。它包含了以下元素。

  - 加入了保存執行酬載的資料結構，即 [`ExecutionPayload`](/part3/containers/execution/#executionpayload) 與 [`ExecutionPayloadHeader`](/part3/containers/execution/#executionpayloadheader)。
  - [執行酬載的處理](/part3/transition/block/#process_execution_payload)被加入[區塊處理](/part3/transition/block/#block-processing)。
  - [分叉選擇](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/bellatrix/fork-choice.md)被更新，以辨識信標鏈端從工作量證明到權益證明的過渡。
  - gossip 訊息與 Req/Resp 分塊的最大尺寸在 [P2P 規格](https://github.com/ethereum/consensus-specs/blob/v1.3.0/specs/bellatrix/p2p-interface.md)中被增加，以容納信標區塊因執行酬載而多出的尺寸。此外，gossip 區塊的有效性規則被更新。

此外，延續 Altair 的變更，一些懲罰參數被更新為它們的最終值。隨著我們對運行信標鏈漸漸熟悉，這些參數在合併前的發布版中曾被放寬：

  - [`INACTIVITY_PENALTY_QUOTIENT`](/part3/config/preset/#inactivity_penalty_quotient_bellatrix) 從 $3 \times 2^{24}$ 減為 $2^{24}$。這在怠惰洩漏期間更快地減少質押。
  - [`MIN_SLASHING_PENALTY_QUOTIENT`](/part3/config/preset/#min_slashing_penalty_quotient_bellatrix) 從 64 減為 32。這把「持有完整質押之驗證者」的初始罰沒懲罰設為 1&nbsp;ETH，而非 0.5&nbsp;ETH。
  - [`PROPORTIONAL_SLASHING_MULTIPLIER`](/part3/config/preset/#proportional_slashing_multiplier_bellatrix) 從 2 增為 3，使得萬一超過三分之一的驗證者一起被罰沒，完整的懲罰會是移除它們的全部質押。

Altair 與 Bellatrix 之間變更的整體描述，在 [Bellatrix 規格](https://github.com/ethereum/consensus-specs/tree/v1.3.0/specs/bellatrix)中。

我的 [Bellatrix 註解版規格](/../bellatrix/part3/)仍然可得。

### Capella <!-- /part4/history/capella/ -->

共識層的 Capella 升級發生於 2023 年 4 月 12 日 UTC 22:27:35，與執行層的 [Shanghai 升級](https://github.com/ethereum/execution-specs/blob/master/network-upgrades/mainnet-upgrades/shanghai.md)同時。這是兩層第一次經協調、同時的升級。這次合併的升級以「Shapella」這個名稱為人所知。

Capella 包含了以下更新：

  - 它啟用了從信標鏈到 Eth1 帳戶的[自動提領](/part3/transition/block/#def_process_withdrawals)；
  - 它為質押者提供了一個方式，做出從 BLS 式提領憑證到 Eth1 式提領憑證的一次性[變更](/part3/transition/block/#def_process_bls_to_execution_change)；
  - 歷史根在信標狀態中被儲存的方式[被修改](/part3/transition/epoch/#def_process_historical_summaries_update)；以及，
  - 有一次對[分叉選擇規則](/part3/forkchoice/)規格的大型重構，連同一些行為上的變更。

藉由終於啟用提領，Capella 在某種意義上完成了合併，履行了 2.5 年前對質押者所做的承諾——它們最終會能領取它們的獎勵、取回它們的質押。

實作了兩種提領機制。

  1. 已退出且可提領的驗證者，它們的全部餘額被自動轉移到它們的提領位址。
  2. 來自活躍驗證者的多餘餘額，定期被掃入它們的提領位址。

Bellatrix 與 Capella 之間變更的整體描述，在 [Capella 規格](https://github.com/ethereum/consensus-specs/tree/v1.3.0/specs/capella)中。

我的 [Capella 註解版規格](/../capella/part3/)仍然可得。

### Deneb <!-- /part4/history/deneb/ -->

Capella 之後的共識層升級被取名為 [Deneb](https://hackmd.io/@benjaminion/Hkm5x5acj#d-star-name)（天津四），會與執行層的 [Cancun 升級](https://github.com/ethereum/execution-specs/blob/master/network-upgrades/mainnet-upgrades/cancun.md)同時發生。

Deneb 所含的主要工作，會是「共識層支援 [EIP-4844](https://eips.ethereum.org/EIPS/eip-4844) 資料可用性[所需的工作](https://github.com/ethereum/consensus-specs/tree/dev/specs/deneb)」。

以下變更也[計畫納入](https://github.com/ethereum/consensus-specs/releases/tag/v1.4.0-beta.0)。

  - [EIP-7044](https://eips.ethereum.org/EIPS/eip-7044)：把自願退出域鎖定在 Capella [#3288](https://github.com/ethereum/consensus-specs/pull/3288)
  - [EIP-7045](https://eips.ethereum.org/EIPS/eip-7045)：增加最大證明納入時段 [#3360](https://github.com/ethereum/consensus-specs/pull/3360)
  - [EIP-4788](https://eips.ethereum.org/EIPS/eip-4788)：在執行層揭露父信標區塊根 [#3421](https://github.com/ethereum/consensus-specs/pull/3421)
  - [EIP-7514](https://eips.ethereum.org/EIPS/eip-7514)：加入最大紀元變動上限 [#3499](https://github.com/ethereum/consensus-specs/pull/3499)
  - 萬一發生模稜兩可，把提議者增益套用於第一個區塊 [#3352](https://github.com/ethereum/consensus-specs/pull/3352)

### Electra <!-- /part4/history/electra/ -->

Deneb 之後的共識層升級被取名為 Electra，會與執行層的 Prague 升級同時發生。

關於 Electra 升級潛在範圍的一場早期階段討論，正在共識規格儲存庫的 [Issue 3449](https://github.com/ethereum/consensus-specs/issues/3449) 中進行。

## 合併 <!-- /part4/merge/* -->

TODO

### 歷史

TODO

#### 測試合併

TODO

### 架構

TODO

### 過渡

TODO

### Engine API

TODO

### 樂觀同步

TODO

# 附錄 <!-- /appendices/ -->

## 質押 <!-- /appendices/staking/* -->

### 引言

TODO

### 質押的方式

TODO

### 客戶端多樣性

TODO

### 常見問答

TODO

## 如何成為一名核心開發者 <!-- /appendices/core-dev/* -->

### 所以你想當核心開發者？

TODO

### 資源

TODO

## 參考

TODO

## 運行規格 <!-- /appendices/running/ -->

### 引言

由於規格是用 Python 寫的，它本身是可執行的。這對於產生測試案例極為美妙，而規格儲存庫中有一整套[基礎設施](https://github.com/ethereum/consensus-specs/tree/dev/tests/generators)正是用來做這件事的。

我們也可以自己運行規格來做有意思的事。在這個演練中，我們會計算規格所定義之各種[容器](/part3/containers/)的最小與最大尺寸。以下程式碼出自 [Protolambda](https://gist.github.com/protolambda/db75c7faa1e94f2464787a480e5d613e#file-compute_bounds-py)，經輕度修改以加以簡化並更新。

```python
from inspect import getmembers, isclass
from eth2spec.utils.ssz.ssz_typing import Container
from eth2spec.capella import mainnet

def get_spec_ssz_types():
    return [
        value for (_, value) in getmembers(mainnet, isclass)
        if issubclass(value, Container) and value != Container  # only the subclasses, not the imported base class
    ]

type_bounds = {
    value.__name__: ({
        'size': value.type_byte_length()
    } if value.is_fixed_byte_length() else {
        'min_size': value.min_byte_length(),
        'max_size': value.max_byte_length(),
    }) for value in get_spec_ssz_types()
}

import json
print(json.dumps(type_bounds))
```

### 設置

在下文中，如果你使用 Ubuntu，你可能需要先運行 `sudo apt install python3-pip`。如果不是，那麼你大概需要使用 `python` 而非 `python3`。

規格的安裝比以前容易得多。

```bash
> git clone https://github.com/ethereum/consensus-specs.git
Cloning into 'consensus-specs'...
...
> cd consensus-specs/
> python3 -m pip install .
... lots of output ...
Successfully installed...
> make pyspec
... lots more output ...
```

一切順利的話，這會在 `tests/core/pyspec/eth2spec/` 之下為每個規格版本建立一個目錄：`altair`、`bellatrix`、`capella` 等等。每個目錄都包含那個版本的完整可執行規格，從 markdown 原始檔自動建構而成。每一個都有一個 `mainnet` 版本，以及一個以較低資源需求運行的 `minimal` 版本。這一切魔法都由 `pysetup` 中的指令稿執行。

### 運行

最後，我們就能單純地運行上面的 Python 指令稿。把它複製進一個叫 `sizes.py` 的檔案，並依如下方式運行它。

```bash
> source venv/bin/activate
(venv) > python sizes.py | jq
{
  "AggregateAndProof": {
    "min_size": 337,
    "max_size": 593
  },
...
```

導向 `jq` 的管線是可選的，沒有它你只會得到較不美觀的輸出。

<details>
<summary>完整輸出</summary>

各個值的單位是位元組。別因為「`BeaconState` 的最大尺寸結果是 139&nbsp;TiB」、或「`BeaconBlockBody` 可以巨大無比」而驚慌。這些尺寸基於它們所含的概念上[最大 SSZ 串列長度](/part2/building_blocks/ssz/#lists)，在實務上並不切實際。

```none
{
  "AggregateAndProof": {
    "min_size": 337,
    "max_size": 593
  },
  "Attestation": {
    "min_size": 229,
    "max_size": 485
  },
  "AttestationData": {
    "size": 128
  },
  "AttesterSlashing": {
    "min_size": 464,
    "max_size": 33232
  },
  "BLSToExecutionChange": {
    "size": 76
  },
  "BeaconBlock": {
    "min_size": 984,
    "max_size": 1125899911198752
  },
  "BeaconBlockBody": {
    "min_size": 900,
    "max_size": 1125899911198668
  },
  "BeaconBlockHeader": {
    "size": 112
  },
  "BeaconState": {
    "min_size": 2737221,
    "max_size": 152833729758309
  },
  "Checkpoint": {
    "size": 40
  },
  "ContributionAndProof": {
    "size": 264
  },
  "Deposit": {
    "size": 1240
  },
  "DepositData": {
    "size": 184
  },
  "DepositMessage": {
    "size": 88
  },
  "Eth1Block": {
    "size": 48
  },
  "Eth1Data": {
    "size": 72
  },
  "ExecutionPayload": {
    "min_size": 512,
    "max_size": 1125899911038176
  },
  "ExecutionPayloadHeader": {
    "min_size": 568,
    "max_size": 600
  },
  "Fork": {
    "size": 16
  },
  "ForkData": {
    "size": 36
  },
  "HistoricalBatch": {
    "size": 524288
  },
  "HistoricalSummary": {
    "size": 64
  },
  "IndexedAttestation": {
    "min_size": 228,
    "max_size": 16612
  },
  "LightClientBootstrap": {
    "min_size": 25600,
    "max_size": 25632
  },
  "LightClientFinalityUpdate": {
    "min_size": 1992,
    "max_size": 2056
  },
  "LightClientHeader": {
    "min_size": 812,
    "max_size": 844
  },
  "LightClientOptimisticUpdate": {
    "min_size": 984,
    "max_size": 1016
  },
  "LightClientUpdate": {
    "min_size": 26776,
    "max_size": 26840
  },
  "PendingAttestation": {
    "min_size": 149,
    "max_size": 405
  },
  "PowBlock": {
    "size": 96
  },
  "ProposerSlashing": {
    "size": 416
  },
  "SignedAggregateAndProof": {
    "min_size": 437,
    "max_size": 693
  },
  "SignedBLSToExecutionChange": {
    "size": 172
  },
  "SignedBeaconBlock": {
    "min_size": 1084,
    "max_size": 1125899911198852
  },
  "SignedBeaconBlockHeader": {
    "size": 208
  },
  "SignedContributionAndProof": {
    "size": 360
  },
  "SignedVoluntaryExit": {
    "size": 112
  },
  "SigningData": {
    "size": 64
  },
  "SyncAggregate": {
    "size": 160
  },
  "SyncAggregatorSelectionData": {
    "size": 16
  },
  "SyncCommittee": {
    "size": 24624
  },
  "SyncCommitteeContribution": {
    "size": 160
  },
  "SyncCommitteeMessage": {
    "size": 144
  },
  "Validator": {
    "size": 121
  },
  "VoluntaryExit": {
    "size": 16
  },
  "Withdrawal": {
    "size": 44
  }
}
```

</details>

### 亦見

Hsiao-Wei Wang 在 Devcon VI 上做了一場關於共識 Pyspec 的[閃電演講](https://archive.devcon.org/archive/watch/6/how-to-use-executable-consensus-pyspec/)。她迅速地涵蓋了它的結構、如何運行它、以及如何建構測試案例。[簡報投影片](https://docs.google.com/presentation/d/10HdtwTaFdTVLaiIGQJClyCs8AzrPXS20i78LZnPXHyo/edit?usp=sharing)可取得。

## 詞彙表 <!-- /appendices/reference/glossary/* -->

TODO
