# Análise de Vendas da E-Total

## Problema de Negócio

A E-Total é um e-commerce com uma década de atuação, oferecendo produtos que vão desde eletrônicos e roupas até beleza e utensílios domésticos. Após anos de crescimento, a empresa chega a um momento decisivo para sua estratégia de expansão. Para embasar essa decisão, é fundamental compreender a fundo o histórico de seus pedidos e o comportamento de suas vendas.

## Premissas da análise

- Base de dados com **4 mil registros de vendas** da E-Total.
- O dataset contempla o período de **2017 a 2018**.

## Estratégia da solução

A investigação foi estruturada em **4 estágios analíticos progressivos**, garantindo uma narrativa lógica e acionável:

- **Descritiva** – Levantamento do cenário atual dos números de pedidos da empresa.
- **Diagnóstica** – Investigação do motivo da tendência de queda observada em 2018.
- **Preditiva** – Projeção do volume de pedidos para os meses de setembro a dezembro de 2018.
- **Prescritiva** – Recomendação de alavancas de negócio para reverter a queda e aumentar o número de pedidos.

A modelagem dos dados seguiu o método **Fato-Dimensão**.

---

## Definição do Escopo Analítico

**Pergunta Aberta:**  
*Como estão os números de pedidos da empresa?*

**Pergunta Fechada:**  
*Como evoluíram as vendas nos últimos anos, considerando todos os produtos vendidos no canal online?*

**Coluna Fato (variável alvo):**  
`order_id` – por meio de sua contagem, obtemos o volume total de vendas (número de pedidos realizados).

**Dimensões analisadas:**

| Dimensão | Variáveis representativas |
| :--- | :--- |
| **Tempo (Data do Pedido)** | `order_purchase_timestamp`, `order_purchase_month`, `order_purchase_year_month`, `order_purchase_year` |
| **Cliente (Quem Comprou)** | `customer_id`, `customer_city`, `customer_state` |
| **Vendedor (Quem Vendeu)** | `seller_id`, `seller_city`, `seller_state` |
| **Produto (O que Foi Vendido)** | `product_id`, `product_category_name` |
| **Pedido (Cabeçalho da Transação)** | `order_id`, `order_status` (entregue, cancelado etc.) |
| **Item do Pedido (Linha/Sequência)** | `order_item_id` (posição do produto dentro do pedido) |

---

## Mind Map – Direcionadores de Análise

Para orientar a exploração dos dados, mesmo sendo um analista novo no setor, foram mapeados os seguintes grupos de perguntas:

**1. Pedidos**
- Volume de pedidos ao longo do tempo.
- Tendência por ano e por mês.
- Preço médio por pedido.
- Média geral de pedidos.

**2. Produtos**
- Volume de pedidos por categoria.
- Participação percentual de cada categoria ao longo dos meses.
- Produtos com maior contribuição em volume.
- Avaliação média e preço médio por categoria.

**3. Clientes**
- Distribuição de pedidos por estado e cidade do cliente.
- Perfil dos clientes (faixa etária, estado civil, gênero) – quando disponível.

**4. Vendedores**
- Distribuição de pedidos por estado e cidade do vendedor.

---

## Hipóteses Analíticas (Diagnóstica)

Embora o foco inicial seja uma análise descritiva, levantamos hipóteses de negócio para direcionar a investigação sobre a queda de pedidos em 2018:

- **H1:** A queda no número de pedidos em 2018 se deve à **diminuição no número de clientes ativos**.
- **H2:** A queda se deve ao **aumento no número de vendedores** (diluição da base).
- **H3:** A queda se deve ao **aumento na variedade de produtos disponíveis** (maior dispersão).
- **H4:** A queda se deve ao **aumento do preço médio dos produtos**.
- **H5:** A queda se deve ao **aumento do número de categorias disponíveis**.

---

## Insights da Análise (Diagnóstica)

Com base nos cruzamentos entre as dimensões e a variável `order_id`, os principais achados foram:

- **H1 validada** – A análise gráfica e as correlações confirmam que a queda no número de pedidos em 2018 está fortemente associada à **redução no número de compradores ativos**.
- **H4 parcialmente validada** – O aumento do preço médio dos produtos também acompanhou a retração, sugerindo que itens mais caros podem estar afastando consumidores.
- **Fatores secundários** – Observou-se uma **estagnação na entrada de novos vendedores** e uma estabilização no número total de categorias, o que indica falta de renovação no marketplace e menor atratividade para novos clientes.

---

## Resultados (Descritiva + Prescritiva)

**Panorama Descritivo – Previsão de Pedidos (Set–Dez/2018):**

| Mês | Pedidos Previstos |
| :--- | :--- |
| Setembro | 347 |
| Outubro | 304 |
| Novembro | 441 |
| Dezembro | 326 |

> **Acurácia da previsão:** O erro médio absoluto (MAE) foi de aproximadamente **37 pedidos** , representando uma margem de erro de **23%** nas projeções para o período.

**Recomendações Prescritivas (ações para reverter a queda):**

1. **Reativação de clientes** – Implementar campanhas de e-mail marketing e cupons de desconto direcionados a clientes que não compram há mais de 90 dias.
2. **Atração de novos vendedores** – Criar programas de incentivo para aumentar o número de sellers ativos, expandindo o catálogo e a competitividade de preços.
3. **Revisão de precificação** – Avaliar a elasticidade-preço das categorias com maior queda, buscando equilibrar ticket médio e volume de vendas.
4. **Ampliação de categorias** – Lançar novas linhas de produtos para atrair diferentes perfis de consumidores e aumentar a base de clientes.

📥 **Baixe a apresentação completa em PowerPoint:**  
[Clique aqui para acessar o arquivo](https://docs.google.com/presentation/d/1ZAYDpxq3G5c3JzxRrJV63NLcst2hbMUj/edit?slide=id.p1#slide=id.p1) (em seguida, clique em *Download* ou *View raw*).

---

## Próximos Passos (Preditiva)

