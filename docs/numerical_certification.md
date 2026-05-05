# Numerical certification method

The implementation evaluates finite sums of recurrence terms

\[
S_\tau(M,R)=\sum_{s=0}^{\min(R,w_\tau(M))}u_s^{(\tau;M,R)}.
\]

Instead of summing all terms at very high precision, the recurrence is rewritten in stable form:

\[
\frac{u_{s+1}}{u_s}
= -q^{-1}\,C_s,
\]

where \(C_s\) is a product of factors of the form \(1\pm q^{-a}\).  A conservative uniform bound is

\[
\left|\frac{u_{s+1}}{u_s}\right|
\le
\rho_q
:=q^{-1}\frac{1+q^{-1}}{(1-q^{-1})^3}.
\]

Therefore, after computing through term \(u_T\), the remaining tail satisfies

\[
\left|\sum_{s>T}u_s\right|
\le
\frac{|u_T|\rho_q}{1-ho_q}.
\]

The script returns an interval enclosure

\[
S_\tau(M,R)\in [S_{\rm mid}-E,S_{\rm mid}+E].
\]

Every ratio of sums is evaluated using the upper bound

\[
\frac{S_{\rm num}}{S_{\rm den}}
\le
\frac{S_{{\rm num},{\rm mid}}+E_{\rm num}}
     {S_{{\rm den},{\rm mid}}-E_{\rm den}}.
\]

Thus, the script certifies an upper bound on \(q^kB_{\rm anis}\) and \(q^kB_{\rm iso}\), rather than relying on underflow or round-to-zero effects.
