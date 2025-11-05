# おみくじ BOT 用 WordParty V2

最終更新日：<% tp.date.now('YYYY/MM/DD') %>

![[/sharedTemplate/intro/intro_11]] WordParty テンプレート です。

- このテンプレートは、下記のパッケージで使用するほか、独自に使用できます。
- それぞれ、最新版で使用できます。バージョンが古い場合、正常に機能しない可能性があります。

![[/packages/OmikujiBot/template/_common/OmikujiBotPackageBOOTH]]

![[/sharedTemplate/intro/intro_22_IntroOneComme]]

## このテンプレートは何？（Features）

![](./images/features-03.webp)

### おみくじ BOT を賑やかに演出する WordParty セット

- 【おみくじ BOT 用 WordParty】は、わんコメの機能 「[WordParty](https://onecomme.com/docs/feature/wordparty)」のセットです。
- 通常の用途でも使用できますが、[おみくじ BOT](app://obsidian.md/OmikujiBot/README.md)  と組み合わせることで、最大限の演出を引き出せます。
  - 遅延を利用して、複数の演出を順番に再生 (WordParty の PRO 版機能「コネクター」のようなもの)
  - おみくじの結果に応じて、ランダムに演出を発動
  - 複数の演出を同時に発動し、画面全体を覆い尽くす ([スイカゲーム](https://suikagame.jp/) のような表現が可能です)

![](../OmikujiBot/images/features-02.webp)

## インストール方法 (Installation)

![Installation_41_GotoTemplate](/sharedTemplate/installation/Installation_41_GotoTemplate.md)

- WordPatry のテンプレートは、他のジェネレーターと同様の導入が可能です。

![Installation_32_AddWordParty](/sharedTemplate/installation/Installation_32_AddWordParty.md)

## つかいかた・カスタマイズ (Usage/Customization)

使い方は、既存の WordParty と同じです。[コメントによる演出 - WordParty](https://onecomme.com/docs/feature/wordparty) をご覧ください。

カスタマイズも、「素材に関する注意事項」さえ守っていただければ、既存の WordParty と同じように扱えます。

## よくある質問 (FAQ)

WordParty に関する内容は、[コメントによる演出 - WordParty](https://onecomme.com/docs/feature/wordparty) をご参照ください。

![faq_11_infoOneComme](/packages/OmikujiBot/template/faq/faq_11_infoOneComme.md)

### 設定関連

#### Q. パターンに入っている、「^」ってなに？「!」ってなに？

A: **「^」は、前方一致と呼ばれる正規表現です。** **正規表現については、生成 AI に聞いてみてください。**「!」が付いているのは、コメントでその演出が意図せず出現しないようにする対処です。_ID で発動させればよかったよね？_

#### Q. 一部 PRO 版の機能使っていない？大丈夫？

A: 大丈夫だって製作者さんが言ってた！

#### Q. 「初見さん参戦」は おみくじ BOT 以外で使ってもいい?

A: わんコメの WordParty と一緒に使っていれば、どんな使い方でも OK です。それ以外の場所で使うのはご遠慮ください。

## トラブルシューティング (Troubleshooting)

![troubleshooting_11_infoOneComme](/packages/OmikujiBot/template/troubleshooting/troubleshooting_11_infoOneComme.md)

### フォルダ名を変えたら WordPatry エディタで開けなくなる

A: [仕様](https://onecomme.com/docs/feature/wordparty#%E3%81%9D%E3%81%AE%E4%BB%96%E4%BB%95%E6%A7%98) です。名前を変える場合、テンプレート名の最初が「word-party」の文字列から始まるようにしてください。

## クレジット・ライセンス（Credits/License）

- [おみくじBOT用WordParty クレジット・ライセンス](sub/OmikenWordPartyCredits.md) にまとめています。
- このアプリに収録されている効果音データは、クリエイティブ・コモンズではないものも含まれております。それらは別途利用規約があるものか、本アプリ専用に制作された画像・動画です。他の用途での使用・転載・再配布は禁止します。

## バージョン情報 (Version)

### v1.4.0-beta5 25/11/03

- [効果音ラボ](https://soundeffect-lab.info/) での利用規約の問題に触れている可能性があったため、ファイルを大きく変更しています。(前バージョンの配布は停止しています)
	- 特に、おみくじ BOT のアプリと組み合わせるケースで問題があった（効果音を任意に選んで鳴らせるような仕組みがあった）ためです。
	- そのため、過去の「おみくじ BOT」のデータとは互換性がありません。
	- また、再配布にならないよう、わんコメの WordParty エディターで編集できないようになっています。
- また、これにより、フキダシ表示時の効果音は、この WordParty からではなく、ジェネレーター本体から鳴らすように変更しています。
- クリエイティブ・コモンズの素材を使用するようになったため、クレジット・ライセンス の表記を細かく記載するようにしました。

### v1.2.0-beta3 25/09/18

- [効果音ラボ](https://soundeffect-lab.info/) から新しい効果音素材を 2 種類追加。
- 「タロットカード」と「超おみくじ」用に新しい素材を追加。

### v1.1.0 25/09/09

- 「おみくじ BOT」「おみくじ BOT コンフィグエディター」と揃えるため、バージョニングを揃えることにしました。
- 過去のリリースノートは [こちら](https://github.com/Pintocuru/OmikujiBot-Docs/releases/tag/v1.0.0-OmikujiBotWordParty)

![credits_99_sesupin](/sharedTemplate/credits/credits_99_sesupin.md)

<%* await tp.user.expandEmbeds(tp) %>
