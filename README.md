# Simulação de Colisão Elástica

## Descrição do Projeto

- **Objetivo e Tipo de Projeto**:
  Criamos uma interface onde o usuário pode fazer a simulação bidimensional onde é possivel visualizar corpos, representados por bolas, se colidindo de forma elástica,
  onde a energia cinética e o momento linear total do sistema se conservam e os corpos envolvidos não sofrem deformações permanentes 
  durante o impacto. Ou seja, após o encontro entre os corpos, a direção, o sentido e o módulo da velocidade é afetado, porém a massa não se altera.
  OBSERVAÇÃO: A parede, ou seja, as bordas da tela, não são consideradas para a colisão e servem apenas para redirecionar o vetor do corpo
  - Manual de Instruções para o Jogo:
    Após executar o código, será aberto uma janela pygame onde o usuário se deparará com um menu contendo 3 opções:

    <img src="images/Imagem do WhatsApp de 2024-12-02 à(s) 20.50.02_1f62514c.jpg" alt="Imagem do menu inicial descrito abaixo">

    - Iniciar:
    Inicia o jogo pressionando a tecla enter, caso o usuário não mexa em nenhuma configuração, o jogo iniciará com o número
    de corpos e suas respectivas massas e velocidades geradas aleatoriamente.
    <img src="images/Imagem do WhatsApp de 2024-12-02 à(s) 20.50.02_8e1bc18d.jpg" alt="Imagem do jogo rodando">
    - Configurar:
    Abre o menu de configurações pressionando a tecla C. navegando por ele através das teclas direcionais (arrow keys) é possivel:
    determinar o intervalo de massa mínima (1) e máxima (2) dos corpos no jogo; Determinar o intervalo de velocidade mínima (3) e máxima (4) dos corpos, e o número de corpos (5). 
    <img src="images/Imagem do WhatsApp de 2024-12-02 à(s) 20.50.02_905e278a.jpg" alt="Imagem do menu de configurações">
    Pressionando ESC, o usuário retorna ao menu inicial.
    - Sair:
    pressiona a tecla ESC para fechar o programa.
    - OBSERVAÇÃO:
    Conforme o usuário expande e contrai a janela do jogo, as paredes que fecham a área do jogo seguem o padrão e adaptam seu comprimento. 
    <img src="images/Imagem do WhatsApp de 2024-12-02 à(s) 20.50.00_3bb2d3ea.jpg" alt="Imagem do jogo com uma janela longa na horizontal e pequena na vertical">

## Conceitos de Física e Modelo Matemático

- **Conceito Principal:** Colisão Elástica

  A colisão elástica é um tipo de colisão onde, após o impacto, a energia cinética total e o momento linear total do sistema são conservados. Isso significa que a direção, o sentido e o módulo da velocidade dos corpos são alterados, mas a energia cinética e o momento linear não se perdem, assumindo que não há perdas para outras formas de energia, como calor ou deformação permanente.  

# Modelo Matemático

## Momento Linear

O momento linear de um corpo de massa constante $$m$$ é dado por

$$
\vec{p} = m \vec{v}
$$

Portanto a variação do momento linear desse corpo pode ser expressa como:

$$
 \Delta \vec{p} = \vec{p_{f}} - \vec{p}_i = m \vec{v_{f}} - m \vec{v_{i}} = m \Delta \vec{v}
$$

## **1. Segunda Lei de Newton**
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

- **Aplicabilidade:**

  O jogo simula como corpos de diferentes massas e velocidades reagem a colisões elásticas entre si, levando em consideração as leis da física mencionadas. No código implementado, as colisões são tratadas de forma a conservar tanto o momento linear quanto a energia cinética dos corpos, aplicando as fórmulas mencionadas para calcular as novas velocidades após cada colisão. Como forças externas como atrito, resistência do ar e gravidade não são consideradas, a simulação é uma idealização simplificada das colisões, sendo útil para a visualização de interações entre corpos em um sistema fechado e para a compreensão básica da física de colisões elásticas.

  ## Implementação

  - **Linguagens e Pacotes:**  
  O projeto foi implementado em Python utilizando os pacotes pygame, sys, random e math. Cada um desses pacotes oferece ferramentas específicas para lidar com visualização, computação científica, interações físicas,         aleatoriedade, permitindo que a simulação seja interativa e visualmente intuitiva.
  
## Como Usar
- **Instalação e Dependências:**  
  -Certifique-se de que o Python 3.6+ (ou outra versão de linguagem) está instalado.
  -Dependências incluem: Math, PyGame, Random.
  -Instale os pacotes necessários executando:
  
  ```
  pip install (coloque a qui o nome da biblioteca que lhe falta)
  ```

- **Exemplos de Uso:** 
  -Para rodar a simulação básica, utilize o código:
  simuladordecolisoes.py e execute o terminal.

- **Informações sobre o projeto:**
  Este projeto foi desenvolvido por:
  
    Matheus Araujo Pinheiro (14676810): matheusaraujopinh@usp.br
  
    Bruno Gonçalves (14762111): brunogb728@usp.br

    Luis Henrique Ponciano (15577760): luishenriqueponciano@usp.br

    Gabriel Araujo Lima (14571376): gabriel.araujolima@usp.br

Como parte do processo avaliativo da disciplina 7600105 - Física Básica I (2024) da USP-São Carlos ministrada pela(o) [Prof. Krissia de Zawadzki/Esmerindo de Sousa Bernardes]

### REFERENCIAS
- Utilizamos o Material didático disponibilizado no edisciplinas: dinamica-v4.pdf
- Utilizamos o Chatgpt para nos auxiliar na parte gráfica do código, como a função gerar_cor e draw (pela falta de familiaridade com essa parte do código)
- Utilizamos o site:
  ```
  https://www.pygame.org/docs/
  ```
  Para consultarmos e identificarmos as funções disponibilizadas pela biblioteca pygame
- Utilizamos o site:
  ```
  https://docs.python.org/3
  ```
  Para consultarmos outras funções disponibilizadas nas linguagens e biliotecas que utilizamos de suporte
