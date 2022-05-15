# SVM

Funcionamento da SVM para dados linearmente separáveis


![image](https://user-images.githubusercontent.com/79231882/168494980-77776dfc-d2fa-4b59-a3c1-1cd8cf9be51e.png)



O hiperplano é a melhor reta que separa dois grupos de dados


![image](https://user-images.githubusercontent.com/79231882/168495004-4cdff5ee-3538-4a67-8154-1e099280622d.png)


E o hiperplano é calculado a partir das margens

![image](https://user-images.githubusercontent.com/79231882/168495018-fd9d4009-7c50-4fe3-b09e-f95719edc9cd.png)



Como encontramos as margens?

Através dos support vectors, que são os pontos de dados de cada classe que estão mais próximos um do outro

![image](https://user-images.githubusercontent.com/79231882/168495027-b8f88835-60e8-4ead-a34c-60bc918ef91c.png)




Uma dose de matemática: distancia minima entre os vetores de suporte

![image](https://user-images.githubusercontent.com/79231882/168495039-23c15b9a-eb3f-4f4f-a524-5411303463bd.png)




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


![image](https://user-images.githubusercontent.com/79231882/168495056-9da541a3-e357-4eea-ae3d-7ced57c6e159.png)


em que:

w^T e a transposta da matriz w (matriz de pesos w)

x e uma outra matriz, que pode ser um vetor (um vetor de uma única coluna)

Qual deve ser a distancia entre os vetores de suporte de cada classe?

→ Deve ser a minima possível, ou seja, o algoritmo vai percorrer todos os pontos de dados, ele vai calculando as distancias entre estes pontos e os pontos com a menor distancia ele vai coloca-los como vetores de suporte, para encontrar as margens e encontrar o hiperplano



O algoritmo faz esse processo de busca e calculo das distancias utilizando a formula matemática abaixo

![image](https://user-images.githubusercontent.com/79231882/168495067-03b3760f-1cad-414b-87f8-9260702e8cda.png)



O somatório colocado na formula e obtido por meio de programação quadrática

A letra “C” colocada na formula representa um parâmetro que aplica penalidade, este valor pode ser definido na formula que calcula o modelo SVM. Esta penalidade permite obtermos a margem rígida e a margem suave

**Uma dose de matemática: otimização com programação quadrática e truque do Kernel**

Os vetores de suporte querem a menor distancia considerando as duas classes de dados so que não queremos estes vetores de suporte muito próximos uns aos outros, queremos na pratica maximizar esta distancia porque quanto maior esta margem mais fácil fica para fazer a classificação dos dados.

Quando o modelo for olhar para novos dados ele simplesmente vai pegar aqueles pontos e coloca-los junto aos dados que correspondem a classificação aprendida por ele mas caso esta margens estejam muito próximas, pode ser que ele fique em duvida e não classifique corretamente.


Por isso torna-se necessário aplicar a otimização, que e encontrar a maior distancia entre as margens:

![image](https://user-images.githubusercontent.com/79231882/168495071-210a7d5c-2174-4965-b9d9-73bd111bb033.png)



**max alpha** na pratica tenta maximizar a distancia entre as margens

**y** e o dado de saída

**x** e dado de entrada

![image](https://user-images.githubusercontent.com/79231882/168495081-d52f52e2-1055-45f0-9d20-9e7836605c5a.png)


![image](https://user-images.githubusercontent.com/79231882/168495089-9f495461-efad-4556-a7f6-41d3b993f240.png)



Tudo funcionaria perfeitamente se nosso problema apresentasse dados linearmente separáveis. Mas quando temos dados não linearmente separáveis e ai que entra o Inner Product.


![image](https://user-images.githubusercontent.com/79231882/168495097-0d13f3df-cc49-4c36-8799-36bc9cc7670f.png)

![image](https://user-images.githubusercontent.com/79231882/168495106-6af5cf70-a7ea-45d1-a373-790a89ce4ac3.png)


