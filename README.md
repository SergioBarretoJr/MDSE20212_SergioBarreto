# MDSE20212_SergioBarreto

## Minimundo
Inúmeras tecnologias fazem parte da nossa rotina mesmo que não percebamos e com o crescimento da conectividade, capacidade de armazenagem das máquinas e processamento delas uma dessas tecnologias tem se destacado bastante recentemente: Machine learning (ML) ou Aprendizagem de máquina (AM).

"Machine Learning é uma tecnologia onde os computadores tem a capacidade de aprender de acordo com as respostas esperadas por meio associações de diferentes dados, os quais podem ser imagens, números e tudo que essa tecnologia possa identificar." [https://www.ibm.com/br-pt/analytics/machine-learning]

### Macroprocesso de Aprendizagem de máquina:
- Construir um Dataset (dados guardados em forma tabular, ou um conjunto de textos, imagens, sonds, etc)

- Processar esse dataset

- Treinar um modelo que atenda a demanda específica

- Analisar a performance desse modelo treinado com Dataset

Com o crescimento da demanda pelos benefícios que o uso de ML traz para as empresas e com a escassez de mão-de-bra especializada, faz-se necessário a criação de aplicações "Low Code" que possibilite usuários não letrado em linguagens de programação de construir seus modelos.

### Objetivo do trabalho
Em vista disso, esse projeto tem como objetivo aplicar os conhecimento desenvolvidos na disciplina Desenvolvimento de Software dirigido a modelos da pós-graduação do IC-UFF e criar um sistema que possibilite usuários criarem e avaliarem o desepenho de modelos de ML sem utilização de código. O usuário apenas entra com su dataset, escolhe as trasnformações que deseja fazer em seu dado, define o problema que quer resolver (Classificação, Regressão, Clusterização), escolhe qual algoritmo deseja utilizar e analisa o desempenho do modelo. Estando o modelo com bom desemepenho, o usuário pode salvar seu modelo.

### Profile (arquivo: MDSE20212_SergioBarreto/MachineLearningSystem/MachineLearningSystem.profile.di)

No perfil, foi criado 10 esteriótipos da metaclass Class, a saber:

- Dataset: representando o elemento de input de um sistema de ML low-code. Essa esteriótipo possui propriedades necessárias, como número de linhas do dado (numlines), número de colunas (numColumns) e qual a coluna que apresenta o valor a ser previsto (target)
- Algoritmos de pré-processamento: representando os algoritmos que o usuário do sistema de ML low-code poderia usar. Além disso, apresento 3 tipos gerais de tipos desse esteriótipo: Removedores de outlier (algoritmos que podem ser usado para remover valores vora do normal), Normalizadores (algoritmos que poder ser usados para deixar todos os dados dentro da mesma distribuição de valores) e Removedores de valores vazios (algoritmos que preenchem dados faltantes.
- Algoritmos de aprendizagem: representando algotirmos de aprendizagem de máquina, ou seja, algoritimos que encontrarão padrões nos dados. Acrescentei 3 tipos gerais de algoritmos de aprendizagem: Classificação, Regressão e Clusterização
- Visualizadores de desempenho: representando meios de se visualizar o desempenho ou capacidade do modelo de ML treinado em encontrar os padrões existente dentro dos dados

Além disso, modelei 3 esteriótipos da metaclasse Association, a saber:

- Carrega: utilizado pelos modelos ao leem os dados originais ou pós-processados
- analisa: utilizado para os Visualizadores avaliarem o desempenho do modelo treinado
- ajusta: utilizado pelos algoritmos de pré-processamento para fazer seus respectivos ajustes

### Uso do OCL (arquivo: MDSE20212_SergioBarreto/MachineLearningSystem/MachineLearningSystem.profile.ocl)
Nesse perfil foi criada 5 OCLs do tipo Invariante para indicar todas as condições necessárias que devem ser satisfeitas em cada
possível instanciação do modelo. A saber fora as seguintes:
- noEmptyDataset: garantindo que será instanciado um dataset com pelo menos 1 linha de dados
- noEmptyFeatures: garantindo que será instanciado um dataset com pelo menos 1 coluna de dados
- imageFormat: garantindo que será instanciado um formato de gráfico "razoável" com eixo Y maior que Eixo x
- noNegativeYAxis: garantindo que será instanciado um formato gráfico com dimensões não negativas
- noNegativeXAxis: garantindo que será instanciado um formato gráfico com dimensões não negativas

### Caso de uso (arquivo: MDSE20212_SergioBarreto/MachineLearningSystem/MachineLearningSystem.di)
No estudo de caso, modelei um diagrama de classes de um sistema onde há a opção de se inserir um dataset, posso escolher algoritmos de remoção de linhas vazias (removeLines) e algoritmos de preenchimento de valores vazios com a média (fillMean). Além disso, o usuário pode escolher algum modelo de aprendizagem de máquina baseado em árvores. Finalizando o protótipo de sistema que utiliza meu perfil, instanciei o Visualizadores de desempenho com a visualização da matriz de confusão do modelo (confusionMatrix).  
