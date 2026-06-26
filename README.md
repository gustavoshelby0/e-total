# Análise de Vendas da E-total
## Problema de Negócio

Vamos imaginar uma empresa de e-commerce chamada "E-Total". Ela foi fundada há dez
anos por um empreendedor visionário, John, que viu uma oportunidade no mercado para criar uma plataforma online que oferecesse uma ampla variedade de produtos, desde eletrônicos e roupas até produtos de beleza e utensílios domésticos.
Nos primeiros anos, a E-Total enfrentou desafios significativos ao estabelecer sua presença online e construir parcerias com fornecedores em diversas categorias de produtos.
Agora, após uma década de operação bem-sucedida, a E-Total está enfrentando uma
decisão estratégica crucial sobre seu crescimento futuro. 

Para tomar essa decisão estratégica, a E-Total precisa entender melhor o histórico de seus números de pedidos.

## Premissas da análise

- Base de dados com 4.000mil vendas da empresa E-total
- O dataset contém datas de vendas do periodo de 2017-2018.

## Estratégia da solução

A investigação foi estruturada em **4 estágios analíticos progressivos**, garantindo uma narrativa lógica e acionável:

- **Descritiva** – levantamento do cenário atual e perfil dos funcionários;
- **Diagnóstica** – teste de hipóteses para identificar as causas da rotatividade;
- **Prescritiva** – recomendações práticas com base nos achados;
- **Preditiva** – modelagem futura (proposta para os próximos passos).

A modelagem dos dados seguiu o método **Fato-Dimensão**.

---

## Definição do Escopo Analítico

**Pergunta Aberta:**  
*Quais fatores mais contribuem para o turnover de funcionários?*

**Pergunta Fechada:**  
*O turnover está relacionado a remuneração abaixo da média do cargo? À realização de horas extras? À falta de promoções? À ausência de plano de carreira?*

**Coluna Fato (variável alvo):**  
`Attrition` – indica se o funcionário permanece ou já se desligou da empresa.

**Dimensões analisadas:**  

| Dimensão | Variáveis representativas |
| :--- | :--- |
| Perfil Pessoal e Demográfico | Age, Gender, MaritalStatus, Education, DistanceFromHome |
| Remuneração e Cargo | Department, JobRole, MonthlyIncome, Comparativo_Salarial, StockOptionLevel |
| Carreira e Mobilidade | YearsAtCompany, YearsInCurrentRole, NumCompaniesWorked, BusinessTravel |
| Satisfação e Engajamento | JobSatisfaction, WorkLifeBalance, OverTime, PerformanceRating |
| Controle | EmployeeNumber, Attrition (target) |

---

## Hipóteses Analíticas (Priorizadas)

Critérios de priorização: dados disponíveis + potencial de geração de insights acionáveis.

- **H1:** Profissionais casados têm menor rotatividade.
- **H2:** Profissionais que passaram por muitas empresas têm alta rotatividade.
- **H3:** Profissionais com baixa qualidade de vida (satisfação/equilíbrio) têm maior rotatividade.
- **H4:** Profissionais que fazem hora extra têm alta rotatividade.
- **H5:** Profissionais com remuneração abaixo da média do cargo têm alta rotatividade.
- **H6:** Profissionais com menos de 3 anos de casa têm maior rotatividade.
- **H7:** Profissionais em cargos iniciais (Jrs/Estagiários) têm maior rotatividade.

---

## Insights da Análise (Diagnóstica)

Os cruzamentos entre as dimensões e a variável `Attrition` revelaram os seguintes direcionadores de rotatividade:

- **H4 validada** – a incidência de horas extras está fortemente correlacionada ao desligamento voluntário.
- **H6 validada** – funcionários com menos de 3 anos de empresa apresentam taxa de saída significativamente maior.
- **H5 parcialmente validada** – a defasagem salarial em relação à média do cargo impacta a decisão de sair, especialmente em níveis hierárquicos intermediários.
- As demais hipóteses (H1, H2, H3 e H7) não apresentaram correlação estatisticamente relevante no dataset analisado.

---

## Resultados (Descritiva + Prescritiva)

**Panorama Descritivo:**  
A taxa geral de turnover identificada foi de X% (coloque o valor real). O perfil médio dos desligamentos concentra-se em profissionais com até 3 anos de casa, faixa etária de 25 a 35 anos e cargos operacionais/técnicos.

**Recomendações Prescritivas (ações imediatas):**

1. **Revisão da política de horas extras** – instituir banco de horas ou compensação financeira mais atrativa para áreas com maior incidência de saídas.
2. **Plano de aceleração para novos talentos** – criar trilhas de desenvolvimento acelerado para funcionários com menos de 3 anos e alto potencial.
3. **Correção salarial competitiva** – realizar benchmarking de mercado para ajustar os salários dos cargos com defasagem identificada.

📥 **Baixe a apresentação completa em PowerPoint:**  
[Clique aqui para acessar o arquivo](https://docs.google.com/presentation/d/1ZAYDpxq3G5c3JzxRrJV63NLcst2hbMUj/edit?slide=id.p1#slide=id.p1) (em seguida, clique em *Download* ou *View raw*).

---

## Próximos Passos (Preditiva)

Embora o dataset atual não possua dimensão temporal para análises de série histórica, propomos como evolução natural a construção de um **modelo preditivo de classificação** (ex.: Regressão Logística ou Random Forest).

Esse modelo utilizará as variáveis comportamentais, demográficas e de carreira já mapeadas para estimar, em tempo real, a **probabilidade de desligamento** de cada funcionário ativo. Com essa ferramenta, o RH poderá atuar de forma proativa, antecipando ações de retenção antes que a saída ocorra.
