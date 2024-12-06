# Modelo Matemático

## Ideia inicial

Utiliza-se a conservação da conservação de momento linear e da energia cinética para encontrar encontrar a trajetória dos corpos após a colisão
## Momento Linear

O momento linear de um corpo de massa constante $$m$$ é dado por

$$
\vec{p} = m \vec{v}
$$

Portanto a variação do momento linear desse corpo pode ser expressa como:

$$
\Delta \vec{p} = \vec{p}_f - \vec{p}_i = m \vec{v}_f - m \vec{v}_i = m \Delta \vec{v}
$$
## Conservação do momento linear

Pela conservação do momento linear para a colisão elástica, temos que:

$$
m_1 \vec{v}_1 + m_2 \vec{v}_2 = m_1 \vec{v}_1' + m_2 \vec{v}_2'
$$

## Definição da linha de colisão e das variações das velocidades

Para analisar a colisão, será utilizado um vetor auxiliar $$ \vec{n} $$ onde iremos decompor o
momento linear de cada corpo nesse vetor e o seu respectivo perpendicular. O vetor $$ \vec{n} $$
conecta os dois centros de massa dos projéteis. Dessa forma,

$$
\vec{n} = \vec{x}_1 - \vec{x}_2
$$

Por sua vez, a variação das velocidades pode ser escrita como:

$$
v_1' = v_1 + \Delta v_1, \quad v_2' = v_2 + \Delta v_2
$$

##
   Onde:
     - `m1` e `m2` são as massas dos corpos.
     - `v1i` e `v2i` são as velocidades iniciais dos corpos.
     - `v1f` e `v2f` são as velocidades finais dos corpos.

$$ 
m_1 (\vec{v}_1 - \vec{v}_1') = m_2 (\vec{v}_2' - \vec{v}_2)
$$

$$
m_1 (|\vec{v}_1|^2 - |\vec{v}_1'|^2) = m_2 (|\vec{v}_2'|^2 - |\vec{v}_2|^2)
$$

$$
\vec{v}_1' = \vec{v}_1 + \Delta \vec{v}_1, \quad \vec{v}_2' = \vec{v}_2 + \Delta \vec{v}_2
$$

$$
(\vec{v}_1' - \vec{v}_2') \cdot \vec{n} = -(\vec{v}_1 - \vec{v}_2) \cdot \vec{n}
$$

$$
(\Delta \vec{v}_1 - \Delta \vec{v}_2) \cdot \vec{n} = -2 (\vec{v}_1 - \vec{v}_2) \cdot \vec{n}
$$

$$
m_1 \Delta \vec{v}_1 + m_2 \Delta \vec{v}_2 = 0
$$

$$
\Delta \vec{v}_1 = -\frac{m_2}{m_1} \Delta \vec{v}_2
$$

$$
\Delta \vec{v}_1 \cdot \vec{n} \left(1 + \frac{m_1}{m_2}\right) = -2 (\vec{v}_1 - \vec{v}_2) \cdot \vec{n}
$$

$$
\Delta \vec{v}_1 = -\frac{2m_2}{m_1 + m_2} \frac{(\vec{v}_1 - \vec{v}_2) \cdot \vec{n}}{|\vec{n}|^2} \vec{n}
$$

$$
\vec{v}_1' = \vec{v}_1 - \frac{2m_2}{m_1 + m_2} \frac{(\vec{v}_1 - \vec{v}_2) \cdot \vec{n}}{|\vec{n}|^2} \vec{n}
$$
