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

# Intro

All of simple physics in 5 equations

$$
\begin{aligned}&1. F=q(E+\nu\times B)\\&2.\iiint E\cdot dA=\frac{Q_{inside}}{\varepsilon_0}\\&3.\iiint B\cdot dA=0\\&4. \iint E\cdot dl=-\frac{d\Phi_B}{dt}\\&5. \iint B\cdot dl =\mu_0I+\mu_0\varepsilon_0 \frac{d\Phi_E}{dt}\end{aligned}
$$

Gravity , Electric and Magnetic Force has magical similarity!

# Chap. 25 Charge and Coulomb's law

:::important[Crucial constant nums]

$e=1.602\times 10^{-19}C$

$k=\frac{1}{4\pi \varepsilon _0}=9\times 10^{9}N\cdot m^2\cdot C^{-2}$

$1C=6\times 10^{18}e$

$m_e=9.1\times 10^{-31}kg$

:::

## 25-2

$1n,1p=3 \mathrm{~quarks}$

$1p(+e)=2\times (\frac{2}{3}e)+(-\frac{1}{3}e)$

$1n(0)=2\times (-\frac{1}{3}e)+\frac{2}{3}e$

## 25-3

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

## 25-4 Conductors and Insulators

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

## 25-5  Continuous Charge Distribution

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

## 25-6 Charge conservation

$$
e^++e^{-}\to 2\gamma\\n\to p+e^- +\nu_e
$$

# Chap. 26 Electric Fields

## 26-1 Field

- scalar field
- Vector field

Mass-field-mass: not action at a distance

## 26-2 E field

$$
\vec E=\lim _{q_0\to 0}\frac{\vec F}{q_0}
$$

## 26-3 The Electric field of point charge

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

## 26-4 The Electric field of Continuous Charge Distribution

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

## 26-5 E-Field Lines

$$
\begin{cases}E_x=E_r\sin\theta\cos\phi\\E_y=E_r\sin\theta\sin\phi\\E_z=E_r\cos\theta\end{cases}
$$

## 26-6 Point Charge in E-field

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

## 26-7 Dipole in E-field

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

## 26-8 Atom Nuclear Model

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

# Chap. 27 Gauss Law

## 27-2(3) Flux

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

### Geometry and Surface Integrals

we can illustrate that Gauss’s Law -> Coulomb’s Law

for a +Q sphere having radius $R$

$E \cdot 4\pi R^2=\frac{Q}{\varepsilon _0}$

## 27-5(6) Application Gauss’s Law

:::note[Uniform charged sphere]

$$
q=\frac{4}{3}\pi  a^3\rho\Rightarrow E=\frac{\rho a^3}{3\varepsilon _0r^2}(r>a)\\E=\frac{\rho r}{3\varepsilon _0}(r<a)
$$

:::

### Conductors——Spherical Symmetry

since E=0 inside a  conductor $Q_{inside}=0$, charges are only on the surface

For a conductor,we obtain a cylinder gauss plane:

$$
\varepsilon_0E\Delta A+0+0=\sigma \Delta A\\E=\frac{\sigma}{\varepsilon _0}
$$

### Line——Cylindrical Symmetry

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

### Sheets——Planar Symmetry

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

## 27-7 Experimental Tests of Gauss’ Law and Coulomb’s Law

:::warning

just skip

:::

# Chap. 28 Electric Potential U & V

## 28-1 Potential Energy

![image-20241013164129339](/pic/phy2/Potential_g)

The union energy of two points of charge :

$$
U_b-U_a=-W_{a,b}=-\int_{a}^b \vec F\cdot \mathrm d\vec l
$$

### The circuit Law of electrostatics field

$$
\oint \vec E\cdot \mathrm d\vec l =0\\\nabla \times \vec E=0
$$

The gauss’ law(the same as **Math Analysis**):

$$
\oint \vec E\cdot\mathrm d \vec A =\frac{q}{\varepsilon _0}=\iiint \frac{\rho}{\varepsilon_0} \mathrm d V
$$

## 28-2 Electric Potential

$$
V_p=\frac{U_p}{q_0}
$$

$$
V_B-V_A\equiv \frac{W_{AB}}{q_0}=-\int _{A}^B \vec E\cdot \mathrm d \vec l
$$

## 28-3 Calculate Potential from E

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

## Sparks

High electric fields can ionize nonconducting materials(**dielectrics**)

(Insulator->Conductor)

:::note[ball breakdown]

we have two ball shell with same potential $V$

Ball 2 is as twice large as Ball 1

as $V$ goes up, the Ball 1 will breakdown first

$$
E_s=\frac{Q}{4\pi \varepsilon _0 r^2},V=\frac{Q}{4\pi \varepsilon_0 r}\Rightarrow E=\frac{V}{r}
$$

then $r_1<r_2\Rightarrow E_1>E_2$

:::

![image-20241015101813495](/pic/phy2/Potential_2.png)

- $\Delta V>0$ means we go uphill
- $\Delta V<0$ means we go downhill

$$
V(r)=V_\infty -\int_{\infty}^c \vec E_l\cdot \vec l-\int_{c}^b \vec E_l\cdot \vec l-\int_{b}^a \vec E_l\cdot \vec l-\int_{a}^r \vec E_l\cdot \vec l\\=V_\infty-\left(\int _{\infty}^c+\int_{b}^{a}\right )\frac{1}{4\pi \varepsilon _0}\frac{Q}{r^2}\mathrm dr-\int_{a}^r \frac{1}{4\pi\varepsilon _0}\frac{Qr}{a^3}\mathrm dr\\=\frac{Q}{4\pi \varepsilon _0}\left(\frac{1}{a}-\left(\frac{1}{b}-\frac{1}{c}\right)+\frac{1}{2a}\left(1-\frac{r^2}{a^2}\right)\right)
$$

you can split into two patterns

## 28-4 Equipotentials

when in the equipotential  surface we can conclude

$$
\vec E\cdot \mathrm d\vec l\equiv V
$$

## 28-5 Potential of a charged conductors

:::important

Claim: The surface of a conductor is an equipotential surfacewhen two sphere conductors are attatched to each others.

$$
\frac{Q_A}{Q_B}=\frac{r_A}{r_B}
$$

:::

for example , when a point of charge is placed off-center inside a sphere conductor,the inside surface will be inuniform and the outside surface will be uniform

## 28-6 Calculate E from Potential

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

then we have two eg

:::note[dipole]

![image-20241015114126009](/pic/P_dipole.png)

$$
V(r)=\frac{q}{4\pi \varepsilon _0}\frac{r_2-r_1}{r_1r_2}\to \frac{1}{4\pi \varepsilon _0}\frac{2aq\cos \theta}{r^2}(r>>a)
$$

then

$$
V(r,\theta)=\frac{1}{4\pi \varepsilon _0}\frac{2aq\cos \theta}{r^2}\\E_r=-\frac{\partial V}{\partial  r}\\E_\theta=-\frac{\partial V}{\partial  \theta}\\\Rightarrow \vec E=\frac{2aq}{4\pi \varepsilon _0 r^3}((2\cos \theta )\hat r+\sin \theta \hat \theta)
$$

![image-20241015114612342](/pic/kk.png)

it's easy to see that $\arg \max_{\theta } ||\vec E||=\frac{\pi}{2}$

:::

:::note[eg. disk]

![image-20241015114925818](/pic/phy2/P_disk.png)

$$
\begin{aligned}
&dq=2\pi\omega\cdot d\omega\cdot\sigma \\
&dV=\frac{dq}{4\pi\varepsilon_{0}\sqrt{z^{2}+\omega^{2}}}=\frac{2\pi\omega\cdot d\omega\cdot\sigma}{4\pi\varepsilon_{0}\sqrt{z^{2}+\omega^{2}}} \\
&V=\int_{0}^{R}\frac{2\pi\omega\cdot d\omega\cdot\sigma}{4\pi\varepsilon_{0}\sqrt{z^{2}+\omega^{2}}}=\frac{\sigma}{2\varepsilon_{0}}\big(\sqrt{z^{2}+R^{2}}-z\big) \\
&E_{z}=-\frac{\partial V}{\partial z}=-\frac{\sigma}{2\varepsilon_{0}}(\frac{2z}{2\sqrt{R^{2}+z^{2}}}-1) \\
&=\frac{\sigma}{2\varepsilon_{0}}(1-\frac{1}{\sqrt{1+(R/z)^{2}}})
\end{aligned}
$$

:::important[a e.g for getting $v$ with $\Delta U$]

$$
\frac{1}{2}mv^2=K=-\Delta U=-q\Delta V\Rightarrow v=\sqrt{\frac{2q\Delta V}{m}}
$$

we can measure $\alpha $ partical's large velocity by measuring eletrostatic information like difference of potential

:::

## Appendix method of images

![image-20241015120204563](/pic/phy2/imaging.png)

we can see

$$
E(\vec r_s)=\frac{\sigma(\vec r_s)}{\varepsilon _0}
$$

we can see that the induced charge distribution generated with a point of charge and a conductor sheet is the same as which is made by two charges. It can be proved with symmetry theorem.

# Chap. 30 Capacitance and Dielectrics

## 30-1 Capacitors

### Classic Capacitors

:::tip[Application]

- flashbulb:capacitor draw energy from battery ($s$) then release  it through bulb($ms$)
- Laser pulse
- thermonuclear fusion $10^{14}W,10^{-9}s,10^8K$

:::

Definition of Capacitance : two spatially seperated conductors($+q/-q$) $C=\frac{q}{\Delta V}$

:::important

one single conductor is capacitor!

:::

:::note[eg:Parallel Plate capacitor]

$$
q=\sigma A\\\Delta V=-\int _{A}^B \vec E\cdot \mathrm{d}\vec l
$$

:::

:::note[eg:Parallel Plate capacitor]

$$
q=\sigma A\\\Delta V=-\int _{A}^B \vec E\cdot \mathrm{d}\vec l
$$

since

$$
EA\varepsilon _0= \sigma A\Rightarrow E=\frac{\sigma}{\varepsilon _0}\Rightarrow \Delta V=\frac{q}{A\varepsilon_0}d\Rightarrow C=\frac{\varepsilon _0 A}{d}
$$

:::

:::tip[Application]

- condenser:$C \propto \frac{1}{d}\xrightarrow{\mathrm{fixed~}\Delta V} Q\propto\frac{1}{d},I=\frac{\mathrm{d} Q}{\mathrm d t}$:the vibration -> different $I$

:::

:::note[eg:Cylindrical Capacitor]

![image-20241018170156213](/pic/phy2/C_cylindrical)

$+Q,-Q$ on surface,$\Delta V$

$$
2\pi r \cdot L\cdot E\cdot \varepsilon_0=Q\Rightarrow E=\frac{Q}{2\pi \varepsilon _0 Lr}
$$

$$
\Delta V=\int_{b}^a \vec E\cdot \mathrm d\vec l =\frac{Q}{2\pi \varepsilon L\ln \frac{b}{a}},C=\frac{2\pi \varepsilon _0 L}{\ln\frac{b}{a}}
$$

:::note[ex:TV signals tansmit/coaxial cable]

$a=r_i=0.15,b=r_o=2.1$

$$
\frac{C}{L}=\frac{2\pi\varepsilon_{0}}{\ln(b/a)}=\frac{2\pi\times8.85\times10^{-12}}{\ln(2.1/0.15)}=21\times10^{-12}F / m=21 pF / m
$$

:::

:::note[eg:spherical capacitor]

![image-20241018170915119](/pic/phy2/C_sphe)

$$
\vec E=\frac{q\hat r}{4\pi \varepsilon _0 r^2}\Rightarrow \Delta V=\frac{q}{4\pi \varepsilon_0 }\left(\frac{1}{a}-\frac{1}{b}\right)\Rightarrow C=\frac{4\pi \varepsilon _0ab}{b-a}
$$

for earth $R=6.37\times 10^6 m\Rightarrow C=7.1\times 10^{-4}\mathrm F=710\mu \mathrm F$

:::

### Summary

- Parallel Plate:$C=\frac{\varepsilon _0 A}{d}$
- Cylindrical Capacitor:$C=\frac{2\pi \varepsilon _0 L}{\ln\frac{b}{a}}$
- Spherical $C=4\pi \varepsilon_0\frac{ab}{b-a} $

### Parallel & Series

![image-20241018171312744](/pic/phy2/C_parallel)

![image-20241018171326385](/pic/phy2/C_series)

for capacitors in parallel

$$
V=\frac{Q_1}{C_1}=\frac{Q_2}{C_2}\Rightarrow Q_2=Q_1\frac{C_2}{C_1}\\C=C_1+C_2
$$

for capacitors in series

$$
V_{ab}=\frac{Q}{C}=\frac{Q}{C_1}+\frac{Q}{C_2}\Rightarrow C=\left(\frac{1}{C_1}+\frac{1}{C_2}\right)^{-1}
$$

![image-20241018171611735](/pic/phy2/C_prac)

$$
\frac{1}{C}=\frac{1}{C_3}+\frac{1}{C_1+C_2}
$$

![image-20241018171919786](/pic/phy2/C_multi-cyl)

$$
C=\frac{2\pi \varepsilon _0L}{\ln\frac{b}{a}\ln \frac{d}{c}}
$$

## 30-2 Energy storage in E-field

for paralleled capacitor

$$
\mathrm d W=V(q)\mathrm d q=\frac{q\mathrm d q}{C}\\
W=\int _{0}^ Q \frac{q\mathrm dq}{C}=\frac{1}{2}\frac{Q^2}{C}=\frac{CV^2}{2}\Rightarrow =\frac{1}{2}CV^2
$$

in some questions ,we need to verify the fact whether $Q$ is const or $V$ is const.

$$
U=\frac{1}{2}\frac{Q}{C^2}=\frac{1}{2}\frac{Q^2}{A\varepsilon _0/d}\Rightarrow E=\frac{\sigma}{\varepsilon_0}=\frac{Q}{\varepsilon _0 A}\\\Rightarrow U=\frac{1}{2}E^2\varepsilon _0 A d
$$

the energy density $u=\frac{W}{Ad}=\frac{1}{2}\varepsilon _0 E^2(J\cdot m^{-3})$

you can calculate with $u$ with Cylindrical Capacitor

$$
U=\int_{a}^b \frac{1}{2}\varepsilon _0 E^2=\frac{\varepsilon _0}{2}\int \left(\frac{\lambda }{2\pi \varepsilon _0 r} \right)^2L2\pi r \mathrm d r=\frac{1}{2}\frac{Q^2}{2\pi \varepsilon _0 L}\ln \frac{b}{a}=\frac{1}{2}\frac{Q^2}{C}
$$

:::note[ACT2 cylindrical capacitors]

with two cylindrical capacitors ($(a,b)~\mathrm{vs}~(2a,2b)$)

$$
C=\frac{2\pi\varepsilon_oL}{\ln\left(\frac{r_{outer}}{r_{inner}}\right)}
$$

so $C_1=C_2$

::: note[P687 30-7]

> $\textbf{Problem 30- 7 ( page 687) . }$
> An isolated conducting sphere whose radius $R$ is 6.85cm carries a charge $q=1.25nC.($a) How much energy is stored in the electric field of this charged conductor? (b) What is the energy density (能量密度) at the surface of the sphere? (c)What is the radius $R_{\vartheta}$ of the imaginary spherical surface such that one-half of the stored potential energy lies within it?
>
> **R=6.85cm, q=1.25nC**
>
> (a)**U=?**
>
> (b)**u=?** **(at the surface of the sphere)**
>
> (c)$R_0=?~$At $R<R_0,U'=\frac{1}{2} U$

(a)

$$
\begin{aligned}&C=4\pi\boldsymbol{\varepsilon}_0R\\&U=\frac{q^2}{2C}=\frac{q^2}{8\pi\boldsymbol{\varepsilon}_0R}=1.03\times10^{-7}J=103nJ\end{aligned}
$$

(b)

$$
\begin{aligned}&E=\frac q{4\pi\varepsilon_0R^2}\\&u=\frac12\varepsilon_0E^2=\frac12\varepsilon_0\frac{q^2}{16\pi^2\varepsilon_0^2R^4}=\frac{q^2}{32\pi^2\varepsilon_0^2R^4}=25.4nJ/cm^3\end{aligned}
$$

(c)

$$
\begin{aligned}
&\int_R^{R_0}\frac12\varepsilon_0E^2d\nu=\int_{R_0}^\infty\frac12\varepsilon_0E^2d\nu \\
&\int_R^{R_0}\frac{1}{2}\varepsilon_0\frac{q^2}{16\pi^2\varepsilon_0^2r^4}4\pi r^2dr=\int_{R_0}^\infty\frac{1}{2}\varepsilon_0\frac{q^2}{16\pi^2\varepsilon_0^2r^4}4\pi r^2dr \\
&\int_R^{R_0}\frac{dr}{r^2}=\int_{R_0}^\infty\frac{dr}{r^2} \\
&\frac1R-\frac1{R_0}=\frac1{R_0} \\
&R_0=2R=13.7cm
\end{aligned}
$$

:::

## 30-3 Dielectrics

### Capacitor with dielectrics

:::note[definition]

- **Empirical observation**: Inserting a non-conducting material  between the plates of a capacitor changes the VALUE of the capacitance.
- dielectric constant $C=\kappa _e C_0$,$\kappa_e>1$(glass=5.6,water=78)
- $C_0$ means the capacitance with vacuum (air)

:::

with dielectric constant $\kappa _e$ and const $Q$

$$
V=\frac{Q}{C}=\frac{V_0}{\kappa_e}\Rightarrow E= \frac{E_0}{\kappa_e}
$$

with const $V$

$Q'=\kappa _e C_0V$

- parallel-plate :$C=\frac{\kappa_e \varepsilon _0 A}{d}$
- cylindrical $C=\frac{\kappa_e 2\pi \varepsilon _0 L}{\ln \frac {b}{a}}$
- spherical $C=4\pi \varepsilon _0\kappa_e\frac{ab}{b-a}$

for point charge $\displaystyle E=\frac{Q}{4\pi \varepsilon _0\kappa_e r^2}$

:::note[the increasing $C$]

$$
C=\frac{C_1C_2}{C_1+C_2}=\frac{\varepsilon _0 A }{d_1+d_2}>\frac{\varepsilon _0 A}{d}(d>d_1+d_2))
$$

**Polarization effect :**

$$
V=Ed=(E_0-E')d<E_0d\\C=\frac{q}{(E_0-E')d}>C_0
$$

:::

### microscopic mechanism of polarization

- Non-polar dielectrics $\vec p=q\vec d=0$
- Polar dielectrics $\vec p=q\vec d\neq 0$

for non-polar dielectrics

we have

**Induced electric dipole moment**

**Electric displacement polarization**

![image-20241020222558545](/pic/phy2/C_nonpolar)

Polar dielectrics

$$
\sum \vec p\neq 0
$$

**Alignment polarization**

:::tip

In high frequency field , Electric displacement polarization plays an important role

:::

### Polarization

Polarization intensity $\vec P$

$$
\vec P=\cfrac{\sum  \vec p_m}{\Delta V} (C\cdot m^{-2})=nq \vec l
$$

![image-20241020222921535](/pic/phy2/C_polar)

$$
\begin{aligned}
&dN=ndV=nldA\cos\theta \\
&dq'=qdN=nqldA\cos\theta \\
&=PdA\cos\theta \\
&=\vec{P}\bullet d\vec{A} \\
&\oint\vec{P}\bullet d\vec{A}=\sum_{out}q'=-\sum_{in}q'\\
&dq'=\vec{P}\bullet d\vec{A}=P\cos\theta\cdot dA\\&\sigma'=\frac{dq'}{dA}=P\cos\theta=\vec{P}\bullet\vec{n}=P_n
\end{aligned}
$$

### Depolarization Field

$$
\vec E=\vec E_0+\vec E'
$$

![image-20241020223121085](/pic/phy2/C_depolar)

$$
\begin{aligned}
&\sigma_e^{\prime}=P_n=P\cos\theta \\
&dE^{\prime}=\frac{dq^{\prime}}{4\pi\varepsilon_0R^2}=\frac{\sigma_e^{\prime}dA}{4\pi\varepsilon_0R^2}=\frac{P\cos\theta dA}{4\pi\varepsilon_0R^2} \\
&dA=Rd\theta\cdot R\sin\theta d\varphi \\
&=R^{2}\sin\theta d\theta d\varphi \\
&dE'=\frac P{4\pi\varepsilon_0}\cos\theta\sin\theta d\theta d\varphi \\
&dE'_z=dE'\cos(\pi-\theta)=-dE'\cos\theta \\
&=-\frac P{4\pi\varepsilon_0}\cos^2\theta\sin\theta d\theta d\varphi \\
&E_z^{\prime}=\oint_zdE_z^{\prime}=-\frac P{4\pi\varepsilon_0}\int_0^\pi\cos^2\theta\sin\theta d\theta\int_0^{2\pi}d\varphi=-\frac P{3\varepsilon_0}
\end{aligned}
$$

:::note[eg2 parallel plate]

$$
\sigma_e'=P\cos \theta =P\\
E'=\frac{\sigma_e'}{\varepsilon_0}
$$

:::

### Polarization law

$$
\vec P\Rightarrow \sigma_e'\Rightarrow \vec E'\Rightarrow \vec E[\vec P(\vec E)]
$$

for general isotropic materials

$$
\vec{P}=\chi_e\varepsilon_0\vec{E}(\kappa _e=1+\chi_e)
$$

$\chi _e$: Polarization coefficient

for crystal materials:

$$
\begin{pmatrix}P_x\\P_y\\P_z\end{pmatrix}=\begin{pmatrix}\chi_{xx}\chi_{xy}\chi_{xz}\\\chi_{yx}\chi_{yy}\chi_{yz}\\\chi_{zx}\chi_{zy}\chi_{zz}\end{pmatrix}\begin{pmatrix}\boldsymbol{\varepsilon}_0E_x\\\boldsymbol{\varepsilon}_0E_y\\\boldsymbol{\varepsilon}_0E_z\end{pmatrix}
$$

:::note[eg:ferroelectric material]

Electric hysteresis effect
Similar to the magnetic hysteresis effect.

:::

### Electric Displacement vector$\vec D$

$$
\vec{E}_0\to\vec{P}\to\boldsymbol{\sigma'}_e\to\vec{E'}\to\vec{E}=\vec{E}_0+\vec{E'}
$$

$\vec D $ means:

- Electric displacement vec
- electric induction

![image-20241020224048323](/pic/phy2/D)

let $q_0$ be inside charge,$q’$ be induced charge

$$
\begin{aligned}
&\varepsilon_0\oint\vec{E}\bullet d\vec{A}=\sum_{In}(q_0+q') \\
&\oint\vec{P}\bullet d\vec{A}=-\sum_{In}q' \\
&\iint\varepsilon_0\vec{E}\bullet d\vec{A}=\sum_{In}q_0-\oint\int\vec{P}\bullet d\vec{A} \\
&\oint(\varepsilon_0\vec{E}+\vec{P})\bullet d\vec{A}=\sum_{In}q_0 \\
&\oint\vec{D}\bullet d\vec{A}=\sum_{In}\\
&\vec D=\varepsilon _0\vec E+\vec P=(1+\chi_e)\varepsilon _0 \vec E=\kappa _e\varepsilon _0 \vec E\\
&\boxed{\oint\vec{D}\bullet d\vec{A}=\sum_{In}q_0}
\end{aligned}
$$

:::note[eg paralleled plate]

$$
\begin{aligned}
&\oint\vec{D}\bullet dA=\sum q_0 \\
&D_1\Delta A+D_2\Delta A=\sigma_{e0}\Delta A \\
&\vec{E}_1=0,D_1=\kappa_{e1}\varepsilon_0E_1=0,\therefore D_1=0 \\
&\therefore D=D_2=\sigma_{e0}=\varepsilon_0E_0 \\
&\therefore E=\frac D{\kappa_e\varepsilon_0}=\frac{\varepsilon_0E_0}{\kappa_e\varepsilon_0}=\frac{E_0}{\kappa_e}\\
&\vec D=\kappa _e\varepsilon _0\vec E
\end{aligned}
$$

:::

:::note[eg charge in a hole]

$$
\begin{aligned}
&\oint\vec{D}\bullet d\vec{A}=\sum q_0 \\
&4\pi r^2D=q_0 \\
&D=\frac{q_0}{4\pi r^2} \\
&E=\frac{D}{\kappa_e\varepsilon_0}=\frac{q_0}{4\pi\varepsilon_0\kappa_er^2}=\frac{E_0}{\kappa_e}
\end{aligned}
$$

$\displaystyle \oint \vec D\cdot \mathrm d\vec l\neq 0$

:::

### Pressure Electric Effect

![image-20241020224455711](/pic/phy2/Pressure-effect)

# Chap 31 The Steady Current and Conduction Law

## 31-1 The Steady Current and Conduction Law

$$
i=\lim _{\Delta t\to 0}\frac{\Delta q}{\Delta t}=\frac{\mathrm d q}{\mathrm d t}
$$

the current density vector $\vec j$

$$
\begin{aligned}&di=\vec{j}\bullet d\vec{A},\\&i=\iint_A\vec{j}\bullet d\vec{A}\\&=\iint_Aj\cos\theta dA\end{aligned}
$$

the steady current condition

$$
\iint_A\vec{j}\bullet d\vec{A}=0\Leftrightarrow j_1\Delta A_1=j_2\Delta A_2
$$

### Ohm Law

- **linear devices** :**Metal, liquid containing acid, alkali, salt**
- **nonlinear devices** :**Evacuated tube, transistor**

![image-20241020225112215](/pic/phy2/Ohm-Law)

Conductance $G=\frac{1}{R}=\frac{\mathrm d I}{\mathrm d V}(Unit:S)$​
differential resistance $R=\frac{dV}{dI}$ (in usual context $R=\frac{V}{I}$ instead)

**Resistivity, & conductivity** :

we call $\rho $ as resistivity and $\sigma =\frac{1}{\rho}$ as conductivity , $R=\rho \frac{L}{A}$​

![image-20241104090458840](/pic/phy2/usual-resistivity.png)
$$
R=\int \rho \frac{\mathrm d l}{A}, \sigma =\frac{1}{\rho}
$$

or differential form:$j=\frac{E}{\rho}=\sigma E$

![image-20241020225354688](/pic/phy2/resistivity)

$$
\begin{aligned}
&R=\int\rho\frac{dl}{A}=\int_a^\infty\rho\frac{dr}{2\pi r^2} \\
&=\frac{\rho}{2\pi}[-\frac{1}{r}]_a^\infty=\frac{\rho}{2\pi a}
\end{aligned}
$$

:::note[$\rho-T$ relativity]

for metal

$$
\rho(T)=\rho_0+\alpha T
$$

:::

### Differential form of Ohm's Law

$$
i = \frac{\Delta V}{R}\\
i=\iint \vec j \cdot d \vec A\Rightarrow \Delta nV=\int \vec E\cdot d\vec l\\R=\int \rho \frac{dl}{A}
$$

it;s the integral form of Ohm's law

and when treating it as differential form
$$
\Delta i =\frac{\Delta V}{R}\\
j\Delta A =\frac{E\Delta l}{\rho \frac{\Delta l}{\Delta A}}\\
j=\frac{E}{\rho}=\sigma E
$$
holds for every node

### Electric power and Joule Law

different load consumes different energy form

- $R$ consumes theometical energy
- $Machine$ consumes machinical energy

$$
P=\frac W{\Delta t}=iV=i^2R=\frac{V^2}R
$$

Unit  $kW,W$

$1~degree =1kW.h=3.6MJ$

### Microscopic explanation of Ohm Law

![image-20241021092841895](/pic/phy2/Ohm_micro.png)

:::note[drift speed of electric charge]
$$
j=2.4A/mm^2\\
b=8.4\times 10^{28}m^{-3}\\
j=\frac{\Delta i}{\Delta A}=neu\\
u=\frac{j}{ne}=1.8\times 10^{-4}m/s<<v_t\approx 10^5m/s
$$
:::

## 31-2 Source and Electromotive Force(emf)

$$
\oint \vec E\bullet d\vec l =0
$$

only E and no current!
$$
\vec j =\sigma(\vec K+\vec E)
$$
for emf
$$
\varepsilon =\oint \vec K dl\approx \int _{-}^+ \vec K \cdot d\vec l
$$

### Terminal Voltage of a Seat

Discharge with $R$,and charge with $\varepsilon '$,
$$
\Delta V=\int _{+}^{-}\vec E\cdot d\vec l\\
\text{in~a~seat}:\vec E=-\vec K+\frac{\vec j}{\sigma}\\
\Delta V=\int_{-}^+ \vec K\cdot d\vec l-\int_{-}^+ \rho j dl \cos \theta\\=\varepsilon \pm (-jA\int_{-}^+ \frac{\rho d l}{A})=\varepsilon\pm ir
$$
the terminal voltage between ends

<img src="/pic/phy2/image-20241104092151726.png" alt="image-20241104092151726" style="zoom:33%;" />

<img src="/pic/phy2/P_dipole.png" alt="image-20241104092234306" style="zoom:33%;" />

- Discharge:

  - $$
    \Delta V_{AB}=\varepsilon -ir
    $$

- Charge

  - $$
    \Delta V_{AB}=\varepsilon +ir
    $$

### the current and output power for closed circuit

$$
i=\frac{\varepsilon }{R+r}
$$

$$
P_{out}=iV_{AB}=\left(\frac{\varepsilon}{R+r}\right)^2R
$$

$\dot P_{out}=0\Rightarrow \varepsilon ^2 \frac{r-R}{(R+r)^2}=0,R^*=r$

![image-20241104092654739]( /pic/phy2/image-20241104092654739.png)
$$
j=\sigma \vec E,\vec S=\vec E\times \vec H
$$

## 31-3 Simple circuit

Resistors connected in Series and Parallel

- $R=\sum R_i$
- $R^{-1}=\sum R_i^{-1}$

:::note[Voltmeter and Amperemeter]

- Galvanometer

  $I_g=50\mu A,R_g =1k\Omega$​

![image-20241104093208377](/pic/phy2/image-20241104093208377.png)
$$
I_g =\frac{U}{R_g+R_m}\
R_m=\frac{U-I_gR_g}{I_g}=\frac{U}{I_g}-R_g =199k\Omega
$$
![image-20241104093437907](/pic/phy2/image-20241104093437907.png)
$$
I_gR_g =(I-I_g)R_s\\R_s=\frac{I_g}{I-I_g}R_g
$$


:::

# Chap 32/33 The Steady Magnetic Field

 ## 32-1 Basic phenomena

:::tip[history]

first hard disk 1957:50 platters

:::

### Basic Phenomena of Magnetism

- attract small bits of metal
- have two poles
- like poles repel, and unlike poles attract
- oersted experiment: $B,i\to F$
- Solenoid is similar to a bar magnet
- Interaction between electric currents

![image-20241021084128203](/pic/phy2/bar_b.png)

the magnetic field line distribution is like electric field of a electdipole pair.



### Magnetic Monopoles

since no monopole has ever been found $\displaystyle \oint \vec B\cdot \mathrm d \vec A=0$

### Magnetic field

(Ampere) molecular current: he bind solenoid and a magnet

electric charge in motion is the source of Magnetic Fields

### Ampere's Law(1820.12.4)

:::note[Ampere's Law]

![image-20241021085424748](/pic/phy2/Ampere.png)

- Current element $i\mathrm d \vec s$

$$
\mathrm d F_{12}\propto \frac{i_1i_2\mathrm d s_1\mathrm d s_2}{r_{12}^2}=\frac{\mu _0}{4\pi } \cdot \frac{i_2\mathrm d \vec s_2\times (i_1\mathrm d \vec s_1\times \hat r_{12})}{r_{12}^2}
$$

$\mu_0 =4\pi\times10^{-7}(N\cdot A^{-2})$:Permeability constant

:::

the consider two examples

:::note[eg1]

![image-20241021085653200](/pic/phy2/B_eg1.png)
$$
\begin{aligned}
&d\vec{F}_{12}=\frac{\mu_0}{4\pi}\frac{i_2d\vec{s}_2\times(i_1d\vec{s}_1\times\hat{r}_{12})}{r_{12}^2} \\
&d\vec{s}_1\perp\hat{r}_{12} \\
&\therefore dF_{12}=\frac{\mu_0}{4\pi}\frac{i_1i_2ds_1ds_2}{r_{12}^2}\\&d\vec{F}_{21}=\frac{\mu_0}{4\pi}\frac{i_1d\vec{s}_1\times(i_2d\vec{s}_2\times\hat{r}_{21})}{r_{21}^2}\\&d\vec{s}_2\perp\hat{r}_{21}\\&\therefore dF_{21}=\frac{\mu_0}{4\pi}\frac{i_1i_2ds_1ds_2}{r_{12}^2}\\&\mathrm d F_{12}= \mathrm d F_{21}\end{aligned}
$$
![image-20241021085726219](/pic/B_eg2.png)
$$
\mathrm d F_{12}=0\\\mathrm d F_{21}=\frac{\mu_0}{4\pi}\frac{i_1i_2\mathrm d s_1\mathrm d s_2}{r_{12}^2}
$$
:::

### The Magnetic Induction Strength

- Coulomb's Law

$$
\vec{F}_{12}=\frac1{4\pi\varepsilon_0}\frac{q_1q_2}{r_{12}^2}\hat{r}_{12}\\\vec{F}_{12}=q_2\vec{E}_1, \vec{E}_1=\frac{\vec{F}_{12}}{q_2}\\\therefore\vec{E}_1=\frac1{4\pi\varepsilon_0}\frac{q_1}{r_{12}^2}\hat{r}_{12}
$$

- Ampere's Law
  $$
  d\vec{F}_{12}=\frac{\mu_0}{4\pi}\frac{i_2d\vec{s}_2\times(i_1d\vec{s}_1\times\hat{r}_{12})}{r_{12}^2}
  $$

let us call $i_2\mathrm d \vec s_2$ the element of a test electric current
$$
\begin{aligned}&d\vec{F}_2=i_2d\vec{s}_2\times\frac{\mu_0}{4\pi}\oint_{\mathrm{L}_1}\frac{i_1d\vec{s}_1\times\hat{r}_{12}}{r_{12}^2}\\&\text{Define:}\quad\vec{B}_1=\frac{\mu_0}{4\pi}\oint_{\mathrm{L}_1}\frac{i_1d\vec{s}_1\times\hat{r}_{12}}{r_{12}^2}\\&\therefore\quad d\vec{F}_2=i_2d\vec{s}_2\times\vec{B}_1\end{aligned}
$$

$$
\begin{aligned}
&d\vec{F}_2=i_2d\vec{s}_2\times\vec{B}_1 \\
&dF_2=i_2ds_2B_1\sin\theta \\
&\theta=0,dF_2=0 \\
&\theta=\frac{\pi}{2}, dF_{2} \mathrm{maximun} \\
&\boxed{\textbf{Define: }B_1=\frac{\left(dF_2\right)_{\max}}{i_2ds_2}}
\\&\Rightarrow \vec B_1=\frac{\mu_0}{4\pi} \oint_{L_1} \frac{i_1\mathrm d \vec s_1 \times \hat r_{12}}{r_{12}^2}
\end{aligned}
$$

the Unit $T$(Tesla=$1N/(m\cdot A)=10^4 \mathrm{~Gauss}$)

## 32-2 The magneticn field of a Current-Carrying loop

:::note[Biot-Savart Law]

![image-20241021091241369](/pic/phy2/Biot-Savart.png)
$$
\vec{B}=\frac{\mu_0}{4\pi}\oint_L\frac{id\vec{s}\times\hat{r}}{r^2}
$$
![image-20241021091446777](/pic/B_line.png)
$$
\begin{aligned}&B=\int_{A_{1}}^{A_{2}}dB=\frac{\mu_{0}}{4\pi}\int_{A_{1}}^{A_{2}}\frac{i\sin\theta dx}{r^{2}}\\&r_{0}=r\sin(\pi-\theta)=r\sin\theta, r=\frac{r_{0}}{\sin\theta}\\&x=-r_{0}ctg\theta,\quad dx=\frac{r_{0}d\theta}{\sin^{2}\theta}\\&B=\int_{\theta_{1}}^{\theta_{2}}\frac{\mu_{0}i}{4\pi}\frac{\sin\theta\cdot\frac{r_{0}d\theta}{\sin^{2}\theta}}{r_{0}^{2}}=\frac{\mu_{0}i}{4\pi r_{0}}\int_{\theta_{1}}^{\theta_{2}}\sin\theta d\theta\\&=\frac{\mu_{0}i}{4\pi r_{0}}(\cos\theta_{1}-\cos\theta_{2})\\&=\frac{\mu _0i}{2\pi r_0}\propto \frac{1}{r_0}\end{aligned}
$$
![image-20241021091716824](/pic/phy2/B_circular.png)
$$
\begin{aligned}
&\left|d\vec{B}\right|=\left|d\vec{B}^{\prime}\right| \\
&d{\vec{B}}={\frac{\mu_{0}}{4\pi}}{\frac{id{\vec{s}}\times{\hat{r}}}{r^{2}}} \\
&dB_{x}=dB\cdot\cos\alpha \\
&dB=\frac{\mu_{0}}{4\pi}\frac{ids}{r^{2}}\sin\theta \\
&\theta=\frac{\pi}{2}, \sin\theta=1, r=r_{0}/\sin\alpha \\
&B_{x}=\int dB\cos\alpha \\
&B=\frac{\mu_{0}i}{4\pi}\oint\frac{\sin^{2}\alpha}{r_{0}^{2}}\cos\alpha ds\\&=\frac{\mu_{0}i}{4\pi r_{0}^{2}}\sin^{2}\alpha\cos\alpha\cdot2\pi R\\
&B=\frac{\mu_0}{2} \frac{iR^2}{(R^2+r_0^2)^{\frac{3}{2}}}\xrightarrow{r_0=0}B=\frac{\mu_0 i}{2R}\\\ &\xrightarrow {r_0>>R} B=\frac{\mu_0 i R^2}{2r_0^3}
\end{aligned}
$$
we can define magnetic dipole moment $\mu$ (just like $\vec p=  q\vec l$)
$$
B=\frac{\mu_0iR^2}{2r_0^3}=\frac{\mu_0i\pi R^2}{2\pi r_0^3}=\frac{\mu_0iA}{2\pi r_0^3}\\\begin{aligned}&\text{Define: }\mu=iA=i\pi R^2(\vec \mu =i\vec A)\\&B=\frac{\mu_{0}}{2}\frac{iR^{2}}{r_{0}^{3}}=\frac{\mu_{0}}{2\pi}\frac{i\pi R^{2}}{r_{0}^{3}}=\frac{\mu_{0}}{2\pi}\frac{\mu}{r_{0}^{3}}\end{aligned}
$$
:::

![image-20241023110346439](/pic/phy2/B_circ.png)

:::note[p757 sample33-5]

![image-20241023110610077](/pic/eg757.png)
$$ {\frac{}{}}
\mathrm d B=\frac{\mu _0 di}{2\pi d}=\frac{\mu _0 \frac{i}{a} dx}{2\pi d}\\
d=\frac{R}{\cos \theta }\Rightarrow B_x=\int dB\cos \theta=\frac{\mu_0i}{2\pi a R}\int \cos^2\theta dx
$$
then 

$dx=\mathrm d (R\tan \theta)=R\frac{\mathrm d}{\cos^2\theta }$
$$
B_x=\frac{\mu_0 i}{2\pi a}\int_{-\theta}^{\theta}d\theta =\frac{\mu _0 i}{\pi a}\alpha =\frac{\mu_0 i}{\pi a}\arctan \frac{a}{2R}
$$
$R>>a:(\alpha \to \tan \alpha)B=\frac{\mu_0 i}{2\pi R}$

$R\to 0,B=\frac{\mu_0i}{2a}$​

:::note[**Bohr model of the hydrogen atom**]
$$
\begin{aligned}&a_0=0.529A=5.29\times10^{-11}m\\&\nu=6.63\times10^{15}Hz\\&i=e\nu=1.60\times10^{-19}\times6.63\times10^{15}=1.63\times10^{-3}A\\&B=\frac{\mu_0i}{2R}=\frac{4\pi\times10^{-7}\times1.06\times10^{-3}}{2\times5.29\times10^{-11}}=12.6T\\&\mu_\mathrm{B}=iA=1.63\times10^{-3}\times\pi\times(5.29\times10^{-11})^2\\&=0.923\times10^{-23}A\cdot m^2\end{aligned}
$$
called as Bohr Magnon

:::

### B of Solenoid

:::tip[Solenoid]

A constant magnetic field can (in principle) be produced by an $\infty$​ sheet of current. In practice, however, a constant magnetic field is often produced by a solenoid. 

Parameters:$i,n,R,L$,we assume $R<<L$

:::

![image-20241023112023529](/pic/phy2/B_solenoid.png)

for a circular loop 
$$
B=\frac{\mu_0}{2}\frac{iR^2}{\left(R^2+r_0^2\right)^{3/2}}
$$

$$
\begin{aligned}
&dB=\frac{\mu_{0}}{2}\frac{R^{2}indl}{\left[R^{2}+(x-l)^{2}\right]^{3/2}} \\
&B=\frac{\mu_{0}}{2}\int_{-L/2}^{L/2}\frac{R^{2}indl}{\left[R^{2}+\left(x-l\right)^{2}\right]^{3/2}} \\
&r={\sqrt{R^{2}+\left(x-l\right)^{2}}}={\frac{R}{\sin\beta}} \\
&\frac{x-l}{R}=ctg\beta\Rightarrow dl=\frac{R}{\sin^{2}\beta}d\beta 
\end{aligned}
$$

then
$$
\begin{aligned}
&B=\frac{\mu_{0}}{2}\int_{\beta_{1}}^{\beta_{2}}\frac{R^{2}ni\frac{R}{\sin^{2}\beta}d\beta}{(\frac{R^{2}}{\sin^{2}\beta})^{3/2}} \\
&=\frac{\mu_{0}}{2}\cdot ni\int_{\beta_{1}}^{\beta_{2}}\sin\beta d\beta \\
&=\frac12 \mu_{0}ni(\cos\beta_{1}-\cos\beta_{2})
\end{aligned}
$$
use
$$
\cos\beta_{1}=\frac{x+L/2}{\sqrt{R^{2}+\left(x+L/2\right)^{2}}}\\\cos\beta_{2}=\frac{x-L/2}{\sqrt{R^{2}+\left(x-L/2\right)^{2}}}
$$
with

- $L\to \infty ,\beta _1=0,\beta_2=\pi$

  $B=\frac{1}{2}\mu _0ni(1+1)=\mu_0ni$

- $\beta _1=0,\beta_2=\frac{\pi}{2}$

  $B=\frac{1}{2}\mu_0 n i(1-0)=\frac{1}{2}\mu_0 ni$

![image-20241023112523551](/pic/B_outside_solenoid.png)

The field outside the ideal solenoid is zero.

:::note[eg:multi-layers solenoid]

![image-20241023112648636](/pic/phy2/B_multilayers.png)
$$
B=\frac12 \mu_{0}ni(\cos\beta_{1}-\cos\beta_{2})
$$
With this
$$
\begin{aligned}&ni=\frac{Ni}{L}\Rightarrow\frac{jLdr}{L}=jdr=\frac{Ni}{2l(R_{2}-R_{1})} dr\\&\cos\beta_{2}=-\cos\beta_{1},\cos\beta_{1}=\frac{l}{\sqrt{l^{2}+r^{2}}}\end{aligned}
$$

$$
\begin{aligned}
&dB=\frac{1}{2} \mu_{0} \frac{Ni}{2l(R_{2}-R_{1})}\cdot\frac{2l}{\sqrt{l^{2}+r^{2}}} dr \\
&B=\mu_{0}jl\int_{R_{1}}^{R_{2}}\frac{dr}{\sqrt{l^{2}+r^{2}}} \\
&=\mu_{0}jl\ln\frac{R_{2}+\sqrt{R_{2}^{2}+l^{2}}}{R_{1}+\sqrt{R_{1}^{2}+l^{2}}}
\end{aligned}
$$
in practice

we define $\gamma=\frac{l}{R_1},\alpha =\frac{R_2}{R_1}$
$$
B_0=\mu_0hR_1\gamma \ln \frac{\alpha +\sqrt {\alpha^2+\gamma^2}}{1+\sqrt{1+\gamma^2}}
$$
:::

## 32-3 Gauss Law and Ampere's Loop Law for B

let's first review

for $\vec E$

- Gauss law:
  $$
  \oint\vec{E}\bullet d\vec{A}=\frac1{\varepsilon_0}\sum q, \nabla\bullet\vec{E}=\frac{\rho_e}{\varepsilon_0}
  $$

- Loop law
  $$
  \oint \vec E\bullet d\vec l =0,\nabla \times \vec E=0(\vec E=-\nabla V)
  $$

$$
\Phi_B=\iint\vec{B}\bullet d\vec{A}=\iint B\cos\theta dA(Unit :T\cdot m^2=Wb)
$$

for $\vec B$

- Gauss law:
  $$
  \oint\vec{B}\bullet d\vec{A}=0, \nabla\bullet\vec{B}=0
  $$

- Loop law
  $$
  \oint \vec B\bullet d\vec l =\mu _0\sum i,\nabla \times \vec B=\mu_0\vec J
  $$
  
- 

:::note[fact...]
$$
\oint \vec B\mathrm d \vec l =\mu_0\sum i+\mu_0\varepsilon_0\frac{\mathrm d}{\mathrm dt}\int _S\vec E\mathrm d \vec S
$$
The differential form is 
$$
\nabla \times \vec B =\mu_0\vec J+\mu_0\varepsilon _0\frac{\partial \vec E}{\partial t}
$$
:::



![image-20241030100813902](/pic/phy2/B-Ampere.png)

$$
\oint \vec B\cdot \mathrm d\vec l=\mu_0(i_1+i_3-2i_2)
$$
:::note[egs]

[e.g.1]

> inf long wire $R$,i uniform distribution 

$$
B\cdot 2\pi r=\mu_0i\cdot \frac{r^2}{\pi R^2}\Rightarrow B=\frac{\mu_0 i r}{2\pi R^2}(r<R)\propto r
$$

$$
B\cdot 2\pi r=\mu_0i\Rightarrow B=\frac{\mu_0 i }{2\pi r}(r>R)\propto \frac{1}{r}
$$

[e.g.2]

> Consider an $\infty$​ sheet of current described by n wires/length each carrying current i **into** the screen as shown. Calculate the B field.

for symmetry:vertical direction on the screen

we catch a w*w square
$$
\oint \vec B \bullet \mathrm d\vec  l=2Bw=\mu_0 n w i\Rightarrow B=\frac{1}{2}\mu_0 ni
$$
[e.g.3]

> calculate B for $\infty $​ solenoid 

view it as two sheets
$$
\oint \vec B\bullet \mathrm d \vec l =Bw=\mu _0 n w i\Rightarrow B=\mu_0 ni
$$
[e.g.4]

> the B of Toroid ($N$ total turns with current i)

![image-20241030102530083](/pic/Toroid.png)
$$
\oint \vec B\bullet \mathrm d \vec l=B2\pi r=\mu_0Ni\to B=\mu _0ni(n=\frac{N}{2\pi r})
$$
:::

::: tip[Application]

- Power door locks

- Magnetic cranes

- Electronic Switch “relay

:::

## 32-4 The magnetic force on a carrying-current wire

remember
$$
\mathrm d \vec F=i\mathrm d\vec s\times \vec B(\mathrm d \vec F_{2} =i_2\mathrm d\vec s_2\times \left(\oint _{L_1}\frac{i_1\mathrm d \vec s_1 \times \hat r_{12}}{r^2_{12}}\right))
$$
:::note[EG32-5,P738]

![image-20241030103224866](/pic/eg738.png)
$$
F_{2}=F_{\perp}=\int_{0}^{\pi}iBR\mathrm d \theta \sin\theta=2iBR
$$

$$
F=F_1+F_2+F_3=iB(2L+2R)
$$

:::

for two parallel conductors

![image-20241030103700752](/pic/phy2/B-two-par.png)
$$
f=\frac{\mu_0i_1i_2}{2\pi d}\xRightarrow{i_1=i_2=i}i\sqrt{\frac{fd}{\frac{\mu_0}{2\pi}}}
$$
we define $i=1A$ to be the current that make two $1m$ apart parallel conductors have force density $2\times 10^{-7}N/m$ 

 for convenience sake, we define $\hat n$ the unit normal vector of current loop
$$
\vec \mu =iA\hat n\\\vec \tau=\vec \mu\times \vec B 
$$
this holds for arbitrary shape loop

![image-20241030104543971](/pic/phy2/torque-shape.png)
$$
\begin{aligned}&dF_{1}=ids_{1}B\sin \theta _1\\&dF_2=ids_2 B\sin \theta _2\\&dF_1=dF_2=iBdh\\&d\tau =dF_1x_1+dF_2x_2=iBdA\end{aligned}
$$
for magnetic dipole

we define $\vec \tau=iA(\vec n \times \vec B)$

then
$$
U_p=-\int_{\infty}^{p} \tau \cdot d\vec \theta =\int \mu  B \sin \theta d\theta=\mu B \cos \theta =\vec \mu \bullet \vec B\Rightarrow U=-\mu \bullet \vec B
$$
remind that
$$
\vec p=q\vec d
$$

$$
\vec \tau =\vec p\times \vec E
$$

$$
U=-\vec p\bullet \vec E
$$

we have
$$
\mu =A\vec i
$$

$$
\vec \tau =\vec \mu \times \vec B
$$

$$
U=-\vec \mu \bullet \vec B 
$$

![image-20241030105437447](/pic/phy2/potential-energy-of-dipole.png)

| System               | μ(J/T)     |
| -------------------- | ---------- |
| Nucleus of N atom    | 2.0x10^-28 |
| Proton               | 1.4x10^-26 |
| Electron             | 9.3x10^-24 |
| N atom               | 2.8x10^-23 |
| Typical small coil   | 5.4x10^-6  |
| Small bar magnet     | 5.0        |
| Superconducting coil | 400        |
| The Earth            | 8.0x10^22  |

:::important[MRI (Magnetic Resonance Imaging)]

**Proton Spin and Magnetic Moment:**

- A single proton possesses a positive charge $ +|e| $ and an intrinsic angular momentum, known as "spin."
- Naively imagining the charge circulating in a loop gives rise to a magnetic dipole moment $ \mu $.

**Behavior in an External Magnetic Field \( B \):**

- **Classically:** Torques will be present unless the magnetic moment $\vec{\mu} $ is aligned with or against the magnetic field \( B \).
- **Quantum Mechanics (QM):** The spin is always aligned either with or against the magnetic field \( B \).

  - **Anti-aligned State:** Energy $ U_2 = \mu B $
  - **Aligned State:** Energy $ U_1 = -\mu B $

- **Energy Difference:** $ \Delta U = U_2 - U_1 = 2\mu B $

> $$
> \begin{aligned}&\mu_{proton}=1.36\times10^{-26}\mathrm{~A~m}^2\quad B=1\text{ Tesla }(=10^4\mathrm{~Gauss})\\&\Delta U=2\mu B=2.7\times10^{-26}\mathrm{J}\end{aligned}
> $$
>
> $h\nu =\Delta U\Rightarrow \nu=\frac{2.7\times 10^{-26}}{6.6\times 10^{-34}Js}=41\mathrm{MHz}$

:::

more applications

:::note[app:Galvanometers ]

![image-20241030110554772](/pic/galvanometers.png)

1. **Magnetic Force on a Current Loop:**
   - When a loop of wire carrying an electric current is placed in a magnetic field, the field exerts a torque on the loop, attempting to align the loop's magnetic dipole moment with the field.
2. **Structure of a Galvanometer:**
   - Inside a galvanometer, there is a rotating coil attached to a pivot.
   - To return the pointer to its equilibrium position, a spring is included in the galvanometer, which creates a torque in the opposite direction to the rotation of the coil.

:::

motor is almost the same ,we just skip it

- fixed voltage:DC motors
- fixed current:AC motors

## 32-5 The motion of a charge in a magnetic field

we define Lorentz Force as
$$
\begin{align*}
\vec F &=q\vec v\times \vec B\\
F&=qvB\sin \theta
\end{align*}
$$
we can find that 

$\vec F_L=q\vec v \times \vec B$ is the microscopic des.

$\mathrm d \vec F_A = id \vec s \times \vec B$ is the macroscopic des.

![image-20241104081624457](/pic/phy2/FLvsFA.png)

from this image we can confirm that
$$
\begin{align*}
\Delta q=enAu\Delta t\\
i=\frac{\Delta q}{\Delta t}=nAue\\
\vec u\perp \vec B,\sin \theta =1,f_L=euB\\
F_A=nA\times \Delta  s f_L=Bi\Delta s

\end{align*}
$$

---

then let's talk about the motion of a charged part. in a magnetic field

- $\vec v\perp \vec B$ 

  - $$
    \vec F =q\vec c\times \vec B\\qvB=n\frac{mv^2}{R},R=\frac{mv}{qB}
    $$

  - period : $T=\frac{2\pi R}{v}=\frac{2\pi m}{qB}$

  - frequency : $f=\frac{qB}{2\pi m}$

- $v_\perp =v\sin \theta ,v_{||} =v\cos \theta $​

  - ![image-20241104082258066](/pic/phy2/螺旋线圈.png)
  - Period : $T=\frac{2\pi R}{v\perp}$
  - $h=v_{||}T =\frac{2\pi mv_{||}}{qB}$

:::note[app:magnetic mirror]

![image-20241104082556278](/pic/phy2/mag-mirror.png)
$$
R=\frac{mv_\perp}{qB}\\
h=\frac{2\pi mv }{qB}\\
\theta \to 0,v_\perp \to v\theta ,v_{||}\to v
$$
in uniform magnetic field

the path is just circles(directions following the signal of charge)

![image-20241104082751733](/pic/phy2/uniform-path.png)

the detailed application is

- convex lens
- magnetic mirror

:::

:::note[app:magnetic bottle]
$$
R=\frac{mv_perp}{qB}
$$
the magnetic bottle is to confine the hot ionized gases and control the thermonuclear fusion

when  taking the strong B, and we can have a small R constraint

:::



---

:::tip[discovery of electron by **J.J.Thomson** in 1897]

![image-20241104083107468](/pic/phy2/JJthomson.png)
$$
\begin{align*}
\vec F=q\vec E+q\vec v\times \vec B\\eE=evB\Rightarrow v=\frac{E}{B}\\y=\frac{1}{2}\frac{eE}{m}\left(\frac{L}{v}\right)^2=\frac{eEL^2}{2mv^2}\\\Rightarrow\frac{e}{m}=\frac{2yE}{B^2L^2} =1.759\times 10^{11}C/kg
\end{align*}
$$
:::

:::note[mass spectrometer]

![image-20241104083413118](/pic/phy2/mass-spec.png)
$$
R=\frac{mv}{qB}\\\frac{1}{2}mv^2=qV \\\Rightarrow \frac{m}{q}=\frac{R^2B^2}{2V}
$$
detailedly we accelerate electrons  in a known potential $U=qv$

with looking at the $m/q$ value we can distinguish different particles and approximately calculate their propotion

- paleoceanography 
- space exploration
- detect chemical and bio. Weapons(*anthrax*)

:::

:::note[movement measurement]
$$
R=\frac{mv}{qB}=\frac{\sqrt {2mK}}{qB}
$$
:::

:::note[the cyclotron]
$$
qvB=m\frac{v^2}{R}\\
f=\frac{qB}{2\pi m}\\
v_M=BR\frac{q}{m}\\
E_K=\frac{1}{2}mv_M^2 =\frac{B^2R^2q^2}{2m}
$$
![image-20241104084028471](/Users/zzw4257/Documents/repo/zzw4257.cn/public/pic/phy2/cyclotron.png)

with relaticity effect
$$
\begin{align}
m=\frac{m_0}{\sqrt{1-\frac{v^2}{c^2}}}\\
T=\frac{2\pi m_0}{qB}\times \frac{1}{\sqrt {1-\frac{v^2}{c^2}}}\\
B\sqrt{1-\frac{v^2}{c^2}}=\mathrm {const}
\end{align}
$$
for proton 
$$
\frac{v}{c}=0.3
\rightarrow \sqrt{1-\frac{v^2}{c^2}}=0.95
$$
we can have synchrotron withe much larger magnitude B and N

:::

### The Hall Effect

![image-20241104084453456](/pic/phy2/hall-effect.png)

when at equilibrium
$$
\begin{align}
qvB=qE,E=vB\\
V_{AA'}=vBb=\frac{j}{nq} Bb=\frac{iB}{nqd}=\kappa \frac{iB}{d}\\
\end{align}
$$
(remember $j\cdot b\cdot d\equiv i$ Please)

we define the charge drift speed as $v$,and the volume density of charge is $n$,the Hall resistance $R_H$(this is a definition with replacement ,not a real concept )
$$
n=\frac{iB}{qd}\frac{1}{V_{AA'}}\\R_H=\frac{V_{AA'}}{i}=\frac{B}{nqd}
$$
:::important[the quantized hall effect]

when detect hall effect on two-dimensional hall effect , it;s displayed not linearly
$$
\frac{\Delta _H}{i}=\frac{B}{nqd}
$$
![image-20241104085112738](/pic/quantized-hall.png)

with const $n,q,d$,$R_H\propto B$

1986 Nobel Prize $\frac{h}{e^2}=25812.806\Omega$ we can define it as new standard resistance unit since it's made of some basic const in late physic

:::

### App of Hall effect

- Measure B
- Measure i P
- Transfer DC->AC

a specific field is ABS: work as B tensor,detect shaft rotation speed and beam oscillating voltage
$$
V_{AA'} = \frac{1}{nq}\cdot \frac{iB}{d}
$$
