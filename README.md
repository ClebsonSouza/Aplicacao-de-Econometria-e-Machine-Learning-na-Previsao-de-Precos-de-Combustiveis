# Projeto_Preco_da_Gasolina
Resumo: analisar através de uma abordagem econométrica e algoritmos de regressão de aprendizado de máquina o comportamento dos preços da gasolina na cidade de João Pessoa- PB, no período de janeiro de 2020 até junho de 2023.
Linguagem: Python
Modelos utilizados: Linear Regression, Random Forest Regressor e Decision Tree Regressor
Variável dependente: preços da gasolina (média semanal)
Variáveis explicativas: Preços Petróleo Brent Futuros (média semanal), Dólar Americano por Real Brasileiro (média semanal) e Euro por Real Brasileiro (média semanal).
Fonte das bases de dados:
A Série Histórica de Preços de Combustíveis foi encontrado em: https://www.gov.br/anp/pt-br/centrais-de-conteudo/dados-abertos/serie-historica-de-precos-de-combustiveis
Petróleo Brent Futuros em: https://br.investing.com/commodities/brent-oil-historical-data
USD/BRL - Dólar Americano Real Brasileiro em: https://br.investing.com/currencies/usd-brl-historical-data
EUR/BRL - Euro Real Brasileiro em: https://br.investing.com/currencies/eur-brl-historical-data
Foram considerados apenas valores nominais (não houve deflação das séries).

Econometria e Aprendizado de Máquina

Econometria é a ciência que busca extrair conhecimento econômico a partir de dados empíricos, desenvolvendo métodos estatísticos para estimar relações, testar teorias e avaliar o impacto de decisões e políticas econômicas. Ela se concentra em estabelecer conclusões estatisticamente válidas, identificar padrões nos dados e resumi-los de forma informativa, com foco em inferência estatística e análise de propriedades teóricas.
Aprendizado de Máquina é a ciência de fazer com que os computadores aprendam a realizar tarefas sem serem explicitamente programados para isso. Ela se concentra em gerar previsões precisas, minimizando o erro quadrático médio, mesmo diante de restrições computacionais. Os modelos de aprendizado de máquina lidam com um trade-off entre viés e variância e frequentemente usam técnicas de regularização para estimativas de parâmetros enviesadas.
Embora essas áreas compartilhem fundamentos teóricos e matemáticos e busquem resolver problemas em cenários de incerteza, suas ênfases diferem: a econometria foca na inferência estatística e interpretação, enquanto o aprendizado de máquina está mais centrado em previsões e desempenho preditivo.

Conclusão:

Abordagem econométrica: 
Este modelo de regressão linear tem alguns pontos fortes, mas também apresenta algumas ineficiências e problemas a serem considerados:
•	R-quadrado (R-squared): O R-quadrado de 0.801 é um valor significativo, indicando que aproximadamente 80.1% da variabilidade em "Price_sem_gasoline" é explicada pelas variáveis independentes no modelo. Isso sugere que o modelo se ajusta bem aos dados, o que é uma boa notícia.

•	Método (Method): O modelo foi ajustado usando o método de Mínimos Quadrados, uma técnica comum em regressão linear, o que é apropriado.

•	No. Observações (No. Observations): Ter um total de 174 observações é razoavelmente substancial para um modelo de regressão linear.

•	Df Residuals e Df Model: Ter informações sobre os graus de liberdade dos resíduos e do modelo é importante para entender a complexidade do modelo.

•	Coeficientes das Variáveis: Os coeficientes estimados para as variáveis independentes são estatisticamente significativos, o que sugere que essas variáveis são importantes para explicar "Price_sem_gasoline".

No entanto, existem algumas ineficiências e questões a serem consideradas:

•	Teste Jarque-Bera (JB): O resultado deste teste indica uma possível não normalidade e assimetria nos resíduos. Isso sugere que os resíduos não seguem uma distribuição normal, o que é uma violação da suposição da regressão linear de que os resíduos devem ser normalmente distribuídos. Isso pode afetar a validade das inferências estatísticas feitas com base no modelo.

•	Variável Explicativa "Price_sem_dolar": O fato dessa variável ter um sinal contraintuitivo pode sugerir a presença de uma quebra estrutural nos dados. Isso significa que algo pode ter mudado durante o período de coleta de dados que afetou a relação entre "Price_sem_dolar" e "Price_sem_gasoline". É importante investigar essa questão e considerar se é necessário incluir variáveis adicionais para capturar essa mudança estrutural.

•	Covariância Não Robusta: O modelo assumiu uma covariância não robusta. Se houver heterocedasticidade nos dados (variância dos erros não constante), isso pode afetar a precisão das estimativas dos coeficientes e dos testes de significância.

•	Teste Durbin-Watson: Embora o valor de Durbin-Watson sugira que não há autocorrelação significativa nos resíduos, é importante conduzir uma análise mais aprofundada para confirmar isso.

Sugestões para melhorar o modelo e a análise incluem:

•	Realizar testes de normalidade mais detalhados nos resíduos, como o teste Shapiro-Wilk, para avaliar a normalidade dos resíduos de forma mais robusta.

•	Investigar a quebra estrutural nos dados, se aplicável, e considerar a inclusão de variáveis de quebra estrutural no modelo.

•	Avaliar a presença de heterocedasticidade nos resíduos e, se detectada, considerar a utilização de um modelo de regressão robusto.

•	Explorar outras variáveis que possam influenciar "Price_sem_gasoline" e que não foram incluídas no modelo inicial, especialmente aquelas que podem estar relacionadas ao período de pandemia, se for relevante.

•	Realizar análises de sensibilidade, como a exclusão de variáveis menos significativas ou a inclusão de variáveis de interação, para verificar se o modelo pode ser aprimorado.

Abordagem dos modelos de Aprendizado de Máquina

Linear Regression:
MSE = 0.14884967579074943
MAE = 0.3059498581252669
R2 = 0.8435768004136235

Random Forest Regressor:
MSE = 0.04604213464959734
MAE = 0.15699692507220245
R2 = 0.9516152253646738

Decision Tree Regressor:
MSE = 0.06847941655754958
MAE = 0.14906551083943329
R2 = 0.928036326670952

Dessa forma:

MSE (Mean Squared Error): Quanto menor o MSE, melhor. Nesse caso, o menor MSE é do modelo RandomForestRegressor (0.046), indicando que ele tem a menor média dos quadrados dos erros, ou seja, é o modelo que se ajusta melhor aos dados.

MAE (Mean Absolute Error): Quanto menor o MAE, melhor. Mais uma vez, o modelo RandomForestRegressor (0.157) tem o menor valor, indicando que suas previsões têm o menor erro médio absoluto em relação aos valores reais.

R2 (R-squared): Quanto mais próximo de 1 o R2, melhor. Aqui, novamente, o modelo RandomForestRegressor (0.952) tem o valor mais alto, o que significa que ele explica a maior parte da variabilidade dos dados, tornando suas previsões mais precisas.
Com base nessas métricas, o modelo Random Forest Regressor apresenta o melhor desempenho, com o menor MSE, MAE e o maior R2. Portanto, sugere-se que o Random Forest Regressor teve a melhor performance entre os três modelos.


