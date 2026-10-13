# Modelamiento de Persecución Target-Proyectil

[Referencia](https://secwww.jhuapl.edu/techdigest/content/techdigest/pdf/V29-N01/29-01-Palumbo_Homing.pdf)

## Modelo General 2D

El Target $T$ sigue la dinámica

$$
\begin{align}
\frac{d\vec{v}_{T}}{dt} &=  \vec{a}_{T} ,\qquad \vec{v}_{T}(0)=\vec{v}_{T,0},\\
\frac{d\vec{x}_{T}}{dt} &= \vec{v}_{T},\qquad \vec{x}_{T}(0)=\vec{x}_{T,0}.
\end{align}
$$

Sea $\vec{a}_{T}=a_{v}\hat{v}_{T}+a_{n} \hat{n}$ , donde $\hat{v}_{T}$ es la dirección unitaria de la velocidad, y $\hat{n}$ es la dirección unitaria perpendicular a $\hat{v}_{T}$. Si consideramos la rotación de 90° 

$$
J=\begin{pmatrix}0 & -1 \\  1 & 0\end{pmatrix},
$$

entonces $\hat{n}=J\hat{v}_{T}$. Para que la aceleración sea perpendicular al movimiento, la componente de aceleración en $\hat{v}_{T}$ debe ser nula, por lo que 

$$
\vec{a}_{T}=a_{T}\hat{n}=a_{T}J\hat{v}_{T}=a_{T}J\frac{\vec{v}_{T}}{\lVert \vec{v}_{T} \rVert }.
$$

Por otro lado, el proyectil obedece a la dinámica dada por

$$
\begin{align}
\frac{d\vec{v}_{M}}{dt} &=  \vec{a}_{M} ,\qquad \vec{v}_{M}(0)=\vec{v}_{M,0},\\
\frac{d\vec{x}_{M}}{dt} &= \vec{v}_{M} ,\qquad \vec{x}_{M}(0)=\vec{x}_{M,0}.
\end{align}
$$

En este caso, la aceleración $a_{M}$ es perpendicular a la LOS. Denotando $\vec{r}=\vec{x}_{T}-\vec{x}_{M}$, la LOS está dada por 

$$
\hat{r}=\frac{\vec{r}}{\lVert \vec{r} \rVert }.
$$

Así, su aceleración está dada por 

$$
\vec{a}_{M}=a_{M}J\hat{r}.
$$

Con todo lo anterior, es posible expresar la dinámica como un sistema de la forma $\dot{z}(t)=f(z(t),u(t)),\ z(0)=z_{0}$. De la definición de $\vec{r}$, tenemos que 

$$
\frac{d\vec{r}}{dt}=\frac{d}{dt}\vec{x}_{T}-\frac{d}{dt}\vec{x}_{M}=\vec{v}_{T}-\vec{v}_{M}.
$$

Definiendo $\vec{v}=\vec{v}_{T}-\vec{v}_{M}$, se tiene además que

$$
\frac{d \vec{v}}{dt}=\frac{d}{dt}\vec{v}_{T}-\frac{d}{dt}\vec{v}_{M}=a_{T}J\hat{v}_{T}-a_{M}J\hat{r}
$$

Así, el sistema se expresa de la forma

$$
\begin{align}\frac{d\vec{r}}{dt}&= \vec{v}, \qquad \qquad \qquad \qquad \qquad \quad\vec{r}(0)=\vec{x}_{T,0}-\vec{x}_{M,0}\\
\frac{d\vec{v}}{dt}&= a_{T}J\frac{\vec{v_T}}{\lVert \vec{v_T} \rVert }-a_{M}J\frac{\vec{r}}{\lVert \vec{r} \rVert }, \qquad \vec{v}(0)=\vec{v}_{T,0}-\vec{v}_{M,0}\\
\frac{d\vec{v}_{T}}{dt}&= a_{T}J\frac{\vec{v}_T}{\lVert \vec{v}_T \rVert }, \qquad \qquad\qquad  \quad \vec{v}_{T}(0)=\vec{v}_{T,0}
\end{align}
$$

donde el objetivo a un tiempo final $t_{f}$ es que $\vec{r}(t_{f})=0$, indicando que el proyectil colisionó con el target. Adicionalmente, dado que vamos a controlar cómo cambia la aceleración perpendicular del proyectil, se denotará $u(t):= a_{M}(t)$.

## Modelo en función de ángulos

Sean $\lambda$ el ángulo de la LOS, $\theta_{M}$ el ángulo de movimiento del proyectil y $\theta_{T}$ el del objetivo, todos respecto al eje horizontal. Al definir las magnitudes $R=\lVert\vec r\rVert$, $V=\lVert\vec v\rVert$ y $V_T=\lVert\vec v_T\rVert$, tenemos que

$$  
\vec r=R\begin{pmatrix}\cos\lambda\\ \sin\lambda\end{pmatrix},\quad  
\vec v=V\begin{pmatrix}\cos\theta\\ \sin\theta\end{pmatrix},\quad  
\vec v_T=V_T\begin{pmatrix}\cos\theta_T\\ \sin\theta_T\end{pmatrix}.
$$

Además, podemos expresar las direcciones $\hat r$, $\hat v$, $\hat v_T$ y sus rotaciones como

$$
\begin{align}\hat r&=\begin{pmatrix}\cos\lambda\\ \sin\lambda\end{pmatrix},&  
J\hat r&=\begin{pmatrix}-\sin\lambda\\ \cos\lambda\end{pmatrix},\\  
\hat v&=\begin{pmatrix}\cos\theta\\ \sin\theta\end{pmatrix},&  
J\hat v&=\begin{pmatrix}-\sin\theta\\ \cos\theta\end{pmatrix},\\
\hat v_T&=\begin{pmatrix}\cos\theta_T\\ \sin\theta_T\end{pmatrix},&  
J\hat v_T&=\begin{pmatrix}-\sin\theta_T\\ \cos\theta_T\end{pmatrix}.\end{align}
$$

Derivando la expresión de $\vec{r}$ respecto al tiempo, obtenemos

$$
\frac{d\vec{r}}{dt}=\dot{R}\begin{pmatrix}\cos\lambda\\\sin\lambda\end{pmatrix}+R\dot{\lambda}\begin{pmatrix}-\sin\lambda\\\cos\lambda\end{pmatrix}.
$$

Como $\frac{d\vec{r}}{d{t}}=\vec{v}$, al proyectar sobre las direcciones $\hat{r}$ y $J\hat{r}$, obtenemos las ecuaciones

$$
\begin{align}
\left\langle\frac{d\vec r}{dt},\hat r\right\rangle  
=\langle\vec v,\hat r\rangle  
&\implies \dot R=V\cos(\theta-\lambda),\\
\left\langle\frac{d\vec r}{dt},J\hat r\right\rangle  
=\langle\vec v,J\hat r\rangle  
&\implies \dot\lambda=\frac{V}{R}\sin(\theta-\lambda).
\end{align}
$$

Por otro lado, derivando la velocidad del target, tenemos

$$
\frac{d\vec{v}_T}{dt}=\dot{V}_T\begin{pmatrix}\cos\theta_T\\\sin\theta_T\end{pmatrix}+V_T\dot{\theta}_T\begin{pmatrix}-\sin\theta_T\\\cos\theta_T\end{pmatrix}.
$$

Análogamente, al proyectar sobre las direcciones $\hat{v}_T$ y $J\hat{v}_T$, obtenemos
$$\dot{V}_T=0,\qquad \dot{\theta}_T=\frac{a_T}{V_T}.$$
De esta forma, la magnitud de la velocidad del objetivo se mantiene constante, mientras que su dirección varía según la aceleración perpendicular $a_T$.

Por último, para la velocidad relativa se tiene que

$$  
\frac{d\vec v}{dt}=\dot V\begin{pmatrix}\cos\theta\\ \sin\theta\end{pmatrix}+V\dot\theta\begin{pmatrix}-\sin\theta\\ \cos\theta\end{pmatrix}.  
$$

Como $\frac{d\vec v}{dt}=a_TJ\hat v_T-uJ\hat r$, al proyectar sobre las direcciones $\hat v$ y $J\hat v$, resulta

$$
\begin{align}  
\left\langle\frac{d\vec v}{dt},\hat v\right\rangle  
&=\langle a_TJ\hat v_T-uJ\hat r,\hat v\rangle\implies \dot V=a_T\sin(\theta-\theta_T)-u\sin(\theta-\lambda),\\ 
\left\langle\frac{d\vec v}{dt},J\hat v\right\rangle  
&=\langle a_TJ\hat v_T-uJ\hat r,J\hat v\rangle
\implies \dot\theta=\frac{a_T\cos(\theta-\theta_T)-u\cos(\theta-\lambda)}{V}.  
\end{align}  
$$

Con todo lo anterior, el sistema puede expresarse mediante las cinco variables de estado $z=(R,\lambda,V,\theta,\theta_T)$, con $V_T$ constante, obteniendo

$$
\begin{align}
\dot R&=V\cos(\theta-\lambda),\\ 
\dot\lambda&=\frac{V}{R}\sin(\theta-\lambda),\\  
\dot V&=a_T\sin(\theta-\theta_T)-u\sin(\theta-\lambda),\\
\dot\theta&=\frac{a_T\cos(\theta-\theta_T)-u\cos(\theta-\lambda)}{V},\\  
\dot\theta_T&=\frac{a_T}{V_T}.
\end{align}
$$

para $R>0$, $V>0$ y $V_T>0$. Las condiciones iniciales se obtienen a partir de las posiciones y velocidades relativas iniciales del sistema general.

## Caso Lineal

Para trabajar con un sistema lineal, consideraremos $a_{T}=0$. En dicho caso, del sistema general se deduce que

$$
\begin{align}\frac{d\vec{r}}{dt}= \vec{v},\qquad 
\frac{d\vec{v}}{dt}=-uJ\frac{\vec{r}}{\lVert \vec{r} \rVert },\qquad\frac{d\vec{v}_{T}}{dt}= 0,
\end{align}$$

en donde si expresamos la dinámica en función de las componentes de $\vec{r}=(r_{x},r_{y})$ y $\vec{v}=(v_{x},v_{y})$, tenemos que $\dot{r}_{x}=v_{x},\ \dot{r}_{y}=v_{y},$ y además

$$
\begin{align}\frac{d}{dt}\begin{pmatrix}v_{x} \\v_{y}\end{pmatrix} =-uJ \hat{r}=-u\begin{pmatrix}0 & -1 \\  1 & 0 \end{pmatrix}\begin{pmatrix}\cos\lambda \\  \sin\lambda\end{pmatrix}\end{align}=\begin{pmatrix}\sin\lambda \\  -\cos\lambda \end{pmatrix}u.
$$

Asumimos además que $\lambda$ es pequeño, de modo que $\cos(\lambda)\approx 1$ y $\sin(\lambda)\approx \lambda$, y luego podemos expresar la dinámica como

$$
\frac{d}{dt}\begin{pmatrix}r_{x } \\  r_{y} \\  v_{x} \\  v_{y}\end{pmatrix}=\begin{pmatrix}0&0&1& 0 \\  0&0&0&1 \\  0&0&0&0 \\ 0&0&0&0\end{pmatrix}\begin{pmatrix}r_x  \\  r_{y} \\  v_{x} \\  v_{y}\end{pmatrix}+\begin{pmatrix}0 \\  0 \\  \lambda \\  -1\end{pmatrix}u
$$

Adicionalmente, asumimos que la velocidad de acercamiento $V_c=-\dot R=-\langle \vec{v}, \hat{r} \rangle$ es positiva. Como $\lambda$ es pequeño, tenemos que

$$
V_c=-v_x\cos\lambda-v_y\sin\lambda\approx-v_x -\lambda v_{y}\approx-v_{x}>0,
$$

de modo que el proyectil siempre se acerca en la dirección $x$ al target, por lo que basta controlar la dinámica en la componente $y$. Definiendo $z=(r_{y},v_{y})$, el sistema linealizado anterior se puede reducir a 

$$
\frac{dz}{dt}=\underbrace{ \begin{pmatrix}0&1 \\  0&0 \end{pmatrix} }_{ A }z+\underbrace{ \begin{pmatrix}0 \\  -1\end{pmatrix} }_{ B }u,\qquad z(0)=\begin{pmatrix}r_{y,0} \\  v_{y,0}\end{pmatrix}.
$$

## Caso No Lineal

[Referencia](https://sci-hub.box/10.2514/6.2013-4785)

Para el caso no lineal, asumimos que el objetivo está fijo, es decir que $v_{T}=a_{T}=0$. ...


