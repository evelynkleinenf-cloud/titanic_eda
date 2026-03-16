# titanic_eda

## Descrição do Projeto
Este projeto tem como objetivo realizar uma Análise Exploratória de Dados (EDA) do conjunto de dados do Titanic, buscando compreender os fatores que podem ter influenciado a sobrevivência dos passageiros.

A análise foi desenvolvida utilizando Python em um Jupyter Notebook (Google Colab), aplicando técnicas de exploração, visualização e análise estatística dos dados.

## Conjunto de Dados
O conjunto de dados utilizado contém informações sobre os passageiros do Titanic, incluindo características como:
- idade (Age)
- tarifa paga (Fare)
- número de irmãos ou cônjuges a bordo (SibSp)
- número de pais ou filhos a bordo (Parch)
- sobrevivência (Survived)
A variável Survived indica se o passageiro sobreviveu ao desastre:
0 → não sobreviveu  
1 → sobreviveu

## Tecnologias Utilizadas
O projeto foi desenvolvido utilizando as seguintes bibliotecas:

- Python
- pandas
- numpy
- matplotlib
- seaborn

# Etapas do Projeto
## 1. Introdução
### Contexto
O naufrágio do RMS Titanic, ocorrido em 1912, é um dos desastres marítimos mais conhecidos da história. Durante sua viagem inaugural, o navio colidiu com um iceberg no Oceano Atlântico Norte e acabou afundando, resultando na morte de grande parte dos passageiros e tripulantes a bordo.

Um dos fatores que agravou a tragédia foi o número insuficiente de botes salva-vidas, que não era suficiente para todos os passageiros. Como consequência, nem todos tiveram as mesmas chances de sobrevivência.

Com o passar do tempo, os dados desse evento passaram a ser amplamente utilizados em estudos de ciência de dados e aprendizado de máquina, permitindo investigar quais fatores podem ter influenciado as chances de sobrevivência.

### Objetivo
O objetivo deste projeto é identificar e analisar os principais fatores que influenciaram a sobrevivência dos passageiros do Titanic.

Para isso, será realizada uma Análise Exploratória de Dados (EDA) utilizando o conjunto de dados do Titanic. A análise busca compreender melhor o perfil dos passageiros e investigar quais características podem ter impactado suas chances de sobrevivência.

Ao longo do notebook, serão exploradas variáveis como sexo, idade, classe do passageiro, entre outras, com o objetivo de identificar possíveis padrões e relações entre essas características e a sobrevivência durante o desastre.

## 2.Bibliotecas
As bibliotecas necessárias neste projeto são importadas para permitir a manipulação, análise e visualização dos dados. 

Pandas será utilizado para trabalhar com o dataset, NumPy para operações numéricas e Matplotlib e Seaborn para a criação de gráficos e visualizações durante a Análise Exploratória.

## 3.DataSet
Através do link disponibilizado pelo curso, é feito o upload do Banco de Dados para o GitHub, organizando em uma pasta e o acessando através de seu caminho.

### Descrição do dataset
O conjunto de dados do Titanic contém informações sobre os passageiros que estavam a bordo do navio durante sua viagem inaugural em 1912. 

Cada linha do DataSet representa um passageiro, e cada coluna contém uma característica associada a ele, como idade, sexo, classe da passagem e porto de embarque.

### Entendimento dos dados
Antes de iniciar a Análise Exploratória, é importante compreender a estrutura do banco de dados.

A função df.shape identifica a quantidade de linhas e colunas, permitindo entender o tamanho do conjunto de dados. 

Com a função df.info obtemos informações sobre os tipos de dados de cada variável, além de indicar a presença de valores nulos. 

Por fim, a função df.describe apresenta um resumo estatístico das variáveis numéricas, incluindo medidas como média, desvio padrão, valores mínimos e máximos.

Essas informações nos permitem uma visão inicial do DataSet e servem como base para as próximas etapas da Análise Exploratória.

### Descrição das variáveis
O banco de dados do Titanic contém informações sobre os passageiros que estavam a bordo do navio. 

Cada variável representa uma característica associada aos passageiros. São elas:

**PassengerId:** Identificador único atribuído a cada passageiro no DataSet.

**Survived:** Indica se o passageiro sobreviveu ao naufrágio.

0 = Não sobreviveu

1 = Sobreviveu

**Pclass:** Classe da passagem do passageiro, que também pode representar o nível socioeconômico.

1 = Primeira classe

2 = Segunda classe

3 = Terceira classe

**Name:** Nome completo do passageiro.

**Sex:** Sexo do passageiro (masculino ou feminino).

**Age:** Idade do passageiro em anos.

**SibSp:** Número de irmãos ou cônjuges do passageiro que estavam a bordo do Titanic.

**Parch:** Número de pais ou filhos do passageiro que estavam a bordo.

**Ticket:** Número do ticket da passagem.

**Fare:** Valor pago pela passagem do navio.

**Cabin:** Número da cabine onde o passageiro estava acomodado.

**Embarked:** Porto onde o passageiro embarcou no Titanic.

C = Cherbourg (França)

Q = Queenstown (Irlanda)

S = Southampton (Inglaterra)

Após visualizar e compreender cada variável do DataSet, é possível identificar quais são relevantes para a análise proposta.


Assim, selecionamos apenas as colunas consideradas mais importantes para investigar os fatores que podem ter influenciado a sobrevivência dos passageiros do Titanic. 

Essa seleção permite simplificar o banco de dados e concentrar a análise em variáveis com maior potencial explicativo, como classe do passageiro, sexo, idade, número de familiares a bordo, valor da passagem e porto de embarque.

Desta forma, o DataSet passa a conter apenas as informações mais relevantes para as etapas seguintes de Tratamento dos Dados e Análise Exploratória.

## 4.Limpeza e Tratamento dos Dados
Identificamos e corrigimos possíveis problemas no conjunto de dados, como valores ausentes, registros duplicados, tipos de dados inadequados e inconsistências nas variáveis.

Desta maneira, evitamos o comprometimento da qualidade da Análise e obtemos interpretações corretas dos resultados. 

Ou seja, garantimos que os dados estejam mais confiáveis e adequados para as próximas etapas.
Foram realizados nesta etapa:

### Tratamento de Duplicados
### Tratamento de Valores Nulos
### Tratamento de Tipagem de Dados
### Valores Inconsistentes
### Feature Engineering
Também é feito Feature Engineering, em que criamos e transformamos variáveis a partir das informações do DataSet.

Deste modo, são geradas novas características que facilitam a Análise e mostram padrões relevantes relacionados à sobrevivência dos passageiros. 

#### Variável Tamanho da Família
Uma informação relevante é o tamanho da família do passageiro a bordo do Titanic. Essa informação pode ser obtida a partir das variáveis SibSp (número de irmãos/cônjuges) e Parch (número de pais/filhos).

A nova variável TamanhoFamilia será criada somando essas duas variáveis e adicionando o próprio passageiro.

#### Variável Passageiro Sozinho
Com base no tamanho da família, identificamos se o passageiro estava viajando sozinho ou acompanhado. Para isso, criamos a variável PassSozinho, que indicará se o passageiro estava sozinho no navio.

#### Grupos de Categoria de Família
Seguindo a mesma lógica das variáveis Tamanho da Família e Passageiro Sozinho, criamos também a variável Categoria de Família, onde agrupamos os passageiros em: Sozinho (passageiro sem familiares a bordo do navio), Família pequena (até 4 familiares a bordo) e Família grande (mais de 4 familiares a bordo).

#### Grupos de Faixas Etárias
Para facilitar a análise da variável Age, as idades podem ser agrupadas em faixas etárias, permitindo analisar de forma mais clara como a idade pode ter influenciado as chances de sobrevivência.
A nova variável FaixaEtaria classifica os passageiros nas seguintes faixas etárias: Criança (0 a 12 anos), Adolescente (13 a 18 anos), Jovem Adulto (19 a 35 anos), Adulto (36 a 60 anos), Idoso (61 a 100 anos).

#### Dataframe atualizado
Após a Limpeza, Tratamento dos Dados, e do Feature Engineering, vamos verificar se todas as alterações estão corretas no novo DataSet e visualizá-lo.
Após confirmar que todas as alterações no DataSet foram realizadas com sucesso, criamos um novo DataFrame(df_titanic) para otimizar a organização e análise do mesmo.

## 5.Análise Estatística
Realizamos a análise estatística para obter uma compreensão mais detalhada das características do conjunto de dados.

Nesta etapa, serão analisadas medidas estatísticas descritivas, como média, mediana, desvio padrão e distribuição dos dados. Essas métricas ajudam a resumir as principais características das variáveis e a identificar possíveis padrões ou diferenças entre grupos de passageiros.
São realizadas:

### Estatísticas Descritivas das Variáveis Numéricas
As estatísticas descritivas permitem observar a distribuição geral das variáveis numéricas. É possível identificar a média das idades dos passageiros, a variação nos valores das passagens e a quantidade média de familiares a bordo.

Essas informações ajudam a compreender melhor o perfil geral dos passageiros presentes no dataset.

### Comparação Estatística entre Sobreviventes e Não Sobreviventes
Em alguns casos, passageiros que sobreviveram podem apresentar valores médios mais altos em determinadas variáveis, como o preço da passagem, o que pode refletir diferenças relacionadas à classe social.

### Distribuição das Variáveis Numéricas
A maioria dos passageiros era adulto jovem.

Muitos passageiros viajavam sozinhos ou com poucos familiares.

O valor da tarifa apresenta grande variação, com poucos passageiros pagando valores muito altos.

Essas características ajudam a compreender melhor o perfil dos passageiros e servem como base para análises posteriores, como investigar quais fatores podem ter influenciado a sobrevivência no desastre do Titanic.

### Análise de Outliers
Observa-se que a variável Fare, por exemplo, apresenta alguns valores significativamente mais altos do que a maioria das passagens, indicando a presença de possíveis outliers.

A identificação desses valores ajuda a compreender melhor a dispersão dos dados e a interpretar corretamente os resultados da análise.

## 6.Análise exploratória (EDA)
Exploramos nosso DataFrame atualizado por meio de estatísticas descritivas e visualizações gráficas, permitindo identificar padrões, tendências e possíveis relações entre as variáveis. Realizamos a EDA das seguintes variáveis:

### Sobrevivência Geral
A análise da variável Survived mostra que a maior parte dos passageiros não sobreviveu ao naufrágio do Titanic.

Esse resultado reforça a gravidade do desastre e destaca a importância de investigar quais fatores podem ter influenciado as chances de sobrevivência dos passageiros.

Essas relações serão exploradas nas próximas análises.

### Sobrevivência por Gênero
Percebemos uma diferença significativa nas taxas de sobrevivência entre os gêneros, tendo as passageiras uma taxa de sobrevivência muito maior em comparação aos passageiros.

Esse padrão pode estar relacionado a forma como foi conduzida a evacuação do navio, que priorizavam mulheres e crianças no embarque nos botes salva-vidas.

Essa observação indica que o gênero foi um dos fatores mais relevantes para a sobrevivência no desastre do Titanic.

### Sobrevivência por Classe Social
Observa-se que a classe do passageiro teve um impacto significativo nas chances de sobrevivência. Passageiros da primeira classe apresentaram uma taxa de sobrevivência maior, enquanto passageiros da terceira classe tiveram as menores chances de sobreviver.

Esse resultado pode estar relacionado a diversos fatores, como a localização das cabines no navio, o acesso aos botes salva-vidas e as prioridades durante o resgate. Passageiros das classes mais altas possivelmente tiveram acesso mais rápido aos botes, enquanto passageiros das classes mais baixas enfrentaram maiores dificuldades durante a evacuação.

Assim, percebemos que a classe social foi um fator relevante na sobrevivência dos passageiros do Titanic.

### Sobrevivência por Idade
Os gráficos indicam que crianças apresentaram uma taxa de sobrevivência relativamente maior em comparação com adultos, o que pode estar relacionado à prioridade dada a mulheres e crianças durante o processo de evacuação.

Entretanto, também é possível observar que passageiros de diversas faixas etárias foram afetados pelo desastre, indicando que a idade, embora relevante, não foi o único fator determinante para a sobrevivência. Isso reforça a importância de considerar múltiplas variáveis para compreender a chance de sobrevivência no Titanic.

### Sobrevivência por Tamanho da Família vs Sozinhos
Passageiros que viajavam com famílias muito grandes ou completamente sozinhos apresentaram menores taxas de sobrevivência. Já passageiros que viajavam com famílias pequenas ou médias parecem ter tido chances maiores de sobreviver.

Esse resultado sugere que o tamanho da família pode ter tido alguma influência na sobrevivência, possivelmente devido ao apoio entre familiares e/ou à organização durante a evacuação.

Essa observação reforça a ideia de que características sociais e familiares também podem ter influenciado a sobrevivência no desastre do Titanic.

### Sobrevivência por Preço da Passagem
Passageiros que pagaram valores mais altos pelas passagens tendem a apresentar uma taxa de sobrevivência maior. Isso sugere que o preço da passagem, que está frequentemente associado à classe social do passageiro, pode ter influenciado as chances de sobrevivência.

Esse padrão reforça os resultados observados anteriormente na análise por classe do passageiro (Pclass), indicando que passageiros de classes mais altas possivelmente tiveram maior acesso aos recursos de evacuação e melhores condições durante o resgate.

Entretanto, também é possível observar uma grande variação nos valores das passagens, indicando que o preço da passagem não foi o único fator determinante para a sobrevivência.

### Sobrevivência por Porto de Embarque
Observa-se diferenças nas taxas de sobrevivência entre os passageiros que embarcaram em diferentes portos. Passageiros que embarcaram em Cherbourg apresentam uma taxa de sobrevivência relativamente maior em comparação com os demais portos.

Essa diferença pode estar relacionada ao perfil socioeconômico dos passageiros, já que uma proporção maior de passageiros da primeira classe embarcou em Cherbourg, enquanto muitos passageiros da terceira classe embarcaram em Southampton (que tiveram menor taxa de sobrevivência).

Esses resultados sugerem que o porto de embarque pode estar indiretamente relacionado à sobrevivência, principalmente por estar associado à classe social e perfil dos passageiros.

## 7.Análises Cruzadas/Relações entre Variáveis
Ao analisar relações entre diferentes variáveis, podemos identificar padrões mais complexos e interações entre fatores que podem ter influenciado a sobrevivência dos passageiros. Realizamos a análise cruzada das seguintes variáveis:

### Sobrevivência por Gênero e Classe Social
A análise mostra que mulheres apresentaram taxas de sobrevivência maiores em todas as classes sociais. No entanto, passageiros da primeira classe tiveram maiores chances de sobreviver em comparação com as classes mais baixas.

Entre os homens, observa-se uma taxa de sobrevivência significativamente menor, especialmente entre os passageiros da terceira classe.

### Sobrevivência por Idade/Faixa Etária e Gênero
Observamos como a idade dos passageiros se distribui entre homens e mulheres que sobreviveram ou não ao desastre. As visualizações sugerem que crianças e mulheres tiveram maiores chances de sobrevivência, reforçando a ideia de que houve prioridade para estes grupos durante o resgate.

### Sobrevivência por Classe Social e Porto de Embarque
Percebemos como a sobrevivência varia entre diferentes classes sociais dentro de cada porto de embarque. Nota-se que passageiros da primeira classe apresentaram maiores taxas de sobrevivência em praticamente todos os portos, enquanto passageiros da terceira classe apresentaram as menores chances de sobreviver.

## 8.Análise de Correlação
### Matriz de Correlação entre Variáveis Numéricas
Além das análises visuais, também é útil analisar a correlação entre variáveis numéricas. A matriz de correlação permite identificar relações entre diferentes variáveis, indicando se elas apresentam associação positiva, negativa ou pouca relação entre si.
Conclusão: 
A matriz de correlação indica que as variáveis relacionadas ao contexto familiar possuem forte relação entre si, enquanto as variáveis numéricas analisadas apresentam baixa correlação direta com a sobrevivência. Entre elas, Fare foi a que apresentou a maior associação positiva com a sobrevivência, sugerindo que passageiros que pagaram tarifas mais altas tiveram maior chance de sobreviver.

## 9.Principais Insights da Análise
Ao longo deste notebook foram realizadas Análise Estatística, Análise Exploratória dos dados e Análise de Correlação do DataSet do Titanic, com o objetivo de identificar fatores que podem ter influenciado as chances de sobrevivência dos passageiros. A partir dessas análises, foi possível identificar alguns padrões importantes.

### Influência do gênero
Um dos fatores mais relevantes observados foi o gênero dos passageiros. Passageiras apresentaram uma taxa de sobrevivência significativamente maior em comparação com passageiros. Esse resultado está alinhado com os relatos históricos de que mulheres e crianças tiveram prioridade no acesso aos botes salva-vidas.

### Influência da classe social
A classe da passagem também mostrou forte relação com a sobrevivência. Passageiros da primeira classe tiveram maiores chances de sobreviver, enquanto passageiros da terceira classe apresentaram as menores taxas de sobrevivência. Esse padrão pode estar relacionado à localização das cabines e ao acesso aos botes salva-vidas.

### Influência da idade
A análise da idade indicou que crianças apresentaram uma taxa de sobrevivência relativamente maior em comparação com adultos. Isso reforça a hipótese de que houve prioridade para mulheres e crianças durante o resgate.

### Influência do preço da passagem
Passageiros que pagaram valores mais altos pelas passagens também apresentaram maiores taxas de sobrevivência. Como o preço da passagem está geralmente associado à classe social, esse fator reforça a relação observada anteriormente entre classe social e sobrevivência.

### Influência do tamanho da família
O tamanho da família a bordo também parece ter influenciado as chances de sobrevivência. Passageiros que viajavam sozinhos ou em famílias muito grandes apresentaram menores taxas de sobrevivência, enquanto passageiros em famílias pequenas tiveram resultados um pouco melhores, possivelmente devido ao apoio entre familiares e/ou à organização durante a evacuação.

### Influência do porto de embarque
Diferenças também foram observadas entre os passageiros que embarcaram em diferentes portos. Passageiros que embarcaram em Cherbourg apresentaram uma taxa de sobrevivência maior, possivelmente devido à maior presença de passageiros de classe mais alta nesse porto.

### Conclusão geral
De forma geral, a análise sugere que a sobrevivência no Titanic não foi aleatória. Esta foi fortemente influenciada por uma combinação de fatores sociais e demográficos.

A análise mostra que os fatores mais importantes para a sobrevivência foram gênero, classe social e idade. Mulheres e passageiros da primeira classe tiveram maior probabilidade de sobreviver, enquanto homens da terceira classe apresentaram as menores taxas.

Esses resultados demonstram como a Análise Exploratória de Dados pode ajudar a identificar padrões importantes em conjuntos de dados históricos, permitindo compreender melhor os fatores que podem ter contribuído para determinados eventos. Desta forma, podemos auxiliar a criação de ações e protocolos a fim de diminuir os danos e prejuízos, prevenir e antecipar futuras tragédias.

# Estrutura do Projeto
titanic_eda
│ dados
├── titanic_dataset.csv 
│ notebooks
├── titanic_analysis.ipynb
├ README.md


# Autor
Projeto desenvolvido por Evelyn Klein dos Santos para atividade "Desafio Extra" para o curso de parceria SENAI e SCTec de **Análise de Dados / Ciência de Dados**.
