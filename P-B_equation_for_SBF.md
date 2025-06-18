# Integration of 1st derivative of P-B equation for the SBF

Here is the detailed, step-by-step solution of the P-B equation of the SBF, the though process is described in the dissertation.

$\sqrt{\frac{\varepsilon}{2k_B T}} \int \frac{d \psi}{\sqrt{ c_0^{2+} \frac{1}{\left ( e^{\frac{q_e \psi(x)}{k_B T}} \right ) ^2} + c_0^{1+} \frac{1}{e^{\frac{q_e \psi(x)}{k_B T}}} + c_0^{1-} e^{\frac{q_e \psi(x)}{k_B T}} + c_0^{2-} \left ( e^{\frac{q_e \psi(x)}{k_B T}} \right )^2 - \left ( c_0^{2+} + c_0^{1+} + c_0^{1-} + c_0^{2-} \right ) }}$

We use a substitution:

$e^{\frac{q_e \psi(x)}{k_B T}} = \beta$

$e^{\frac{q_e \psi(x)}{k_B T}} \cdot \frac{q_e}{k_B T} d\psi = d\beta$

$\beta \frac{q_e}{k_B T} d\psi = d\beta$

$d\psi = \frac{d\beta}{\beta} \frac{k_B T}{q_e}$

getting:

$\sqrt{\frac{\varepsilon}{2k_B T}} \frac{k_B T}{q_e} \int \frac{d \beta}{ \beta \sqrt{ c_0^{2+} \frac{1}{\beta^2} + c_0^{1+} \frac{1}{\beta} + c_0^{1-} \beta + c_0^{2-} \beta^2 - \left ( c_0^{2+} + c_0^{1+} + c_0^{1-} + c_0^{2-} \right ) }}$

$\sqrt{\frac{\varepsilon k_B T}{2 q_e^2}} \int \frac{d \beta}{ \sqrt{ c_0^{2+}  + c_0^{1+} \beta - c_{tot} \beta^2 + c_0^{1-} \beta^3 + c_0^{2-} \beta^4 }}$

where $c_{tot} = c_0^{2+} + c_0^{1+} + c_0^{1-} + c_0^{2-}$. Having a solution for a following integral:

$\int \frac{d \beta}{ \sqrt{ \left( \beta - K_1 \right ) \left( \beta - K_2 \right ) \left( \beta - K_3 \right ) \left( \beta - K_4 \right ) }}$

which is:

$\frac{2 \sqrt{\beta - K_1} \sqrt{\beta - K_2} (\beta -K_4) \sqrt{\frac{(\beta-K_3) (K_1-K_2)}{(\beta -K_2) (K_1-K_3)}} \mathcal{G}\left(\arcsin \left( \frac{\sqrt{\beta -K_1} \sqrt{K_2-K_4}}{\sqrt{\beta -K_2} \sqrt{K_1-K_4}}\right),\frac{(K_2-K_3) (K_1-K_4)}{(K_1-K_3) (K_2-K_4)}\right) } {\sqrt{K_1-K_4} \sqrt{K_2-K_4} \sqrt{\frac{(\beta -K_4) (K_1-K_2)}{(\beta -K_2) (K_1-K_4)}} \sqrt{(\beta -K_1) (\beta -K_2) (\beta -K_3) (\beta -K_4)}}$

The function $\mathcal{G}(\varphi,k^2)$ is an incomplete elliptic integral of the first kind, given as:

$\mathcal{G}(\varphi,k^2) = \int_0^{\varphi} \frac{d\theta}{\sqrt{1-k^2 \mathrm{sin}^2 \theta}}$

with arguments, amplitude:

$\varphi = \arcsin \left(\frac{\sqrt{\beta -K_1} \sqrt{K_2-K_4}}{\sqrt{\beta -K_2} \sqrt{K_1-K_4}}\right)$

and the square of the modulus of eccentricity:

$m = k^2 = \frac{(K_2-K_3) (K_1-K_4)}{(K_1-K_3) (K_2-K_4)}$

from which we get additional constraints for the constans: $K_1 \neq K_3$, $K_2 \neq K_4$, $K_1 \neq K_4$. Factorising the integrand:

$\left( \beta - K_1 \right ) \left( \beta - K_2 \right ) \left( \beta - K_3 \right ) \left( \beta - K_4 \right ) =$

$=\beta^4 + \beta^3 (-K_1-K_2-K_3-K_4) + \beta^2 (K_1 K_2 + K_1 K_3 + K_1 K_4 + K_2 K_3 + K_2 K_4 + K_3 K_4) + \beta (-K_1 K_2 K_3 - K_1 K_3 K_4 - K_1 K_2 K_4 - K_2 K_3 K_4 ) + K_1 K_2 K_3 K_4$

Aligning coefficients at each power of beta:

$\sqrt{\frac{\varepsilon k_B T}{2 q_e^2}} \int \frac{d \beta}{ \sqrt{c_0^{2-}} \sqrt{ \beta^4 + \frac{c_0^{1-}}{c_0^{2-}}  \beta^3 - \frac{c_{tot}}{c_0^{2-}} \beta^2 + \frac{c_0^{1+}}{c_0^{2-}}\beta + \frac{c_0^{2+}}{c_0^{2-}} }}$

and compare them, getting the following system of equations:

$-K_1-K_2-K_3-K_4 = \frac{c_0^{1-}}{c_0^{2-}}$

$K_1 K_2 + K_1 K_3 + K_1 K_4 + K_2 K_3 + K_2 K_4 + K_3 K_4 = - \frac{c_{tot}}{c_0^{2-}}$

$-K_1 K_2 K_3 - K_1 K_3 K_4 - K_1 K_2 K_4 - K_2 K_3 K_4 = \frac{c_0^{1+}}{c_0^{2-}}$

$K_1 K_2 K_3 K_4 = \frac{c_0^{2+}}{c_0^{2-}}$

To proceed, we can substitute the values for the SBF and solve the system numerically. The numerical solver returns 12 solutions, consisting of all the permutations of constants $K_i$, where two equal to 1, the other two are negative numbers. If we choose $K_3 = 1$ and $K_4 = 1$, with the other two considered as some negative numbers. First, the parameter $m$ reduces to:

$m = k^2 = \frac{(K_2-1) (K_1-1)}{(K_1-1) (K_2-1)} = 1$

Amplitude $\varphi$ is:

$\varphi = \arcsin \left(\frac{\sqrt{\beta -K_1} \sqrt{K_2-1}}{\sqrt{\beta -K_2} \sqrt{K_1-1}}\right)$

and the equation:

$\frac{2 \sqrt{\beta - K_1} \sqrt{\beta - K_2} (\beta - 1) \cancel{ \sqrt{\frac{(\beta-1) (K_1-K_2)}{(\beta -K_2) (K_1-1)}} } \mathcal{G} \left ( \varphi, m \right)}{\sqrt{K_1-1} \sqrt{K_2-1} \cancel{  \sqrt{\frac{(\beta -1) (K_1-K_2)}{(\beta -K_2) (K_1-1)}} } \sqrt{(\beta -K_1) (\beta -K_2) (\beta -1) (\beta -1)}}$

$= \frac{2 \sqrt{(\beta - K_1) (\beta - K_2) } (\beta - 1) \mathcal{G} \left ( \varphi, m \right)}{\sqrt{K_1-1} \sqrt{K_2-1}\sqrt{(\beta -K_1) (\beta -K_2) (\beta -1)^2}} =$

$= \frac{2 \cancel{  \sqrt{(\beta - K_1) (\beta - K_2) } } \cancel{(\beta - 1)} \mathcal{G} \left ( \varphi, m \right)}{\sqrt{K_1-1} \cancel{(\beta - 1)} \sqrt{K_2-1}\cancel{  \sqrt{(\beta - K_1) (\beta - K_2) }  }} =$

$= \frac{2 \mathcal{G} \left ( \varphi, m \right)}{\sqrt{K_1-1} \sqrt{K_2-1} }$

The expression is very conveniently reduced to:

$\sqrt{\frac{\varepsilon k_B T}{2 q_e^2 c_0^{2-}}} \frac{2 \mathcal{G}(\varphi,k^2)}{\sqrt{K_1-1} \sqrt{K_2-1}} = x + C$

with $k^2 = 1$ and 

$\varphi(\beta) = \arcsin {\left(\frac{\sqrt{\beta -K_1} \sqrt{K_2-1}}{\sqrt{\beta -K_2} \sqrt{K_1-1}}\right)}$

The constants gradually formed exactly into the Debye length $\lambda_D = \sqrt{\frac{\varepsilon k_B T}{2 q_e^2 c_0}} $

$\lambda_D (c_0^{2-}) \frac{2 \mathcal{G}(\varphi,k^2)}{\sqrt{K_1-1} \sqrt{K_2-1}} = x + C$

To solve the elliptic integral, we use the identities:

$u = \mathcal{G}(\varphi,k^2) = \int_0^\varphi \frac{d\theta}{\sqrt{1-k^2 \mathrm{sin}^2 \theta}}$

and

$u = \int_0^{\mathrm{sn} u} \frac{da}{\sqrt{(1-a^2)\cdot (1-k^2a^2)}} = \int_0^{\sin \varphi} \frac{da}{\sqrt{(1-a^2)\cdot (1-k^2a^2)}}$

This integral upper limit gets rid of the arcus sine in our $\varphi$ and is also simplified given $k^2  = 1$; this integral then is:

$\int_0^x \frac{da}{\sqrt{(1-a^2)\cdot (1-a^2)}} = \int_0^x \frac{da}{1-a^2} = \frac{1}{2} \ln{\frac{1+x}{1-x}} = \mathrm{arctanh}  x$

where x is our $\sin{\varphi}$, so we can write the equation without the elliptic integral:

$\lambda_D (c_0^{2-}) \frac{2  \mathrm{arctanh} \left(\frac{\sqrt{\beta -K_1} \sqrt{K_2-1}}{\sqrt{\beta -K_2} \sqrt{K_1-1}}\right) } {\sqrt{K_1-1} \sqrt{K_2-1}} = x + C$

We now have to express $\beta$ and substitute back. Knowing $\frac{1}{\lambda_D} = \kappa (c_0^{2-})$:

$\frac{2  \mathrm{arctanh} \left(\frac{\sqrt{\beta -K_1} \sqrt{K_2-1}}{\sqrt{\beta -K_2} \sqrt{K_1-1}}\right) } {\sqrt{K_1-1} \sqrt{K_2-1}} = \kappa x + \kappa C$

$\frac{2  \mathrm{arctanh} \left(\frac{\sqrt{\beta -K_1} \sqrt{K_2-1}}{\sqrt{\beta -K_2} \sqrt{K_1-1}}\right) } {\sqrt{-1} \sqrt{1-K_1} \sqrt{-1} \sqrt{1-K_2}} = \kappa x + \kappa C$

$\frac{2  \mathrm{arctanh} \left(\frac{\sqrt{\beta -K_1} \sqrt{K_2-1}}{\sqrt{\beta -K_2} \sqrt{K_1-1}}\right) } { i^2 \sqrt{1-K_1} \sqrt{1-K_2}} = \kappa x + \kappa C$

$\mathrm{arctanh} \left(\frac{\sqrt{\beta -K_1} \sqrt{K_2-1}}{\sqrt{\beta -K_2} \sqrt{K_1-1}}\right) = -\frac{\sqrt{1-K_1} \sqrt{1-K_2}}{2} \left ( \kappa x + \kappa C \right )$

setting $K' = \frac{\sqrt{1-K_1} \sqrt{1-K_2}}{2}$,

$\mathrm{arctanh} \left(\frac{\sqrt{\beta -K_1} \sqrt{K_2-1}}{\sqrt{\beta -K_2} \sqrt{K_1-1}}\right) = -K' \left ( \kappa x + \kappa C \right )$

$\frac{\sqrt{\beta -K_1} \sqrt{K_2-1}}{\sqrt{\beta -K_2} \sqrt{K_1-1}} = \mathrm{tanh} \left ( -K' \left ( \kappa x + \kappa C \right ) \right )$

$\sqrt{\frac{\beta -K_1 }{\beta -K_2} } = \sqrt{ \frac{K_1-1}{K_2-1} }  \mathrm{tanh} \left ( -K' \left ( \kappa x + \kappa C \right ) \right )$

$\frac{\beta -K_1 }{\beta -K_2} = \frac{K_1-1}{K_2-1}  \mathrm{tanh}^2 \left ( -K' \left ( \kappa x + \kappa C \right ) \right )$

$\beta -K_1 = (\beta -K_2) \frac{K_1-1}{K_2-1}  \mathrm{tanh}^2 \left ( -K' \left ( \kappa x + \kappa C \right ) \right )$

$\beta - \beta \frac{K_1-1}{K_2-1}  \mathrm{tanh}^2 \left ( -K' \left ( \kappa x + \kappa C \right ) \right ) = K_1 - K_2 \frac{K_1-1}{K_2-1}  \mathrm{tanh}^2 \left ( -K' \left ( \kappa x + \kappa C \right ) \right )$

$\beta = \frac{K_1 - K_2 \frac{K_1-1}{K_2-1}  \mathrm{tanh}^2 \left ( -K' \left ( \kappa x + \kappa C \right ) \right ) } {1 -\frac{K_1-1}{K_2-1}  \mathrm{tanh}^2 \left ( -K' \left ( \kappa x + \kappa C \right ) \right )}$

we substitute back $\beta = e^{\frac{q_e \psi(x)}{k_B T}}$

$e^{\frac{q_e \psi(x)}{k_B T}} = \frac{K_1 - K_2 \frac{K_1-1}{K_2-1}   \mathrm{tanh}^2 \left ( -K' \left ( \kappa x + \kappa C \right ) \right ) } {1 -\frac{K_1-1}{K_2-1}  \mathrm{tanh}^2 \left ( -K' \left ( \kappa x + \kappa C \right ) \right )}$

$\frac{q_e \psi(x)}{k_B T} = \mathrm{ln} \left [ \frac{K_1 - K_2 \frac{K_1-1}{K_2-1}  \mathrm{tanh}^2 \left ( -K' \left ( \kappa x + \kappa C \right ) \right ) } {1 -\frac{K_1-1}{K_2-1}   \mathrm{tanh}^2 \left ( -K' \left ( \kappa x + \kappa C \right ) \right )} \right ]$

we get the final and general solution for the SBF:

$\psi(x) = \frac{k_B T}{q_e} \mathrm{ln} \left [ \frac{K_1 - K_2 \frac{K_1-1}{K_2-1}  \mathrm{tanh}^2 \left ( -K' \left ( \kappa x + \kappa C \right ) \right ) } {1 -\frac{K_1-1}{K_2-1}   \mathrm{tanh}^2 \left ( -K' \left ( \kappa x + \kappa C \right ) \right )} \right ]$

The constant $C$ is defined from boundary conditions:

$C = \frac{2 \lambda_D (c_0^{2-})}{\sqrt{K_1-1} \sqrt{K_2-1}} \mathrm{arctanh} \left(\frac{\sqrt{e^\frac{q_e \psi_0}{k_B T} -K_1} \sqrt{K_2-1}}{\sqrt{e^\frac{q_e \psi_0}{k_B T} -K_2} \sqrt{K_1-1}}\right)$

$C = \frac{\lambda_D (c_0^{2-})}{K'} \mathrm{arctanh} \left(\frac{\sqrt{e^\frac{q_e \psi_0}{k_B T} -K_1} \sqrt{K_2-1}}{\sqrt{e^\frac{q_e \psi_0}{k_B T} -K_2} \sqrt{K_1-1}}\right)$
