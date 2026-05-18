# Auナノギャップ構造を用いたDIETによる超伝導量子ビット1/fノイズ低減：理論的設計提案

## Abstract

超伝導量子ビットにおける1/fノイズは、表面に吸着した熱的揺らぎ子（TLF: Two-Level Fluctuator）が主要な原因の一つである。de Graaf et al.（2018）は、Auナノギャップ構造を用いたDIET（電子遷移誘起脱離）プロセスにより、TLFを除去し1/fノイズを10倍低減することを実験的に示した。ただし同論文は、DIETが除去するのはTLF（low速揺らぎ子）のみであり、量子ビットと直接共鳴するコヒーレントTLS（cTLS）の密度は変化しないことを明示している。ノイズ低減はGTM（一般化トンネリングモデル）を通じたTLF→cTLSの間接的な相互作用によるものである。

本研究では、この実験的知見に基づき、Auナノギャップ構造の設計パラメータとDIETによるノイズ低減効果の理論的関係を定量化し、設計ツール群（Tool 1〜5）として公開した。主な新規貢献として、（1）de Graaf 2018のTLF帯域幅W〜100K（〜8,600 μeV）と量子ビット動作温度15mKにおける熱エネルギー（1.3 μeV）の6,615倍のエネルギースケール乖離を初めて定量化し、DIETの有効性に関する未解決の理論的問題を明示した。（2）Gans理論による電場増強の近似計算に使用した定数（LZ・EPS_M・L=80nm）の導出根拠が未記録であることを明示し、FDTD計算の必要性を示した。（3）ScAlN薄膜のCTE整合点がalpha_ScN=6.61 ppm/K（Ciprian et al. 2024）の使用により13.8%から33.2%へ大幅に修正され、弾性定数M_biが44%異なることを示した。本研究は理論的提案であり、実験的検証は今後の課題である。

---

## 1. Introduction

超伝導量子ビットおよびイオントラップ量子デバイスの性能は、電極表面に吸着した不純物分子が引き起こす1/fノイズによって制限される。このノイズの主要因は、表面の熱的揺らぎ子（TLF: Two-Level Fluctuator）であり、一般化トンネリングモデル（GTM）を通じてコヒーレントTLS（cTLS）に間接的に影響を与える。

表面ノイズを低減する手法として、de Graaf et al.（2018）はAuナノギャップ構造を用いたDIET（電子遷移誘起脱離）プロセスにより、超伝導共振器のTLFを除去し1/fノイズを約10倍低減することを実験的に示した。ただし同論文は、DIETが除去するのはTLF（low速揺らぎ子）のみであり、cTLS密度は変化しなかったことを明示している。このDIETプロセスを実装するデバイスとして、表面音響波（SAW）デバイスが有力な候補である。SAWデバイスはLiNbO3またはLiTaO3基板上のIDT（櫛形電極）により弾性波を励起し、圧電効果を通じてAuナノギャップ近傍に局所電場を生成できる。

SAWデバイスの性能は圧電薄膜材料の選択に大きく依存する。ScAlN（窒化スカンジウムアルミニウム）はSc組成の調整により圧電係数・弾性定数・熱膨張係数（CTE）を制御できる材料として注目されており、LiNbO3基板との熱応力整合が重要な設計課題である。本研究では、M_bi（Zhang et al. 2013）およびα_ScN（Ciprian et al. 2024、6.61±0.60 ppm/K）に基づき、CTE整合点をSc濃度33.2%と算出した。これは従来値（13.8%）から大幅に修正された値であり、弾性定数M_biに44%の差異をもたらす。

以上の知見に基づき、本研究は以下の論理的接続による統合設計ツール群（Tool 1〜5）を開発した：ScAlN SAWデバイス設計（Tool 3・4・5）→ DIET前処理によるTLF除去 → Auナノギャップ近傍の電場増強（Tool 1）→ 量子ビット1/fノイズ低減（Tool 2）。本研究は理論的設計提案であり、この接続の実験的検証は今後の課題である。

---

## 2. Physical Model

### 2.1 TLFと量子ビットノイズの関係（GTMモデル）

表面TLFと量子ビットノイズの関係は、一般化トンネリングモデル（GTM）によって記述される。GTMにおいて、1/fノイズのスペクトル密度S(f)は以下のように表される：

S(f) ∝ (T/W) × d²_TLF × N_TLF / f

ここでTは温度、Wはエネルギー分布の帯域幅（de Graaf 2018においてW~100K、~8,600 μeVと推定。これは脱離エネルギーによって上限が制限された推定値であり、直接測定値ではない）、d_TLFはTLFの双極子モーメント、N_TLFはTLF密度である。DIETによりN_TLFが低減すると、S(f)が比例して低減する。

d_TLFについて：本研究ではSarabi et al.（PRL 116, 167002, 2016）のSiNx薄膜における実測値（0.1〜8.3 D）を参考値として使用した。ただしAuナノギャップ表面上のd_TLFは現時点で未測定であり、SiNxの値を直接適用することの妥当性は確認されていない。これは本研究における最優先の未解決課題である。

重要な制約：de Graaf et al.（2018）は、DIETによってcTLS密度は変化しなかったことを明示している。ノイズ低減はTLF→cTLSの間接的相互作用を通じた効果である。エネルギー乖離にもかかわらず実験的に10倍のノイズ低減が確認されており、そのメカニズムは未解明である。

### 2.2 Auナノギャップの電場増強（Gans近似）

Auナノギャップ近傍の電場増強は、Gans（1915）の回転楕円体モデルに基づく近似式を用いた：

E_field ∝ (λ/gap)^1.5 × E_incident

ただしGans理論は孤立回転楕円体に適用される理論であり、ダイマーナノギャップへの直接適用は近似的である。本ツール群の目的はFDTD計算の代替ではなく、実験設計の初期指針を提供することである。正確な電場増強値にはFDTD計算が必要であり（Oskooi et al., Comput. Phys. Commun. 181, 687, 2010）、これは今後の課題である。実際の計算コードでは以下の近似式を使用した：

E_field ∝ gap^(-2.5)

### 2.3 エネルギースケールの乖離

DIETが作用するTLFのエネルギースケールと量子ビット動作域のエネルギースケールの間には重大な乖離が存在する。de Graaf et al.（2018）においてW~100Kは、TLFのエネルギー分布帯域幅の推定値であり脱離エネルギーによって上限が制限される。一方、量子ビット動作温度15mKにおける熱エネルギーはkT = 1.3 μeVである。

kT（15mK）= (1.381×10⁻²³ × 0.015) / 1.602×10⁻¹⁹ = 1.293 μeV

この6,615倍のエネルギースケール乖離は本研究で初めて定量化されたものである。エネルギー乖離にもかかわらずde Graaf 2018は実験的に10倍のノイズ低減を確認しており、DIETがなぜ有効であるかのメカニズムは未解明の理論的問題である。

### 2.4 ScAlN設計モデル

ScAlNの二軸弾性定数M_biはZhang et al.（JAP 114, 243516, 2013）の多項式フィットを使用した：

M_bi(x) = -1430x² - 264x + 471 [GPa]（0 ≤ x ≤ 0.375、室温DFT値）

CTE整合条件（α_ScAlN = α_substrate）はVegard則に基づく線形補間により算出した：

α_ScAlN(x) = α_AlN + x × (α_ScN - α_AlN)

α_AlN = 4.2 ppm/K（Davydov 2002）、α_ScN = 6.61±0.60 ppm/K（Ciprian et al. APL 124, 052203, 2024、XRD実測値）を使用した。サファイア基板（α = 5.0 ppm/K）との整合点はSc ≈ 33.2%と算出された。

重要な注意が2点ある。第一に、線形補間はVegard則に基づく近似であり、実測値との乖離が生じる可能性がある。第二に、Lu et al.（APL Mater. 6, 076105, 2018）はScAlNのCTEを全Sc%において4.18〜4.65 ppm/Kと測定しており、サファイアCTE（5.0 ppm/K）を下回る。このため、CTE整合点が実際には存在しない可能性があり、本モデルには高い不確実性が伴う。また4K以下の極低温におけるScAlNのCTEおよびM_biの文献は現時点で存在しない。

---

## 3. Key Results

### 3.1 エネルギースケール乖離の定量化

de Graaf et al.（2018）のTLFエネルギー分布帯域幅W~100K（~8,600 μeV）と量子ビット動作温度15mKにおける熱エネルギーkT = 1.293 μeVの比を計算した：

乖離比 = 8,600 / 1.293 = 6,615倍

この乖離は本研究で初めて定量化されたものであり、DIETが量子ビット動作域のTLSに直接作用するかどうかは未解決の理論的問題である。一方、de Graaf et al.（2018）は実験的に10倍のノイズ低減を確認しており、GTMを通じた間接的効果が有効であることを示している。

### 3.2 Gans近似の限界の明示

電場増強の計算にはGans近似（E∝gap^(-2.5)）を使用したが、脱分極因子LZ=0.039はcylinder AR=4として記録されているが独立した検証がなされていない。また媒質誘電率EPS_M=2.25（SiO₂として設定）の根拠も記録されていない。de Graaf et al.（2018）の実験環境はAl₂O₃基板（ε≈3.1）であり設定値との乖離がある。Gans理論はダイマーナノギャップには不適用であり、正確な電場増強値にはFDTD計算が必要である。

### 3.3 ScAlN CTE整合点の修正

旧モデル（出典不明のα_ScN = 10.0 ppm/Kに基づく）：
CTE整合点（サファイア基板） Sc ≈ 13.8%
M_bi(0.138) = -1430×0.019 - 264×0.138 + 471 = 407.4 GPa

新モデル（Ciprian et al. 2024、α_ScN = 6.61 ppm/Kに基づく）：
CTE整合点（サファイア基板） Sc ≈ 33.2%
M_bi(0.332) = -1430×0.110 - 264×0.332 + 471 = 226.0 GPa

差異：CTE整合点が+19.4ポイント修正され、M_biが407.4→226.0 GPa（44%減少）となった。ただしLu et al.（2018）の実測値との矛盾があり、CTE整合点が実際には存在しない可能性がある。

### 3.4 d_TLS感度解析

ノイズスペクトル密度S(f)はd²_TLFに比例する。Sarabi et al.（2016）が報告するSiNxにおけるd_TLFの範囲（0.1〜8.3 D）を用いると：

S(f)の変化比 = (8.3/0.1)² = 6,889倍

この6,889倍の不確実性は、Au表面上のd_TLFが未測定であることに起因する。d_TLFの実測はこの研究における最優先の実験課題である。

---

## 4. Discussion

### 4.1 本研究の位置づけ

本研究は実験的検証を伴わない理論的設計提案である。既存の電磁場シミュレーションツール（COMSOL、MEEPなど）は高精度な数値計算を提供するが、量子デバイス設計に特化したパラメータ（DIETによるTLF除去効果・ScAlN応力・SAW-TLS結合）を統合した設計指針を一つのフレームワークで提供するツールは現時点で存在しない。本ツール群はその初期設計指針を提供することを目的としている。

本研究の価値は完成した設計を提供することではなく、以下の3点にある：（1）既存文献の誤った解釈の修正（W~100KをTLFエネルギー分布帯域幅として正確に特定）、（2）未指摘だった定量的問題の明示（6,615倍のエネルギースケール乖離・d_TLS未測定・電場増強定数の未検証）、（3）ScAlN設計パラメータの修正（CTE整合点13.8%→33.2%・M_biの44%差異）。これらは実験グループが研究を設計する際の出発点となる。

### 4.2 エネルギースケール乖離の意味

本研究で定量化した6,615倍のエネルギースケール乖離（W~8,600 μeV vs kT@15mK=1.3 μeV）は、DIETの有効性に関する未解決の理論的問題を提起する。GTMにおいて1/fノイズのスペクトル密度はS(f) ∝ (T/W) × d²_TLF × N_TLF / fと表される。DIETによりN_TLFが低減すれば、エネルギースケールの乖離に関わらずS(f)は低減する。

以下の事実を区別して理解する必要がある：（1）de Graaf et al.（2018）はDIETにより実験的に10倍のノイズ低減を確認した。（2）同論文はDIETが除去したのはTLF（slow fluctuators）のみであり、cTLS密度は変化しなかったと明示している。（3）ノイズ低減はGTMを通じたTLF→cTLSの間接的効果によるものである。エネルギースケール乖離が存在するにもかかわらず実験的効果が確認されたことは、GTMの間接効果が有効に機能していることを示唆するが、そのメカニズムの詳細は未解明であり、今後の理論的研究が必要である。

### 4.3 電場増強計算の限界

本研究ではGans近似（E∝gap^(-2.5)）を使用したが、この計算に用いた定数の導出根拠が記録されていない。具体的には以下の3点が未検証である：

（1）脱分極因子LZ=0.039：cylinder AR=4として記録されているが、Moskowitz（1966）の解析式によるcylinder AR=4の計算値はLz≈0.075であり一致しない。prolate spheroid AR≈5の計算値（Lz≈0.040）に近く、形状の定義が不正確である可能性がある。

（2）媒質誘電率EPS_M=2.25（SiO₂として設定）：de Graaf et al.（2018）の実験環境はAl₂O₃基板（ε≈3.1）であり、SiO₂を選択した根拠が記録されていない。

（3）参照長さL=80nm：導出根拠がコードに記録されていない。

これらの定数の不確実性により、電場増強の定量的計算結果の信頼性は限定的である。正確な電場増強値にはFDTD計算（Oskooi et al., Comput. Phys. Commun. 181, 687, 2010）が必要であり、これは今後の課題である。本ツール群の電場増強計算はギャップサイズ依存性の定性的な傾向を示すものとして使用することを推奨する。

### 4.4 ScAlN設計モデルの限界

本研究のScAlN CTE整合点計算（Sc≈33.2%）はVegard則による線形補間に基づく上限値の推定である。Lu et al.（APL Mater. 6, 076105, 2018）はScAlNのCTEを全Sc%において4.18〜4.65 ppm/Kと実測しており、サファイアCTE（5.0 ppm/K）を下回る。このためVegard則モデルとLu et al. 2018の実測値は矛盾しており、CTE整合点が実際には存在しない可能性がある。本モデルはVegard則に基づく理論的上限値として解釈すべきであり、実設計への適用には実測データによる検証が必要である。

また4K以下の極低温におけるScAlNのCTEおよびM_biの文献は現時点で存在しない。量子デバイスの動作温度（15mK）における設計には、極低温での実測データが不可欠であり、これは最優先の実験課題の一つである。

### 4.5 今後の実験課題（優先順位順）

（1）Au表面上のd_TLSの実測（最優先）
現在SiNxの値（Sarabi 2016、0.1〜8.3 D）を参考値として使用しているが、Au表面上での実測値は存在しない。この測定により6,889倍の不確実性が解消される。

（2）電場増強定数の検証（FDTD計算）
LZ・EPS_M・L=80nmの妥当性確認および正確な電場増強値の計算。

（3）ScAlNの極低温CTE・M_bi測定
4K以下での実測データが設計精度向上に不可欠である。

（4）DIETのイオントラップへの適用実験（将来の応用可能性として）
Brownnutt et al.（Rev. Mod. Phys. 87, 1419, 2015）およびNoel et al.（PRA 99, 063427, 2019）の知見に基づき、イオントラップ電極（Au表面）へのDIET適用を実験的に検証することは将来の応用として有望である。ただしこれは本研究の直接の対象ではなく、今後の研究課題として位置づける。

---

## 5. Conclusion

本研究では、Auナノギャップ構造を用いたDIET（電子遷移誘起脱離）による超伝導量子ビットの1/fノイズ低減に関する理論的設計提案を行い、設計ツール群（Tool 1〜5）を開発・公開した。

本研究の主な貢献は以下の4点である：

（1）エネルギースケール乖離の定量化（最重要）
de Graaf et al.（2018）のTLFエネルギー分布帯域幅W~100K（~8,600 μeV）と量子ビット動作温度15mKにおける熱エネルギー（1.3 μeV）の6,615倍の乖離を初めて定量化した。この定量化により、DIETの有効性に関する未解決の理論的問題を明示し、今後の理論・実験研究の出発点を提供した。

（2）ScAlN CTE整合点の修正と限界の明示
alpha_ScN = 6.61±0.60 ppm/K（Ciprian et al. 2024）の使用により、CTE整合点がSc濃度13.8%から33.2%へ修正され、弾性定数M_biに44%の差異をもたらすことを示した。同時にLu et al.（2018）の実測値との矛盾を明示し、CTE整合点の存在自体が不確実であることを定量的に示した。

（3）実験課題の定量化と優先順位の明示
Au表面上のd_TLSが未測定であることによる6,889倍の不確実性を定量化し、電場増強計算の定数（LZ・EPS_M・L=80nm）の導出根拠が未記録であることを明示した。これらの定量化により、実験グループが取り組むべき課題の優先順位を明確にした。

（4）de Graaf 2018の物理的解釈の明確化
DIETが除去するのはTLF（slow fluctuators）のみであり、cTLS密度は変化しないことを明示した。ノイズ低減はGTMを通じたTLF→cTLSの間接的効果によるものであり、この正確な理解は今後の設計において重要な前提となる。

本研究は理論的提案であり、実験的検証は今後の課題である。設計ツール群は公開済みであり、実験グループによる検証・改善への利用を期待する。

---

## References

[1] de Graaf, S.E., Faoro, L., Burnett, J., Adamyan, A.A., Tzalenchuk, A.Ya., Kubatkin, S.E., Lindström, T., Danilov, A.V. "Suppression of low-frequency charge noise in superconducting resonators by surface spin desorption." Nature Communications 9, 1143 (2018). DOI: 10.1038/s41467-018-03577-2

[2] Sarabi, B., Ramanayaka, A.N., Burin, A.L., Wellstood, F.C., Osborn, K.D. "Projected dipole moments of individual two-level defects extracted using circuit quantum electrodynamics." Physical Review Letters 116, 167002 (2016). DOI: 10.1103/PhysRevLett.116.167002

[3] Johnson, P.B., Christy, R.W. "Optical constants of the noble metals." Physical Review B 6, 4370 (1972). DOI: 10.1103/PhysRevB.6.4370

[4] Zhang, S., Holec, D., Fu, W.Y., Humphreys, C.J., Moram, M.A. "Elastic constants and critical thicknesses of ScGaN and ScAlN." Journal of Applied Physics 114, 243516 (2013). DOI: 10.1063/1.4848036

[5] Ciprian, L., Mihalic, S., Lüttich, C., Hörich, F., Wade, E., Christian, B., Dadgar, A., Ambacher, O. "Thermal expansion coefficient of ScN(111) thin films grown on Si(111) determined by X-ray diffraction." Applied Physics Letters 124, 052203 (2024). DOI: 10.1063/5.0176082

[6] Lu, Y., Reusch, M., Kurz, N., Ding, A., Christoph, T., Prescher, M., Kirste, L., Ambacher, O., Žukauskaitė, A. "Elastic modulus and coefficient of thermal expansion of piezoelectric Al1−xScxN (up to x = 0.41) thin films." APL Materials 6, 076105 (2018). DOI: 10.1063/1.5040190

[7] Watanabe, K., Takigawa, S. "Bond stress limit for Au thin film bonding." Applied Surface Science 620, 156666 (2023). DOI: 10.1016/j.apsusc.2023.156666

[8] Gans, R. "Über die Form ultramikroskopischer Goldteilchen." Annalen der Physik 352, 270 (1915). DOI: 10.1002/andp.19153521006

[9] Brownnutt, M., Kumph, M., Rabl, P., Blatt, R. "Ion-trap measurements of electric-field noise near surfaces." Reviews of Modern Physics 87, 1419 (2015). DOI: 10.1103/RevModPhys.87.1419

[10] Noel, C., Berlin-Udi, M., Matthiesen, C., Yu, J., Zhou, Y., Lordi, V., Häffner, H. "Electric-field noise from thermally activated fluctuators in a surface ion trap." Physical Review A 99, 063427 (2019). DOI: 10.1103/PhysRevA.99.063427

[11] Oskooi, A.F., Roundy, D., Ibanescu, M., Bermel, P., Joannopoulos, J.D., Johnson, S.G. "MEEP: A flexible free-software package for electromagnetic simulations by the FDTD method." Computer Physics Communications 181, 687 (2010). DOI: 10.1016/j.cpc.2009.11.008

[12] Moskowitz, R., Della Torre, E. "Theoretical aspects of demagnetization tensors." IEEE Transactions on Magnetics 2, 739 (1966). DOI: 10.1109/TMAG.1966.1065877
