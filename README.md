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

- **Descritiva** – levantamento do cenário atual de como estao os números dos pedidos da empresa;
- **Diagnóstica** – descobrir o motivo de porque o ano de 2018 esta com a tedencia de queda;
- **Preditiva** – fazer uma previsao de Quantos pedidos serão feitos nos meses de setembro a dezembro de 2018?;
- **Prescritiva** – Dentre todas as alavancas do negocio, quais você recomendaria alterar para aumentar o numero de pedidos?.

A modelagem dos dados seguiu o método **Fato-Dimensão**.

---

## Definição do Escopo Analítico

**Pergunta Aberta:**  
*como estão os números dos pedidos da empresa*

**Pergunta Fechada:**  
*Pergunta fechada: Como estão as vendas da empresa nos últimos 3 anos, considerando todos os produtos que a E-Total vende na modalidade online?*

**Coluna Fato (variável alvo):**  
`order_id` – quanto feito uma contagem indica o numero de vendas feita pela empresa.

**Dimensões analisadas:**  

Dimensão	Variáveis representativas
Tempo (Data do Pedido)	order_purchase_timestamp, order_purchase_month, order_purchase_year_month, order_purchase_year
Cliente (Quem Comprou)	customer_id, customer_city, customer_state
Vendedor (Quem Vendeu)	seller_id, seller_city, seller_state
Produto (O que Foi Vendido)	product_id, product_category_name
Pedido (Transação / Cabeçalho)	order_id, order_status (para saber se foi entregue, cancelado, etc.)
Item do Pedido (Linha / Sequência)	order_item_id (identifica a posição do produto dentro do pedido)


--- fiz o mandmap de hipoteses para me guiar na analise, isso me da contexto sobre a area, mesmo eu sendo novo no setor eu poderei me adptar 

aqui abaixo estaa o prototipo do painel, aqui eu ja fiz a priorizacao do fato-dimensao com maior relevancia para essa analise

https://img.notionusercontent.com/s3/prod-files-secure%2F2b76fb90-3276-8107-9a2b-0003db8f3f1b%2F10ebc204-6354-4b32-96eb-d2d3b9968fd1%2Fimage.png/size/w=2000?exp=1782502229&sig=6q7nVkLP-2bKHnd-rEDeJ3C46E227qeWeNqb6lQ37do&imgBuildSrc=presignImageUrl&id=37c6fb90-3276-80bf-bd3b-c27508a04c5f&table=block&userId=2cdd872b-594c-8197-aa3d-0002004cefb4&mtd=com

# Mind Map - Hipóteses

## 1. Pedidos

- O número de pedidos ao longo do tempo.
- Tendência de pedidos por ano.
- Tendência de pedidos por mês.
- Preço médio por pedido.
- Média de pedidos.

## 2. Produtos

- O número de pedidos por categoria.
- Contribuição percentual de cada categoria nos pedidos ao longo dos meses.
- Os produtos que mais contribuem com os pedidos.
- Avaliação média dos produtos por pedido.
- Preço médio dos produtos por categoria.

## 3. Clientes

- O número de pedidos por estado de residência.
- O número de pedidos por cidade de residência.
- O número de pedidos por faixa etária.
- O número de pedidos por estado civil.
- O número de pedidos por gênero.

## 4. Vendedores

- O número de pedidos por estado de residência do vendedor.
- O número de pedidos por cidade de residência do vendedor.

## Hipóteses Analíticas (Priorizadas)

como e uma analise descritiva, entao nao ouve hipoteses analiticas a serem validadas

---

## Insights da Análise (Diagnóstica)

Hipotese do problema de negocio

O numero de pedidos diminiu em 2018 devido a diminuicao no numero clientes
O numero de pedidos diminui em 2018 devido ao aumento no numero de vendedores
O numero de pedidos diminui em 2018 devido ao aumento no numero de produtos disponiveis
O numero de pedidos diminui em 2018 devido ao aumento do preco medio dos produtos produtos
O numero de pedidos diminui em 2018 devido ao aumento do numero de categorias disponiveis

Os cruzamentos entre as dimensões e a variável `order_id` revelaram os seguintes direcionadores de rotatividade:


Segundo a análise gráfica e as correlações, podemos observar que a queda no número de pedidos em 2018 e o aumento do preço médio foram fortemente influenciados pela diminuição do número de compradores.

Além disso, a queda no número de vendedores e a estabilização do número total de categorias mostram uma estagnação na entrada de novos vendedores e no lançamento de novos produtos.


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
