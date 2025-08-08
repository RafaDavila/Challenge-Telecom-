O objetivo deste projeto é analisar o comportamento de clientes de uma empresa de telecomunicações com foco na evasão de clientes (churn). A evasão representa a perda de clientes ao longo do tempo e é um grande desafio para empresas que dependem de contratos recorrentes.

Este estudo busca responder:

Quais características estão mais associadas à evasão?

Como os dados de cobrança e perfil impactam no cancelamento?

Que padrões podemos identificar para criar estratégias de retenção?

Limpeza e Tratamento de Dados
Nesta seção, descrevemos as etapas de limpeza e tratamento dos dados realizadas:

Carregamento dos Dados: Os dados foram carregados a partir de um arquivo JSON.
Normalização de Colunas Aninhadas: As colunas aninhadas 'account' foram normalizadas e integradas ao DataFrame principal.
Verificação e Tratamento de Valores Ausentes: Foi verificado que não havia valores nulos no dataset.
Verificação de Duplicatas: Foi verificado que não havia linhas duplicadas no dataset.
Tratamento de Valores Vazios na Coluna 'Churn': Foi identificado que a coluna 'Churn' continha valores vazios (''). Esses valores foram removidos do DataFrame.
Remoção de Espaços em Branco: Espaços em branco no início e no final dos valores nas colunas 'Churn', 'Contract', 'PaperlessBilling' e 'PaymentMethod' foram removidos.
Criação de Coluna 'Contas_Diarias': Uma nova coluna 'Contas_Diarias' foi criada dividindo 'Charges.Monthly' por 30 para obter a cobrança diária aproximada.
Criação de Coluna 'Churn_bin': Uma coluna binária 'Churn_bin' foi criada mapeando 'Yes' para 1 e 'No' para 0 na coluna 'Churn'.
Renomeação de Colunas: As colunas foram renomeadas para o português para maior clareza.
Tradução de Valores Categóricos: Os valores nas colunas 'Contrato' e 'Metodo_Pagamento' foram traduzidos para o português.
Análise Exploratória de Dados
A análise exploratória de dados revelou insights importantes sobre as características dos clientes e sua relação com a evasão:

Distribuição da Evasão: Aproximadamente 26.5% dos clientes na base de dados apresentaram evasão.

Evasão por Tipo de Contrato: Clientes com contrato mensal ('Mensal') apresentam uma taxa de evasão significativamente maior (42.7%) em comparação com contratos de um ano (11.3%) e dois anos (2.8%).

Evasão por Método de Pagamento: Clientes que utilizam 'Cheque Eletrônico' como método de pagamento demonstram uma taxa de evasão maior do que aqueles que utilizam outros métodos.

Evasão por Faturamento sem Papel: Clientes que optam por 'Faturamento sem Papel' ('Yes') têm uma taxa de evasão mais alta do que aqueles que não utilizam este serviço.

Distribuição de Cobranças por Evasão: As distribuições das cobranças mensais e diárias mostram que clientes que evadiram ('Yes') tendem a ter cobranças mensais e diárias medianas mais altas do que clientes que não evadiram ('No'). A coluna 'Cobranca_Total' apresenta muitos valores "0" ou em branco, o que pode indicar problemas de preenchimento ou um viés na coleta desses dados.

Conclusões e Insights
Com base na análise exploratória, podemos concluir que diversos fatores estão associados à evasão de clientes:

Contratos: Clientes com contratos de curta duração, especialmente mensais, são mais propensos a cancelar o serviço.
Método de Pagamento: O uso de cheque eletrônico está associado a uma maior probabilidade de evasão.
Faturamento: Clientes que optam pelo faturamento sem papel também apresentam uma tendência maior à evasão.
Cobranças: Cobranças mensais e diárias mais altas parecem estar relacionadas a uma maior taxa de evasão. A qualidade dos dados na coluna 'Cobranca_Total' é questionável e precisa ser investigada.
Esses insights sugerem que clientes com maior flexibilidade (contratos mensais), que utilizam métodos de pagamento menos tradicionais (cheque eletrônico) e que têm cobranças mais elevadas têm uma maior propensão a evadir.

Recomendações
Para reduzir a evasão de clientes, recomendamos as seguintes ações baseadas nesta análise:

Foco em Clientes com Contratos Mensais: Desenvolver programas de fidelidade e ofertas especiais para incentivar a migração de clientes com contratos mensais para contratos de maior duração (um ou dois anos).
Incentivo a Outros Métodos de Pagamento: Promover o uso de transferência bancária e cartão de crédito com benefícios ou descontos para desencorajar o uso de cheque eletrônico.
Análise do Faturamento Sem Papel: Investigar os motivos pelos quais clientes que optam pelo faturamento sem papel têm maior evasão. Pode ser necessário melhorar a experiência do usuário com este serviço ou oferecer mais opções de faturamento.
Análise de Cobranças Elevadas: Realizar uma análise mais aprofundada dos clientes com cobranças mensais e diárias elevadas para entender se há insatisfação com o custo-benefício ou problemas com o serviço que levam à evasão.
Investigação da Coluna 'Cobranca_Total': É fundamental investigar os valores "0" ou em branco na coluna 'Cobranca_Total' para garantir a integridade dos dados e possibilitar análises mais precisas sobre o impacto da cobrança total na evasão.
A implementação dessas recomendações pode ajudar a empresa a reter clientes e reduzir a taxa de evasão, contribuindo para o crescimento e a sustentabilidade do negócio.

