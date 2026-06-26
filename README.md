# Análise de Turnover da IBM

# Problema de Negócio

Contexto: A IBM, gigante global de tecnologia e consultoria, possui um quadro extenso de talentos em um mercado altamente competitivo.

Problema interno do RH: A alta taxa de turnover (Attrition) está gerando custos enormes – repor um profissional pode consumir de 50% a 200% do salário anual do cargo.

Análise proposta: Vamos cruzar a variável Attrition com os principais fatores internos para descobrir o que está expulsando nossos talentos:

Satisfação no trabalho;

Realização de horas extras;
Faixa salarial;
Tempo de casa;
Equilíbrio entre vida e trabalho.

Resultado prático: Entregaremos ao RH da IBM uma lista objetiva de fatores de risco (ex: perfis com baixa satisfação + muitas horas extras). Com isso, o time poderá agir preventivamente, ajustando políticas e criando planos de retenção antes que o pedido de demissão chegue.

# Premissas da análise

Foram coletados os dados de 1471 funcionários da IBM.
Não existem datas de contratação dos funcionários.
Não há menção a qual período se refere esse dataset.

# Estratégia da solução

O método Fato-Dimensão foi usado para desenvolver a análise de dados.

# Passo 1: Resumir o contexto em uma pergunta aberta

As perguntas abertas são um tipo de demanda muito comum em análise de dados nas quais a demanda possui N possíveis soluções e cabe ao analista de dados avaliar as possibilidades e escolher a alternativa com o maior retorno e o menor esforço possível. Para essa análise, foi definida a seguinte pergunta aberta:

**Quais fatores mais contribuem para o turnover de funcionários?**

# Passo 2: Transformar pergunta aberta em fechada

As perguntas fechadas são um tipo de demanda muito comum na área de análise de dados. Essa demanda contém todos os detalhes da análise de dados e direciona o analista exatamente para o que precisa ser feito. Geralmente, a pergunta fechada é a escolha de uma solução entre todas as alternativas possíveis, feita por um profissional mais sênior da área.

Para essa análise, foi definida a seguinte pergunta fechada:

**Pergunta Fechada: faça uma análise do turnover da IBM, analisando o porquê de o funcionário ter uma alta taxa de rotatividade. Será porque ele ganha abaixo da média? Por que ele faz hora extra? Por que não há promoção? Por que não há visão de futuro dentro da empresa para a carreira dele? Por que ele recebe abaixo do que a média do cargo considera, considerando o mercado como um todo?**

# Passo 3: Definição da Coluna Fato

O Fato é a coluna de interesse que representa o ponto focal da análise. Nesse caso, a coluna "Attrition" mostra se o funcionário está na empresa ou se já saiu.

# Passo 4: Identificação das Dimensões

As colunas foram agrupadas em dimensões comuns que fornecem mais detalhes sobre o Fato que será analisado. Foram organizadas as seguintes dimensões:

Perfil Pessoal e Demográfico: Age, Gender, MaritalStatus, Education, EducationField, DistanceFromHome, Over18.

Remuneração e Cargo: Department, JobRole, JobLevel, MonthlyIncome, Média_Cargo, Comparativo_Salarial, HourlyRate, DailyRate, MonthlyRate, StockOptionLevel, PercentSalaryHike.

Carreira, Tempo de Casa e Mobilidade: YearsAtCompany, YearsAtCompany_Blocks, YearsInCurrentRole, YearsSinceLastPromotion, YearsWithCurrManager, TotalWorkingYears, NumCompaniesWorked, BusinessTravel.

Satisfação, Engajamento e Desempenho: JobSatisfaction, EnvironmentSatisfaction, RelationshipSatisfaction, WorkLifeBalance, JobInvolvement, PerformanceRating, OverTime, TrainingTimesLastYear.

Controle e Identificação do Registro: EmployeeNumber, EmployeeCount, StandardHours, Attrition (variável alvo).

# Passo 5: Hipóteses Analíticas

H1: Profissionais casados têm uma rotatividade menor.

H2: Profissionais que trabalham em muitas empresas têm alta rotatividade.

H3: Profissionais com baixa qualidade de vida têm rotatividade maior.

H4: Profissionais que fazem hora extra têm alta rotatividade.

H5: Profissionais que recebem menos que os colegas estando no mesmo cargo têm alta rotatividade.

H6: Profissionais com menos de 3 anos de trabalho na IBM têm rotatividade maior.

H7: Profissionais Jrs e Estagiários têm uma rotatividade maior.

# Passo 6: Critérios de Priorização

- **Critério 1:** Dados disponíveis.
- **Critério 2:** Insights acionáveis.

# Passo 7: Priorização das Hipóteses Analíticas

H1: Profissionais casados têm uma rotatividade menor.

H2: Profissionais que trabalham em muitas empresas têm alta rotatividade.

H3: Profissionais com baixa qualidade de vida têm rotatividade maior.

H4: Profissionais que fazem hora extra têm alta rotatividade.

H5: Profissionais que recebem menos que os colegas estando no mesmo cargo têm alta rotatividade.

H6: Profissionais com menos de 3 anos de trabalho na IBM têm rotatividade maior.

H7: Profissionais Jrs e Estagiários têm uma rotatividade maior.

# Insights da análise

# Resultados

**📥 Baixe a apresentação em PowerPoint (clique no link e, em seguida, em "Download" ou "View raw"):**  
  [https://docs.google.com/presentation/d/1ZAYDpxq3G5c3JzxRrJV63NLcst2hbMUj/edit?slide=id.p1#slide=id.p1](https://docs.google.com/presentation/d/1ZAYDpxq3G5c3JzxRrJV63NLcst2hbMUj/edit?slide=id.p1#slide=id.p1)

# Próximos passos

Fazer uma análise preditiva para saber o Turnover da IBM para o próximo ano.

(não é possível fazer essa análise porque esse dataset não tem dimensão de data)
