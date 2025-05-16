# Análise de Desempenho Estudantil

Este repositório contém o resultado da análise de dados realizada sobre o desempenho de estudantes em duas escolas portuguesas, utilizando o dataset "Student Performance" do UCI Machine Learning Repository.

## Definição do Problema e Perguntas

O conjunto de dados "Student Performance" contém informações sobre o desempenho de estudantes do ensino secundário em duas escolas portuguesas, abrangendo duas disciplinas: Matemática (student-mat.csv) e Português (student-por.csv). 

### Problema Central

Identificar os fatores que mais influenciam o desempenho acadêmico dos estudantes (expresso pelas notas finais - G3) e construir modelos preditivos capazes de estimar esse desempenho ou classificar os alunos em categorias de rendimento.

### Perguntas Principais

1. Quais são os principais fatores demográficos (sexo, idade) que afetam o desempenho dos alunos em Matemática e Português?
2. Como as características socioeconômicas da família do estudante (educação dos pais, tamanho da família, status de coabitação dos pais) se relacionam com suas notas finais?
3. Qual é o impacto dos hábitos de estudo (tempo de estudo semanal, falhas em classes anteriores) no desempenho final dos alunos?
4. Atividades extracurriculares (pagas ou não) e o uso da internet (para fins não escolares) influenciam positivamente ou negativamente as notas?
5. Fatores comportamentais como o consumo de álcool (durante a semana e fim de semana) e a frequência de saídas com amigos estão associados a um menor desempenho acadêmico?
6. A qualidade das relações familiares e o apoio educacional fornecido pela escola ou família têm um papel significativo nas notas dos estudantes?
7. Existem diferenças significativas no desempenho e nos fatores influenciadores entre as disciplinas de Matemática e Português?
8. É possível construir um modelo de regressão preciso para prever a nota final (G3) dos alunos com base nas características disponíveis? Quais variáveis são mais preditivas?
9. É possível desenvolver um modelo de classificação eficaz para categorizar os alunos em diferentes níveis de desempenho com base em seus atributos? Quais variáveis são mais discriminantes?
10. Quais são as implicações práticas das descobertas para educadores, pais e formuladores de políticas educacionais visando a melhoria do desempenho estudantil?

### Utilidade Pública do Problema

A compreensão dos fatores que afetam o desempenho estudantil tem grande utilidade pública:

- **Informar Políticas Educacionais**: Identificar os principais preditores de sucesso ou fracasso escolar para formulação de políticas públicas mais eficazes.
- **Orientar Intervenções Pedagógicas**: Desenvolver estratégias pedagógicas personalizadas e programas de tutoria focados nos alunos de maior risco.
- **Engajar Pais e Responsáveis**: Destacar a importância do ambiente familiar e envolvimento dos pais no processo educacional.
- **Promover a Equidade**: Identificar disparidades para criar iniciativas que visem promover maior equidade no sistema de ensino.
- **Prevenção do Abandono Escolar**: Identificação precoce de alunos com maior propensão a notas baixas para intervenções preventivas.

## Dicionário de Dados

### Atributos Comuns a Ambos os Datasets:

1. **school**: Escola do estudante ("GP" - Gabriel Pereira ou "MS" - Mousinho da Silveira)
2. **sex**: Sexo do estudante ("F" - feminino ou "M" - masculino)
3. **age**: Idade do estudante (15 a 22)
4. **address**: Tipo de endereço residencial ("U" - urbano ou "R" - rural)
5. **famsize**: Tamanho da família ("LE3" - <=3 ou "GT3" - >3)
6. **Pstatus**: Status de coabitação dos pais ("T" - morando juntos ou "A" - separados)
7. **Medu**: Nível de educação da mãe (0 - nenhum, 1 - 4ª série, 2 - 5ª à 9ª série, 3 - ensino secundário, 4 - ensino superior)
8. **Fedu**: Nível de educação do pai (0 - nenhum, 1 - 4ª série, 2 - 5ª à 9ª série, 3 - ensino secundário, 4 - ensino superior)
9. **Mjob**: Trabalho da mãe ("teacher", "health", "services", "at_home", "other")
10. **Fjob**: Trabalho do pai ("teacher", "health", "services", "at_home", "other")
11. **reason**: Razão para escolher esta escola ("home", "reputation", "course", "other")
12. **guardian**: Guardião do estudante ("mother", "father", "other")
13. **traveltime**: Tempo de viagem de casa para a escola (1: <15 min, 2: 15-30 min, 3: 30min-1h, 4: >1h)
14. **studytime**: Tempo de estudo semanal (1: <2h, 2: 2-5h, 3: 5-10h, 4: >10h)
15. **failures**: Número de reprovações anteriores (n se 1<=n<3, senão 4)
16. **schoolsup**: Suporte educacional extra da escola (binário: "yes" ou "no")
17. **famsup**: Suporte educacional familiar (binário: "yes" ou "no")
18. **paid**: Aulas extras pagas na disciplina (binário: "yes" ou "no")
19. **activities**: Atividades extracurriculares (binário: "yes" ou "no")
20. **nursery**: Frequentou creche (binário: "yes" ou "no")
21. **higher**: Deseja cursar ensino superior (binário: "yes" ou "no")
22. **internet**: Acesso à internet em casa (binário: "yes" ou "no")
23. **romantic**: Com um relacionamento romântico (binário: "yes" ou "no")
24. **famrel**: Qualidade das relações familiares (1 - muito ruim a 5 - excelente)
25. **freetime**: Tempo livre após a escola (1 - muito baixo a 5 - muito alto)
26. **goout**: Sair com amigos (1 - muito baixo a 5 - muito alto)
27. **Dalc**: Consumo de álcool durante a semana (1 - muito baixo a 5 - muito alto)
28. **Walc**: Consumo de álcool no fim de semana (1 - muito baixo a 5 - muito alto)
29. **health**: Estado de saúde atual (1 - muito ruim a 5 - muito bom)
30. **absences**: Número de faltas escolares (0 a 93)

### Atributos Específicos da Disciplina:
1. **G1**: Nota do primeiro período (0 a 20)
2. **G2**: Nota do segundo período (0 a 20)
3. **G3**: Nota final (variável alvo, 0 a 20)

### Quantidade de Instâncias e Características:
- **Matemática**: 395 instâncias, 33 características.
- **Português**: 649 instâncias, 33 características.
- Não há valores ausentes nos datasets.

## Metodologia

### Limpeza de Dados e Análise Exploratória

- **Dimensões dos Dados**:
  - Matemática: 395 instâncias, 33 colunas.
  - Português: 649 instâncias, 33 colunas.
- **Tipos de Dados**: Mistura de colunas numéricas (int64) e categóricas (object).
- **Valores Ausentes**: Nenhum valor ausente encontrado.
- **Estatísticas Descritivas**: Foram geradas estatísticas descritivas para as variáveis numéricas (média, desvio padrão, quartis, mínimo, máximo).

### Pré-processamento

- **Encoding de Variáveis Categóricas**:
  - Variáveis binárias ("yes"/"no") mapeadas para 0 e 1.
  - Variáveis categóricas nominais com poucas categorias mapeadas para representações numéricas.
  - Variáveis nominais com múltiplas categorias convertidas com One-Hot Encoding.
  - Após o encoding, ambos os datasets passaram a ter 42 colunas.

### Análise Exploratória de Dados (EDA)

- **Distribuição da Variável Alvo (G3)**: Histogramas para visualizar a distribuição das notas finais.
- **Detecção de Outliers**: Boxplots para as principais variáveis numéricas.
- **Correlações**: Matrizes de correlação visualizadas como heatmaps.
- **Relação com a Variável Alvo**: Boxplots comparando a distribuição de G3 em relação a diversas variáveis categóricas.

## Modelagem

### Modelagem Linear

- **Seleção de Características**:
  - Correlação de Pearson entre features numéricas e G3.
  - F-ANOVA para selecionar features relevantes.

- **Resultados**:
  - **Matemática**: MSE ≈ 4.84, R² ≈ 0.764
  - **Português**: MSE ≈ 1.40, R² ≈ 0.856

### Modelagem Não Linear

- **Modelos Treinados**:
  - **Árvore de Decisão (Regressão)**: Com hiperparâmetros padrão.
  - **Random Forest (Regressão)**: Com n_estimators=100 e outros hiperparâmetros padrão.

- **Resultados**:
  - **Matemática**:
    - Árvore de Decisão: MSE ≈ 8.09, R² ≈ 0.606
    - Random Forest: MSE ≈ 3.70, R² ≈ 0.820
  - **Português**:
    - Árvore de Decisão: MSE ≈ 2.75, R² ≈ 0.718
    - Random Forest: MSE ≈ 1.58, R² ≈ 0.838

- **Importância das Features (Random Forest)**:
  - Para ambas as disciplinas, G2 (nota do segundo período) e absences (número de faltas) foram consistentemente importantes.

## Conclusões e Respostas às Perguntas

### Análise Comparativa dos Modelos

- **Matemática**: O modelo Random Forest teve o melhor desempenho (MSE = 3.70, R² = 0.820).
- **Português**: A Regressão Linear superou ligeiramente o Random Forest (MSE = 1.40, R² = 0.856 vs. MSE = 1.58, R² = 0.838).
- **Importância das Features**: G2, absences e G1 foram consistentemente importantes em ambas as disciplinas.

### Respostas às Perguntas Principais

1. **Fatores demográficos**:
   - **Sexo**: Em Matemática, ligeira vantagem para alunos do sexo masculino; em Português, ligeira vantagem para o sexo feminino.
   - **Idade**: Correlação negativa em ambas disciplinas - alunos mais velhos tendem a ter notas inferiores.

2. **Características socioeconômicas**:
   - **Educação dos Pais**: Correlação positiva com G3 - maior nível de educação dos pais está associado a melhores notas.
   - **Tamanho da Família**: Correlação ligeiramente negativa - alunos de famílias menores podem ter desempenho um pouco melhor.
   - **Status de Coabitação dos Pais**: Pouco impacto direto isolado.

3. **Hábitos de estudo**:
   - **Tempo de Estudo**: Correlação positiva, especialmente em Português.
   - **Falhas Anteriores**: Forte correlação negativa - histórico de reprovações é um forte preditor de notas mais baixas.

4. **Atividades extracurriculares e uso da internet**:
   - **Atividades Extracurriculares**: Impacto mínimo ou ligeiramente positivo.
   - **Aulas Extras Pagas**: Impacto varia por disciplina - positivo para Matemática, ligeiramente negativo para Português.
   - **Uso da Internet**: Correlação positiva - acesso à internet em casa associado a notas ligeiramente melhores.

5. **Fatores comportamentais**:
   - **Consumo de Álcool**: Correlação negativa, especialmente em Português - maior consumo está associado a notas piores.
   - **Saídas com Amigos**: Correlação negativa - saídas frequentes podem estar associadas a notas ligeiramente inferiores.

6. **Relações familiares e apoio educacional**:
   - **Qualidade das Relações Familiares**: Impacto positivo, mas fraco.
   - **Apoio Educacional da Escola**: Correlação negativa - alunos com dificuldades provavelmente são os que mais recebem esse apoio.
   - **Apoio Educacional Familiar**: Correlação muito baixa.

7. **Diferenças entre Matemática e Português**:
   - Muitas tendências similares, mas a força de correlações varia.
   - Tempo de estudo e consumo de álcool têm impacto mais pronunciado em Português.
   - Modelos de predição tiveram desempenho diferente para cada disciplina.

8. **Modelos de regressão**:
   - É possível construir modelos precisos - R² de 0.820 (RF) para Matemática e 0.856 (RL) para Português.
   - Variáveis mais preditivas: G1, G2, failures, absences.

9. **Modelos de classificação**:
   - Não implementados nesta análise, mas as features importantes identificadas (G1, G2, failures, absences) provavelmente seriam altamente discriminantes.

10. **Implicações práticas**:
    - **Intervenção Precoce**: Importância da intervenção para alunos com dificuldades iniciais.
    - **Combate à Infrequência**: Políticas para promover a assiduidade.
    - **Apoio Socioeconômico**: Programas para famílias com menor background educacional.
    - **Conscientização sobre Hábitos**: Campanhas sobre tempo de estudo e consumo de álcool.
    - **Personalização do Ensino**: Abordagens pedagógicas diferenciadas para cada disciplina.

## Limitações do Estudo

- **Causalidade vs. Correlação**: A análise identifica correlações, mas não estabelece relações causais diretas.
- **Dados de Duas Escolas**: Resultados podem não ser generalizáveis para outros contextos.
- **Variáveis Auto-Reportadas**: Algumas informações podem estar sujeitas a vieses.
- **Outliers**: Tratamento não foi aprofundado nesta análise.
- **Hiperparâmetros dos Modelos**: Não foram otimizados extensivamente.
- **Interpretabilidade**: Modelos como Random Forest são mais difíceis de interpretar diretamente.

## Trabalhos Futuros

- **Modelagem de Classificação**: Desenvolver modelos para classificar os alunos em categorias de desempenho.
- **Análise de Interação entre Features**: Investigar como diferentes variáveis interagem.
- **Otimização de Hiperparâmetros**: Realizar um tuning mais rigoroso dos modelos.
- **Análise Longitudinal**: Investigar a progressão do desempenho ao longo do tempo.
- **Coleta de Dados Adicionais**: Incluir fatores psicológicos ou qualidade do ensino percebida.
- **Comparação com Outros Contextos**: Replicar o estudo em diferentes escolas ou países.


![Portugues_G3_pearson_correlation](https://github.com/user-attachments/assets/6874cc14-f412-4e83-844b-58d1e7a1ccbe)
![Portugues_G3_distribution](https://github.com/user-attachments/assets/5dbf4695-2d3d-461c-a26b-1e04f2f1b8d4)
![Portugues_correlation_matrix](https://github.com/user-attachments/assets/5d5775eb-672e-4f23-bc54-0e15ce01f234)
![Matematica_G3_pearson_correlation](https://github.com/user-attachments/assets/bc2c85da-2d21-4863-b88b-1aa9ff7d963a)
![Matematica_G3_distribution](https://github.com/user-attachments/assets/8aaac60b-7c90-492a-b3d9-6f606613727e)
![Matematica_correlation_matrix](https://github.com/user-attachments/assets/29dafdc8-84f9-4215-8f8f-c0bc9a88b95f)











