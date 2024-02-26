---
title: (Short) Spinor
author: cj
date: 2024-02-26 23:50:00 +0900
categories: [shorts]
tags:
pin: true
math: true
mermaid: false
---

## Clifford Algebra

Minkowski spacetime $\mathbb{R}^{1,\mathsf{D}-1}$에 대해 정의된 Clifford algebra (혹은 geometric algebra)는 러프하게 말해,  $\mathbb{R}^{1,\mathsf{D}-1}$의 subspace들을 그 대수의 '원소'로서 가지며 refelction과 rotation (include boosts) 같은 변환들을 자연스럽게 표현할 수 있는 대수 구조이다. 이를테면, 13차원 공간 속 7차원 초부피의 $(x^3,x^{11})$-plane에 대한 회전 따위를 깔끔하게 표현할 수 있다.

**Definition 1.1. (Clifford Algebra)** $\mathbb{R}^{1,\mathsf{D}-1}$위에 정의된 Clifford algebra

$$
\mathrm{Cl}(\mathbb{R}^{1,\mathsf{D}-1})
$$

는 scalar를 실수로 가지는 $\mathbb{Z}_2$-graded associative algebra이다. 이는 odd degree를 갖는 $\mathsf{D}$개의 generator $\{\Gamma^0,\cdots,\Gamma^{\mathsf{D}-1}\}$ such that

$$
\{\Gamma^a,\Gamma^b\}=-2\eta^{ab}
$$

으로 생성된다.

**Remark 1.2.** $v\in\mathbb{R}^{1,\mathsf{D}-1}$에 대해 identification

$$
v=v^ae_a\rightarrow \hat{v}=v^a\Gamma_a
$$

을 생각하면, 이는 자연스러운 inclusion $\mathbb{R}^{1,\mathsf{D}-1}\hookrightarrow \mathrm{Cl}(\mathbb{R}^{1,\mathsf{D}-1})$이다 (generator의 index는 Minkowski metric을 통해 올리고 내린다). 즉, generator들의 linear combinations들은 $\mathbb{R}^{1,\mathsf{D}-1}$의 벡터로 생각할 수 있다. 두 벡터 사이의 내적은

$$
\eta_{ab}v_1^av_2^b= -\frac{1}{2}\{\hat{v}_1,\hat{v}_2\}
$$

으로도 표현될 수 있다.

**Proposition 1.3.** $v\in\mathbb{R}^{1,\mathsf{D}-1}$에 대해 

$$
\hat{v}'=-\Gamma_a^{-1}\hat{v}\Gamma_a
$$

이라 하면 $v'\in\mathbb{R}^{1,\mathsf{D}-1}$은 $v$를 $x^a=0$ hyperplane에 대해 reflection시킨 벡터이다. 또한, 

$$
\hat{v}'=\exp\left(-\frac{\theta}{2}\Gamma_{ab}\right)\hat{v}\exp\left(\frac{\theta}{2}\Gamma_{ab}\right)
$$

이라 하면 $v'$은 $v$를 $(a,b)$-plane에 대해 각도 $\theta$만큼 회전시킨 벡터이다.


**Proof.** 첫 번째 statement의 경우, $-\Gamma_a^{-1}\Gamma_b\Gamma_a$가 $a=b$인 경우 $-\Gamma_b$이고 아닌 경우 $\Gamma_b$이므로 $a$-component에만 $-$부호를 얻으므로 성립한다.

두 번째 statement의 경우, $a$와 $b$가 다를 때

$$
\begin{align*}
-\frac{1}{2}[\Gamma_a\Gamma_b,\Gamma_c]&=-\frac{1}{2}(\Gamma_a\{\Gamma_b,\Gamma_c\}-\{\Gamma_c,\Gamma_a\}\Gamma_b)\\
&=\Gamma_a\eta_{bc}-\Gamma_b\eta_{ac}
\end{align*}
$$

이고 이는 $\mathfrak{so}(1,\mathsf{D}-1)$의 canonical action이므로, $(a,b)$-plane에 대한 $\theta$ rotation은

$$
\exp\left(-\frac{\theta}{2}[\Gamma_a\Gamma_b,-]\right)\hat{v}=\exp\left(-\frac{\theta}{2}\Gamma_{ab}\right)\hat{v}\exp\left(\frac{\theta}{2}\Gamma_{ab}\right)
$$

이다. $\square$

따라서 conjugation action을 사용하면 Clifford algebra의 element들에 reflection과 rotation을 자연스럽게 가할 수 있으며, generator들의 linear combination들을 원래 $\mathbb{R}^{1,\mathsf{D}-1}$속의 벡터와 identify하면 기존 결과와 일치한다. 따라서 Clifford algebra는 벡터보다 더 높은 차원의 object들의 rotation과 reflection을 자연스럽게 표현하기 위해 공간에 구조를 더 가한 것으로 생각할 수 있다.

**Definition 1.4.** Clifford algebra의 object에 bar를 취하는 것을 anti-automorphism i.e. $\overline{\Gamma}_a=\Gamma_a$, $\overline{\Gamma_a\Gamma_b}=\Gamma_b\Gamma_a$로 정의하자. 또한,

$$
\Gamma_{a_1\cdots a_p}\equiv \frac{1}{p!}\sum_\sigma (-1)^{|\sigma|}\Gamma_{a_{\sigma(1)}}\cdots \Gamma_{a_{\sigma(p)}}
$$

을 정의하자. 특히, $a_i$들이 모두 다른 경우는

$$
\Gamma_{a_1\cdots a_n}=\Gamma_{a_1}\cdots \Gamma_{a_n}
$$

이다.

Bar operation은 주어진 object의 "방향"을 뒤집는 것으로 생각할 수 있고, $\Gamma_{a_1\cdots a_p}$는 더 높은 차원의 object들을 표현하는 것으로 생각할 수 있다. Antisymmetrize를 하는 이유는 잘 정의된 방향을 가지기 위해서이다. 이는 differential form을 기하학적으로 생각할 때의 직관과 완벽히 동일하다.

**Remark 1.5.** 앞서 정의한 reflection과 rotation을 표현하는 두 operation은 conjugation operation이므로 obvious한 sign ambiguity가 있다. 즉, $\Gamma_a$와 $-\Gamma_a$의 conjugation operation은 같은 결과를 준다 (회전의 경우에도 마찬가지).

## Spin Group

**Definition 2.1. (Spin Group)** Spin group은 Clifford algebra의 even graded element들 중 bar operation에 대해 *unitary*인 element들로 구성되는 군이다. 즉, 집합으로써,

$$
\mathrm{Spin}(1,\mathsf{D}-1)=\{\left.A\in\mathrm{Cl}(\mathbb{R}^{1,\mathsf{D}-1})_{\mathrm{even}}\right|\overline{A}A=1\}.
$$

**Proposition 2.2.** 다음과 같이 정의되는 map $\mathrm{Spin}(1,\mathsf{D}-1)\rightarrow\mathrm{GL}(\mathbb{R}^{1,\mathsf{D}-1})$

$$
A\mapsto \overline{A}(\quad)A
$$

는 $2$ to $1$ group homomorphism to $\mathrm{SO}_0(1,\mathsf{D}-1)$이다.

**Proof.** 이 action이 orthogonal임은

$$
\eta(\overline{A}v_1A,\overline{A}v_2A)=-\frac{1}{2}\{\overline{A}v_1A,\overline{A}v_2A\}
$$

으로부터 명백하다. 

또한 모든 reflection은 하나의 generator에 의한 conjugation action으로 표현되므로,  reflection은 spin group에 포함되지 않아 special orthogonal임을 알 수 있다. 

$\mathrm{SO}_0(1,\mathsf{D}-1)$의 모든 원소는 어떤 plane에 대한 rotation들의 곱으로 표현될 수 있고, 이는 모두 spin group에 포함되어 있으므로 이 mapping은 surjective이다.

마지막으로, $A$와 $-A$는 같은 linear transformation을 정의하므로 $2$ to $1$이다 (조금 더 엄밀하게는, center가 $\{-1,+1\}$ 뿐임을 unitarity condition으로부터 얻을 수 있어 정확히 '$2$'이다) . $\square$

Spin group은 그 이름에서도 알 수 있듯이 주어진 공간 위에서의 회전 변환들을 나타내는 원소만을 Clifford algebra에서 추출해 구성한 group이다. Unitarity condition은 bar operation을 '방향을 뒤집는 것'으로 이해했을 때 어떤 변환과 반대 방향의 변환을 연달아 가하면 자기 자신으로 돌아오는 것을 나타낸다. Clifford algebra에서도 나타났던 sign ambiguity는 spin group이 $\mathrm{SO}_0(1,\mathsf{D}-1)$의 double cover가 되게 하는 결과를 낳았다.

**Spinor**는 이러한 spin group의 representation이 작용하는 공간('spinor space')의 원소로서 생각할 수 있다. 정의로부터, 이는 실제 물리적 세계(시공간)과는 무관한 abstract space이다. 그러나 QFT에서 spinor field를 생각하게 될 때 이러한 spinor space는 그 field들이 'value'로서 갖는 공간의 역할을 한다. 수학적으로 말하면, spinor field는 시공간을 base manifold로 하는 spin group-principal bundle에 대한 associated vector bundle의 어떤 section이다.

## Dirac And Weyl Representations

이제 specific한 representation에 대해 다루어 보자. 우선은 complex vector space로의 representation을 생각할 것이다.

**Theorem 3.1.** $\mathsf{D}\in\{2n+1,2n\}$, $\mathsf{D}\ge 4$라 하면 linear representation

$$
\rho:\mathrm{Cl}(\mathbb{R}^{1,\mathsf{D}-1})\rightarrow\mathrm{GL}(\mathbb{C}^{2^n})
$$

such that

$$
\Gamma_0^\dagger=\Gamma_0, \Gamma_i^\dagger=-\Gamma_i
$$

and unitary for spin group elements with respect to following Hermitian form ('Dirac pairing')

$$
\langle v_1,v_2\rangle\equiv v_1^\dagger\Gamma_0 v_2\quad (v_1,v_2\in \mathbb{C}^{2^n}).
$$

이때 representation $\rho(\Gamma_a)$를 그냥 간단히 $\Gamma_a$로 표기하였다. 이 representation을 **Dirac representation**이라 한다.

**Proof.** 수학적 귀납법을 사용할 수 있다. 우선 $\mathsf{D}=4$의 경우 Pauli matrix를 다음 항등식

$$
\sigma_a x^a= \begin{pmatrix} x^0+x^1 & x^2+ix^3\\ x^2-ix^3 & x^0-x^1\end{pmatrix}
$$

으로 정의하면, 

$$
\Gamma_0\equiv \begin{pmatrix} 0 & I_2\\ I_2 & 0\end{pmatrix}\quad \Gamma_i\equiv \begin{pmatrix} 0 & \sigma_i\\ -\sigma_i & 0\end{pmatrix}
$$

는 조건을 모두 만족하는 representation이 된다. 

이제 $\mathsf{D}=2n+1$이고 $2n$ dim에서 조건을 만족하는 rep $\{\Gamma_0\cdots\Gamma_{\mathsf{D}-2}\}$가 주어졌다고 하자. 그럼 이 집합에 

$$
\Gamma_{D-1}=\epsilon \Gamma_0\cdots \Gamma_{D-2}
$$

where $\epsilon=1$ ($n$ odd)/ $\epsilon=i$ ($n$ even)을 추가한 행렬들의 집합은 조건을 만족하는 representation을 구성한다.

마지막으로 $\mathsf{D}=2n+2$이라 하자. 그럼

$$
\Gamma_{a(<2n)}\equiv \begin{pmatrix} 0 & \Gamma_a \\ \Gamma_a & 0\end{pmatrix}\quad \Gamma_{2n}\equiv \begin{pmatrix} 0 & I_{2^n}\\ -I_{2^n} & 0\end{pmatrix}\quad \Gamma_{2n+1}\equiv \begin{pmatrix} iI_{2^n} & 0\\ 0 & -iI_{2^n}\end{pmatrix}
$$

으로 representation을 찾을 수 있다 (첫 번째 식의 행렬 속 행렬들은 $2n$ dim에서의 representation matrix이다).

representation을 찾는 과정에서 $\Gamma_0$는 계속해서 Hermitian matrix로 정의되었으므로 $(-)^\dagger\Gamma_0(-)$는 Hermitian form의 조건을 만족한다.

마지막으로, $a,b$가 서로 다른 spatial index라 하면

$$
\Gamma_0^{-1}(\Gamma_a\Gamma_b)^\dagger\Gamma_0=\Gamma_0^{-1}\Gamma_b\Gamma_a\Gamma_0=-\Gamma_a\Gamma_b
$$

이고

$$
\Gamma_0^{-1}(\Gamma_0\Gamma_a)^\dagger\Gamma_0=-\Gamma_0^{-1}\Gamma_0(-\Gamma_a)\Gamma_0=-\Gamma_0\Gamma_a
$$

이므로, $\Gamma_a\Gamma_b$는 이 Hermitian form에 대해 anti-Hermitian이다. 따라서

$$
\exp\left(\omega^{ab}\Gamma_a\Gamma_b\right)
$$

로 구성되는 $(a,b)$-plane rotation의 representation matrix는 unitary이고 spin group의 원소를 이러한 element로 generate할 수 있으므로 전체 representation또한 unitary이다. $\square$

정리하면, Dirac representation은 Cliffrod algebra의 complex vector space로의 representation이며, spin group의 element들을 Dirac pairing $\langle -,-\rangle=(-)^\dagger\Gamma_0(-)$에 대해 unitary한 transformation으로 보낸다. 이러한 Dirac representation가 작용하는 공간의 벡터들을 **Dirac spinor**라 부른다.

**Dirac conjugation**을 $\overline{(-)}\equiv (-)^\dagger\Gamma_0$로 정의하면, 위의 Dirac pairing은 $\langle -,-\rangle=\overline{(-)}(-)$가 된다. 어떤 matrix $A$의 adjoint w.r.t. Dirac pairing은

$$
\Gamma_0^{-1}A^\dagger\Gamma_0
$$

이 됨을 어렵지 않게 보일 수 있으며, 특히 이렇게 정의된 adjoint는 Clifford algebra에서의 bar operation과 동일한 결과를 준다. 그러므로 앞으로 $A$의 adjoint 또한 $\overline{A}$로 표기하자 (Dirac conjugation은 spinor에, adjoint는 matrix에 작용하는 것에 주의하라). 

**Definition 3.2. (Weyl Representation)** even $\mathsf{D}$에 대해, $\mathsf{D}+1$ dim Dirac representation은 같은 complex vector space에 작용하므로, 자연스럽게 $\mathsf{D}+1$ dim rep의 element 

$$
\Gamma_\mathsf{D}\propto \Gamma_0\cdots \Gamma_{\mathsf{D}-1}
$$

는 $\mathsf{D}$-dim Dirac representation이 작용하는 space에 $\mathrm{Spin}(1,\mathsf{D}-1)$-invariantly (i.e. element들과 anticommute) 작용한다. 여기에 적당한 factor $c$를 곱해 

$$
\Gamma_*\equiv c\Gamma_0\cdots \Gamma_{\mathsf{D}-1}
$$

가 $\Gamma_*^2=1$를 만족하도록 할 수 있다. 이를 **chirality operator**라 한다.

그럼 이 representation 자체는 chirality operator의 eigenvalue $\pm 1$에 따라 둘로 분해될 수 있다. 이 각각의 representation을 Weyl representation이라 하며, Weyl representation이 작용하는 공간의 원소를 **Weyl spinor** (혹은 chiral spinor) 라 한다. Eigenvalue $+1$을 'left handed', $-1$을 'right handed'라고 보통 명명한다.

즉, even dimensional spacetime에서의 Dirac representation은 항상 reducible이며, 두 Weyl representation으로 쪼개질 수 있다.

## Real Structure And Majorana Representation

이제 real vector space로의 representation을 생각해보자. 이를 처음부터 구성하기보다는, 이미 구성해놓은 complex vector space로의 representation에서 'real part'를 취하는 것이 더욱 효율적이다. 그러기 위해서는,  주어진 representation의 **real structure**의 개념을 정의해야 한다.

**Definition 4.1.** complex vector space $V$의 real structure는 linear automorphism $\phi:V\rightarrow V$ such that
1) $\phi(\lambda v)=\overline{\lambda}v$
2) $\phi^2=\mathrm{id}_V$

이다. 어떤 Lie group $G$의 representation $\rho :G\rightarrow\mathrm{GL}_\mathbb{C}(V)$가 주어져 있을 때, 만약 $\phi$가 $G$-equivariant i.e.

$$
\phi\circ\rho(g)=\rho(g)\circ\phi
$$

라면 $\phi$를 representation $(V,\rho)$의 real structure라 한다.

**Remark 4.2.** complex vector space $V$의 real structure의 eigenvalue $+1$에 대응되는 eigenspace를 $V_+$라 하면,

$$
V\simeq V_+\otimes_\mathbb{R}\mathbb{C}
$$

이다. 즉, $V$를 complexification으로 생각할 수 있는 real vector space $V_+$의 선택과 real structure는 대응된다.

**Definition 4.3. (Charge Conjugation Matrix)** Dirac representation이 주어져 있을 때, 다음과 같은 두 equation

$$
C_\pm\Gamma_aC_\pm^{-1}=\pm\Gamma_a
$$

를 생각할 수 있다. 이 equation이 real matrix solution을 가질 때, 그 solution들을 charge conjugation matrix들이라 한다.

**Remark 4.4.** Dirac이나 Weyl representation의 경우와는 다르게, charge conjugation matrix의 존재성은 $\mathsf{D}$에 매우 민감하게 의존하며, 그 성질 또한 달라진다. 따라서 이 글에서는 QFT에서 다루게 될 $\mathsf{D}=4$인 경우에 집중하기로 하자. 증명은 하지 않겠지만 수학적으로 이 경우 두 equation의 solution이 모두 존재하며,

$$
C_\pm^T=-C_\pm,\quad C_\pm^2=-1
$$

를 만족한다. 

$\mathrm{Spin}(1,3)$의 Dirac representation이 작용하는 Dirac spinor space에 다음과 같은 **Majorana conjugation**

$$
\psi\mapsto C_-\Gamma_0^T\psi^*\equiv J\psi
$$

을 정의하자. 여기에서 $C_-\equiv \mathcal{C}$를 선택한 이유는 그래야

$$
J^2\psi=\psi, \quad J(\Gamma_a\Gamma_b\psi)=\Gamma_a\Gamma_bJ\psi
$$

가 성립하기 때문이다 (이는 정의로부터 쉽게 보일 수 있다).  즉, $J$는 Dirac representation의 real structure를 정의한다. 

**Definition 4.5. (Majorana Representation)** real structure $J$에 의해 결정되는 real subrepresentation을 Majorana representation이라 하고, 이 representation이 작용하는 공간의 원소들 i.e. $J\psi=\psi$를 만족하는 spinor들을 **Majorana spinor**라 한다.

**Remark 4.6.** Majorana conjugation과 Dirac pairing을 결합해 새로운 bilinear form

$$
(-,-)\equiv\langle J(-),-\rangle=(-)^T\mathcal{C}(-)
$$

를 구성할 수 있다. Majorana spinor가 될 조건은 Majorana conjugation과 Dirac conjugation이 동일한 것이고, 이는 다시 $\langle\psi,-\rangle=(\psi,-)$와 동일한 조건이다.
