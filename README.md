# Aeterno Invest 

### Simulador de Investimentos e Planejamento Financeiro com Excel

O **Aeterno Invest** é um projeto desenvolvido no Microsoft Excel com o objetivo de auxiliar no planejamento financeiro de longo prazo, permitindo simular a evolução de investimentos recorrentes, estimar a geração de renda mensal por dividendos e visualizar sugestões de distribuição de capital entre diferentes categorias de Fundos de Investimento Imobiliário (FIIs).

A ferramenta utiliza fórmulas financeiras, referências entre planilhas e tabelas de parâmetros para transformar informações configuráveis em projeções que facilitam a compreensão do impacto dos aportes mensais e dos rendimentos ao longo do tempo.

O projeto foi desenvolvido com foco na aplicação prática do Excel para cálculos financeiros, organização de dados e apoio à tomada de decisão.

---

##  Objetivos do projeto

- Simular o crescimento patrimonial a partir de aportes mensais recorrentes.
- Estimar o patrimônio acumulado em diferentes horizontes de tempo.
- Projetar a renda mensal potencial proveniente de dividendos.
- Relacionar o salário informado a uma sugestão de investimento mensal.
- Distribuir o valor disponível entre categorias de FIIs conforme o perfil selecionado.
- Demonstrar a aplicação de fórmulas financeiras e ferramentas de busca no Excel.

## ⚙️ Funcionalidades

### 1. Configurações financeiras

A planilha permite configurar os principais parâmetros utilizados nas simulações:

| Parâmetro | Descrição |
|---|---|
| Salário | Renda mensal utilizada como referência para o planejamento. |
| Rendimento da carteira | Taxa mensal estimada para o cálculo dos dividendos. |
| Sugestão de investimento | Calculada com base em 30% do salário informado. |
| Aporte mensal | Valor investido periodicamente nas simulações. |
| Horizonte de investimento | Período de acumulação, expresso em anos. |
| Taxa de rendimento mensal | Taxa utilizada para projetar o crescimento do patrimônio. |

Esses parâmetros podem ser alterados para explorar diferentes cenários financeiros.

### 2. Simulação de patrimônio

O simulador utiliza a função financeira `FV` para estimar o valor futuro dos aportes mensais, considerando a taxa de rendimento informada e o período de investimento.

As projeções contemplam os seguintes horizontes:

- 2 anos;
- 5 anos;
- 10 anos;
- 20 anos;
- 30 anos.

O modelo considera aportes recorrentes e capitalização mensal dos rendimentos. Dessa forma, permite observar como o tempo e a continuidade dos investimentos podem influenciar o patrimônio projetado.

### 3. Estimativa de dividendos mensais

Além de projetar o patrimônio, a planilha calcula uma estimativa de renda mensal utilizando o patrimônio acumulado e o rendimento da carteira informado nas configurações.

**Fórmula conceitual:**

`Dividendos mensais estimados = Patrimônio acumulado × Taxa de rendimento da carteira`

Esse cálculo permite comparar o patrimônio projetado com a renda mensal potencial associada a ele, de acordo com a taxa utilizada na simulação.

### 4. Distribuição de investimentos por perfil

O Aeterno Invest apresenta três perfis de alocação, com percentuais definidos para seis categorias de FIIs.

| Categoria | Conservador | Moderado | Agressivo |
|---|---:|---:|---:|
| Papel | 30% | 32% | 50% |
| Tijolo | 50% | 35% | 10% |
| Híbridos | 10% | 8% | 5% |
| FOFs | 10% | 5% | 5% |
| Desenvolvimento | 0% | 10% | 20% |
| Hotelarias | 0% | 10% | 10% |
| **Total** | **100%** | **100%** | **100%** |

A partir do perfil selecionado e do valor mensal disponível para investir, a planilha calcula o percentual correspondente a cada categoria e o valor financeiro sugerido para sua distribuição.

Os percentuais representam parâmetros configurados no projeto, não recomendações individualizadas de investimento.

##  Fórmulas e recursos utilizados

O projeto utiliza recursos do Excel para automatizar cálculos e conectar informações entre diferentes abas.

| Recurso | Aplicação |
|---|---|
| `FV` — Valor Futuro | Projeção do patrimônio a partir de aportes recorrentes e taxa de rendimento. |
| `PROCV` | Busca dos percentuais de alocação na tabela de parâmetros. |
| `SOMA` | Consolidação dos valores distribuídos entre as categorias de FIIs. |
| Operações matemáticas | Cálculo da sugestão de investimento e dos dividendos estimados. |
| Referências entre planilhas | Integração entre os parâmetros de alocação e a área de simulação. |
| Nomes definidos | Referenciamento de células e parâmetros, facilitando a leitura das fórmulas. |

### Exemplo de cálculo

Considerando um salário de R$ 2.000,00 e uma sugestão de investimento equivalente a 30% da renda mensal:

`Sugestão de investimento = 2.000 × 30% = R$ 600,00`

Se o aporte mensal escolhido para a simulação for de R$ 200,00, o sistema utiliza esse valor para projetar a evolução do patrimônio.

Os parâmetros são independentes: a sugestão calculada a partir do salário não substitui automaticamente o aporte utilizado na simulação.

##  Estrutura da planilha

O arquivo está organizado em duas abas principais.

**`Planilha1` — Simulação e resultados**

Responsável pela interface principal do projeto, reunindo:

- Configurações financeiras;
- Parâmetros dos aportes mensais;
- Projeções de patrimônio;
- Estimativas de dividendos;
- Seleção do perfil de alocação;
- Cálculo dos valores sugeridos por categoria de FII.

**`Planilha2` — Parâmetros de alocação**

Armazena a tabela de percentuais associados a cada combinação de perfil e categoria de FII.

Sua estrutura inclui:

- `CHAVE`: identificador formado pela combinação do perfil com o tipo de FII;
- `PERFIL`: classificação da alocação;
- `TIPO DE FII`: categoria do fundo;
- `%`: percentual utilizado nos cálculos.

A coluna de chave permite que a função `PROCV` localize o percentual correspondente ao perfil selecionado e retorne o valor utilizado na distribuição dos aportes.

##  Como utilizar

1. Abra o arquivo `projAeternoInvest.xlsx` no Microsoft Excel.
2. Acesse a aba `Planilha1`.
3. Informe ou ajuste o salário e os parâmetros de rendimento.
4. Defina o aporte mensal, o horizonte de investimento e a taxa mensal utilizada na projeção.
5. Consulte os cenários de patrimônio acumulado e os dividendos mensais estimados.
6. Selecione o perfil de alocação desejado.
7. Analise os percentuais e os valores sugeridos para cada categoria de FII.
8. Caso deseje personalizar os perfis, altere os percentuais correspondentes na aba `Planilha2`, verificando se cada conjunto totaliza 100%.

Os resultados dependem dos parâmetros informados e das fórmulas presentes na planilha.

##  Tecnologias e ferramentas

- **Microsoft Excel:** desenvolvimento da ferramenta, cálculos financeiros e organização dos parâmetros.
- **Funções financeiras:** projeção de patrimônio e estimativa de rendimentos.
- **Funções de busca e referência:** integração entre as abas e recuperação dos percentuais de alocação.

##  Limitações e premissas

As projeções apresentadas são simulações matemáticas e não representam garantias de rentabilidade.

O modelo considera taxas informadas pelo usuário e não incorpora automaticamente fatores como:

- Inflação e perda do poder de compra;
- Variações reais nos rendimentos dos FIIs;
- Oscilações nos preços das cotas;
- Impostos, taxas e demais custos;
- Vacância, inadimplência e mudanças nas condições do mercado;
- Alterações futuras na distribuição de dividendos.

A estimativa de dividendos utiliza uma taxa mensal configurada pelo usuário e pressupõe que ela seja aplicável ao patrimônio projetado. Os resultados podem divergir significativamente do desempenho real dos investimentos.

O Aeterno Invest possui finalidade educacional e de planejamento. Não constitui recomendação financeira, indicação de ativos ou garantia de retorno.

##  Possíveis melhorias futuras

- Criar um dashboard com indicadores financeiros e gráficos de evolução patrimonial.
- Adicionar comparações visuais entre os três perfis de alocação.
- Separar o patrimônio formado por aportes dos rendimentos acumulados.
- Incluir cenários otimista, moderado e pessimista para as taxas de retorno.
- Considerar a inflação nas projeções de longo prazo.
- Implementar validações para os parâmetros e os percentuais de alocação.
- Integrar os dados a ferramentas como Power BI para ampliar as possibilidades de análise.

##  Sobre o projeto

O Aeterno Invest é um projeto prático voltado à aplicação do Microsoft Excel em simulações financeiras e organização de dados.

Seu desenvolvimento proporciona experiência com fórmulas financeiras, referências entre planilhas, automatização de cálculos e estruturação de parâmetros para apoiar análises quantitativas.

**Arquivo principal:** `projAeternoInvest.xlsx`

---

*Aviso: este projeto possui caráter exclusivamente educacional. Os valores apresentados são estimativas baseadas nas premissas configuradas e não devem ser interpretados como promessa de rentabilidade ou recomendação de investimento.*
