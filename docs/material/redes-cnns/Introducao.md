# Introdução

Em visão computacional, o termo "o que o computador enxerga" refere-se à capacidade dos computadores de processar e interpretar imagens e vídeos de maneira semelhante à forma como os seres humanos percebem visualmente o mundo ao seu redor. É um campo da inteligência artificial que se concentra no desenvolvimento de algoritmos e técnicas para que os computadores possam adquirir, analisar e compreender informações visuais. A imagem abaixo demonstra o modo como uma imagem é processada pelo computador.

<p align='center'> 
<img src='https://github.com/Octo-IA/Material-Conhecimento/blob/main/docs/material/redes-cnns/imagens/introducao/imagem_processada_computador.png?raw=true'>
</p>

Durante décadas pesquisadores tem estudado algoritmos capazes de identificar e analisar imagens com boa precisão. Dentre as diversas alternativas pesquisadas, surgiram as redes neurais artificiais (RNAs) que são uma classe de algoritmos de aprendizado de máquina inspirados na estrutura e funcionamento do cérebro humano. Elas são compostas por um conjunto de neurônios artificiais interligados que podem ser treinados para realizar tarefas específicas, como classificação ou previsão.

<p align='center'>
<img src='https://github.com/Octo-IA/Material-Conhecimento/blob/main/docs/material/redes-cnns/imagens/introducao/rnas.png?raw=true'>
</p>

Já as redes neurais convolucionais (CNNs) são um tipo específico de RNA que é especialmente adequado para o processamento de imagens e reconhecimento de padrões. A principal diferença entre as RNAs e as CNNs é a forma como elas processam as informações.

<p align='center'>
<img src='https://github.com/Octo-IA/Material-Conhecimento/blob/main/docs/material/redes-cnns/imagens/introducao/cnns.png?raw=true'>
</p>

Enquanto as RNAs processam as informações em camadas totalmente conectadas, as CNNs utilizam camadas convolucionais que extraem características específicas das imagens, como bordas, texturas e formas. Essas características são então combinadas em camadas subsequentes para gerar uma representação da imagem que pode ser usada para classificação ou detecção de objetos.

---

## **O que são as CNN's**

A Rede Neural Convolucional (CNN) é um tipo de rede neural de aprendizado profundo comumente usada em tarefas de reconhecimento de imagens e vídeos. O nome "convolucional" vem da operação matemática de convolução, que é usada para calcular a saída de cada neurônio na rede. As CNNs são inspiradas na estrutura e função do córtex visual humano, responsável pelo processamento de informações visuais.

As CNNs consistem em várias camadas, cada uma com uma função específica. A primeira camada é a camada de entrada, onde a imagem é alimentada na rede. As camadas seguintes são as camadas convolucionais, onde as convoluções são realizadas. As convoluções ajudam a extrair características da imagem de entrada, como bordas, cantos e formas. As camadas convolucionais são seguidas pelas camadas de pooling, que reduzem o tamanho dos mapas de características e ajudam a tornar a rede mais eficiente computacionalmente.

Após as camadas convolucionais e de pooling, seguem-se as camadas totalmente conectadas. Essas camadas são semelhantes às de uma rede neural regular e são usadas para realizar a tarefa de classificação. A saída das camadas totalmente conectadas é a classificação final da imagem de entrada.

As CNNs foram usadas em uma variedade de aplicações, como classificação de imagens, detecção de objetos e reconhecimento facial. Também foram aplicadas com sucesso em outros campos, como reconhecimento de fala e processamento de linguagem natural. O sucesso das CNNs pode ser atribuído à sua capacidade de aprender automaticamente características dos dados de entrada, sem a necessidade de intervenção humana.

Em conclusão, as CNNs são uma ferramenta poderosa para tarefas de reconhecimento de imagens e vídeos. Elas revolucionaram o campo da visão computacional e possibilitaram uma ampla gama de aplicações. Com avanços adicionais no aprendizado profundo, espera-se que as CNNs continuem a desempenhar um papel crítico em vários campos da inteligência artificial.

---

## **Motivações para o uso de CNN's**

Quando paramos para pensar em como funcionam as RNAs notamos que essa recebe um vetor de entrada  e os transformam através de uma série de camadas ocultas. Sendo cada uma dessas camadas ocultas, compostas por neurônios que está totalmente conectados aos neurônios da camada anterior. 

<p align='center'>
<img src='https://github.com/Octo-IA/Material-Conhecimento/blob/main/docs/material/redes-cnns/imagens/introducao/rnas_color.png?raw=true'>
</p>

Devido a esse motivo, as redes neurais possuem limitações para receber imagens com alta resolução pois seria enorme o número de pesos necessários para realizar tal processamento. Imagine o cenário de uma imagem de 200x200x3  utilizando uma RNA demandaria 200*200*3 = 120.000 pesos. Claramente essa quantidade de pesos exigiria um poder computacional grande para realizar todos os cálculos presentes na tarefa de forward e backward de uma rede neural, além também de ocasionar o overfitting do modelo.

### *Compartilhamento de Parâmetros em CNN's*

Uma das principais características das redes neurais convolucionais (CNNs) é o compartilhamento de parâmetros. Isso significa que os mesmos parâmetros são usados em diferentes partes da rede para extrair características de diferentes regiões da imagem. O compartilhamento de parâmetros permite que a rede seja mais eficiente em termos de memória e computação, além de torná-la mais robusta a variações na posição do objeto na imagem.

O compartilhamento de parâmetros é possível porque as camadas convolucionais da CNN usam filtros que deslizam pela imagem para extrair características. Cada filtro é composto por um conjunto de pesos que são aplicados a cada região da imagem, produzindo uma nova imagem que representa a presença ou ausência da característica correspondente em cada posição. O compartilhamento de parâmetros é alcançado ao usar o mesmo conjunto de pesos para todos os pixels da imagem, ou para todos os pixels de uma região específica da imagem.

### *Conexões Esparsas em Redes Neurais Convolucionais*

Como resolução do problema de termos muito pesos para analisar em uma rede neural, as CNNs esparsas foram introduzidas. Em uma CNN esparsa, nem todas as entradas são conectadas a todas as saídas em cada camada. Em vez disso, apenas um subconjunto das entradas é conectado a cada saída.

A principal vantagem das CNNs esparsas é a redução no número de cálculos necessários para processar cada imagem. Além disso, as CNNs esparsas podem ser mais robustas a variações na posição do objeto na imagem, pois cada neurônio é responsável por apenas um subconjunto das características.

Existem várias abordagens para implementar conexões esparsas em CNNs. Uma abordagem comum é a utilização de filtros com tamanhos diferentes em diferentes partes da imagem. Outra abordagem é a utilização de técnicas de seleção de características para identificar as características mais relevantes e conectar apenas essas características às saídas.

Em conclusão, as CNNs esparsas são uma técnica promissora para reduzir o número de cálculos necessários para processar imagens em redes neurais convolucionais.

---

## **Macro áreas da visão computacional**

As redes neurais convolucionais (CNNs) são amplamente utilizadas em várias áreas da visão computacional, incluindo classificação, detecção de objetos e segmentação. Cada uma dessas áreas tem suas próprias técnicas e desafios, mas todas elas se beneficiam da capacidade das CNNs de extrair características das imagens.

### *Classificação*

A classificação é a tarefa de atribuir uma imagem a uma de várias classes pré-definidas. Por exemplo, uma CNN pode ser treinada para classificar imagens de animais em gatos, cães e pássaros. Uma das abordagens mais comuns para a classificação em CNNs é usar a camada Softmax na saída da rede. A camada Softmax produz uma distribuição de probabilidade sobre as classes de saída, permitindo que a rede "decida" qual classe é a mais provável. A classificação é uma tarefa importante em muitas aplicações, incluindo reconhecimento de imagens, diagnóstico médico e análise de dados.

### *Detecção de Objetos*

A detecção de objetos é a tarefa de localizar objetos em uma imagem e classificá-los em uma ou várias categorias. Por exemplo, uma CNN pode ser treinada para detectar carros em uma imagem e classificá-los em carros esportivos ou carros familiares. A detecção de objetos é uma tarefa mais complexa do que a classificação, pois envolve localizar objetos em uma imagem. Uma abordagem comum para a detecção de objetos em CNNs é usar uma arquitetura de rede que inclui camadas convolucionais e de pooling, seguidas por uma ou várias camadas totalmente conectadas. Essa arquitetura permite que a rede localize objetos em diferentes partes da imagem e, em seguida, faça uma classificação baseada nas características extraídas.

### *Segmentação*

A segmentação é a tarefa de dividir uma imagem em regiões que correspondem a objetos ou partes de objetos. Por exemplo, uma CNN pode ser treinada para segmentar uma imagem de uma rua em regiões que correspondem a carros, pedestres e edifícios. A segmentação é uma tarefa ainda mais complexa do que a detecção de objetos, pois envolve dividir uma imagem em muitas regiões diferentes. Uma abordagem comum para a segmentação em CNNs é usar uma arquitetura de rede que inclui camadas convolucionais e de pooling, seguidas por camadas de convolução transposta. Essa arquitetura permite que a rede crie uma máscara para cada região da imagem que corresponde a um objeto ou parte de um objeto.

[INSERIR UMA IMAGEM BEM LEGAL SOBRE esses 3 pontos]

<p align='center'>
<img src='https://github.com/Octo-IA/Material-Conhecimento/blob/main/docs/material/redes-cnns/imagens/introducao/imagem_cld.png?raw=true'>
</p>