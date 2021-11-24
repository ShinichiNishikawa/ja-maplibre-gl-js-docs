---
title: Style Specification
description: 'This specification defines and describes the visual appearance of a map: what data to draw, the order to draw it in, and how to style the data when drawing it.'
contentType: specification
navOrder: 4
order: 1
layout: page
hideFeedback: true
products:
- Mapbox Style Specification
overviewHeader:
  title: Style Specification
  features: []
  ghLink: https://github.com/maplibre/maplibre-gl-js/tree/main/src/style-spec
  changelogLink: https://github.com/maplibre/maplibre-gl-js/blob/main/src/style-spec/CHANGELOG.md
---

<!-- A MapLibre style is a document that defines the visual appearance of a map: what data to draw, the order to draw it in, and how to style the data when drawing it. A style document is a [JSON](http://www.json.org/) object with specific root level and nested properties. This specification defines and describes these properties. -->
MapLibre スタイルとは、地図の見え方を定義するドキュメントです。定義には、どのようなデータを描画するか、どのような順序で描画するか、データを描画する際にどのようにスタイルを設定するかなどが含まれます。スタイルドキュメントは、特定のルートレベルとネストされたプロパティを持つ[JSON](http://www.json.org/)オブジェクトです。本仕様では、これらのプロパティを定義し、説明します。

<!-- The intended audience of this specification includes: -->
この仕様書の想定読者は次の方々を含みます:

<!-- - Advanced designers and cartographers who want to write styles by hand. -->
- 地図スタイルを直接記述したい専門性の高いデザインーとカルトグラファー
<!-- - Developers using style-related features of [MapLibre GL JS](https://github.com/maplibre/maplibre-gl-js) or the [MapLibre Maps SDK for Android](https://github.com/maplibre/maplibre-gl-native). -->
- MapLibre GL JS](https://github.com/maplibre/maplibre-gl-js)または[MapLibre Maps SDK for Android](https://github.com/maplibre/maplibre-gl-native)のスタイル関連機能を使用する開発者
<!-- - Authors of software that generates or processes MapLibre styles. -->
- MapLibre のスタイルを生成、または処理するソフトウェアの作成者

<!-- ## Style document structure -->
## スタイルドキュメントの構造

<!-- A MapLibre style consists of a set of [root properties](/maplibre-gl-js-docs/style-spec/root), some of which describe a single global property, and some of which contain nested properties. Some root properties, like [`version`](/maplibre-gl-js-docs/style-spec/root/#version), [`name`](/maplibre-gl-js-docs/style-spec/root/#name), and [`metadata`](/maplibre-gl-js-docs/style-spec/root/#metadata), don't have any influence over the appearance or behavior of your map, but provide important descriptive information related to your map. Others, like [`layers`](/maplibre-gl-js-docs/style-spec/layers) and [`sources`](/maplibre-gl-js-docs/style-spec/sources), are critical and determine which map features will appear on your map and what they will look like. Some properties, like [`center`](/maplibre-gl-js-docs/style-spec/root/#center), [`zoom`](/maplibre-gl-js-docs/style-spec/root/#zoom), [`pitch`](/maplibre-gl-js-docs/style-spec/root/#pitch), and [`bearing`](/maplibre-gl-js-docs/style-spec/root/#bearing), provide the map renderer with a set of defaults to be used when initially displaying the map. -->
MapLibreのスタイルは、一連の[ルートプロパティ](/maplibre-gl-js-docs/style-spec/root)から構成されています。その中には、グローバルなプロパティを示す一行の記述もあれば、ネストされたプロパティもあります。[`version`](/maplibre-gl-js-docs/style-spec/root/#version)、[`name`](/maplibre-gl-js-docs/style-spec/root/#name)、[`metadata`](/maplibre-gl-js-docs/style-spec/root/#metadata)は、地図の外観や動作には影響しない、重要な記述的情報を提供します。[`layers`](/maplibre-gl-js-docs/style-spec/layers)や[`sources`](/maplibre-gl-js-docs/style-spec/sources)は、地図にどの要素を表示させ、それらの外観をどうするのかを決定する重要なプロパティです。[`center`](/maplibre-gl-js-docs/style-spec/root/#center)、[`zoom`](/maplibre-gl-js-docs/style-spec/root/#zoom)、[`pitch`](/maplibre-gl-js-docs/style-spec/root/#pitch)、[`bearing`](/maplibre-gl-js-docs/style-spec/root/#bearing)などは、地図を最初にレンダリングして表示する際のデフォルトの値を指定します。

