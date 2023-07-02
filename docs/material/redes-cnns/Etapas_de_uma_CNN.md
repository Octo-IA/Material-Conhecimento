# Etapas de uma CNN

Uma rede neural convolucional (CNN) possui diversas camadas e nesse capítulo vamos detalhar cada um deles. No capítulo seguinte você irá ver as operações matemáticas que ocorrem em cada uma destas etapas. 

Como exemplo, aqui vamos descrever as camadas de uma CNN chamada de **Lenet5** que contêm as seguintes camadas: **camada convolucional, camada pooling, camada convolucional 2, camada pooling 2 e 3 camadas totalmente conectadas.** A figura 2.1 mostra a arquitetura da LeNet5.

<p align='center'> 
<img src='https://github.com/Octo-IA/Material-Conhecimento/blob/main/docs/material/redes-cnns/imagens/etapas_cnns/arquitetura_LeNet5.jpg?raw=true'>
</p>

IFigura 2.1: Arquitetura da LeNet5

A Figura 2.2 mostra a análise das dimensões presentes, bem como parâmetros utilizados na convolução e pooling da LeNet5. Note que também há as funções de ativação utilizadas na saída de cada uma das suas respectivas camadas. Logo em seguida há uma descrição dos volumes de saída em cada uma das camadas. 

<p align='center'>
<img src='https://github.com/Octo-IA/Material-Conhecimento/blob/main/docs/material/redes-cnns/imagens/etapas_cnns/leNet_Structure.png?raw=true'>
</p>

Figura 2.2: Parâmetros da arquitetura LeNet5

- INPUT [32x32x1] manterá os valores brutos de pixel da imagem, neste caso uma imagem de largura 32, altura 32 e com 1 canal de cor.
- A camada CONV1 calculará a saída dos neurônios que estão conectados a regiões locais na entrada, cada um calculando um produto escalar entre seus pesos e uma pequena região à qual estão conectados no volume de entrada. Isso pode resultar em um volume como [28x28x6] se decidirmos usar 6 filtros.
- A camada POOL1 aplicará uma função de ativação elemento a elemento na saída da convolução, e isso deixa o tamanho do volume inalterado ([14x14x6]).
- A segunda camada CONV2 resultará em um volume como [10x10x16] se decidirmos usar 16 filtros.
- A camada POOL2 executará uma operação de redução da resolução ao longo das dimensões espaciais (largura, altura), resultando em um volume como [5x5x16].
- A terceira camada CONV3 terá como foco fazer uma operação que chamamos de **Flatten**, que consistem em transformar um volume em uma camada totalmente conectada. Nessa etapa isso resultará em um volume como [1x1x120].
- A primeira camada totalmente conectada (FC) será responsável por mapear 84 features em tons de cinza.
- A camada de saída é totalmente conectada (FC) que contêm 10 neurônios que irão classificar 10 objetos através da função de ativação softmax.

Conforme pode-se analisar, além dos volumes de saída em cada camada de uma CNN, há a necessidade em se descrever os seguintes parâmetros do **tamanho do kernel, stride e pading,** para que assim se possa avaliar o tamanho dos volumes de entrada e saída em cada uma das respectivas camadas. Fique tranquilo que nesse livro abordaremos cada uma dessas etapas e você também aprenderá a calculas as dimensões de cada uma dessas camadas. 

Outro ponto importante que pode-se analisar na Figura 2.2 é a quantidade de parâmetros necessários em cada uma das camadas. Por exemplo na camada CONV 1 precisa somente de 156 parâmetros, enquanto a camda totalmente conectada precisa de 10.164 parâmetros. Isso demonstra a alta capacidade das CNNs processarem a análise de imagens requerindo um menor poder computacional, bem como menor tempo para disponibilização da resposta. A seguir, vamos ver os detalhes de cada uma das camadas de uma CNN. 

## **A camada de Convolução**

Na camada de convolução, um conjunto de filtros ou kernels é aplicado a uma janela deslizante (também chamada de "patch") que percorre toda a entrada da camada. Cada filtro é uma matriz de pesos que é multiplicada pelos valores na janela para produzir uma única saída. O processo de aplicar um filtro a uma janela é conhecido como operação de convolução.

### *A camada Relu*

A camada Relu é uma camada usada em redes neurais convolucionais (CNNs) que é usada para introduzir não-linearidade nas saídas das camadas convolucionais. 

A camada Relu é importante porque as camadas convolucionais produzem saídas lineares, o que significa que a rede neural convolucional como um todo seria uma função linear se não houvesse camadas não-lineares como a camada Relu. A introdução de não-linearidade nas saídas das camadas convolucionais permite que a rede neural convolucional modele relacionamentos mais complexos entre as entradas e as saídas.

### *A camada Pooling*

A camada de pooling é usada para reduzir o tamanho dos volumes de entrada. Essa camada é geralmente usada após as camadas convolucionais e antes das camadas totalmente conectadas.

A camada de pooling funciona aplicando uma função de agregação em regiões locais do volume de entrada. A função de agregação mais comum é o máximo, o que significa que o valor máximo em cada região local é mantido e o restante é descartado. Outras funções de agregação incluem a média e a soma.

A camada de pooling é importante porque ela ajuda a reduzir o tamanho dos volumes de entrada, o que pode reduzir o tempo de treinamento da CNN e tornar a rede mais eficiente em termos de memória. A camada de pooling também pode ajudar a tornar a rede mais robusta à variação nas posições das características na entrada.

### *A camada Flatten*

A camada Flatten é uma camada usada em redes neurais convolucionais (CNNs) para converter uma matriz multidimensional em um vetor unidimensional. Essa camada é geralmente usada após as camadas convolucionais e de pooling e antes das camadas totalmente conectadas.

A camada Flatten é importante porque as camadas totalmente conectadas requerem um vetor unidimensional como entrada. As camadas convolucionais e de pooling produzem saídas multidimensionais, então a camada Flatten é usada para "achatar" essas saídas em um vetor unidimensional que pode ser usado como entrada para as camadas totalmente conectadas.

### *Camada totalmente conectada (FC)*

Enquanto as camadas de convolução são responsáveis por extrair características das entradas, as camadas totalmente conectadas são responsáveis por produzir uma saída final a partir dessas características. A camada totalmente conectada geralmente é colocada no final da rede e é composta por neurônios conectados a todas as saídas da camada anterior.

FORWARD E BACKWARD em Redes Neurais

[Função de Ativação](https://www.notion.so/Fun-o-de-Ativa-o-b9f2b56735c34c00bee2e3c1e7e351fc?pvs=21)