# Simulação de Colisão Elástica

## Descrição do Projeto

- **Objetivo e Tipo de Projeto**:
  Criamos um jogo simulação bidimensional onde é possivel visualizar corpos, representados por bolas, se colidindo de forma elástica,
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
\Delta \vec{v}_1 \cdot  \left\|\vec{n}\right\|^2 = (-\frac{2m_2}{m_1 + m_2} (\vec{v}_1 - \vec{v}_2) \cdot \vec{n}) \cdot \vec{n}
$$

$$
\Delta \vec{v}_1 = -\frac{2m_2}{m_1 + m_2} \frac{(\vec{v}_1 - \vec{v}_2) \cdot \vec{n}}{\left\|\vec{n}\right\|^2} \cdot \vec{n}
$$

Desenvolvendo o $\Delta \vec{v}_1$, temos:

$$
\vec{v}_1' = \vec{v}_1 - \frac{2m_2}{m_1 + m_2} \frac{(\vec{v}_1 - \vec{v}_2) \cdot \vec{n}}{|\vec{n}|^2} \vec{n}
$$

Retornando para o vetor do centro de massa:

$$
\vec{v}_1' = \vec{v}_1 - \frac{2m_2}{m_1 + m_2} \frac{(\vec{v}_1 - \vec{v}_2) \cdot \vec{x}_1-\vec{x}_2}{|\vec{x}_1-\vec{x}_2|^2} \vec{x}_1-\vec{x}_2
$$

Observação: pode-se simplificar pela definição de projeção vetorial

## Cálculo de $\vec{v}_2'$

De maneira análoga ao processo exibido, obtém-se $\vec{v}_2'$ como:

$$
\vec{v}_2' = \vec{v}_2 - \frac{2m_1}{m_1 + m_2} \frac{(\vec{v}_1 - \vec{v}_2) \cdot \vec{x}_1-\vec{x}_2}{|\vec{x}_1-\vec{x}_2|^2} \vec{x}_1-\vec{x}_2
$$

## Implementação dessa trajetória no código

A mudança da velocidade pode ser implementada como:

```
v1_new = v1 - (2 * m2 / (m1 + m2)) * pygame.math.Vector2.project((v1 - v2), (x1 - x2))
```

```
v2_new = v2 - (2 * m1 / (m1 + m2)) * pygame.math.Vector2.project((v2 - v1), (x2 - x1))
```

## Alteração da trajetória

A alteração da trajetória segue uma relação simples de soma, onde as coordenadas
são alteradas a cada unidade de tempo medida. Ao decorrer do tempo, as velocidades
serão somadas com suas respectivas velocidades na componente analisadas

Dessa forma, temos a posição dada por:

$$
\gamma (t) = (x(t), y(t))
$$

Por sua vez, a velocidade é dada em componentes:

$$
\vec{v} (t) = (v_x (t), v_y (t))
$$

A atualização da posição pode ser expressa por:

$$
\gamma (t+dt) = (x(t+dt), y(t+dt))
$$

Onde:

$$
x(t+dt) = x(t) + v'_1x 
$$

$$
x(t+dt) = x(t) + v'_1y 
$$

## Implementação

A trajetória é atualizada com a seguinte linha de código

```
self.pos = self.pos + self.v
```
Onde
```
self: estrutura que armazena a posição
pos: posição atual
v: velocidade do objeto
```

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

## Referencias
- Utilizou-se o material das notas de aula do professor Esmerindo de Souza Bernardes para curso de Física Básica 1 (2024)
- Usou-se:
  ```
  https://www.pygame.org/docs/
  ```
  Para consulta e identificação das funções disponibilizadas pela biblioteca pygame
- Utilizou-se o site:
  ```
  https://docs.python.org/3
  ```
  Para consulta de outras funções disponibilizadas nas linguagens e biliotecas que utilizamos de suporte
