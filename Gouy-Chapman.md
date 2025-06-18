\section{Poisson-Boltzmann general solution}
\label{PB solution}

We are finding the solution of Poisson-Boltzmann 1D equation:

\begin{equation}
    \frac{d^2\psi}{dx^2}  =  \frac{c_{0}zq_e}{\varepsilon} \left ( e^{\frac{zq_e\psi \left ( x \right )}{k_BT}}-e^{-\frac{zq_e\psi \left ( x \right )}{k_BT}} \right ).
\end{equation}

To solve it, we define new variable $b \equiv \frac{zq_e \psi}{k_BT}$:

\begin{subequations}
\begin{eqnarray}
     \frac{d^2 b}{dx^2} \frac{k_B T}{zq_e} &=& \frac{c_0 zq_e}{\varepsilon} \left ( e^{b}-e^{-b} \right ),\\
     \frac{d^2 b}{dx^2} \frac{k_B T}{zq_e} &=& \frac{c_0 zq_e}{\varepsilon} 2 \frac{1}{2} \left ( e^{b}-e^{-b} \right ).
\end{eqnarray}
\end{subequations}

Then we simplify to:

\begin{equation}
    \frac{d^2 b}{dx^2} = \kappa^2 \ \mathrm{sinh}\,{b},
    \label{eq:PB_with_b}
\end{equation}

using the definition of the hyperbolic sine:

\begin{equation}
    \ \mathrm{sinh}\,{b} \equiv \frac{e^{b}-e^{-b}}{2}.
\end{equation}

To solve for $b$, we multiply both sides of the equation by an integrating factor $2 \cdot db/dx$, which leads to:

\begin{equation}
    \frac{d}{dx} \left ( \frac{db}{dx} \right )^2 = 2 \kappa^2 \frac{db}{dx} \ \mathrm{sinh}\,{b},
\end{equation}

because by the chain rule, it follows that:

\begin{equation}
    \frac{d}{db} \left ( \frac{db}{dx} \right )^2 = 2 \frac{db}{dx} \frac{d^2 b}{dx^2}.
\end{equation}

Now we can integrate:

\begin{equation}
    \int{\frac{d}{dx'} \left ( \frac{db}{dx'} \right )^2 dx'} = 2 \kappa^2 \int{\frac{db}{dx'} \ \mathrm{sinh}\,{b} \: dx'},
\end{equation}

which results in:

\begin{equation}
    \left ( \frac{db}{dx} \right )^2 = 2 \kappa^2 \int{\ \mathrm{sinh}\,{b'} \: db'},
\end{equation}

because on the left side one integration and one derivation cancelled each other and on the right side we used the identity $\frac{db}{dx}dx=db$. The result:

\begin{equation}
    \left ( \frac{db}{dx} \right )^2 = 2 \kappa^2 \ \mathrm{cosh}\,{b} + C
\end{equation}

yields an integration constant, which is determined, again, from boundary conditions. As b is dependent on the potential, it behaves the same, and at infinity both the change $\frac{db}{dx}$ as well as $b$ itself are zero. Since $\ \mathrm{cosh}\,{b}=1$ for $b=0$, it follows that $C = -2\kappa^2$, so that both sides are equal. Then

\begin{subequations}
\begin{eqnarray}
     \left ( \frac{db}{dx} \right )^2 &=& 2\kappa^2 \left ( \ \mathrm{cosh}\,{b} -1 \right ), \\
     \frac{db}{dx} &=& -\kappa \sqrt{2 \ \mathrm{cosh}\,{b} -2}.
\end{eqnarray}
\end{subequations}

The square root would allow for both signs, $b$ must be non-increasing though, therefore at kappa is a minus sign. To solve for $b$ itself, we use the identity: $\ \mathrm{sinh}{\frac{b}{2}}=\sqrt{\frac{1}{2} \ \mathrm{cosh}\,{b} -1}$ and get:

\begin{equation}
    \frac{db}{dx} = -2 \kappa \ \mathrm{sinh}{\frac{b}{2}}.
\label{eq:b_derivative}
\end{equation}


Now we separate variables and integrate:

\begin{equation}
    \int{\frac{db'}{\ \mathrm{sinh}{\frac{b}{2}}}} = -2 \kappa \int{dx'}
\end{equation}

and get:

\begin{equation}
    2 \cdot \ln { \left ( \tanh{\frac{b}{4}} \right ) } = -2 \kappa x + C'.
\end{equation}

Note to the above integration:

$\left [ 2\: ln{\left ( \mathrm{tanh}{\frac{b}{4}} \right )} \right ]' = 2 \cdot \frac{1}{tanh{\frac{b}{4}}} \cdot \left ( sech{\frac{b}{4}} \right )^2 \cdot \frac{1}{4} = \frac{1}{2} \frac{ \mathrm{cosh}{\frac{b}{4}}}{ \mathrm{sinh}{\frac{b}{4}}} \cdot \frac{1}{\left (  \mathrm{cosh}{\frac{b}{4}} \right )^2 } = \frac{1}{2} \frac{1}{ \mathrm{sinh}{\frac{b}{4}} \mathrm{cosh}{\frac{b}{4}}} = \frac{1}{ \mathrm{sinh}{\frac{b}{2}}}$.

From $\mathrm{tanh}$ definition: 

\begin{equation}
    ln{\left ( \frac{e^{\frac{b}{4}}-e^{-\frac{b}{4}}}{e^{\frac{b}{4}}+e^{-\frac{b}{4}}} \right )} = -\kappa x + C'',
\end{equation}

which can be further simplified by expanding the bracket  by $e^{\frac{b}{4}}$:

\begin{equation}
    ln{\left ( \frac{e^{\frac{b}{2}}-1}{e^{\frac{b}{2}}+1} \right )} = -\kappa x + C''
\end{equation}

Now, the integration constant $C''$ is trivial, because as $b=\left ( zq_e \psi\right )/\left ( k_B T\right )$: $b_0 \left (  x=0 \right ) = \left ( zq_e \psi_0\right )/\left ( k_B T\right )$ from definition. Then

\begin{equation}
    ln{\left ( \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1} \right )} = C'',
\end{equation}

and we can simplify

\begin{subequations}
\begin{eqnarray}
     ln{\left ( \frac{e^{\frac{b}{2}}-1}{e^{\frac{b}{2}}+1} \right )} - ln{\left ( \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1} \right )} &=& -\kappa , \\
     ln{\left ( \frac{e^{\frac{b}{2}}-1}{e^{\frac{b}{2}}+1} \cdot \left ( \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1} \right )^{-1} \right )} &=& -\kappa x,  \\
     ln{\left [ \frac{\left ( e^{\frac{b}{2}}-1 \right ) \cdot \left ( e^{\frac{b_0}{2}}+1 \right )}{\left ( e^{\frac{b}{2}}+1 \right ) \cdot \left ( e^{\frac{b_0}{2}}-1 \right )} \right ] } &=& -\kappa x, \\
     \frac{\left ( e^{\frac{b}{2}}-1 \right ) \cdot \left ( e^{\frac{b_0}{2}}+1 \right )}{\left ( e^{\frac{b}{2}}+1 \right ) \cdot \left ( e^{\frac{b_0}{2}}-1 \right )} &=& e^{-\kappa x },
\end{eqnarray}
\end{subequations}

and solve for $e^{\frac{b}{2}}$:

\begin{subequations}
\begin{eqnarray}
      \frac{e^{\frac{b}{2}}-1}{e^{\frac{b}{2}}+1} &=& e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1} {e^{\frac{b_0}{2}}+1} ,\\
      e^{\frac{b}{2}}-1 &=& e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1} {e^{\frac{b_0}{2}}+1} \left ( e^{\frac{b}{2}}+1 \right ) ,\\
      e^{\frac{b}{2}}-1 &=& e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1} + e^{\frac{b}{2}} e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1} ,\\
      e^{\frac{b}{2}} \left ( 1 - e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1} \right ) &=& e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1}+1 ,\\
      e^{\frac{b}{2}} &=& \frac{e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1}+1}{1 - e^{-\kappa x } \frac{e^{\frac{b_0}{2}}-1}{e^{\frac{b_0}{2}}+1}} ,\\
      e^{\frac{b}{2}} &=& \frac{e^{-\kappa x } \left ( e^{\frac{b_0}{2}}-1 \right ) + e^{\frac{b_0}{2}}+1}{-e^{-\kappa x } \left ( e^{\frac{b_0}{2}}-1 \right ) + e^{\frac{b_0}{2}}+1}.
\end{eqnarray}
\end{subequations}

Now we can substitute back for b:

\begin{equation}
    \psi \left ( x \right ) = \frac{2 k_B T}{z q_e} ln { \left ( \frac{e^{-\kappa x } \left ( e^{\frac{z q_e \psi_0}{2 k_B T}}-1 \right ) + e^{\frac{z q_e \psi_0}{2 k_B T}}+1}{-e^{-\kappa x } \left ( e^{\frac{z q_e \psi_0}{2 k_B T}}-1 \right ) + e^{\frac{z q_e \psi_0}{2 k_B T}}+1} \right ) }.
\label{eq:potential_app}
\end{equation}

and in the end, we have a relation for potential in the distance.
