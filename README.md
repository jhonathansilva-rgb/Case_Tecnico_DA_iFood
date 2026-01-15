
README – Case Técnico de Data Analytics (Cupons)

**Visão geral** 🎯
- Objetivo:  avaliar o impacto de uma estratégia de cupons na retenção de usuários/frequência, AOV e ROI, via experimento A/B.
- Entregáveis: notebook (case_completo.ipynb), apresentações executivas (Case DA - Tech - Apresentação.pdf) e artefatos analíticos (métricas, gráficos e cálculos de ROI).

**Dados** 📦
- Pedidos (order.json ou .gz): ~3,6M pedidos (dez/2018–jan/2019), itens, valores, horários, merchant_id.
- Consumidores (consumer.csv ou .gz): ~806k usuários, data de criação e status.
- Restaurantes (restaurant.csv ou .gz): ~7k merchants, faixa de preço, ticket médio, tempo de entrega, cidade/UF.
- Marcação A/B (ab_test_ref.csv ou .tar.gz): customer_id e is_target (teste/controle).

**Estrutura recomendada de pastas** 🗂️
- data/raw: colocar order.json(.gz), consumer.csv(.gz), restaurant.csv(.gz), ab_test_ref.csv(.tar.gz)
- outputs/figures: gráficos exportados
- outputs/tables: tabelas/CSV com métricas

**Como executar (Databricks)** ▶️
1) Abra case_completo.ipynb no Databricks.
2) Execute “Run All”. O notebook realiza: ETL (Bronze/Silver/Gold), criação de métricas por usuário/mês, segmentação (ex.: lifecycle semanal), comparação teste vs. controle, cálculos de incrementalidade e ROI, e exporta gráficos/tabelas em outputs/.

**Saídas geradas** 📤
- Tabelas (CSV/Parquet) com KPIs por grupo (teste/controle) e por segmento/coorte.
- Gráficos (PNG) de distribuição/comparação (ex.: frequência, AOV/GMV, retenção) e, quando aplicável, resultados estatísticos.
- Relatório executivo (as apresentações anexas) com leitura de negócio e recomendações.

**Resultados principais (da apresentação)** 📈
- AOV: estável (~ -0,2% vs. controle).
- Frequência: +13,3% (indício de maior retenção).
- Reativados: +20,8% vs. controle.
- Incrementalidade (período do teste): GMV incremental total ~R$14,4M.
- ROI do período: ~2,4 (cupom R$10/unidade; ver detalhes em Case DA - Tech - Apresentação.pdf).

**Limitações conhecidas** ⚠️
- Janela curta e sazonal (dez–jan).
- Sem custos definidos exigiram premissas.

**Próximos passos sugeridos** 🚀
- Rodar novo A/B com desenho aprimorado (targeting por segmentos de maior ROI, MDE/power definidos, correção por múltiplas comparações).
- Monitorar canibalização e efeitos de longo prazo (retenção D+60/D+90; LTV).
