![image](https://user-images.githubusercontent.com/79231882/168495685-1269a2b0-ceff-4977-8388-f5a3f6a7cdd5.png)

![image](https://user-images.githubusercontent.com/79231882/168495694-377714c6-2f8f-41c6-b371-036430388548.png)


![image](https://user-images.githubusercontent.com/79231882/168495705-d29069ce-67fa-468d-aed6-1573db74a8dc.png)

Considerando os dois modelos de classificação acima, qual voce escolheria?

Vamos a algumas considerações:

![image](https://user-images.githubusercontent.com/79231882/168495732-63ec33b8-3b90-4edd-beb2-8b22ed0b0a74.png)

O **modelo (a) e o melhor** porque o hiperplano dele foi capaz de maximizar melhor a distancia entre os vetores de suporte

O modelo (b) apresenta uma probabilidade muito maior de classificar de maneira incorreta diante de um novo conjunto de dados

Uma observação quanto a maior proximidade do hiperplano da bolinha branca no modelo (a):

Ele foi feito para gerar duvida quanto ao conceito de separação entre as classes e traz reflexões sobre os conceitos de margens rígidas e flexíveis

![image](https://user-images.githubusercontent.com/79231882/168495794-766e2300-38ea-45e5-ab52-0fd0c3de4004.png)


Observando o gráfico da esquerda vemos que os vetores de suporte conseguem fazer a separação entre as classes de forma bastante clara, aparentemente e um bom hiperplano

Imaginemos que recebamos um novo conjunto de dados em ques testes não caiam dentro de nenhumas das classes determinadas pois são pontos com características de ambas as classes ou ainda podemos ter pontos de dados que são extremos (outliers).

O que aconteceria com este modelo?

![image](https://user-images.githubusercontent.com/79231882/168495811-80757afe-c87d-40ef-b763-3438c3d3939d.png)

Muito provavelmente estes pontos cairiam no meio (gráfico da direita) porque o modelo SVM não foi capaz de classificar, ele acaba colocando dentro da margem (o correto seria fora) porque estes pontos não caem dentro de uma característica ou outra.

Isso acontece quando temos dados quase linearmente separáveis.

Para estes casos não vale a pena aplicar o truque do Kernel, pois eles estão quase classificados, provavelmente ele tem algum detalhe bem especifico (outlier, por exemplo) que o faz não ser classificado. Para estes casos não poderíamos utilizar o modelo SVM de margens rígidas.

A margem rígida so pode ser usada quando os dados são totalmente linearmente separáveis. E preciso garantir que os dados não possuam outliers.

Na grande maioria dos casos os dados são quase linearmente separáveis. Para estes casos a solução e a margem flexível.

![image](https://user-images.githubusercontent.com/79231882/168495824-b503f7f3-1b46-46da-aa19-a1e25b639cc9.png)


Considerando o mundo real em que a imensa maioria dos dados são quase linearmente separáveis a margem rígida não e a melhor solução.

![image](https://user-images.githubusercontent.com/79231882/168495835-eae2dd59-9e48-4348-b817-6063473e9951.png)

A variável possibilidade adicionar mais um parâmetro para que possamos trabalhar com margens flexíveis.

![image](https://user-images.githubusercontent.com/79231882/168495847-4693c3f2-273c-44e1-8f0b-fd918ea78096.png)

Na pratica utilizamos sempre modelos SVM com margem flexível, pois teremos um modelo bem menos restritivo.

![image](https://user-images.githubusercontent.com/79231882/168495868-82f13540-2d2c-4249-a0f2-9ce02c5717a8.png)


Nao tem importância deixarmos alguns pontos classificados incorretamente desde que a grande maioria esteja classificada corretamente.

**Parâmetro de regularização C**

![image](https://user-images.githubusercontent.com/79231882/168495884-3af7a0cb-5040-40b4-bd4f-27dcec6bd9b1.png)


O parâmetro C, do lado esquerdo da somatória na formula acima, permite determinar ate aonde podemos ir entre margem rígida e flexível.

Ele vai tentando ajustar dentro da melhor maneira possível a margem ideal.

![image](https://user-images.githubusercontent.com/79231882/168495898-0db08351-3848-40de-9aa9-c9d796cbb48c.png)


No final das contas queremos determinar a melhor margem.

Se ao final do calculo do modelo ficar determinado que o modelo encontrou uma margem muito rígida, precisaremos ajustar o hiperparametro C para tentar reduzir esta rigidez.

Se o modelo estiver com a margem muito flexível, sito também poderá gerar problemas porque ele poderá classificar qualquer coisa, perdendo a capacidade de generalização.

Deve-se buscar o meio termo, que e o equilíbrio.



