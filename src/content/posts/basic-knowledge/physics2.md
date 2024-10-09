---

title: 普物二总结
published: 2024-10-07
description: 普物二总结，后续将搬迁到mkdocs上
tags: [note,links]
category: Unconcerned
draft: false

---



# 普物二总结——电磁学部分

:::tip[About the tutor]

Prof.*FangMinghu*

mhfang@zju.edu.cn

:::

- E&M
- Optics
- Modern Physics

## Intro

All of simple physics in 5 equations
$$
\begin{aligned}&1. F=q(E+\nu\times B)\\&2.\iiint E\cdot dA=\frac{Q_{inside}}{\varepsilon_0}\\&3.\iiint B\cdot dA=0\\&4. \iint E\cdot dl=-\frac{d\Phi_B}{dt}\\&5. \iint B\cdot dl =\mu_0I+\mu_0\varepsilon_0 \frac{d\Phi_E}{dt}\end{aligned}
$$
Gravity , Electric and Magnetic Force has magical similarity!

## Chap. 25 Charge and Coulomb's law

:::important[Crucial constant nums]

$e=1.602\times 10^{-19}C$​

$k=\frac{1}{4\pi \varepsilon _0}=9\times 10^{9}N\cdot m^2\cdot C^{-2}$

$1C=6\times 10^{18}e$

$m_e=9.1\times 10^{-31}kg$

:::

### 25-2

$1n,1p=3 \mathrm{~quarks}$

$1p(+e)=2\times (\frac{2}{3}e)+(-\frac{1}{3}e)$

$1n(0)=2\times (-\frac{1}{3}e)+\frac{2}{3}e$

### 25-3

$$
\vec F=\frac{1}{4\pi \varepsilon _0} \cdot \frac{q_1q_2}{r^2}\hat r
$$

Electrostatics in matter

Atom force **H**

Ionic Crystal force **NaCl**

Covalent Bond force **H-H**

Metal force **Au**

:::note

Coulomb’s laws an exact result for stationary 

charges and **not an approximation** form some higher 

law.

:::

- Gravitational vs Electric Force
  $$
  \frac{F_e}{F_g}=\cfrac{\frac{1}{4\pi \varepsilon _0}\frac{q_1q_2}{r^2}}{G\frac{m_1m_2}{r^2}}=4.17\times 10^{42}
  $$

:::note[e.g 25-3]

> for a man ,he push his arms apart with a force of 450N,how many charge can he hold outstretched?

$$
F=450N\\
Q=r\sqrt{\frac{F}{k}}=4.47\times 10^{-4}
$$

:::

:::note[e.g 25-3-2]

> How many electrons in a person by **Feynman**

treat people like water
$$
\lambda_p=\frac{NA}{M_r(H_2O)}\times e(H_2O)=3.3\times 10^{23}e/g
$$
then ,assume he is 80kg
$$
n_e=\lambda _p m=2.6\times 10^{28}e
$$
1% of  a person
$$
1\%\times 2.6\times 10^{28}\times 1.6\times 10^{-19}=4.2\times 10^7C
$$
then for two people 0.75m apart:
$$
F=9\times 10^{9}\times \left(\frac{4.2\times 10^7C}{0.75m}\right)^2=2.8\times 10^{25}\approx W_{earth}=6\times 10^{24}kg\times 9.8m/s^2
$$
:::

:::important

you should distinguish the difference between the vec and scalars

:::

### 25-4 Conductors and Insulators

- **Insulators** : $\leqslant 1 e_c ~\mathrm{per}~ cm^3$,*Glass,Plastics,Dry wood*
- **Conductors** : $\approx 10^{23} e_c ~\mathrm{per}~ cm^3$, *Aluminum,Copper,Silver...*
- **Semiconductor** : $10^{10}\to 10^{12} ~\mathrm{per}~ cm^3$, *Silicon,Germanium*
- **Superconductor** : $R=0,B=0$

(the following picture is from OCR,so some fault occurred )
$$
\begin{aligned}&\mathrm{Hg}\left(T_{c}{=}4.2K,1911\right)\\&\mathrm{NhSn}\left(T_{c}{=}23K,1969\right),\\&\mathrm{YBa}_{2}\mathrm{Cu}_{3}\mathrm{O},\quad(T_{c}{=}90K,1987)\\&\mathrm{HgBaCaCuO}\quad(T_{c}{=}156K,1988)\\&\mathrm{ReO}_{1},\mathrm{F}_{2}\mathrm{FeeA}_{3}\mathrm{~(T_{c}{=}55K,2008)}\\&\mathrm{(BaK)Fe}_{2}\mathrm{As}_{2},(T_{c}{=}39K,2008)\\&\mathrm{H}_{3}\mathrm{S}\quad(T_{c}{=}210\mathrm{K},\mathrm{High~Pressure},2016)\\&\mathrm{LaH}_{10}(T_{c}{=}250\mathrm{K},\mathrm{High~Pressure},2019)\\&\mathrm{Pe}(\mathrm{Te},\mathrm{So})\quad(T_{c}{=}144K,2008)\\&(\mathrm{Ti},\mathrm{K},\mathrm{Rb},\mathrm{CS}))\mathrm{Fe}_{s}(\mathrm{Se}_{s},\quad(T_{c}{=}30K,2010).........\\&\mathrm{ThNi}_{2}\mathrm{Se}_{2},\mathrm{ThNi}_{2}\mathrm{S}_{2}(T_{c}{=}3.7K,2013)\end{aligned}
$$
:::important[usage of $B=0$​]

- NMR(**Nuclear Magnetic Resonance**)
- Brain research
- **Magnetic Levitation **(Maglev)

:::

### 25-5  Continuous Charge Distribution

**The charge density**

- $\lambda =\frac{\mathrm d q}{\mathrm d x}$
- $\sigma =\frac{\mathrm d q}{\mathrm d A}$
- $\rho =\frac{\mathrm d q}{\mathrm d V}$

to calculate $q_0\to (\mathrm{distribution})\rho$
$$
\mathrm d\vec {F_{q_0}}=\frac{1}{4\pi \varepsilon _0}\frac{q_0(\rho \mathrm d V)}{|\vec r-\vec r'|^3} (\vec r-\vec r')
$$
:::note[eg-ring]

For a uniform ring of charge :

![image-20241007170248597](/Users/zzw4257/Documents/repo/zzw4257.cn/src/content/posts/basic-knowledge/physics2.assets/image-20241007170248597.png)

$$
\begin{aligned}
&\lambda=\frac{q}{2\pi R} \\
&dF=\frac{1}{4\pi\varepsilon_{0}}\frac{q_{0}dq}{r^{2}}=\frac{1}{4\pi\varepsilon_{0}}\frac{q_{0}\lambda Rd\phi}{(z^{2}+R^{2})} \\
&F_{z}=\int dF_{z}=\int dF\cos\theta \\
&=\int\frac1{4\pi\varepsilon_0}\frac{q_0\lambda Rd\phi}{(z^2+R^2)}\frac z{\sqrt{z^2+R^2}} \\
&=\frac1{4\pi\varepsilon_0}\frac{q_0\lambda Rz}{\left(z^2+R^2\right)^{3/2}}\int_0^{2\pi}d\phi \\
&=\frac1{4\pi\varepsilon_0}\frac{q_0qz}{\left(z^2+R^2\right)^{3/2}}
\end{aligned}
$$
for approximation
$$
z\to \infty ,F_z\to \frac{1}{4\pi \varepsilon _0}\frac{q_0q}{z^2}
$$
:::

:::note[eg-disk]

For a uniform disk of charge :

![image-20241007170550521](/Users/zzw4257/Documents/repo/zzw4257.cn/src/content/posts/basic-knowledge/physics2.assets/image-20241007170550521.png)
$$
\begin{aligned}
\sigma &=\frac{q}{\pi R^2}\\\mathrm d q&=\sigma \mathrm dA =2\pi \sigma \omega \mathrm d\omega\\\mathrm dF_z&=\frac{1}{4\pi \varepsilon _0}\frac{q_0(2\pi \sigma \omega \mathrm d\omega)}{(z^2+\omega ^2)^{\frac{3}{2}}}\\F_z&=\frac{1}{4\pi \varepsilon _0}q_02\pi \sigma z \int _{0}^R \frac{\omega \mathrm d\omega }{(z^2+\omega ^2)^{\frac{3}{2}}}\\&=\frac{1}{4\pi \varepsilon _0 }\frac{2q_0q}{R^2}\left(1-\frac{z}{\sqrt{z^2+R^2}}\right)
\end{aligned}
$$
for approximation
$$
z\to \infty ,F_z\to \frac{1}{4\pi \varepsilon _0}\frac{q_0q}{z^2}
$$
:::

### 25-6 Charge conservation

$$
e^++e^{-}\to 2\gamma\\n\to p+e^- +\nu_e
$$

![image-20241007171417628](/Users/zzw4257/Documents/repo/zzw4257.cn/src/content/posts/basic-knowledge/physics2.assets/image-20241007171417628.png)

## Chap. 26 Electric Fields

### 26-1 Field

- scalar field
- Vector field

Mass-field-mass: not action at a distance

### 26-2 E field

$$
\vec E=\lim _{q_0\to 0}\frac{\vec F}{q_0}
$$

### 26-3 The Electric field of point charge

for a single charge $q$
$$
\vec E=\frac{F}{q_0}=\frac{1}{4\pi \varepsilon  _0}\frac{1}{r^2}\hat r
$$
:::caution

施工地带，没有内容

:::

## Chap. 28 Electric Potential U & V

### 28.6 Calculate E from Potential

$$
V_P=\int _{P}^{\infty }\vec E\cdot \mathrm d \vec l
$$

- Graphically the E-field line is the fastest-descending line of equipotential surfaces

- Math:

  从$\mathrm d W=-q_0 \mathrm d V$出发
  $$
  \mathrm d W=\vec F\cdot \mathrm d\vec l=q_0\vec F\cdot \mathrm d \vec l=q_0E\mathrm d l\cos \theta\\E\cos \theta =-\frac{\mathrm d V}{\mathrm dl}
  $$

  $$
  E_l=-\frac{\mathrm d V}{\mathrm d l}\Rightarrow \vec E=-\nabla V
  $$

  

  - Cartesian coordinates:
    $$
    \nabla V=\frac{\partial V}{\partial x}\bar x+\frac{\partial V}{\partial y}\bar y+\frac{\partial V}{\partial z}\bar z
    $$

  - Spherical coordinates:
    $$
    \nabla V=\frac{\partial V}{\partial r}\bar x+\frac{1}{r}\frac{\partial V}{\partial \theta}\bar y+\frac{1}{r\sin \varphi}\frac{\partial V}{\partial \varphi}\bar \varphi
    $$
    :::note[回顾]

    ![Spherical coordinates](https://en.wikipedia.org/wiki/File:3D_Spherical.svg)
    $$
    \begin{align*}
    x & = r \sin \theta \cos \phi \\
    y & = r \sin \theta \sin \phi \\
    z & = r \cos \theta
    \end{align*}
    $$

    $$
    r=\sqrt{x^2+y^2+z^2}\\\theta=\arccos\frac z{\sqrt{x^2+y^2+z^2}}=\arccos\frac zr=\begin{cases}\arctan\frac{\sqrt{x^2+y^2}}z&\mathrm{if~}z>0\\\\\pi+\arctan\frac{\sqrt{x^2+y^2}}z&\mathrm{if~}z<0\\\\+\frac\pi2&\mathrm{if~}z=0\mathrm{~and~}\sqrt{x^2+y^2}\neq0\\\mathrm{undefined}&\mathrm{if~}x=y=z=0&\end{cases}\\\varphi=\mathrm{sgn}(y)\arccos\frac x{\sqrt{x^2+y^2}}=\begin{cases}\arctan(\frac8x)&\mathrm{if~}x>0,\\\arctan(\frac9x)+\pi&\mathrm{if~}x<0\mathrm{~and~}y\geq0,\\+\frac\pi2&\mathrm{if~}x<0\mathrm{~and~}y>0,\\-\frac\pi2&\mathrm{if~}x=0\mathrm{~and~}y>0,\\\mathrm{undefined}&\mathrm{if~}x=0\mathrm{~and~}y=0.&\end{cases}
    $$

    :::

​		:::tip[例子]
$$
\begin{align*}
V=3x^2+2xy-z^2
\\ \vec E=(-6x-2y,-2x,2z)^T\\
\vec E=\frac{2aq}{4\pi \varepsilon _0r^3}(2\cos \theta ,\sin \theta ,0)_{sp}^T
\end{align*}
$$
​		:::
