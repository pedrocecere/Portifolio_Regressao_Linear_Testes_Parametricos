# TESTES PARAMÉTRICOS E REGRESSÃO LINEAR PARA TAXA DE OCUPAÇÃO DE IMÓVEIS

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
- **Outliers:** Valores extremos que podem distorcer a análise dos dados. Importante identificá-los e tratá-los para garantir a precisão das análises estatísticas.
- **Multicolinearidade:** Situação onde duas ou mais variáveis independentes estão altamente correlacionadas, o que pode dificultar a interpretação dos coeficientes da regressão.
- **Homocedasticidade:** Propriedade dos resíduos do modelo de regressão de terem variância constante. A heterocedasticidade pode levar a erros em testes estatísticos e previsões.
- **Normalidade dos Resíduos:** Os resíduos devem seguir uma distribuição normal para que os testes estatísticos sejam válidos. A falta de normalidade pode indicar a necessidade de ajustes no modelo.

# 3. Pipeline de solução

# 4. Tecnologias e ferramentas

# 6. Principais Insights Retirados do Projeto

### 6.1 Correlação Positiva Significativa: 
A taxa de ocupação das casas aumenta com o número médio de quartos, indicando que imóveis com mais quartos tendem a ter maior taxa de ocupação.
### 6.2 Efeito dos Outliers:
A alta correlação inicial entre variáveis foi significativamente reduzida após a remoção de outliers, sugerindo que os outliers tinham um impacto considerável nas correlações observadas.
### 6.3 Influência de Desabrigados: 
Bairros com maior número de desabrigados apresentam menor taxa de ocupação de residências, indicando uma relação inversa entre a quantidade de desabrigados e a ocupação dos imóveis.
### 6.4 Multicolinearidade: 
As variáveis com alta multicolinearidade foram identificadas e removidas para melhorar a precisão do modelo.
### 6.5 Performance do Modelo: 
O modelo de regressão apresentou boa performance com um coeficiente R² acima de 0.8, mas ajustes foram necessários para atender às suposições de homocedasticidade, normalidade dos resíduos e independência dos erros.
### 6.6 Validação das Suposições: 
O modelo final mostrou que a maioria das suposições da regressão linear foi satisfeita, com exceção da normalidade dos resíduos, que indicou a necessidade de considerar ajustes adicionais ou a aceitação de um modelo "bom o suficiente".

# 7. Modelagem

### 7.1 Carregamento dos Dados:
   - Dados foram carregados e inicialmente explorados para entender a estrutura e as características das variáveis.

### 7.2 Exploração e Limpeza dos Dados:
   - Análise de correlação inicial indicou a presença de outliers que afetaram as correlações observadas.
   - Dados foram limpos removendo outliers para obter uma visão mais precisa das relações entre variáveis.
   - Identificação e tratamento de multicolinearidade usando o Variance Inflation Factor (VIF). Variáveis com VIF > 5 foram removidas.

### 7.3 Testes Estatísticos:
   - **Teste de Linearidade:** Verificação se a relação entre variáveis independentes e dependentes é linear. Utilização do teste linear_rainbow.
   - **Teste de Independência dos Erros:** Aplicação do Teste de Durbin-Watson para verificar autocorrelação nos resíduos.
   - **Teste de Homocedasticidade:** Aplicação do Teste de Goldfeld-Quandt para verificar se a variabilidade dos resíduos é constante.
   - **Teste de Normalidade dos Resíduos:** Criação de QQ Plot e aplicação do Teste de Shapiro-Wilk para verificar se os resíduos seguem uma distribuição normal.

### 7.4 Validações:
   - **Linearidade:** Supondo que a relação é linear, confirmada pelo gráfico e teste linear_rainbow.
   - **Independência dos Erros:** Confirmado pelo Teste de Durbin-Watson e análise visual dos resíduos.
   - **Homocedasticidade:** Confirmado pelo Teste de Goldfeld-Quandt, indicando que a variabilidade dos resíduos é constante.
   - **Normalidade dos Resíduos:** Identificado que os resíduos não passaram no teste de normalidade, sugerindo a necessidade de ajustes adicionais ou aceitação do modelo com limitações.

### 7.5 Regras Aplicadas e Modelo Detalhado:
   - Variáveis com alta multicolinearidade foram removidas para melhorar a precisão do modelo.
   - Variáveis com valor-p maior que 0.05 foram removidas, focando apenas nas variáveis com significância estatística.
   - O modelo final é uma regressão linear múltipla ajustada para satisfazer a maioria das suposições, com algumas limitações reconhecidas.
