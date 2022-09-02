---
layout:
title: 教員付加価値を用いた教員効果の測定について
date_post: 20190408
tags: survey
hidden: false
---
<script async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS_CHTML"></script>

## 教員付加価値を用いた教員効果の測定について
教員の質や効果を測定する手法として頻繁に用いられるのは教員付加価値である。教員付加価値は「教員が担当した子どものアウトプット（往々にして学力を指す）の平均的な増加分」として定義される（Jackson et al., 2014)
この教員効果を推定するときは、多くの場合次の様なモデル化を行う（Jackson et al. (2014)に従っている。）。


$$A _ { ijt } = \beta X _ { ijt } + \nu _ { ijt }  \quad where \quad \nu _ { ijt } = \theta _ { j } + \mu _ { jt } + \varepsilon _ { ijt }$$

iは生徒、jは教員、tは時間を指し、Aは教育成果、Xは生徒の個人特性、$\nu$は観察不可能な要因を表す。$\nu$は教員効果$\theta$、クラスルーム効果$\mu$、その他の要因$\varepsilon$で構成されるとする。
上記式から$A _ { i t }  - \beta X _ { i t } $は教員効果$\theta$についての情報を持つがその中には今関心がないノイズである$\mu$と$\varepsilon$を含んでいる。そのため多くの研究はsingal extraction問題を解くことで教員効果を推定していくことになる。

#### 教員付加価値の推定
ノイズを含む信号から真の情報を抽出する問題を一般にsingal extractionと言う。
教員付加価値の推定ではこの問題設定を援用するが、その際によく使う定理として次を挙げることができる。

---
**定理**\\
$\theta$についてのpriorとして

  $$
\begin{eqnarray}
   E(\theta) &=& m \\
   V(\theta) &=& 1/\rho
 \end{eqnarray}
  $$

とした時に、次の様なシグナルの集合$X = \\{x_i \| i \in I \\}$を受け取るとする。

$$
\begin{eqnarray}
  x_i &=& \theta + \epsilon_i \\\\
  && where  \\
  \epsilon_i &\sim& N(0, 1/\rho_i ) \\
  Cov(\epsilon_i, \epsilon_j) &=& 0 (i \neq j)
\end{eqnarray}
$$

この時、$\theta$に関する期待値は

$$
\begin{eqnarray}
   E(\theta | X) &=& \frac{\rho}{\rho ^ { \prime }} m
    + \sum _ { i = 1, i \in I} \frac{\rho_i}{\rho ^ { \prime }} x _ { i } \\
   V(\theta | X) &=& 1 / \rho ^ { \prime }  \\
   && where \\
   \rho ^ { \prime } &=& \rho + \sum _ { i = 1, i \in I}  \rho _ { i }
\end{eqnarray}
$$

と更新される。

---

上記定理を直感的に解釈すると、上記定理ではpriorをも含めた様々な情報をその正確さで重み付けをしていってfundamental variableを更新していく手続きが描写されている。


この定理を教員付加価値推定に応用していく。この時、先の教育生産関数の式は教員効果$\theta _ {j}$についての次の様なシグナルなのではないかと考えることができる。

$$ s_{ijt} = A _ { ijt } - \beta X_{ ijt } =  \theta _ {j} + \mu _ {jt} + \varepsilon _ {ijt}$$


ただし先ほどのsignal extractionのセットアップだとシグナルのノイズ間に相関がないというセットアップだったので、このままでは使えない。そのため、次の様なセットアップに書き直す（害はない）。教員jがt期に担当している生徒を$I_{jt}$と書けば、

$$
\begin{eqnarray}
s_{jt} &=& \frac{\sum_{i, i \in I_{jt}} s_{ijt}}{\|I_{jt}\|} \\
         &=& \theta _ {j} + \mu _ {jt} + \frac{\sum_{i, i \in I_{jt}} \varepsilon _ {ijt}}{\|I_{jt}\|} \\
         &=& \theta _ {j} + v_{jt}
\end{eqnarray}
 $$

という教員効果$\theta _ {j}$についてのシグナルを毎期受け取ると考えることができる。

もし教員効果$\theta _ {j}$に対するpriorが期待値0及び分散$V(\theta)$であり、上記シグナルをt期分受け取ると上記のsignal extraction定理より(そのシグナルの集合を$s_j = \\{s_{jt} \| t \in T \\}$と書くことにする)、

\begin{eqnarray}
   E(\theta | s_j ) &=& \sum_{t, t \in T} s_{jt} \frac{ \frac{1}{V(v_{jt})} }{ \frac{1}{V(\theta)} + \sum_{t, t \in T}\frac{1}{ V(v_{jt})} }
\end{eqnarray}

と教員jの効果$\theta$の期待値を書くことができる。

多くの場合は得られたデータから、$V(\theta)$や$V(v_{jt})$を無理やり（？）計算して妥当性の高いpriorを構成した後、期待値を計算することが多い。

###### Lefgren&Sims(2012)でのさらなる縮約
さらに、Lefgren&Sims(2012)などはシグナルをさらに集約して、
\begin{eqnarray}
s_{j} = \theta _ {j} + \frac{\sum_{t, t \in T} v_{jt}}{ \|\| T \|\| }
\end{eqnarray}
と書いて、$V(\frac{\sum_{t, t \in T} v_{jt}}{\|T\|}) = \frac{V(v_j)}{\|T\|}$と書くことで($V(v_j)$というものをどっかから調達してくるということ)、

$$
\begin{eqnarray}
   E(\theta | s_j )
   &=& s_{j} \times \frac{ \frac{1}{\frac{V(v_j)}{\|T\|}}}{ \frac{1}{V(\theta)} + \frac{1}{\frac{V(v_j)}{\|T\|}} } \\
   &=& s_{j} \times \frac{V(\theta)}{V(\theta) + \frac{V(v_j)}{\|T \|}}
\end{eqnarray}
$$

と教員効果を構成している。

<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  displayAlign: "center",
  displayIndent: "2em",
  tex2jax: {
    inlineMath: [['$','$'], ['\\(','\\)']],
    processEscapes: true
  },
  CommonHTML: { matchFontHeight: false }
});
</script>

