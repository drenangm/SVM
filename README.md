# SVM
Funcionamento da SVM para dados linearmente separáveis

https://www.notion.so/drgm/Funcionamento-da-SVM-para-dados-linearmente-separ-veis-5a3da4d8443148f9a470c2917d12c9c5#cec844e33d8046559638700fb763da97

O hiperplano é a melhor reta que separa dois grupos de dados

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fd1ef031-21a6-4cd8-9ad3-b16b57abb58a/Untitled.png)

E o hiperplano é calculado a partir das margens

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2c2e4beb-8c7e-4433-ad12-c8d5ff7f4836/Untitled.png)

Como encontramos as margens?

Através dos support vectors, que são os pontos de dados de cada classe que estão mais próximos um do outro

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d63dddd8-ae36-42c6-a8ac-8770d388713f/Untitled.png)

Uma dose de matemática: distancia minima entre os vetores de suporte

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ab24c799-0951-4dc8-a2d2-712a2929546c/Untitled.png)

Compreendendo o algoritmo:

→ X1 e X2 representam os dois dados de entrada, por exemplo, eles podem representar resultados de exames medicos, um exame de sangue (X1) e um exame de eletroencefalograma (X2)

→ Queremos desenvolver um modelo de classificação em que o modelo consiga responder se uma pessoa ira desenvolver uma doença ou não 

→ Observamos no gráfico um hiperplano no meio e as duas margens

→ Vemos que no grupo de bolinhas brancas existem duas bolinhas na margem, o que e totalmente possível, podemos ter dois vetores para uma classe e apenas um para outra

→ na linha que representa o hiperplano vemos w * x - b = 0, em que:

- w: e o peso, coeficiente, o que o modelo realmente aprende
- x: e o conjunto de dados
- b: e o bias, outro coeficiente

→ no hiperplano esta equação tem que ser igual a 0

Na margem superior esta equação e igual a 1

Na margem inferior esta equação e igual a 0

Temos ainda o b / ||w|| na parte inferior da linha do hiperplano e 2 / ||w|| na parte superior


![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2080d9c8-e1df-44be-990e-529f94581258/Untitled.png)

em que:

w^T e a transposta da matriz w (matriz de pesos w)

x e uma outra matriz, que pode ser um vetor (um vetor de uma única coluna)

Qual deve ser a distancia entre os vetores de suporte de cada classe?

→ Deve ser a minima possível, ou seja, o algoritmo vai percorrer todos os pontos de dados, ele vai calculando as distancias entre estes pontos e os pontos com a menor distancia ele vai coloca-los como vetores de suporte, para encontrar as margens e encontrar o hiperplano

O algoritmo faz esse processo de busca e calculo das distancias utilizando a formula matemática abaixo

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f76b16bb-45f6-4351-8be9-8d774353cf94/Untitled.png)

O somatório colocado na formula e obtido por meio de programação quadrática

A letra “C” colocada na formula representa um parâmetro que aplica penalidade, este valor pode ser definido na formula que calcula o modelo SVM. Esta penalidade permite obtermos a margem rígida e a margem suave

**Uma dose de matemática: otimização com programação quadrática e truque do Kernel**

Os vetores de suporte querem a menor distancia considerando as duas classes de dados so que não queremos estes vetores de suporte muito próximos uns aos outros, queremos na pratica maximizar esta distancia porque quanto maior esta margem mais fácil fica para fazer a classificação dos dados.

Quando o modelo for olhar para novos dados ele simplesmente vai pegar aqueles pontos e coloca-los junto aos dados que correspondem a classificação aprendida por ele mas caso esta margens estejam muito próximas, pode ser que ele fique em duvida e não classifique corretamente.

Por isso torna-se necessário aplicar a otimização, que e encontrar a maior distancia entre as margens:

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8564dd8d-ee46-4168-a6e2-9b78cd6257b8/Untitled.png)

**max alpha** na pratica tenta maximizar a distancia entre as margens

**y** e o dado de saída

**x** e dado de entrada

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e32566fe-3c33-4e04-8c65-1ce9b2e6b9c0/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2dea3396-58ce-49b0-a503-faebc49de39f/Untitled.png)

Tudo funcionaria perfeitamente se nosso problema apresentasse dados linearmente separáveis. Mas quando temos dados não linearmente separáveis e ai que entra o Inner Product.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/42a6e418-25ee-4cd6-a215-1bfb288029a1/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0627c7c6-0d99-4780-ab5e-2b75403dc36a/Untitled.png)
