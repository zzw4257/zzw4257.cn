---
title: 普物二总结Chap32~?磁学部分
published: 2024-11-11
description: 普物二总结，后续将搬迁到mkdocs上
tags: [note,links]
category: Unconcerned
draft: false

---

# 普物二总结——电学部分

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
$$
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

## Chap 34 The Faraday's Law of Induction

### General Review

- Electrostatics
  - motion of $q$ in $\vec E$
  - $\displaystyle \int \vec E\cdot d\vec A =\frac{\sum q_{cls}}{\varepsilon}$
- Magnetostatics
  - motion of $q$ in $\vec B$
- Electrodynamics
  - $\frac{d\vec B}{d t}\neq 0\Rightarrow \vec E$
  - AC circuit,inductors,transformers
  - $\frac{d\vec E}{d t}\neq 0\Rightarrow \vec B$

### 34-1/2 Basic Phenomena & Faraday's Law of Induction

$$
\frac{d\Phi_B}{dt}\to i_{ind}\\
\varepsilon =-\frac{d\Phi_B}{dt}
$$



just treat $\varepsilon$'s sign with right hand rule

### 34-3 Lenz's Law

The induced current will appear in such a direction that it **opposes the change in flux** that produced it.

![image-20241106104234350](/pic/phy2/laminated.png)

laminated materials can reduce **eddy currents**

:::note[app : magnetic Induction]

- E-M Cannon: alternating voltage to a solenoid ,then the flux changes -> current -> force
- **Tape/Hard Drive/ZIP Readout** : Tiny coil responds to change in flux as the magnetic domains (encoding 0’s or 1’s) go by.
- **Credit Card Reader**:faster  swipe -> large signal
- **Magnetic Levitation (Maglev) Trains**: eddy currents produce field in opposite direction

:::

### 34-4  Motional emf and Induced emf

- Motional emf: $\frac{d S}{d t}\to \frac{d\Phi}{dt}\to \varepsilon $
- Induced emf: $\frac{d B}{d t}\to \frac{d\Phi}{dt}\to \varepsilon $

#### Motional emf

Lorentz force results in a motional emf
$$
\vec f =-e(\vec v\times \vec B)
$$
Non electrostatic force 
$$
\vec K=\frac{\vec f}{-e}=\vec v\times \vec B
$$
Motional emf 
$$
\varepsilon =\int_{-}^+ \vec K \bullet d\vec l=\int_{C}^D (\vec  v\times \vec  B)\cdot d\vec l
$$
Lorentz force can't do work to electron

:::note[P781  34-4]

![image-20241116093051415](/pic/phy2/FL-eg1.png)

Sol1:
$$
d\varepsilon =(\vec v\times \vec B)\cdot d\vec r =-Bvdr\\
\varepsilon =-\frac{1}{2}B\omega R^2 
$$
Sol2:
$$
\varepsilon =\frac{-d\Phi_B}{dt}=-\frac{1}{2}\frac{dB(\frac{1}{2}R^2\theta)}{dt}
$$
direction +o -a

:::

:::note[App:Generators and Motors ]

![image-20241116093500033](/pic/phy2/image-20241116093500033.png)

![image-20241116093524271](/pic/image-20241116093524271.png)
$$
\Phi_B=BA\cos \omega t\\\varepsilon =BA\omega \sin \omega t
$$
:::

#### Induced emf

- Vortex electric field

a increasing magnetic field pass through the loop will generate a ringing electric field.
$$
\varepsilon =\oint \vec E\cdot d\vec l
$$
![image-20241116094304723](/pic/image-20241116094304723.png)
$$
\varepsilon =-\frac{d\Phi_B}{dt}=-Ak
$$

$$
\begin{aligned}&W=\varepsilon q_{0}=q_{0}E_{induced}\cdot2\pi r\\&\varepsilon=E_{induced}\cdot2\pi r=\oint\vec{E}_{induced}\cdot d\vec{l}\end{aligned}
$$

$$
\varepsilon=-\frac{d\Phi_{B}}{dt}\\\therefore\quad\oint\vec{E}_{induced}\cdot d\vec{l}=-\frac{d\Phi_{B}}{dt}
$$

it just implide that

$$
\nabla \times \vec E=-\frac{\partial \vec B}{\partial t}
$$

$$
\begin{aligned}&\vec{E}=\vec{E}_{sta}+\vec{E}_{ind}\\&\therefore\quad\oint\vec{E}\cdot d\vec{l}=\oint(\vec{E}_{sta}+\vec{E}_{ind})\cdot d\vec{l}=0+(-\frac{d\Phi_B}{dt})=-\frac{d\Phi_B}{dt}\end{aligned}
$$

Es is set up by charges,     Ein is set up by changing magnetic field.    Both kinds of electric field exert on charges.

:::note[The betatron]

![image-20241116095020370](/pic/image-20241116095020370.png)

Betatron produces a pulse rather than a continuous beam.

:::

### 34-5. Induction & Relative Motion

![image-20241116095155600](/pic/image-20241116095155600.png)
$$
\begin{aligned}&\text{Motional emf:}\\&\vec{V}=\vec{\nu}+\vec{\nu}_{a},\quad\vec{F}_{b}=\vec{N}+\vec{F}_{i}\\&\mathrm{d}W_{N}=N(\nu\mathrm{d}t)\\&=F_{B}\sin\theta(\nu\mathrm{d}t)\\&=(qVB)(\nu_{d}/V)(\nu\mathrm{d}t)\\&=(qB\nu_{d})(\nu\mathrm{d}t)\\&=(qB\nu)(\nu_{d}\mathrm{d}t)\\&=qB\nu dl\\&W_N=\int qBvdl=qBvD\\&\varepsilon = W_N/q=BDv \\&dW_i=-F_idl=-qvBdl\\&W_i=-qvBD=-W_N\end{aligned}
$$

$$
\varepsilon =\int (\vec E'+\vec v\times \vec B)\cdot d\vec l
$$

![image-20241116095538359](/pic/image-20241116095538359.png)

# Chapter 35(36) Inductance and    Magnetic properties of materials

## 35-1 Inductance

### Mutual Inductance

i1 change   s2 induced emf $\varepsilon _2$

i2 change   s1 induced emf $\varepsilon _1$
$$
M_{12}=\frac{\Psi_{12}}{i_{1}}=\frac{N_{2}\Phi_{12}}{i_{1}};\quad\varepsilon_{2}=-\frac{d\Psi_{12}}{dt}=-M_{12} \frac{di_{1}}{dt},\quad(i_{1} \mathrm{change})\\M_{21}=\frac{\Psi_{21}}{i_{2}}=\frac{N_{1}\Phi_{21}}{i_{2}};\quad\varepsilon_{1}=-\frac{d\Psi_{21}}{dt}=-M_{21} \frac{di_{2}}{dt},\quad(i_{2} \mathrm{change})
$$
$M_{12},M_{21}$ are called inductance constant (Unit: Henry)

![image-20241116095932154](/pic/image-20241116095932154.png)
$$
\begin{aligned}
&B=\mu_{0}ni, B_{1}=\mu_{0} \frac{N_{1}}{l}i_{1} \\
&\Psi_{_{12}}=N_{_2}B_{_1}A=\mu_{_0} \frac{N_{_1}N_{_2}A}{l}i_{_1}&& \varepsilon_{2}=-M\frac{di_{1}}{dt} \\
&M_{12}=\frac{\Psi_{_{12}}}{i_{_1}}=\mu_{_0}\frac{N_{_1}N_{_2}A}{l}&& =-25\times10^{-6}\times10V \\
&=4\pi\cdot10^{-7}\frac{1000\times20\times10^{-3}}{1}&& |=-250 \mu V \\
&=25\times10^{-6}H=25 \mu H \\
\end{aligned}
$$
:::note[App:Mutual Inductance]

- Transformers
- Airport Metal Detectors
- Pacemaker

:::

### Self-Inductance

![image-20241116100138609](/pic/image-20241116100138609.png)
$$
\begin{aligned}&\psi=NBA=Li\\&\varepsilon_{L}=-\frac{d\psi}{dt}=-L\frac{di}{dt}\\&V_{b}-V_{a}=-L\frac{di}{dt}\end{aligned}
$$
L —— self-inductance

![image-20241116100749029](/pic/image-20241116100749029.png)
$$
L=\frac{\displaystyle \iint  \vec B \cdot d\vec A }{i}
$$

$$
\varepsilon =-\frac{d\Phi_B }{dt}=-L\frac{di}{dt}
$$

how to calculate self-inductance?

$i,\vec B,N\to L$
$$
L=\frac{N\Phi_B}{i}\to\varepsilon _L =-\frac{d(N\Phi_B)}{dt}
$$
![image-20241116101221305](/pic/image-20241116101221305.png)

:::note[Toroid of rectangular]

![image-20241116101304824](/pic/image-20241116101304824.png)
$$
\begin{gathered}
\oint\vec{B}\bullet d\vec{l}=\mu_0N\boldsymbol{i} \\
B=\frac{\mu_0\boldsymbol{i}N}{2\pi r} \\
\boldsymbol{\Phi}_B=\int\int\vec{B}\bullet d\vec{A}=\int_a^b\frac{\mu_0\boldsymbol{i}N}{2\pi r}\boldsymbol{h}\mathrm{d}r \\
=\frac{\mu_0iNh}{2\pi}\int_a^b\frac{\mathrm{d}r}r=\frac{\mu_0iNh}{2\pi}\ln\frac ba\quad\therefore L=\frac{N\boldsymbol{\Phi}_B}i=\frac{\mu_0N^2\boldsymbol{h}}{2\pi}\ln\frac ba 
\end{gathered}
$$
:::
