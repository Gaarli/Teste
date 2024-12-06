##
   Onde:
     - `m1` e `m2` são as massas dos corpos.
     - `v1i` e `v2i` são as velocidades iniciais dos corpos.
     - `v1f` e `v2f` são as velocidades finais dos corpos.

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

Para analisar a colisão, será utilizado um vetor auxiliar $\vec{n}$ onde iremos decompor o
momento linear de cada corpo nesse vetor e o seu respectivo perpendicular. O vetor $\vec{n}$
conecta os dois centros de massa dos projéteis. Dessa forma,

$$
\vec{n} = \vec{x}_1 - \vec{x}_2
$$

Por sua vez, a variação das velocidades pode ser escrita como:

$$
\vec{v}'_1 = \vec{v}_1 + \Delta v_1, \quad \vec{v}_2' = \vec{v}_2 + \Delta \vec{v}_2
$$

## Relacionar as mudanças das velocidades

Reescrevendo a equação do momento linear conservado pela variação das velocidades, temos:

$$
m_1 \Delta \vec{v}_1 + m_2 \Delta \vec{v}_2 = 0
$$

Assim,

$$
\Delta \vec{v}_1 = -\frac{m_2}{m_1} \Delta \vec{v}_2
$$

## Análise da velocidade relativa

Pela conservação da energia cinética na colisão, tem-se que o vetor da velocidade
relativa $\vec{v}_r = \vec{v}_1 - \vec{v}_2$ apenas inverte seu sinal após a colisão:

$$
(\vec{v}_1' - \vec{v}_2') = -(\vec{v}_1 - \vec{v}_2)
$$

Como estamos analisando na componente $\vec{n}$ que conecta os centros de massa:

$$
(\vec{v}_1' - \vec{v}_2') \cdot \vec{n} = -(\vec{v}_1 - \vec{v}_2) \cdot \vec{n}
$$

Observa-se que 

$$
\vec{v}_1' = \vec{v}_1 + \Delta \vec{v}_1, \quad \vec{v}_2' = \vec{v}_2 + \Delta \vec{v}_2
$$

Substituindo, temos

$$
((\vec{v}_1 + \Delta \vec{v}_1) - (\vec{v}_2 + \Delta \vec{v}_2)) \cdot \vec{n} = -(\vec{v}_1 - \vec{v}_2) \cdot \vec{n}.
$$

$$
\Delta \vec{v}_1 \cdot \vec{n} \left(1 + \frac{m_1}{m_2}\right) = -2 (\vec{v}_1 - \vec{v}_2) \cdot \vec{n}
$$

## Resolver $\Delta \vec{v}_1$

Sabendo-se que

$$
\vec{v}_1' = \vec{v}_1 + \Delta \vec{v}_1
$$

Temos 

$$
\Delta \vec{v}_2 = -\frac{m_2}{m_1} \Delta \vec{v}_1
$$

Substituindo na equação encontrada pela velocidade relativa

$$
\Delta \vec{v}_1 \cdot \vec{n} - \left( -\frac{m_1}{m_2} \Delta \vec{v}_1 \right) \cdot \vec{n} = -2 (\vec{v}_1 - \vec{v}_2) \cdot \vec{n}.
$$

Simplificando,

$$
\Delta \vec{v}_1 \cdot \vec{n} \left( 1 + \frac{m_1}{m_2} \right) = -2 (\vec{v}_1 - \vec{v}_2) \cdot \vec{n}.
$$

Assim, 

$$
\Delta \vec{v}_1 \cdot \vec{n} = -\frac{2m_2}{m_1 + m_2} (\vec{v}_1 - \vec{v}_2) \cdot \vec{n}
$$

Pela igualdade, fazemos produto escalar novamente para podermos isolar $\vec{v}_1$

$$
(\Delta \vec{v}_1 \cdot \vec{n}) \cdot \vec{n} = (-\frac{2m_2}{m_1 + m_2} (\vec{v}_1 - \vec{v}_2) \cdot \vec{n}) \cdot \vec{n}
$$

$$
\Delta \vec{v}_1 \cdot || \vec{n} || = (-\frac{2m_2}{m_1 + m_2} (\vec{v}_1 - \vec{v}_2) \cdot \vec{n}) \cdot \vec{n}
$$


$$  
m_1 (\vec{v}_1 - \vec{v}_1') = m_2 (\vec{v}_2' - \vec{v}_2)
$$

$$
m_1 (|\vec{v}_1|^2 - |\vec{v}_1'|^2) = m_2 (|\vec{v}_2'|^2 - |\vec{v}_2|^2)
$$

$$
(\vec{v}_1' - \vec{v}_2') \cdot \vec{n} = -(\vec{v}_1 - \vec{v}_2) \cdot \vec{n}
$$

$$
\Delta \vec{v}_1 = -\frac{2m_2}{m_1 + m_2} \frac{(\vec{v}_1 - \vec{v}_2) \cdot \vec{n}}{|\vec{n}|^2} \vec{n}
$$

$$
\vec{v}_1' = \vec{v}_1 - \frac{2m_2}{m_1 + m_2} \frac{(\vec{v}_1 - \vec{v}_2) \cdot \vec{n}}{|\vec{n}|^2} \vec{n}
$$
