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
