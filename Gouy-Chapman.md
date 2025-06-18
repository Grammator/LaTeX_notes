# Poisson-Boltzmann general solution - the Gouy-Chapman approach

We are finding the solution of Poisson-Boltzmann 1D equation:

$\frac{d^2\psi}{dx^2}  =  \frac{c_{0}zq_e}{\varepsilon} \left ( e^{\frac{zq_e\psi \left ( x \right )}{k_BT}}-e^{-\frac{zq_e\psi \left ( x \right )}{k_BT}} \right )$

To solve it, we define new variable: 

$b \equiv \frac{zq_e \psi}{k_BT}$,

$\frac{d^2 b}{dx^2} \frac{k_B T}{zq_e} = \frac{c_0 zq_e}{\varepsilon} \left ( e^{b}-e^{-b} \right )$

$\frac{d^2 b}{dx^2} \frac{k_B T}{zq_e} = \frac{c_0 zq_e}{\varepsilon} 2 \frac{1}{2} \left ( e^{b}-e^{-b} \right )$

Then we simplify to:

$\frac{d^2 b}{dx^2} = \kappa^2 \mathrm{sinh}{b}$

using the definition of the hyperbolic sine:

$\mathrm{sinh}{b} \equiv \frac{e^{b}-e^{-b}}{2}$

To solve for $b$, we multiply both sides of the equation by an integrating factor $2 \cdot db/dx$, which leads to (further explained in Differential_identity.md):

$\frac{d}{dx} \left ( \frac{db}{dx} \right )^2 = 2 \kappa^2 \frac{db}{dx} \ \mathrm{sinh}{b}$

Now we can integrate:

$\int{\frac{d}{dx'} \left ( \frac{db}{dx'} \right )^2 dx'} = 2 \kappa^2 \int{\frac{db}{dx'} \ \mathrm{sinh}{b} \: dx'}$

which results in:

$\left ( \frac{db}{dx} \right )^2 = 2 \kappa^2 \int{\ \mathrm{sinh}{b'} \: db'}$

because on the left side one integration and one derivation cancelled each other and on the right side we used the identity $\frac{db}{dx}dx=db$. The result:

$\left ( \frac{db}{dx} \right )^2 = 2 \kappa^2 \ \mathrm{cosh}{b} + C$

yields an integration constant, which is determined, again, from boundary conditions. As b is dependent on the potential, it behaves the same, and at infinity both the change $\frac{db}{dx}$ as well as $b$ itself are zero. Since $\ \mathrm{cosh}{b}=1$ for $b=0$, it follows that $C = -2\kappa^2$, so that both sides are equal. Then

$\left ( \frac{db}{dx} \right )^2 = 2\kappa^2 \left ( \ \mathrm{cosh}{b} -1 \right )$

$\frac{db}{dx} = -\kappa \sqrt{2 \ \mathrm{cosh}{b} -2}$

The square root would allow for both signs, $b$ must be non-increasing though, therefore at kappa is a minus sign. To solve for $b$ itself, we use the identity: $\ \mathrm{sinh}{\frac{b}{2}}=\sqrt{\frac{1}{2} \ \mathrm{cosh}{b} -1}$ and get:

$\frac{db}{dx} = -2 \kappa \ \mathrm{sinh}{\frac{b}{2}}$

Now we separate variables and integrate:

$\int{\frac{db'}{\ \mathrm{sinh}{\frac{b}{2}}}} = -2 \kappa \int{dx'}$

and get:

$2 \cdot \ln { \left ( \tanh{\frac{b}{4}} \right ) } = -2 \kappa x + C'$

Note to the above integration:

$\left [ 2 ln{\left ( \mathrm{tanh}{\frac{b}{4}} \right )} \right ]' = 2 \cdot \frac{1}{tanh{\frac{b}{4}}} \cdot \left ( sech{\frac{b}{4}} \right )^2 \cdot \frac{1}{4} = \frac{1}{2} \frac{ \mathrm{cosh}{\frac{b}{4}}}{ \mathrm{sinh}{\frac{b}{4}}} \cdot \frac{1}{\left (  \mathrm{cosh}{\frac{b}{4}} \right )^2 } = \frac{1}{2} \frac{1}{ \mathrm{sinh}{\frac{b}{4}} \mathrm{cosh}{\frac{b}{4}}} = \frac{1}{ \mathrm{sinh}{\frac{b}{2}}}$.

From $\mathrm{tanh}$ definition: 

$ln{\left ( \frac{e^{\frac{b}{4}}-e^{-\frac{b}{4}}}{e^{\frac{b}{4}}+e^{-\frac{b}{4}}} \right )} = -\kappa x + C''$

which can be further simplified by expanding the bracket  by $e^{\frac{b}{4}}$:

$ln{\left ( \frac{e^{\frac{b}{2}}-1}{e^{\frac{b}{2}}+1} \right )} = -\kappa x + C''$

Now, the integration constant $C''$ is trivial, because as $b=\left ( zq_e \psi\right )/\left ( k_B T\right )$: $b_0 \left (  x=0 \right ) = \left ( zq_e \psi_0\right )/\left ( k_B T\right )$ from definition. Then

$ln{\left ( \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1} \right )} = C''$

and we can simplify

$ln{\left ( \frac{e^{\frac{b}{2}}-1}{e^{\frac{b}{2}}+1} \right )} - ln{\left ( \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1} \right )} = -\kappa$

$ln{\left ( \frac{e^{\frac{b}{2}}-1}{e^{\frac{b}{2}}+1} \cdot \left ( \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1} \right )^{-1} \right )} = -\kappa x$

$ln{\left [ \frac{\left ( e^{\frac{b}{2}}-1 \right ) \cdot \left ( e^{\frac{b_0}{2}}+1 \right )}{\left ( e^{\frac{b}{2}}+1 \right ) \cdot \left ( e^{\frac{b_0}{2}}-1 \right )} \right ] } = -\kappa x$
     
$\frac{\left ( e^{\frac{b}{2}}-1 \right ) \cdot \left ( e^{\frac{b_0}{2}}+1 \right )}{\left ( e^{\frac{b}{2}}+1 \right ) \cdot \left ( e^{\frac{b_0}{2}}-1 \right )} = e^{-\kappa x }$


and solve for $e^{\frac{b}{2}}$:

$\frac{e^{\frac{b}{2}}-1}{e^{\frac{b}{2}}+1} = e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1} {e^{\frac{b_0}{2}}+1}$

$e^{\frac{b}{2}}-1 = e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1} {e^{\frac{b_0}{2}}+1} \left ( e^{\frac{b}{2}}+1 \right )$

$e^{\frac{b}{2}}-1 = e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1} + e^{\frac{b}{2}} e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1}$

$e^{\frac{b}{2}} \left ( 1 - e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1} \right ) = e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1}+1$

$e^{\frac{b}{2}} = \frac{e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1}+1}{1 - e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1}}$

$e^{\frac{b}{2}} = \frac{e^{-\kappa x } \left ( e^{\frac{b_0}{2}}-1 \right ) + e^{\frac{b_0}{2}}+1}{-e^{-\kappa x } \left ( e^{\frac{b_0}{2}}-1 \right ) + e^{\frac{b_0}{2}}+1}$

Now we can substitute back for b:

$\psi \left ( x \right ) = \frac{2 k_B T}{z q_e} ln { \left ( \frac{e^{-\kappa x } \left ( e^{\frac{z q_e \psi_0}{2 k_B T}}-1 \right ) + e^{\frac{z q_e \psi_0}{2 k_B T}}+1}{-e^{-\kappa x } \left ( e^{\frac{z q_e \psi_0}{2 k_B T}}-1 \right ) + e^{\frac{z q_e \psi_0}{2 k_B T}}+1} \right ) }$

and in the end, we have a relation for potential in the distance.
