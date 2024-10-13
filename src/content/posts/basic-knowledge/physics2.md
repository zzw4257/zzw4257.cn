---
title: 普物二总结
published: 2024-10-07
description: 普物二总结，后续将搬迁到mkdocs上
tags: [note,links]
category: Unconcerned
draft: false
---
# 普物二总结——电磁学部分



```mermaid
graph TD;
  A-->B;
  A-->C;
  B-->D;
  C-->D;
```

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

$e=1.602\times 10^{-19}C$

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

:::important[usage of $B=0$]

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

we just deal with **electrostatics** instead of **electrodynamics**

for a single charge $q$

$$
\vec E=\frac{F}{q_0}=\frac{1}{4\pi \varepsilon  _0}\frac{1}{r^2}\hat r
$$

for the Electric Dipole ($p=2Qa=Ql$)

![image-20241013135307542](/pic/phy2/E_electric_dipole)

remember $\vec p=q\cdot\vec l$,the direction is from $-q$ to $+q$
$$
E_x(x,0)=0\\E_y(x,0)=-2\frac{1}{4\pi \varepsilon _0}\frac{Q}{r^2}\sin \theta\\\sin \theta =\frac{a}{r},r=\sqrt{x^2+a^2}\\E_y(x,0)=-2\frac{1}{4\pi \varepsilon _0} \frac{Qa}{(x^2+a^2)^{\frac{3}{2}}}\to-2k\frac{Qa}{r^3}
$$
then for y-axis



$$
E_x\left(0,r\right)=0\\E_y(0,r)=\frac{Q}{4\pi\varepsilon_0}\frac{4ar}{r^4\left(1-\frac{a^2}{r^2}\right)^2}\to E_y(0,r)\approx+4\frac1{4\pi\varepsilon_0}\frac{Qa}{r^3}=4k\frac{Qa}{r^3}
$$
:::note[NaCl e.g.]

$2a=0.236nm,p_t=2ea=1.6\times 3.78\times 10^{-29}$

$p_e=3\times 10^{-29}$(measured)

it indicates that the electron is not entirely removed from Na to Cl

:::

for $x>>a$

we can approximate $E$ more precisely
$$
E=\frac{pk}{x^3}[1+(-\frac{3}{2})(\frac{a}{x})^2+\cdots ]\propto \frac{1}{r^3}
$$


### 26-4 The Electric field of Continuous Charge Distribution

once again we turn to distribution densities:$\mathrm d q=\lambda d x=\sigma d A=\rho d V$

![image-20241013141019977](/pic/phy2/E_line)
$$
dE_{x}=-\frac{1}{4\pi\varepsilon_{0}}\frac{\lambda d\theta}{r}\sin\theta\\dE_{y}=+\frac{1}{4\pi\varepsilon_{0}}\frac{\lambda d\theta}{r}\cos\theta 
$$
then
$$
E_x=0,E_y=\int_{-{\frac{\pi}{2}}}^{\frac{\pi}{2}} k \frac{\lambda \mathrm d \theta}{r}\cos \theta =\frac{2k\lambda}{r}=\frac{\lambda}{2\pi \varepsilon _0 r}\propto \frac{1}{r}
$$
![image-20241013141723256](/pic/phy2/E_ring)
$$
\begin{aligned}
&dE=\frac{\lambda ds}{4\pi\varepsilon_{0}r^{2}}=\frac{\lambda ds}{4\pi\varepsilon_{0}(z^{2}+R^{2})} \\
&dE_{z}=dE\cos\theta \\
&=\frac{\lambda ds}{4\pi\varepsilon_{0}(z^{2}+R^{2})}\cdot\frac{z}{(z^{2}+R^{2})^{1/2}} \\
&=\frac{z\lambda ds}{4\pi\varepsilon_0(z^2+R^2)^{3/2}}\\E_z&=\frac{z}{4\pi \varepsilon _0(z^2+R^2)^{\frac{3}{2}}}\int _{0}^{2\pi R}\lambda \mathrm ds\to \frac{q}{4\pi \varepsilon _0z^2}
\end{aligned}
$$
![image-20241013142455784](/pic/phy2/E_disk)
$$
\begin{aligned}
&dq=2\pi\omega\cdot d\omega\cdot\sigma \\
&dE=\frac{zdq}{4\pi\varepsilon_{0}(z^{2}+\omega^{2})^{3/2}}=\frac{z2\pi\sigma\omega d\omega}{4\pi\varepsilon_{0}(z^{2}+\omega^{2})^{3/2}} \\
&E=\int dE=\frac{\sigma z}{2\varepsilon_{0}}\int_{0}^{R}\frac{\omega d\omega}{\left(z^{2}+\omega^{2}\right)^{3/2}} \\
&=\frac{\sigma z}{4\varepsilon_{0}}\int_{0}^{R}\frac{d(z^{2}+\omega^{2})}{(z^{2}+\omega^{2})^{3/2}} \\
&=\frac{\sigma}{2\varepsilon_{0}}(1-\frac{1}{\sqrt{1+\frac{R^{2}}{z^{2}}}})\\&R>>z:E\to \frac{\sigma }{2\varepsilon_0}\\&z>>R:E=\frac{\sigma }{2\varepsilon _0}\left(\frac{1}{2}\left(\frac{R}{z}\right)^2-\frac{3}{8}\left(\frac{R}{z}\right)^4+\cdots\right)\to \frac{q}{4\pi \varepsilon _0 z^2}
\end{aligned}
$$


### Summary

when $r>>a/R$

- Dipole $p=2Qa=Ql$
  - in line : $E=\frac{4Qa}{4\pi \varepsilon_0 r^3 }=\frac{2p}{4\pi \varepsilon _0r^3}$
  - off line :  $E=\frac{2Qa}{4\pi \varepsilon _0r^3}=\frac{p}{4\pi \varepsilon _0r^3}$
- Point $E=\frac{q}{4\pi \varepsilon_0 r^2 }$

- Line $E=\frac{2\lambda }{4\pi \epsilon_0 r}$
- Ring $E=\frac{q}{4\pi \varepsilon _0z^2}$

- Disk $E=\frac{q}{4\pi \varepsilon _0z^2}$

### 26-5 E-Field Lines

$$
\begin{cases}E_x=E_r\sin\theta\cos\phi\\E_y=E_r\sin\theta\sin\phi\\E_z=E_r\cos\theta\end{cases}
$$

### 26-6 Point Charge in E-field

:::note[deflecting electrode system of an ink-jet printer]
$$
\begin{aligned}\text{An ink drop}&:m=1.3\times 10^{-10}kg\quad L=1.6cm\\&q=-1.5\times l0^{-13}C,\quad E=1.4\times 10^6N/C\\&v=18m/s\end{aligned}
$$

$$
y=\frac{1}{2}\frac{qE}{m}\frac{L^2}{v^2}\approx 0.64mm
$$

one letter -> about 100 drops

100000 drops/s $\to 1000$ letters/s

:::

:::important[bonus:measure the elementary charge $e=1.602\times 10^{-19}C$]

skip

:::

then in an ununiformed field,for example
$$
\begin{aligned}
&F=qE\neq const\quad F(z) \\
&\frac{d^{2}z}{dt^{2}}=\frac{q}{m}E(z) \\
&E=\frac{\mathrm{Q}z}{4\pi\varepsilon_{0}(z^{2}+R^{2})^{3/2}} \\
&\frac{d^{2}z}{dt^{2}}=\frac{q}{m}\frac{Qz}{4\pi\varepsilon_{0}(z^{2}+R^{2})^{3/2}}
\end{aligned}
$$


### 26-7 Dipole in E-field

![image-20241013144629047](/pic/phy2/E_dipole)

- Torque:$\vec \tau=pE\sin \theta=\vec p\times \vec E$

- $W=\int _{\theta_0}^\theta =pE(\cos \theta -\cos \theta_0)=-\Delta U,U(\theta)=-\vec p\cdot \vec E$

we can divide molecules to 

- Dipole-molecule $\mathrm{H_2O}$
- non-dipole molecule $\mathrm{C_2O}$

:::note[the max torque on H2O]
$$
\tau =qE\sin \theta =9.3\times 10^{-26}N\cdot m\\
\\
\theta :\pi\to 0 :W=2pE=1.9\times 10^{-25}J\\
\epsilon _{int}=\frac{3kT}{2}-6.3\times 10^{-21}>>\epsilon _{elect}
$$
:::

### 26-8 Atom Nuclear Model

- Thomson model plum pudding

Rutherford:
$$
\begin{aligned}
&E_{\max}=\frac{Q}{4\pi\varepsilon_{0}R^{2}}=1.2\times10^{13}N/C \\
&R=1.0\times10^{-10}m \\
&Q=79e \\
&U=6\mathrm{Mev}=9.6\times10^{-13}J \\
&\nu=\sqrt{\frac{2U}{m}}=1.7\times10^{7}m/s
\end{aligned}
$$

$$
\begin{aligned}
&F=qE_{\max}=ma \\
&a=\frac{q}{m}E_{\max} \\
&\Delta\nu=a\Delta t=\frac{q}{m}E_{\max}\frac{2R}{\nu}=6.6\times10^{3}m/s \\
&\therefore\theta=tg^{-1}\frac{\Delta\nu}{\nu}=tg^{-1}(\frac{6.6\times10^{3}}{1.7\times10^{7}})\approx0.02
\end{aligned}
$$



 

then , the result disobeys the experimental result!

## Chap. 27 Gauss Law

### 27-2(3) Flux

We need to at first define flux and the vector of surface of a closed region.
$$
\begin{aligned}
&\Phi=\oint\vec{\nu}\bullet d\vec{A} \\
&d\Phi=\vec{\nu}\bullet d\vec{A} \\
&d\vec{A}=dydz\vec{i}+dzdx\vec{j}+dxdy\vec{k} \\
&\vec{\nu}=\nu_{x}\vec{i}+\nu_{y}\vec{j}+\nu_{z}\vec{k} \\
&\vec{\nu}•d\vec{A}=\nu_{x}dydz+\nu_{y}dzdx+\nu_{z}dxdy
\end{aligned}
$$
if no source or sink of fluid
$$
\Phi=\oint \vec \nu \cdot \mathrm d\vec A=0
$$
for electrostatic case
$$
\Phi=\oint\vec{E}\bullet \mathrm d\vec{A}=\frac{q_{enclosed}}{\varepsilon _0}
$$

#### Geometry and Surface Integrals

we can illustrate that Gauss’s Law -> Coulomb’s Law

for a +Q sphere having radius $R$

$E \cdot 4\pi R^2=\frac{Q}{\varepsilon _0}$

### 27-5(6) Application Gauss’s Law

:::note[Uniform charged sphere]
$$
q=\frac{4}{3}\pi  a^3\rho\Rightarrow E=\frac{\rho a^3}{3\varepsilon _0r^2}(r>a)\\E=\frac{\rho r}{3\varepsilon _0}(r<a)
$$
:::

#### Conductors——Spherical Symmetry

since E=0 inside a  conductor $Q_{inside}=0$, charges are only on the surface

For a conductor,we obtain a cylinder gauss plane:
$$
\varepsilon_0E\Delta A+0+0=\sigma \Delta A\\E=\frac{\sigma}{\varepsilon _0} 
$$

#### Line——Cylindrical Symmetry

$$
E \cdot 2\pi r h\cdot \varepsilon_0=\lambda h\to E=\frac{
\lambda 
}{2\pi \varepsilon _0 r}
$$

:::note[Chap27,ACT2]
Aline charge $\lambda\left(\text{C/m}\right)$ is placed along the axis of an uncharged conducting cylinder of inner radius $r_i=a$, and outer radius $r_o=b$ as shown.

we need to get $\sigma_o$

:::tip
$$
E_o=\frac{\lambda }{2\pi \varepsilon _0 r}=\frac{\sigma_0b}{\varepsilon _0 r}\Rightarrow \sigma_o=\frac{\lambda}{2\pi b}
$$
:::

#### Sheets——Planar Symmetry

$$
\varepsilon _0(2EA)=\sigma A \Rightarrow E=\frac{\sigma}{2\varepsilon _0}
$$

for two paralleled sheets
$$
E_{in}=\frac{\sigma}{\varepsilon _0}
$$
![image-20241013155219398](/pic/phy2/E_sheets)
$$
E_A=\frac{-\sigma_1}{2\varepsilon _0}\\E_B=\frac{+\sigma_1}{2\varepsilon _0}\\E_C=0\\E_D=\frac{+\sigma_1}{2\varepsilon _0}
$$
always based on gauss plane

![image-20241013160823665](/pic/phy2/E_double_sphere)
$$
Q_2=-3Q_1
$$

$$
\sigma _i=-\frac{Q_1}{4\pi R_2^2}\\\sigma _o=-\frac{2Q_1}{4\pi R_2^2}\\E=\begin{cases}0&r<R_1\\\frac{1}{4\pi \varepsilon_0 }\frac{Q_1}{r^2} &R_1<r<R_2\\-\frac{1}{4\pi \varepsilon _0 }\frac{2Q_1}{r^2}&r>R_2\end{cases}
$$

Once we connect the two spheres with a wire:,it becomes a whole conductor with $-2Q_1$

:::note[eg2 Cylinders]

![image-20241013162838562](/pic/phy2/E_pipeline)
$$
\sigma _i =-\frac{\lambda }{2\pi R},\sigma _o = \sigma_t+\frac{\lambda }{2\pi R}
$$

$$
E_r=\begin{cases}\frac{\lambda }{2\pi \varepsilon _0 r}&r<R\\\frac{\lambda }{2\pi \varepsilon _0,r}+\frac{\sigma R}{\varepsilon _0r} &r>R\end{cases}
$$

:::

### 27-7 Experimental Tests of Gauss’ Law and Coulomb’s Law

:::warning

just skip

:::

## Chap. 28 Electric Potential U & V

### 28-1 Potential Energy

![image-20241013164129339](/pic/phy2/Potential_g)

The union energy of two points of charge :
$$
U_b-U_a=-W_{a,b}=-\int_{a}^b \vec F\cdot \mathrm d\vec l 
$$

#### The circuit Law of electrostatics field

$$
\oint \vec E\cdot \mathrm d\vec l =0\\\nabla \times \vec E=0
$$

The gauss’ law(the same as **Math Analysis**):
$$
\oint \vec E\cdot\mathrm d \vec A =\frac{q}{\varepsilon _0}=\iiint \frac{\rho}{\varepsilon_0} \mathrm d V
$$

### 28-2 Electric Potential

$$
V_p=\frac{U_p}{q_0}
$$

$$
V_B-V_A\equiv \frac{W_{AB}}{q_0}=-\int _{A}^B \vec E\cdot \mathrm d \vec l
$$

### 28-3 Calculate Potential from E

$$
W_{ab}=-\int _{a}^b \vec E \cdot \mathrm d \vec l\\V_p=W_{\infty p}=-\int_{\infty}^{p} \vec E\cdot \mathrm d \vec l
$$

for a point charge:
$$
V_b-V_a=-\int _{r_a}^{r_b}\frac{q}{4\pi \varepsilon _0r^2}\mathrm dr=\frac{q}{4\pi \varepsilon _0}\left(\frac{1}{r_b}-\frac{1}{r_a}\right)
$$
:::note[Dipole]

![image-20241013170530297](/pic/phy2/Potential_dipole)
$$
r>>a\\V_r=\frac{1}{4\pi \varepsilon _0}\frac{r_2-r_1}{r_1r_2}\\
r_2-r_1\approx 2a\cos \theta ,r_1r_2=r^2\\
V_r=\frac{1}{4\pi \varepsilon_0}\frac{2aq\cos \theta }{r^2}=\frac{\vec p\cdot \hat r}{4\pi \varepsilon_0 r^2}
$$
:::

:::note[quadrupole]

![image-20241013171208250](/pic/phy2/Potential_quadrupole)
$$
\begin{aligned}
&V(r)=\sum_{i}V_{i}(r_{i}) \\
&=\frac{1}{4\pi\varepsilon_{0}}(\frac{q}{r-d}+\frac{-2q}{r}+\frac{q}{r+d}) \\
&=\frac{1}{4\pi\varepsilon_{0}}\frac{2qd^{2}}{r(r^{2}-d^{2})} \\
&=\frac{1}{4\pi\varepsilon_{0}}\frac{2qd^{2}}{r^{3}(1-d^{2}/r^{2})}\to \frac{Q}{4\pi \varepsilon _0r^3}(d<<r)
\end{aligned}
$$
:::

- Point charge $\propto \frac{1}{r}$
- Dipole $\propto \frac{1}{r^2}$
- Quadrupole $\propto \frac{1}{r^3}$

we can trace back to the distribution reflected by n-dipoles.

:::[egs for potential calculation]

for a charged sphere shell
$$
E=[r\geqslant R]\cdot \frac{q}{4\pi \varepsilon _0r^2}
$$

$$
V(P)=\frac{q}{4\pi \varepsilon _0\max \{r_P,R\}}
$$

$$
U=\frac{1}{2}
\int V\mathrm d q=\frac{q^2}{8\pi \varepsilon _0 R}
$$

$$
W=mc^2=\frac{e^2}{8\pi \varepsilon _0R}\Rightarrow R_e\approx 1.4\times 10^{-15}m
$$

for a ring
$$
V=\oint \frac{1}{4\pi \varepsilon _0}\frac{\lambda \mathrm d s}{\sqrt{z^2+R^2}}=\frac{q}{4\pi \varepsilon _0 \sqrt{z^2+R^2}}
$$
for a disk
$$
\begin{aligned}
&dq=2\pi\omega\cdot d\omega\cdot\sigma \\
&dV=\frac{2\pi\omega\cdot d\omega\cdot\sigma}{4\pi\varepsilon_{0}\sqrt{z^{2}+\omega^{2}}} \\
&V=\int_{0}^{R}\frac{2\pi\omega\cdot d\omega\cdot\sigma}{4\pi\varepsilon_{0}\sqrt{z^{2}+\omega^{2}}}=\frac{\sigma}{2\varepsilon_{0}}(\sqrt{z^{2}+R^{2}}-z)\to \frac{q}{4\pi \varepsilon _0 z}
\end{aligned}
$$
:::

### Sparks



### 28-6 Calculate E from Potential

$$
V_P=\int _{P}^{\infty }\vec E\cdot \mathrm d \vec l
$$

- Graphically the E-field line is the fastest-descending line of equipotential surfaces

- Math:

  from $\mathrm d W=-q_0 \mathrm d V$
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
    :::note[review]
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

:::tip[eg]
$$
\begin{align*}
V=3x^2+2xy-z^2
\\ \vec E=(-6x-2y,-2x,2z)^T\\
\vec E=\frac{2aq}{4\pi \varepsilon _0r^3}(2\cos \theta ,\sin \theta ,0)_{sp}^T
\end{align*}
$$
:::