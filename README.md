Essa competição de machine learning encontra-se no site Machine Hack. Fiquei em 34º no ranking.
Ela consiste na predição de energia solar gerada (DHI, DNI, GHI):

*Irradiação Horizontal Global (GHI) é a quantidade total de radiação solar por unidade de área medida em uma
superfície horizontal na Terra. Ela é composta por duas componentes: Irradiação Normal Direta (DNI) e Irradiação
Difusa Horizontal (DHI).DNI representa a parte da radiação solar que atinge a Terra em um caminho direto vindo do sol.
Já a DHI é a porção da radiação solar que atinge a Terra de forma indireta, dispersa e difusa por fatores como vapor de
água, aerossóis e nuvens na atmosfera. A relação entre GHI, DHI e DNI é expressa pela equação:
GHI = DHI + DNI * cos(α zênite).*

*Você pode encontrar mais informações sobre esses conceitos e suas definições na seguinte fonte: Solar Anywhere - Definições de Campos de Dados*


Arquitetura dos dados: <br>

Timestamp: Data e hora da medição <br>
Temperatura: Graus Celsius (°C) <br>
Ponto de Orvalho: Graus Celsius (°C) <br>
Albedo da Superfície: Fração decimal entre 0 e 1 <br>
Pressão: Hectopascais (hPa) <br>
Direção do Vento: Graus (°) <br>
Velocidade do Vento: Metros por segundo (m/s) <br>
DHI Céu Limpo: Watts por metro quadrado (W/m²) <br>
DNI Céu Limpo: Watts por metro quadrado (W/m²) <br>
GHI Céu Limpo: Watts por metro quadrado (W/m²) <br>
Fill Flag: Binário (0 ou 1) indicando se os dados estavam ausentes ou não <br>
Ozônio: Unidades Dobson (DU) <br>
Tipo de Nuvem: Esquema de classificação (0-9) indicando o tipo de cobertura de nuvens<br>
Ângulo Zenital Solar: Graus (°) <br>
Água Precipitável: Milímetros (mm) <br>
Umidade Relativa: Porcentagem (%) <br>




Para lidar com esse problema utilizei técnicas de séries temporais. No notebook você pode acompanhar 
passo a passo do procedimento que consiste na análise dos dados com gráficos, seu devido tratamento, 
criação de novas features e por fim a criação de um modelo com XGboost. Testei outros algoritmos
e ele foi o que melhor performou, além de ser não ter problemas em entregar 3 variáveis target.
