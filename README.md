# Modelo Matemático

## Momento Linear

O momento linear de um corpo de massa constante $$m$$ é dado por

$$
\vec{p} = m \vec{v}
$$

Portanto a variação do momento linear desse corpo pode ser expressa como:

$$
\Delta \vec{p} = \vec{p}_f - \vec{p}_i = m \vec{v}_f - m \vec{v}_i = m \Delta \vec{v}
$$
## 
A segunda lei de Newton diz que:

$$
F = \frac{\Delta p}{\Delta t},
$$

onde $F$ é a força, $p = m \cdot v$ é o momento linear, e $\Delta p$ é a variação do momento em um intervalo de tempo $\Delta t$. 

Para dois corpos interagindo, temos:

$$
F_1 = \frac{\Delta p_1}{\Delta t} \quad \text{e} \quad F_2 = \frac{\Delta p_2}{\Delta t}.
$$

---

## **2. Terceira Lei de Newton**
A terceira lei de Newton afirma que as forças trocadas entre dois corpos são **iguais em módulo e opostas em direção**:

$$
F_1 = -F_2.
$$

Substituímos na equação da força:

$$
\frac{\Delta p_1}{\Delta t} = -\frac{\Delta p_2}{\Delta t}.
$$

Multiplicando ambos os lados por $\Delta t$, obtemos:

$$
\Delta p_1 = -\Delta p_2.
$$

Ou seja:

$$
\Delta p_1 + \Delta p_2 = 0.
$$

---

## **3. Definição de Variação do Momento**
A variação do momento para cada corpo é:

$$
\Delta p_1 = p_{1f} - p_{1i}, \quad \Delta p_2 = p_{2f} - p_{2i}.
$$

Substituímos na equação anterior:

$$
(p_{1f} - p_{1i}) + (p_{2f} - p_{2i}) = 0.
$$

Reorganizando:

$$
p_{1i} + p_{2i} = p_{1f} + p_{2f}.
$$

---

## **4. Momento Linear em Função de Massa e Velocidade**
Sabemos que $p = m \cdot v$, então:

  1. **Conservação do Momento Linear**:

     O momento linear total do sistema (no eixo x e y) é conservado durante a colisão. A fórmula para a conservação do momento linear é dada por:

     ```
     m1 * v1i + m2 * v2i = m1 * v1f + m2 * v2f
     ```

     Onde:
     - `m1` e `m2` são as massas dos corpos 1 e 2, respectivamente.
     - `v1i` e `v2i` são as velocidades iniciais dos corpos 1 e 2, respectivamente.
     - `v1f` e `v2f` são as velocidades finais dos corpos 1 e 2, respectivamente.

  2. **Conservação da Energia Cinética**:

     A energia cinética total do sistema também é conservada durante a colisão elástica, e a fórmula para a conservação da energia cinética é:

     ```
     (1/2) * m1 * v1i^2 + (1/2) * m2 * v2i^2 = (1/2) * m1 * v1f^2 + (1/2) * m2 * v2f^2
     ```

     Onde:
     - `m1` e `m2` são as massas dos corpos.
     - `v1i` e `v2i` são as velocidades iniciais dos corpos.
     - `v1f` e `v2f` são as velocidades finais dos corpos.

  3. **Cálculo das Velocidades Finais**:

     Em uma colisão elástica entre dois corpos, as velocidades finais dos corpos podem ser calculadas usando as fórmulas específicas que derivam da conservação do momento linear e da energia cinética:

     ```
     v1f = [(m1 - m2) * v1i + 2 * m2 * v2i] / (m1 + m2)
     ```

     ```
     v2f = [(m2 - m1) * v2i + 2 * m1 * v1i] / (m1 + m2)
     ```

     Onde:
     - `m1` e `m2` são as massas dos corpos.
     - `v1i` e `v2i` são as velocidades iniciais dos corpos.
     - `v1f` e `v2f` são as velocidades finais dos corpos.

$$
\section*{Dedução da Fórmula para $\vec{v}_1'$ com $\vec{n} = \vec{x}_1 - \vec{x}_2$}

\subsection*{1. Conservação do Momento Linear}
\[
m_1 \vec{v}_1 + m_2 \vec{v}_2 = m_1 \vec{v}_1' + m_2 \vec{v}_2'.
\]
Reorganizando:
\[
m_1 (\vec{v}_1 - \vec{v}_1') = m_2 (\vec{v}_2' - \vec{v}_2). \tag{1}
\]

\subsection*{2. Conservação da Energia Cinética}
\[
\frac{1}{2} m_1 |\vec{v}_1|^2 + \frac{1}{2} m_2 |\vec{v}_2|^2 = \frac{1}{2} m_1 |\vec{v}_1'|^2 + \frac{1}{2} m_2 |\vec{v}_2'|^2.
\]
Cancelando o fator $\frac{1}{2}$:
\[
m_1 (|\vec{v}_1|^2 - |\vec{v}_1'|^2) = m_2 (|\vec{v}_2'|^2 - |\vec{v}_2|^2). \tag{2}
\]

\subsection*{3. Vetor Direção da Colisão}
Definimos $\vec{n} = \vec{x}_1 - \vec{x}_2$ como o vetor de referência. A colisão altera apenas as componentes ao longo de $\vec{n}$. Assim, as velocidades após a colisão são:
\[
\vec{v}_1' = \vec{v}_1 + \Delta \vec{v}_1, \quad \vec{v}_2' = \vec{v}_2 + \Delta \vec{v}_2.
\]

\subsection*{4. Relacionando as Alterações}
Usando a Eq. (1), temos:
\[
m_1 \Delta \vec{v}_1 + m_2 \Delta \vec{v}_2 = 0. \tag{3}
\]
Logo:
\[
\Delta \vec{v}_1 = -\frac{m_2}{m_1} \Delta \vec{v}_2. \tag{4}
\]

\subsection*{5. Velocidades Relativas}
A velocidade relativa ao longo de $\vec{n}$ inverte após a colisão:
\[
(\vec{v}_1' - \vec{v}_2') \cdot \vec{n} = -(\vec{v}_1 - \vec{v}_2) \cdot \vec{n}. \tag{5}
\]
Substituímos $\vec{v}_1'$ e $\vec{v}_2'$:
\[
((\vec{v}_1 + \Delta \vec{v}_1) - (\vec{v}_2 + \Delta \vec{v}_2)) \cdot \vec{n} = -(\vec{v}_1 - \vec{v}_2) \cdot \vec{n}.
\]
Reorganizando:
\[
(\Delta \vec{v}_1 - \Delta \vec{v}_2) \cdot \vec{n} = -2 (\vec{v}_1 - \vec{v}_2) \cdot \vec{n}. \tag{6}
\]

\subsection*{6. Substituindo $\Delta \vec{v}_2$}
Usamos a Eq. (4):
\[
\Delta \vec{v}_1 \cdot \vec{n} - \left(-\frac{m_1}{m_2} \Delta \vec{v}_1\right) \cdot \vec{n} = -2 (\vec{v}_1 - \vec{v}_2) \cdot \vec{n}.
\]
Simplificando:
\[
\Delta \vec{v}_1 \cdot \vec{n} \left(1 + \frac{m_1}{m_2}\right) = -2 (\vec{v}_1 - \vec{v}_2) \cdot \vec{n}.
\]
Logo:
\[
\Delta \vec{v}_1 \cdot \vec{n} = -\frac{2m_2}{m_1 + m_2} (\vec{v}_1 - \vec{v}_2) \cdot \vec{n}. \tag{7}
\]

\subsection*{7. Projeção Vetorial para $\Delta \vec{v}_1$}
A projeção vetorial ao longo de $\vec{n}$ é:
\[
\Delta \vec{v}_1 = -\frac{2m_2}{m_1 + m_2} \frac{\text{proj}_{\vec{n}} (\vec{v}_1 - \vec{v}_2)}{|\vec{n}|^2}.
\]

Substituímos em $\vec{v}_1'$:
\[
\vec{v}_1' = \vec{v}_1 + \Delta \vec{v}_1.
\]

\subsection*{8. Fórmula Final}
\[
\vec{v}_1' = \vec{v}_1 - \frac{2m_2}{m_1 + m_2} \frac{(\vec{v}_1 - \vec{v}_2) \cdot \vec{n}}{|\vec{n}|^2} \vec{n}.
\]

$$
