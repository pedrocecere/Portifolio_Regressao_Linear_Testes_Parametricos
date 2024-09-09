# TESTES PARAMÉTRICOS E REGRESSÃO LINEAR PARA TAXA DE OCUPAÇÃO DE IMÓVEIS
![https__img migalhas com br__SL__gf_base__SL__empresas__SL__MIGA__SL__imagens__SL__2023__SL__02__SL__15__SL__d90cd13d-88c0-4f57-9aa5-c7878b109c0b jpg _PROC_CP65](https://github.com/user-attachments/assets/bff56a72-8584-40f8-b0a9-412dd4347128)
# 1. Descrição do projeto

- Este projeto tem como objetivo principal analisar as variáveis que influenciam diretamente a taxa de ocupação de imóveis em uma cidade específica. A análise estatística foi conduzida com uma forte ênfase em testes paramétricos, garantindo que todas as decisões fossem embasadas em fundamentos estatísticos sólidos.

- Um dos principais diferenciais deste projeto é a inclusão intencional de erros em determinadas etapas, para evidenciar a importância crucial de utilizar os testes corretos, aplicar as transformações adequadas nos dados e fundamentar todas as decisões em fatos estatísticos concretos. A análise é feita de forma minuciosa, com decisões sendo tomadas a cada etapa, simulando um problema de negócio real em um cenário verossímil.

- O processo envolve uma análise iterativa dos dados, onde hipóteses são testadas e modelos são ajustados até encontrarmos a melhor solução possível. O foco está em fornecer ao tomador de decisão uma resposta precisa e confiável para o problema de negócio em questão, demonstrando como a estatística e a ciência de dados podem ser utilizadas para resolver desafios do mundo real.

# 2. Problema de negócio e objetivos
### 2.1 Qual o problema de negócio deste projeto?

O problema de negócio deste projeto é entender quais fatores influenciam a taxa de ocupação de imóveis em um contexto urbano. A análise visa identificar as variáveis que mais afetam a ocupação dos imóveis, considerando aspectos como mobilidade urbana, saneamento e condições gerais dos bairros. A ideia é fornecer insights que possam auxiliar na tomada de decisões relacionadas a planejamento urbano e políticas públicas.

### 2.2 Quais são os objetivos e benefícios do projeto?

**Objetivos:**
- Identificar e quantificar os fatores que mais influenciam a taxa de ocupação dos imóveis.
- Avaliar a correlação entre diferentes variáveis, como o número de quartos e o índice de acessibilidade.
- Determinar a presença de outliers e multicolinearidade nos dados para melhorar a precisão do modelo.
- Validar as suposições do modelo de regressão linear para garantir a robustez das previsões.

**Benefícios:**
- Fornecer uma compreensão mais clara dos fatores que afetam a ocupação de imóveis, facilitando o planejamento urbano e a alocação de recursos.
- Ajudar na formulação de políticas públicas mais eficazes relacionadas a mobilidade e saneamento.
- Melhorar a precisão das previsões relacionadas à ocupação de imóveis, contribuindo para decisões mais informadas.

### 2.3 Quais são os conceitos importantes a conhecer no contexto de ocupação imobiliária, mobilidade urbana, saneamento e assuntos correlatos?

**Conceitos Importantes:**
- **Taxa de Ocupação de Imóveis:** Percentual de imóveis ocupados em relação ao total de imóveis disponíveis. Influenciado por fatores como localização, tamanho e condições do imóvel.
- **Mobilidade Urbana:** Relaciona-se à facilidade com que os residentes podem se deslocar dentro da cidade. Impacta a atratividade de uma localização para ocupação de imóveis.
- **Saneamento:** Refere-se à infraestrutura para gestão de resíduos e fornecimento de água limpa. Afeta diretamente a qualidade de vida e, consequentemente, a taxa de ocupação dos imóveis.
  
# 3. Pipeline de solução

- Entendendo o problema de negócio
- Análise exploratória dos dados
- Preparação e limpeza dos dados
- Aplicação dos testes estatísticos
- Criação do modelo de Regressão Linear

# 4. Tecnologias e ferramentas

- Python
  - Pandas
  - Numpy
  - Matplotlib
  - Seaborn
  - Statsmodels
  - Scipy
  - Sciki-Learn
  - Pylab   
- Estatística
- Ferramentas de limpeza e visualização de dados

# 5. Principais insights retirados do projeto

- Quantidade de quartos por residência:
Existe uma média de cerca de 6,28 quartos por habitação (variável numero_medio_quartos_por_residencia).
- Taxa de criminalidade e Proporção de lotes:
Há uma variação muito grande para a taxa de criminalidade (variável taxa_criminalidade), pois podemos ver que a taxa de criminalidade mais baixa é de 0,006, enquanto a mais alta é de 88,97. Provavelmente são valores outliers, pois são muito diferentes da mediana e até 75% do quarti. O mesmo comportamento se percebe na variável de proporção de lotes.
- Influência de Desabrigados: 
Bairros com maior número de desabrigados apresentam menor taxa de ocupação de residências, indicando uma relação inversa entre a quantidade de desabrigados e a ocupação dos imóveis.
- Correlação entre variáveis: 
Observamos uma correlação significativa entre as variáveis taxa de poluição e proporção de empresas. A variável taxa de poluição também apresenta uma alta correlação positiva com a idade média das residências e uma correlação negativa significativa com a distância ao centro.
A proporção de empresas tem uma alta correlação com o imposto residencial.
A taxa de ocupação mostra uma alta correlação com o número médio de quartos por residência e uma correlação negativa significativa com a taxa de desabrigados.
- Performance do Modelo: 
O modelo de regressão apresentou boa performance com um coeficiente R² acima de 0.8, mas ajustes foram necessários para atender às suposições de homocedasticidade, normalidade dos resíduos e independência dos erros.

# 6. Modelagem

### 6.1 Carregamento dos Dados:
   - Os dados deste estudo foram carregados através de uma arquivo csv que se encontra na pasta deste repositório. Os pacotes foram instalados e importados para utilização no modelo.

### 6.2 Exploração e Limpeza dos Dados:
   - Análise de correlação inicial indicou a presença de outliers que afetaram as correlações observadas.
   - A análise exploratória iniciou verificando a presença ou não de valores nulos no dataset, eles representam problemas para testes estatísticos e modelos de machine learning.
   - Foi feita uma análise das estatíticas gerais do conjunto de dados utilizando o método describe(), desta análise podemos entender algumas variáveis provavelmente contém outliers.
   - Plotamos a distribuição da variável dependente (taxa de ocupação), percebemos que existe uma assimatria. Foi utilizado o método skewness para verificar a assimetria de todo conjunto. Essa assimetria foi corrigida utilizando a tranformação de log(), para deixar os dados na mesma escala.
   - Após ajustar nossa variável alvo partimos para as análises bivariadas, através da matriz de correlação percebemos que algumas variáveis tinham forte correlação, o que significa um problema para nosso modelo estatístico.
   - Verificamos todas as correlações altas (entre 0.59 e 0.99), sejam positivas ou negativas
   - Mesmo sabendo do problema destas variáveis, deixamos elas no conjunto para provocar o erro e avaliar o resultado.  

### 6.3 Validações e métodos:
   - **Variance Inflation Factor (VIF)**: Utilizaremos o Variance Inflation Factor (VIF), para verificar se há multicolinearidade nos dados. O Variance Inflation Factor (VIF) é uma medida que     quantifica o quanto a variância de um estimador de regressão (coeficiente) é aumentada devido à multicolinearidade na regressão múltipla. A multicolinearidade ocorre quando há correlações altas   entre duas ou mais variáveis explicativas (independentes) em um modelo de regressão, o que pode dificultar a estimação dos coeficientes da regressão com precisão.
   - **Standar Scaler**: Utilizamos o StandarScaler() para padronizar a escala dos dados, pois nosso modelo de Regressão Linear supões que os dados estejam na mesma escala.

### 6.4 Testes Estatísticos Aplicados:
   - **Teste de Regressão Linear**: Utilizamos o modelo de Regressão Lienar do statsmodels para verificar a relação multipla entre variáveis do dataset.
   - **Teste de Linearidade:** Verificação se a relação entre variáveis independentes e dependentes é linear. Utilização do teste linear_rainbow.
   - **Teste de Independência dos Erros:** Aplicação do Teste de Durbin-Watson para verificar autocorrelação nos resíduos.
   - **Teste de Homocedasticidade:** Aplicação do Teste de Goldfeld-Quandt para verificar se a variabilidade dos resíduos é constante.
   - **Teste de Normalidade dos Resíduos:** Criação de QQ Plot e aplicação do Teste de Shapiro-Wilk para verificar se os resíduos seguem uma distribuição normal.

### 6.5 Regras Aplicadas e Resultado do Modelo:
   - Variáveis com alta multicolinearidade foram removidas para melhorar a precisão do modelo.
   - Variáveis com valor-p maior que 0.05 foram removidas, focando apenas nas variáveis com significância estatística.
   - O modelo final é uma regressão linear múltipla ajustada para satisfazer a maioria das suposições, com algumas limitações reconhecidas.
   - Obtivemos um R-squared de aproximadamente 0.8, o que indica que nossas variáveis independentes explicam 80% da variável dependente Taxa de Ocupação, este é um resultado considerado satisfatório para o escopo do projeto.

![Captura de tela 2024-09-09 101850](https://github.com/user-attachments/assets/9432a7c9-356e-431e-b84f-a1d7533a1289)

