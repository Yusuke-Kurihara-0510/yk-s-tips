# 概要
もう少し現在のチャットの内容を深掘りしたいが、新しいチャットに移動しないといけない時に役立つプロンプト

```
トークン節約のためここまでの情報をプロンプトに変換してください。
あなたが理解できれば良いので日本語である必要はありません。人間が理解できる必要もありません
```

すると以下のようなものが回答されます（claudeの場合。他のLLMだと違うかも）
この時はGraphDBについてのレポート作成の時に整形してもらったりしていました

```
<context>
GDB_PROPS={
  core:[flexibility,schemaless,runtime_mod],
  key_points:{
    ext:"Node props dynamic add w/o schema mod",
    fe_impact:"FE needs updates for new props",
    impl_note:"TypeScript: optional props + any"
  },
  patterns:{
    ts:"interface N{req:str,opt?:T,[k:s]:any}",
    neo4j:"MATCH(n)SET n.new='val'"
  },
  doc_style:{
    audience:"non_tech",
    focus:["biz_impact","concepts"],
    avoid:["impl_details","coding_rules"],
    structure:[
      "summary",
      "core_features",
      "considerations",
      "examples",
      "fe_integration"
    ]
  },
  req:{
    format:"md",
    tone:"simple",
    depth:"mid"
  }
}
</context>
```

次に引き継ぎ先で以下のプロンプト

```
以下の情報はあなたが別セッションで圧縮した情報になります
こちらを展開して会話を継続したいです

<context> GDB_PROPS={ core:[flexibility,schemaless,runtime_mod], key_points:{ ext:"Node props dynamic add w/o schema mod", fe_impact:"FE needs updates for new props", impl_note:"TypeScript: optional props + any" }, patterns:{ ts:"interface N{req:str,opt?:T,[k:s]:any}", neo4j:"MATCH(n)SET n.new='val'" }, doc_style:{ audience:"non_tech", focus:["biz_impact","concepts"], avoid:["impl_details","coding_rules"], structure:[ "summary", "core_features", "considerations", "examples", "fe_integration" ] }, req:{ format:"md", tone:"simple", depth:"mid" } } </context>
```

これで別チャットの内容を引き継げる