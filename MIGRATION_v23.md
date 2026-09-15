# RDL Music Theory — v2.3 boundary migration

この文書は、RDL Music Theoryを現行RDL_Core v2.3の有限境界モデルへ同期するための読み替え境界を記録する。

## Current authority

現行Music本線では、次を基準とする。

```text
対象側の有限関係構造
  -> SILN_music / W_music

interaction
  ↓ finite B
有限作用断面
  -> RIB_B

自己側
  -> M_B

same frozen pre-update M_B
  + RIB_B(t)
  -> F

same frozen pre-update M_B
  + RIB_B(t+Δ)
  -> F'

E = Δ(F, F')
  ↓ finite review
unresolved remainder -> H_vec
H = ||H_vec||

H >= θ
  -> M_Δ
  -> T1 reconstruction path
```

有限Bは少なくとも、Purpose、対象範囲、interaction/action section、選択関係・次元、比較条件、必要な提示・観測条件を有限に固定する。

`W_music` と Γ はMusic-localな補助記述・検証規則であり、T0 primitiveを追加するものではない。

## EFP compatibility

旧文書に残る `EFP` は、現行Music本線のprimitiveとしては使用しない。

旧文書が `EFP` を「現在入力として切り出された作用断面」の意味で使っている場合、現行基準では次のように読む。

```text
legacy EFP
  -> interactionからfinite Bで切り出された RIB_B
```

ただし、機械的な文字列置換は行わない。旧検証記録・旧計画書・文書地図には形成史として `EFP` が残りうる。そこから現行T0/T1の意味を採用するときは、`00_RDL音楽理論.md`、`01_RDL音楽_Core.md`、`03_RDL音楽_全体設計方針.md`、`00_Core/README.md` を優先する。

## Non-equivalences

```text
SILN_music / W_music != RIB_B
RIB_B != M_B
F != RIB_B
E != H
nonzero E != unresolved by identity
H != musical tension
ξ != noise
ξ != numeric runtime pressure
ξ != probe target
```

有限Bを引く限り、未回収関係ξは残る。

```text
forall finite B:
  ξ(B) != 0
```

Bを変更して以前の未回収関係の一部を新しい有限断面で記述できても、ξの最終消去を意味しない。

## Scope

このmigrationは、Musicの既存検証Python群や音楽固有の検証結果を大規模に作り直すものではない。今回の中心は前提境界と役割分離の同期である。

歴史的な検証結果はその時点の語彙とともに保持し、現行仕様として再利用するときだけ、この読み替え境界を通す。
