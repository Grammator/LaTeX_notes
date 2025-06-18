# Used differential identitity

We are using an identity:

$\frac{\partial^2 \psi}{\partial x^2} = \frac{1}{2} \frac{d}{d\psi} \left ( \frac{\partial \psi}{\partial x} \right )^2$

Is that identity true? The identity can be written straightforward:

$\frac{d}{d\psi} \left ( \frac{\partial \psi}{\partial x} \right )^2 = \frac{d}{d\psi} \left ( \frac{\partial \psi}{\partial x} \cdot \frac{\partial \psi}{\partial x} \right )
        \frac{d}{d\psi} \frac{\partial \psi}{\partial x} \frac{\partial \psi}{\partial x} + \frac{\partial \psi}{\partial x} \frac{d}{d\psi} \frac{\partial \psi}{\partial x} = \frac{\partial^2 \psi}{\partial \psi \partial x} \frac{\partial \psi}{\partial x} + \frac{\partial \psi}{\partial x} \frac{\partial^2 \psi}{\partial \psi \partial x} = \\
        \frac{\partial \psi}{\partial \psi} \frac{\partial}{\partial x} \frac{\partial \psi}{\partial x} + \frac{\partial \psi}{\partial \psi} \frac{\partial}{\partial x} \frac{\partial \psi}{\partial x} = \frac{\partial}{\partial x} \frac{\partial \psi}{\partial x} + \frac{\partial}{\partial x} \frac{\partial \psi}{\partial x} = 2 \frac{\partial^2 \psi}{\partial x^2}.$

Or, from the chain rule, if we have a functions $h(g)$ and $g(x)$, meaning both $h,g$ depend on $x$, the derivative is then:
    
$\frac{dh}{dx} = \frac{dh}{dg} \cdot \frac{dg}{dx} |: \frac{dg}{dx}$

$\frac{dx}{dg} \cdot \frac{dh}{dx} = \frac{dh}{dg}$

$\frac{d}{dg} h = \frac{dx}{dg} \cdot \frac{dh}{dx}$


if we now set $g = f$ and $h(g) = \frac{df}{dx}$ we get:

$\frac{d}{df} \left ( \frac{\partial f}{\partial x} \right ) = \frac{dx}{df} \frac{d \left ( \frac{\partial f}{\partial x} \right )}{dx} = \frac{dx}{df} \frac{\partial^2 f}{\partial x^2}$

as $\frac{dx}{df} = \frac{1}{\frac{df}{dx}}$:

$\frac{d}{df} \left ( \frac{\partial f}{\partial x} \right ) = \frac{f''}{f'}$

If we apply this to our case, we get twice the chain rule:

$\frac{d}{df} \left ( \frac{\partial f}{\partial x} \right )^2 = 2 \frac{\partial f}{\partial x} \cdot \frac{d}{df} \frac{\partial f}{\partial x}$

and as we already know the second factor:

$\frac{d}{df} \left ( \frac{\partial f}{\partial x} \right )^2 = 2 f' \cdot \frac{f''}{f'} = 2 f''$

We have shown that the identity works from both chain rule and derivative of product rule.
