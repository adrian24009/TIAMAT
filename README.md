# TIAMAT

Autores: Gabriel Viégas Ribeiro e Adrian Lincoln Paz

Modelos epidemiológicos, cujo objetivo é capturar o comportamento de uma epidemia a partir
de dados reais, mostraram ser de grande utilidade para a elaboração de estratégias de prevenção
na saúde pública, em especial na pandemia de COVID-19. Um dos modelos separa a população em
compartimentos de Suscetíveis, Infectados, Recuperados e Falecidos (SIRD, da sigla em inglês). De forma simplificada, podemos dizer que Sucetíveis corresponde a pessoas que tem a possibilidade de serem infectadas, Infectados são as pessoas que estão ativamente espalhando a doença, Recuperados são as pessoas que se recuperaram ou deixaram de ser infecciosas, e Falecidos é o cojunto que representa as pessoas que morreram. Esses compartimentos seguem o seguinte modelo de equações diferenciais:

$$
\frac{dS}{dt} = -\beta S I
$$

$$
\frac{dI}{dt} = \beta S I - \gamma I - \alpha I
$$

$$
\frac{dR}{dt} = \gamma I
$$

$$
\frac{dD}{dt} = \alpha I 
$$

Nessas equações diferenciais acopladas, $\alpha$, $\beta$ e $\gamma$ representam as taxas de morte, transmissão de infecção e recuperados. Assim, o nosso trabalho tem como objetivo minimizar a função custo entre número de casos de pessoas infectadas ($$I_{real}(t)$$) e o número calculado pelo modelo SIRD ($$I_{calculado}(t)$$) a partir de um número ótimo da taxa de infecção ($$\beta$$). Para isso, utilizamos os dados do site [[Coronavírus Brasil](https://covid.saude.gov.br/)], onde encontramos o número de mortos, infectados e recuperados em 2020. A função de custo  $C(\beta)$ pode ser definida como abaixo:

$$
C(\beta) = \sum_{t=0}^{n}[I_{real}(t) - I_{calculado}(t)]^2
$$

Em que "n" é o número de dias descritos pelos dados. [[Prediction of Epidemic Peak and Infected Cases for COVID-19 Disease in Malaysia, 2020](https://pmc.ncbi.nlm.nih.gov/articles/PMC7312594/pdf/ijerph-17-04076.pdf)]

Primeiramente, vamos apresentar o tratamento de dados e modelagem com o modelo SIRD (adaptado das referências [[Mastering the SEIR Model: A Comprehensive Guide with Python Code and Real-World Applications Examples](https://medium.com/pythoneers/mastering-the-seir-model-a-comprehensive-guide-with-python-code-and-real-world-applications-da7584a4fb23)] e [[Estimation of the epidemiological model with a system of
differential equations (SIRD) using the Runge-Kutta method in
Ira](https://ijnaa.semnan.ac.ir/article_6509.html)]. Em seguida, vamos otimizar o valor de $\beta$ a partir do algoritmo genético. Por último, analisaremos se o valor de beta produziu resultados coerentes com o que foi observado na literatura. 

O trabalho foi realizado em conjunto em todas as partes, ou seja, o trabalho foi igualmente distribuído entre os integrantes do grupo. 
