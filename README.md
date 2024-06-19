# 📊  Análise de Dados para Segmentar Clientes 

💡 Projeto: Segmentação de clientes e análise de dados para uma loja especializada em produtos alimentícios importados chamada El Mercado

Bem-vindo(a) à ficha técnica da análise de segmentação de clientes da empresa o Mercado. A ficha técnica apresenta uma visão abrangente do projeto de análise de dados, focado na segmentação de clientes usando o método RFM (Recência, Frequência e Valor Monetário) e na análise de coorte. 
Essa abordagem visa aprofundar a compreensão do comportamento dos clientes e identificar padrões relevantes para a tomada de decisões estratégicas, pois ao entender melhor quem são os clientes e como eles se comportam, podemos tomar decisões mais informadas e estratégicas que impulsionam o crescimento do negócio.


**Título do Projeto**
Segmentação de Clientes


<details>
<summary><b>Objetivo</b></summary>
  
O objetivo deste projeto é realizar uma análise abrangente de segmentação de clientes, utilizando métricas essenciais como RFM (Recency, Frequency, Monetary) e análise de coorte. Através desta análise, busquei entender mais profundamente o comportamento dos  clientes, identificando padrões de compra, preferências e tendências. Esses insights são fundamentais para adaptar estratégias de marketing de forma precisa e eficaz, permitindo direcionar melhorias específicas para grupos de clientes de acordo com suas necessidades e características distintas.

Este projeto reveste-se de uma importância crucial para a loja o Mercado, especializada em produtos alimentícios importados, que enfrenta desafios constantes na compreensão das preferências mutáveis de seus clientes. A necessidade de fidelizar esses clientes é premente, e para superar esse desafio, a empresa busca identificar onde investir seus esforços. Portanto, esta análise é de grande relevância para orientar as estratégias de negócio e impulsionar o sucesso da empresa no mercado competitivo de alimentos importados.
</details>

<details>
<summary><b>Equipe</b></summary>

Trabalhei de forma independente neste projeto, assumindo todas as responsabilidades, desde o planejamento até a execução e análise dos resultados. Apesar de ser um projeto individual, busquei feedback de colegas e auxílio quando necessário, priorizando a entrega de qualidade. Mesmo atuando sozinha, reconheço a importância da aprendizagem colaborativa e valorizo as contribuições de outras colegas ao buscar insights e perspectivas externas e diferentes. A capacidade de gerenciar todas as etapas do projeto de forma independente me proporcionou um valioso aprendizado e desenvolvimento de habilidades em diversas áreas, desde análise de dados até comunicação eficaz, ao mesmo tempo em que pude perceber a importância da colaboração para enriquecer o resultado final.

</details>

<details>
<summary><b>Ferramentas e Tecnologia</b></summary>

Durante o desenvolvimento deste projeto, foram utilizadasferramentas e tecnologias para coleta, análise e visualização de dados. Algumas das principais incluem:

**Planilhas Eletrônicas (Spreadsheets):**

- Utilizei planilhas eletrônicas para importar, limpar e tratar os dados iniciais, realizar cálculos de métricas e manipulações além de criar variáveis, aplicar fórmulas e criar tabelas dinâmicas para análises de criação de gráficos e dashboard interativo através do filtro de segmentação.

**Looker Studio:**

- O Looker Studio foi a principal ferramenta de visualização e análise de dados utilizada neste projeto. Através do Looker, criei dashboards interativos e personalizados que permitiram explorar os dados de forma dinâmica e extrair insights valiosos para apresentação dos resultados das análises realizadas.


</details>


<details>
<summary><b>Processamento de dados</b></summary>


<details>
<summary><b>Obtenção de dados</b></summary>
  
Os dados dos clientes foram obtidos, através do google planilhas, realizei uma cópia e depois importei todos os dados para uma planilha onde seria feita a análise visando não apagar ou danificar a base de dados origem
Importei os dados para uma nova planilha de forma automatizada através da fórmula IMPORTRANGE, trouxe as 3 planilhas sendo: clientes, transacoes, e resumo compras inseri cada uma em abas diferentes para realizar o tratamento na base de dados.

</details>

<details>
<summary><b> Limpeza dos dados</b></summary>

Antes da análise, os dados passaram por um processo de limpeza para lidar com inconsistências, erros e valores ausentes, isso incluiu:

- **Remoção de registros duplicados**:  Identifiquei 9 valores duplicados na tabela resumo_compra**s** na coluna id_cliente, através da formatação condicional,  retirei os valores duplicados com a fórmula ARRAY E UNIQUE
- **Tratamento de valores ausentes (nulos):**  Para tratar valores ausentes na tabela de clientes, identifiquei 24 compradores sem informação de salário. Optei por preencher esses campos com a mediana dos salários existentes, a fim de manter a consistência na base de dados e evitar distorções na distribuição dos dados. Essa abordagem foi escolhida para garantir que a falta de informação não prejudicasse a análise futura, especialmente ao criar gráficos, onde a presença de valores ausentes poderia distorcer a representação visual dos dados. Para realizar esse tratamento, utilizei fórmulas como "contar vazio", "mediana" e "SE", combinadas com a função "colar valores", aplicando a mediana nos campos vazios e garantindo a integridade dos dados de salário.

Ao identificar na tabela de transações a presença de 7 compradores sem IDs, utilizei a função "contar vazio" para verificá-los. Neste contexto, decidi excluir esses registros, uma vez que não contribuiriam para o propósito da análise em questão. A exclusão desses registros sem IDs foi uma medida adotada para garantir a integridade e a precisão dos dados utilizados na análise das transações.
- **Inconsistências:** Identifiquei na base de dados a presença de 10 usuários que possuíam cadastro, mas não tinham registros de compras, o que foi considerado um outlier para o propósito da análise em questão. Optei por remover esses usuários das tabelas de resumo de compras e clientes, como uma medida para eliminar essa inconsistência e manter a integridade dos dados utilizados na análise. Essa abordagem foi considerada válida para corrigir o problema, uma vez que preservou a qualidade dos dados sem comprometer a análise. No entanto, esses clientes foram mantidos em uma base separada e não tratada, caso fossem necessários para referência futura. Os IDs dos clientes excluídos foram: 5376, 8475, 5555, 3955, 10749, 6862, 11110, 4931, 9931 e 11181. Essa ação foi realizada apenas na tabela de análise em que estava trabalhando, sem afetar a fonte original de dados.

Na base de clientes, identifiquei a presença de 3 clientes com idades de 122, 123 e 129 anos, valores consideravelmente elevados. Embora essas idades possam parecer improváveis, optei por mantê-las na análise. A decisão de reter esses registros se deve ao fato de que, apesar das idades incomuns, todas as outras informações desses clientes estão disponíveis e eles possuem histórico de compras, o que os torna relevantes para a análise. Além disso, considerei a possibilidade de que essas idades incomuns pudessem ser resultado de erros de preenchimento ou entrada de dados. No entanto, a idade em si não é um fator crítico que impactaria negativamente na análise em questão. Portanto, decidi manter esses registros para preservar a integridade e completude dos dados, garantindo que todas as informações relevantes fossem consideradas durante a análise.

Para unir as tabelas, utilizei as funções QUERY e PROCV para consolidar todas as informações em uma única tabela. Através da função QUERY, selecionei os dados relevantes de todas as tabelas e os organizei conforme necessário. Em seguida, utilizei a função PROCV para buscar informações adicionais de outras tabelas com base em chaves de identificação comuns, garantindo a integridade e a precisão dos dados consolidados. Essa abordagem permitiu criar uma visão unificada e coesa de todos os dados, facilitando a análise e a obtenção de insights significativos.

- **Criei tabelas dinâmicas para resumir dados em variáveis categóricas -** criei tabelas dinâmicas para condensar informações em variáveis categóricas relevantes, abrangendo aspectos como por exemplo nível de escolaridade predominante, estado civil, renda média anual dos clientes, número médio de filhos, média salarial por nível de educação e valor gasto por categoria, entre outros aspectos significativos. Essa abordagem permite uma análise mais precisa e acessível dos dados, proporcionando insights essenciais para tomadas de decisão estratégicas.

</details>

<details>
<summary><b> Transformação dos dados</b></summary>

Após a limpeza inicial, os dados foram transformados para realizar a  análise de segmentação de clientes. Isso pode incluir:

- **Tabelas dinâmicas e gráficos:** Na aba "Tabela Resumo", incluí tabelas dinâmicas que sintetizam as respostas às perguntas feitas sobre o perfil dos clientes. Além disso, criei gráficos para visualizar de forma clara e acessível informações como o nível de escolaridade predominante, estado civil, renda média anual dos clientes, número médio de filhos e média salarial por nível de educação, entre outros. Essas tabelas e gráficos proporcionam uma compreensão abrangente do perfil demográfico dos clientes, facilitando a identificação de padrões e tendências importantes para a estratégia de negócios.
- **Quartil:** Calculei os quartis para segmentar os clientes em grupos com base nas métricas RFM (Recency, Frequency, Monetary).ara isso, criei uma tabela auxiliar com a coluna "Posição Quartil", numerada de 1 a 4, e utilizei a fórmula do quartil para calcular a posição RFM. Esse processo gerou um número limite no intervalo de valores, que pude utilizar como pontuação para definir as classificações posteriormente. Essa abordagem possibilitou uma segmentação mais precisa dos clientes, permitindo uma análise mais detalhada de seus comportamentos e necessidades.
- **Cálculo das métricas RFM (Recency, Frequency, Monetary):** No cálculo das métricas RFM (Recency, Frequency, Monetary) para cada cliente, levei em consideração suas transações  passadas e calculei individualmente cada valor conforme descrito abaixo:

**Recência (R):** Determinei a recência com base na data da última transação do cliente em relação ao último dia de compra registrado na base de dados. Como a base de dados se estendia até 31/12/2022 e alguns clientes haviam realizado compras até o último dia disponível, utilizei a data fictícia de 01/01/2023 na fórmula. Essa abordagem garantiu que os clientes não fossem penalizados com uma recência excessiva devido à falta de registros mais recentes além do último dia da base de dados.

**Frequência (F):** No cálculo da frequência, utilizei a contagem de transações por cliente, utilizando a fórmula "Contar Se", a fim de determinar quantas compras cada cliente realizou desde sua data de cadastro. Essa abordagem proporcionou uma medida da frequência de compras de cada cliente ao longo do tempo, permitindo uma avaliação clara de seu engajamento e atividade dentro do período de análise.

**Monetário (M):** utilizei o total de compras de cada cliente para determinar quanto ele já gastou na empresa. Essa abordagem proporcionou uma medida direta do valor monetário que cada cliente contribuiu para o negócio, permitindo uma análise detalhada do seu comportamento de compra e do seu impacto financeiro.

Além disso, criei uma métrica de média entre frequência e monetário, considerando que essas duas métricas estão correlacionadas. Essa média proporcionou uma perspectiva mais abrangente sobre o comportamento dos clientes, permitindo uma análise mais detalhada sobre como essas métricas se relacionam e como influenciam o desempenho geral do cliente.


</details>

</details>

<details>
<summary><b> Análise Exploratória dos dados </b></summary>


<details>
<summary><b> Comportamento e visualização dos dados </b></summary>
  
Após importar os dados tratados para o ambiente do Power BI, realizamos uma análise exploratória para entender o comportamento dos dados e extrair insights valiosos. Esta etapa envolveu várias técnicas de visualização e análise estatística para compreender melhor as características dos dados.

* Agrupamento por Artista e por Música: Inicialmente, realizamos um agrupamento para verificar quantos streams havia por artista e por música. Essa análise nos permitiu entender a distribuição dos streams em relação aos artistas e às músicas, identificando padrões de popularidade e engajamento.

* Gráfico de Barras: Para visualizar essas distribuições, criamos gráficos de barras que destacavam a quantidade de streams por artista e por música. Esses gráficos proporcionaram uma representação visual clara e intuitiva da popularidade das músicas e dos artistas no Spotify.

* Estatísticas Descritivas: Além disso, calculamos os valores de média, mediana e desvio padrão das variáveis numéricas da tabela. Essas estatísticas descritivas nos forneceram insights sobre a tendência central e a dispersão dos dados, ajudando a identificar possíveis outliers e padrões de comportamento.
  
* Histograma: Para uma compreensão mais detalhada da distribuição das variáveis numéricas, criamos um histograma que mostra a frequência de ocorrência de diferentes faixas de valores. Esse histograma nos permitiram visualizar a forma e a dispersão dos dados, facilitando a identificação de padrões e tendências.
  
* Gráfico de Linhas:
Por fim, geramos um gráfico de linhas para visualizar o número de músicas lançadas por ano. Esse gráfico nos ajudou a entender a evolução temporal da produção musical e a identificar tendências ao longo do tempo.
  
</details>  

<details>
<summary><b> Cálculo de quartis </b></summary>

Para uma análise mais granular das características das músicas (“bpm”, “danceability”, “valence”, “energy”, “acousticness”, “instrumentalness”, “liveness” e “speechiness”) , decidimos categorizar as variáveis ​​que representam essas características em quartis, atribuindo valores de 1 a 4. . Essa abordagem nos permitiu agrupar as músicas com base em diferentes níveis dessas características, proporcionando uma compreensão mais detalhada de sua diversidade e distribuição.

Utilizamos uma combinação de comandos SQL, incluindo WITH, NTILE, OVER e ORDER BY, para realizar essa categorização de maneira eficiente e escalável. Primeiramente, definimos a lógica para a categorização dos quartis, atribuindo valores de 1 a 4 com base na distribuição das características das músicas na amostra de dados.

Essa categorização nos permitiu analisar as características das músicas de forma mais abrangente, identificando padrões e tendências em diferentes faixas de valores. Além disso, facilitou a comparação entre músicas com características semelhantes e a identificação de grupos distintos com base em suas características musicais.

</details>

<details>
<summary><b> Segmentação de Dados por Quartis </b></summary>
  
Para uma análise mais simplificada e interpretável, decidimos segmentar os dados em duas categorias distintas, denominadas "alta" e "baixa", para os quartis das variáveis que representam as características das músicas. Essa segmentação nos permitiu agrupar os valores dos quartis de maneira mais intuitiva, facilitando a comparação e interpretação dos resultados.



**Metodologia de Segmentação:**
Utilizamos uma abordagem baseada em regras simples para atribuir os valores dos quartis às categorias "alta" e "baixa". Os valores 1 e 2 foram agrupados na categoria "baixa", enquanto os valores 3 e 4 foram agrupados na categoria "alta". Para realizar essa segmentação, empregamos o comando IF para criar uma lógica de classificação e agregamos os resultados por meio do comando JOIN.

**Criação de Tabelas Matrizes:**
Para avaliar o comportamento das variáveis das características das músicas em relação ao número médio de streams, criamos tabelas matriz para cada uma das variáveis. Essas tabelas permitiram verificar o valor médio de streams para cada uma das duas categorias criadas (alta e baixa) em relação a cada variável.

Ao final, foi criada uma nova tabela utilizando o comando CREATE TABLE chamada “dados_spotify_categorizados".

</details>

<details>
<summary><b> Teste de correlação </b></summary>

Para validar as hipóteses inicialmente propostas neste projeto, realizamos o teste de correlação dentro do ambiente do BigQuery. Utilizamos o comando CORR para calcular a correlação entre as variáveis relevantes e investigar possíveis relações entre elas.

**Metodologia do Teste:**
Utilizamos uma abordagem estatística para avaliar a correlação entre as variáveis selecionadas. O teste de correlação nos permitiu determinar se existe uma relação linear entre duas variáveis e a direção (positiva ou negativa) e a força dessa relação.

**Comando Utilizado:**

* CORR: Utilizamos o comando CORR dentro do ambiente do BigQuery para calcular a matriz de correlação entre as variáveis de interesse. Esse comando nos forneceu uma visão geral das relações entre as variáveis e ajudou a identificar possíveis associações significativas.

**Benefícios do Teste:**
O teste de correlação nos permitiu avaliar a presença e a magnitude das relações entre as variáveis, fornecendo insights valiosos para a validação das hipóteses levantadas no início do projeto. Ao identificar correlações significativas, pudemos confirmar ou refutar  as relações esperadas entre as variáveis e orientar análises posteriores com base nos resultados obtidos. Esse teste foi essencial para fundamentar nossas conclusões e recomendações finais com base em evidências estatísticas sólidas.

</details>

<details>
<summary><b> Teste de significância (Mann-Whitney) </b></summary>

No ambiente do Google Colab, empregamos a linguagem Python para conduzir o teste de significância não paramétrico de Mann-Whitney, como parte da análise das hipóteses deste projeto. O objetivo principal desse teste foi determinar se existe uma diferença significativa entre dois grupos independentes de dados.

**Metodologia do Teste:**
O teste de Mann-Whitney é uma técnica estatística robusta que não requer que os dados sigam uma distribuição normal, tornando-o ideal para situações em que a normalidade dos dados é desconhecida. Ele avalia se existe uma diferença estatisticamente significativa entre as distribuições de duas amostras independentes, com base nos valores das observações.

**Vantagens do Teste:**
Uma das principais vantagens do teste de Mann-Whitney é sua capacidade de lidar com dados que não seguem uma distribuição normal. Isso o torna uma ferramenta valiosa para análises estatísticas em que a normalidade dos dados não pode ser assumida. Além disso, por ser um teste não paramétrico, ele é menos sensível a outliers e é mais robusto em relação a violações de pressupostos estatísticos.

**Implementação em Python:**
Utilizamos a linguagem Python no ambiente do Google Colab para implementar o teste de Mann-Whitney. Isso nos permitiu realizar uma análise estatística precisa e eficiente, aproveitando as bibliotecas e ferramentas disponíveis na linguagem para conduzir o teste de forma adequada.

**Importância do Teste:**
O teste de Mann-Whitney desempenhou um papel crucial na validação das hipóteses deste trabalho, fornecendo evidências estatísticas sólidas para suportar nossas conclusões. Ao determinar se existem diferenças significativas entre os grupos de dados analisados, este teste nos permitiu identificar padrões e tendências importantes, contribuindo para uma compreensão mais profunda do fenômeno em estudo.
</details>

<details>
<summary><b> Teste de Regressão Linear </b></summary>
  
Utilizando a linguagem Python, conduzimos uma análise de regressão linear como parte da investigação das hipóteses deste projeto. O objetivo principal dessa análise foi examinar as relações entre as variáveis selecionadas e determinar se existem associações significativas entre elas.

**Metodologia do Teste:**
A análise de regressão linear é uma técnica estatística poderosa que nos permite modelar e investigar a relação entre uma variável dependente e uma ou mais variáveis independentes. Neste contexto, empregamos a regressão linear para avaliar o impacto de determinadas variáveis sobre uma variável de interesse e identificar padrões ou tendências nos dados.

**Visualização dos Resultados:**
Além da análise estatística, criamos gráficos de dispersão para visualizar o comportamento das variáveis em cada uma das hipóteses do projeto. Esses gráficos nos forneceram uma representação visual das relações entre as variáveis e ajudaram a identificar padrões ou tendências nos dados.

**Importância da Análise:**
A análise de regressão linear desempenhou um papel crucial na investigação das hipóteses deste projeto, fornecendo insights sobre a natureza das relações entre as variáveis estudadas. Ao identificar associações significativas, pudemos validar nossas hipóteses e compreender melhor os fatores que influenciam as variáveis de interesse.

**Implementação em Python:**
Utilizamos a linguagem Python para implementar a análise de regressão linear, aproveitando as bibliotecas e ferramentas disponíveis na linguagem para conduzir a análise de forma eficiente e precisa. A flexibilidade e a robustez do Python nos permitiram explorar as relações entre as variáveis e extrair insights valiosos dos dados.
</details>

</details>

<details>
<summary><b> Resultados e Conclusões </b></summary>

Conclusões da Análise Exploratória dos Dados

<details>
<summary><b> Hipótese 1 - Impacto BPM nos Streams </b></summary>

A suposição inicial de que músicas com um maior número de batidas por minuto (BPM) teriam um maior número de streams não foi confirmada pela análise exploratória dos dados. Os resultados dos testes estatísticos revelaram o seguinte:

**Teste de Correlação:**
O coeficiente de correlação entre as variáveis "bpm" e "streams" foi calculado como -0.0009, indicando uma correlação negativa muito fraca entre elas. Esse valor sugere que não há uma associação significativa entre o BPM e o número de streams das músicas.

**Teste de Significância (Mann-Whitney):**
Ao analisar as categorias "alta" e "baixa" da variável "bpm" em relação ao número de streams, não foi encontrada diferença significativa entre elas. Isso indica que o BPM não parece influenciar de forma significativa o número de streams das músicas.

**Teste de Regressão Linear:**
O teste de regressão linear apresentou um valor de p = 0.944 para a variável independente "bpm". Esse valor elevado de p indica que o BPM não é estatisticamente significativo para prever os streams. Em outras palavras, o BPM não é um bom preditor do número de streams das músicas.

**Conclusão Geral:**
Com base nos resultados desses testes estatísticos, não encontramos evidências estatísticas que sustentem a ideia de uma relação significativa entre as variáveis "bpm" e "streams". Portanto, não podemos afirmar que o BPM das músicas influencia diretamente o número de streams no Spotify. Outros fatores podem ter um papel mais significativo na popularidade e no sucesso das músicas na plataforma.


</details>

<details>
<summary><b> Hipótese 2 - Correlação entre o Ranking do Spotify e Outras Plataformas </b></summary>

Os testes realizados confirmaram a hipótese inicial de que as músicas mais populares no ranking do Spotify também têm um desempenho semelhante nas plataformas Deezer e Apple. Os resultados dos testes estatísticos são os seguintes:

**Teste de Correlação:**
As correlações entre o ranking do Spotify e as plataformas Deezer e Apple foram calculadas como 0.5998 e 0.5519, respectivamente. Esses valores indicam uma correlação positiva entre as plataformas, sugerindo que as músicas populares no Spotify tendem a ter um desempenho semelhante nas plataformas Deezer e Apple.

**Teste de Regressão Linear:**
As regressões aplicadas apresentaram valores de p < 0.05, o que indica que há uma evidência estatisticamente significativa para a relação entre as músicas populares no ranking do Spotify e seu desempenho nas plataformas Deezer e Apple. Em outras palavras, as músicas que são populares no Spotify têm uma associação estatisticamente significativa com as plataformas Deezer e Apple.

**Conclusão Geral:**
Com base nos resultados desses testes estatísticos, podemos concluir que há uma associação estatisticamente significativa entre a popularidade das músicas no ranking do Spotify e seu desempenho nas plataformas Deezer e Apple. Portanto, a hipótese de que as músicas mais populares no Spotify também são populares nas plataformas Deezer e Apple foi validada. Isso sugere que o sucesso de uma música em uma plataforma de streaming pode influenciar seu desempenho em outras plataformas, indicando uma tendência geral no comportamento dos usuários.
</details>

<details>
<summary><b> Hipótese 3 - Correlação entre a Presença em Playlists e o Número de Streams  </b></summary>
Os testes realizados confirmaram a hipótese de que a presença de uma música em um maior número de playlists está correlacionada com um aumento significativo no número de streams. Abaixo estão os resultados dos testes estatísticos:

**Teste de Correlação:**
Após análises, verificou-se uma correlação positiva entre a presença de uma música em playlists e o número de streams, com um valor de p = 0.7835. Esse resultado indica que há uma correlação significativa entre as duas variáveis, confirmando a hipótese de que uma maior presença em playlists está associada a um aumento no número de streams.

**Teste de Regressão Linear:**
O teste de regressão revelou um R-quadrado de 0.625, o que significa que aproximadamente 62.5% da variabilidade nos streams pode ser explicada pela presença de uma música em playlists. Esse valor indica uma relação moderadamente forte entre as variáveis e sugere que a presença em playlists é um fator significativo na determinação do número de streams de uma música.

**Conclusão Geral:**
Com base nos resultados dos testes estatísticos, pode-se concluir que há uma relação significativa entre a presença de uma música em playlists e o aumento no número de streams. Isso confirma a importância das playlists como impulsionadores de sucesso para as músicas no ambiente de streaming. Portanto, a hipótese de que a presença em playlists está correlacionada com o número de streams foi validada.

</details>

<details>
<summary><b> Hipótese 4 - Relação entre o Número de Músicas de um Artista e o Total de Streams no Spotify  </b></summary>

Os resultados da análise indicam uma correlação positiva e significativa entre o número de músicas disponíveis de um artista no Spotify e o total de streams acumulados. Os testes estatísticos realizados revelaram o seguinte:

**Teste de Correlação:**
Foi observada uma correlação positiva entre o número de músicas de um artista e o total de streams no Spotify, com um valor de p = 0.7783. Esse resultado sugere uma associação significativa entre as duas variáveis, apoiando a hipótese de que um maior catálogo de músicas está relacionado a um aumento nos streams.

**Teste de Regressão Linear:**
O teste de regressão linear apresentou um R-quadrado de 0.606, indicando que aproximadamente 60.6% da variação nos streams pode ser explicada pelo número de músicas de um artista no Spotify. Esse valor aponta para uma relação positiva e substancial entre as variáveis, evidenciando que um aumento no número de faixas está associado a um aumento significativo na quantidade de streams.

**Conclusão Geral:**
Com base nos resultados dos testes estatísticos, podemos concluir que existe uma relação estatisticamente significativa entre o número de músicas de um artista e o total de streams no Spotify. Isso destaca a importância da disponibilidade do catálogo de um artista para o sucesso na plataforma de streaming. Portanto, a hipótese de que o número de faixas de um artista está relacionado ao número de streams foi validada.

</details>

<details>
<summary><b> Hipótese 5- Influência das Características Musicais no Número de Streams no Spotify  </b></summary>

Após análise, concluiu-se que as características das músicas têm impacto variado no sucesso em termos de número de streams no Spotify. Os resultados dos testes estatísticos são os seguintes:

**Teste de Correlação:**
Observou-se uma correlação negativa muito fraca entre todas as características das músicas e o número de streams no Spotify, com valores próximos de zero. Isso sugere uma relação mínima ou inexistente entre essas variáveis.

**Teste de Significância:**
Apenas a variável "speechiness" apresentou diferença significativa entre suas categorias e o número de streams. Isso indica que o conteúdo falado na música tem alguma influência no número de streams, mas as outras características não demonstraram uma diferença significativa.

**Teste de Regressão Linear:**
A análise de regressão linear mostrou que algumas características da música, como "danceability" e "speechiness", têm uma influência significativa no número de streams. No entanto, outras características, como "valence", "energy", "acousticness", "instrumentalness" e "liveness", não apresentaram uma relação estatisticamente significativa com os streams.

**Conclusão Geral:**
Considerando os resultados dos testes estatísticos e a análise dos coeficientes de regressão, optou-se por refutar a hipótese de que as características das músicas influenciam o sucesso em termos de número de streams no Spotify. Embora algumas características, como "danceability" e "speechiness", pareçam ter impacto significativo, outras não demonstraram uma associação clara com o número de streams. Portanto, a influência das características musicais no sucesso das músicas em termos de streams no Spotify não pode ser generalizada, e a relação entre essas variáveis é mais complexa do que inicialmente previsto.
</details>

</details>

<details>
<summary><b> 💡 Recomendações  </b></summary>

Com base nas conclusões da análise exploratória dos dados e no objetivo de ajudar o novo artista a alcançar o sucesso, aqui estão algumas sugestões:

**Diversificação do Conteúdo Musical:** Embora as características das músicas não demonstram uma influência clara no número de streams, é importante diversificar o conteúdo musical para atrair uma ampla audiência. É recomendável experimentar criar músicas com diferentes estilos, ritmos e letras para atingir diferentes públicos-alvo.

**Aproveitar Plataformas de Playlist:** A presença em playlists é um fator significativo para o sucesso no Spotify. Portanto, é recomendável concentrar-se em promover músicas para curadores de playlists (responsável por criar as playlists editoriais da maneira mais segmentada possível, casando com o público alvo daquele gênero e organizando as músicas que fazem sentido estar dentro da playlist) e tentar garantir inclusões em playlists populares. Isso pode ser feito através de networking, promoção ativa e envio direto das  músicas do novo artista para os curadores.

**Foco na Qualidade do Conteúdo Falado:** A variável "speechiness" mostrou ter alguma influência no número de streams. Embora refutamos a análise olhando para o contexto geral, é importante prestar atenção à qualidade e ao conteúdo das partes faladas em suas músicas, como letras e interlúdios, garantindo que sejam cativantes e envolventes para os ouvintes.

**Engajamento com a Audiência:** É recomendável construir uma forte presença nas redes sociais e interagir regularmente com a base de fãs. Respondendo a comentários, participando de conversas e compartilhando conteúdos exclusivos para manter os fãs engajados e criar uma comunidade em torno da música do novo artista.

**Replicação de Estratégias Bem-Sucedidas:** Observar a correlação positiva entre as músicas mais populares no Spotify e seu desempenho nas plataformas Deezer e Apple sugere que estratégias bem-sucedidas no Spotify podem ser replicadas em outras plataformas de streaming. A gravadora pode explorar essas oportunidades para maximizar o alcance do novo artista e aumentar sua base de fãs em diferentes plataformas.

**Análise Contínua de Dados:** É recomendável se manter atualizado com as tendências do mercado musical e analisar continuamente os dados de streaming das  músicas do novo artista. Isso permitirá ajustes e adaptações em sua estratégia conforme necessário para maximizar seu potencial de sucesso.

**Colaborações com Artistas Reconhecidos:** Se possível  sugerimos parcerias com artistas já estabelecidos que podem ajudar a aumentar a visibilidade do novo artista. Procure colaborações com artistas que tenham um grande número de seguidores nas plataformas de streaming, o que pode levar a um aumento no número de streams.

Ao implementar essas sugestões e permanecer flexível e adaptável ao ambiente em constante mudança da indústria musical, o novo artista terá uma melhor chance de alcançar o sucesso desejado.


</details>

<details>
<summary><b> Links de interesse  </b></summary>

Teste não paramétrico: https://www.inf.ufsc.br/~vera.carmo/Testes_de_Hipoteses/Testes_nao_parametricos_Mann-Whitney.pdf

</details>
