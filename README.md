# Projeto de Redução de Custos de Manutenção do Sistema de Ar de Caminhões

## Descrição do Projeto
Este projeto tem como objetivo reduzir os custos de manutenção do sistema de ar de uma empresa de transporte, utilizando técnicas de Machine Learning para identificar e prever possíveis falhas no sistema. A empresa vem notando um aumento significativo nas despesas relacionadas à manutenção desse sistema nos últimos três anos, mesmo mantendo o tamanho da frota relativamente constante. Com base nos dados históricos e atuais, nossa meta é otimizar os processos de manutenção e evitar reparos corretivos caros.

## Problema
A empresa está enfrentando três tipos de custos relacionados à manutenção do sistema de ar:
- **Inspeção sem defeito no sistema de ar:** Custo de $10 por caminhão inspecionado.
- **Manutenção preventiva de caminhões com defeito no sistema de ar:** Custo de $25 por caminhão.
- **Manutenção corretiva de caminhões que falham durante a operação:** Custo de $500 por caminhão.

A falta de uma abordagem preditiva tem levado a um aumento de manutenções corretivas, que são consideravelmente mais caras. 

## Objetivos
1. **Reduzir os custos de manutenção do sistema de ar utilizando técnicas de Machine Learning.**
2. **Identificar os principais fatores que indicam falhas no sistema de ar.**
3. **Avaliar o modelo preditivo com os dados do ano corrente para apresentar resultados que possam convencer a diretoria a expandir a solução para outros sistemas de manutenção.**

## Dados Utilizados
O projeto faz uso de dois arquivos principais de dados:
- **air_system_previous_years.csv:** Contém os dados históricos dos anos anteriores a 2022, com 178 colunas de informações codificadas.
- **air_system_present_year.csv:** Contém os dados do ano corrente (2022) e será usado para avaliar a performance final do modelo.
  
> **Observação:** Dados ausentes no banco de dados são denotados como `na`.

### Classificação dos Caminhões
Os caminhões são classificados da seguinte forma:
- **pos:** Caminhões com defeitos no sistema de ar.
- **neg:** Caminhões com defeitos em outros sistemas que não o de ar.

## Metodologia
1. **Análise Exploratória de Dados (EDA):** Analisamos os dados fornecidos, identificando possíveis valores ausentes e padrões.
2. **Pré-processamento dos Dados:** Tratamento de dados faltantes e codificados, além da normalização/transformação de colunas quando necessário. Por fim, a aplicação de redução de dimensionalidade com PCA.
3. **Treinamento de Modelos Preditivos:** Testamos diferentes algoritmos de machine learning (Regressão Logística, Random Forest, etc.) para identificar falhas no sistema de ar. Focamos em um alto recall pois o custo dos falsos negativos era altíssimo. Portanto o trade-off optando por um recall alto ao invés de uma alta precision foi necessário.
4. **Avaliação de Performance:** Utilizamos o arquivo `air_system_present_year.csv` para avaliar o desempenho final do modelo.
5. **Análise dos Fatores de Risco:** Identificação dos principais fatores que indicam uma possível falha no sistema de ar.

## Resultados
- **Análise dos fatores influentes**: Realizamos a análise dos fatores que mais explicavam a variabilidade do conjunto através dos componentes principais encontrados.
- **Redução de gastos para a empresa**: Ao criar o modelo de classificação, conseguimos obter, no dataset do present_year, uma economia de mais de $160.000,00.
