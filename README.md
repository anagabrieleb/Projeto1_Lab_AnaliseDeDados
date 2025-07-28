# Documentação - Análise “O Mercado”

## **Equipe e Documentação**

Ana Gabriele Brito dos Santos - Projeto Individual

- [Apresentação](https://docs.google.com/presentation/d/1zJAbmM-YS1FlDZc2gzK3f9XXOwHlpC6ObJMdh0O9rE4/edit?usp=sharing)
- [Documentação](https://www.notion.so/Documenta-o-An-lise-O-Mercado-20f2424d7a1c809a9495f46155824dd7?pvs=21)
- [Planilha](https://docs.google.com/spreadsheets/d/10BOLhnN0Zpq4eVTa_haaVR6PrwwdYf6S5da1gG9__M4/edit?usp=sharing)
- [Vídeo](https://www.loom.com/share/50c0b74dd4814c3c84467494e8317639?sid=4ef80a9b-b171-4ee9-90e6-2a348154084d)

## **Objetivo da Análise**

O projeto tem como foco aplicar a metodologia RFM (Recência, Frequência e Valor Monetário) para segmentar os clientes da loja "O Mercado". A ideia é identificar padrões de comportamento de compra e apoiar a criação de estratégias mais personalizadas de marketing e retenção.

Com base nos dados de vendas e no perfil demográfico dos clientes, a análise busca entender quem são os consumidores mais valiosos, quais grupos precisam de mais atenção para garantir a fidelização e onde estão as maiores oportunidades de crescimento.

### Hipóteses

### 👥 Quem são os clientes d’O Mercado?

- Quais são as faixas etárias mais presentes na base de clientes?
- Como está distribuída a quantidade de filhos?
- Qual é a média de renda mensal desse público?

---

### 🛒 Quais são seus hábitos de consumo?

- Qual faixa etária concentra o maior volume de gastos?
- Como se distribui o volume total de compras?
- Quais produtos são mais consumidos?
- Quais categorias têm menor saída?

---

### 🔍 Há fatores externos que influenciam o consumo?

- O estado civil impacta nas decisões de compra? Qual perfil se destaca?
- A quantidade de filhos interfere no comportamento de consumo?
- A renda mensal influencia diretamente no padrão de compra?

---

### 🎯 Marketing e Retenção

- Qual canal de compra é o mais utilizado, de forma geral e por faixa etária?
- Qual é o nível de resposta às campanhas de marketing?
- Há oportunidades para melhorar o engajamento?

## Fonte de Dados

- [Clientes](https://docs.google.com/spreadsheets/d/1joGlhjv9IOlDiThGv1bfqliYi8gwuNRP9B20sSKnqJc/edit?gid=0#gid=0)
- [Compras](https://docs.google.com/spreadsheets/d/1UFUQ23mYuo68yU_BOa2hYqoGA3Rlm-uJlVcenhOlpSE/edit?gid=1803379532#gid=1803379532)
- [Transações](https://docs.google.com/spreadsheets/d/1kscIzh8UFIoX3OQM4f1MT1L002njWLz2QK_s_uIUIYE/edit?gid=0#gid=0)

## Ferramentas e Tecnologias

- Google Sheets e Google Slides;
- Notion;
- Loom.

## Processamentos e Análises

- Extração de Dados
    - Importação dos dados de todas as pastas de trabalho utilizando a fórmula `=IMPORTRANGE("URL";"A1:I2241")`, aplicada individualmente para os conjuntos de dados de **clientes**, **compras** e **transações.**
    - Criação de planilhas de processamento e análises: `clientes_dados_limpos`, `transacoes_dados_limpos` e `compras_dados_limpos`.
    
    ---
    
- Limpeza de Dados
    
    Após a exportação dos dados, iniciei a etapa de tratamento de valores nulos utilizando a função `COUNTBLANK`.
    
    ---
    
    - Clientes:
        
        `clientes_dados_limpos`
        
    
    Foram identificados 24 valores ausentes na coluna `salario_anual_dolar`. Para preenchê-los, optei por uma abordagem condicional baseada no perfil do cliente (filhos e escolaridade).
    
    | **id_cliente** | **salario_anual_dolar** |
    | --- | --- |
    | 1994 |  |
    | 5255 |  |
    | 7281 |  |
    | 7244 |  |
    | 8557 |  |
    | 10629 |  |
    | 8996 |  |
    | 9235 |  |
    | 5798 |  |
    | 8268 |  |
    | 1295 |  |
    | 2437 |  |
    | 2863 |  |
    | 10475 |  |
    | 2902 |  |
    | 4345 |  |
    | 3769 |  |
    | 7187 |  |
    | 1612 |  |
    | 5079 |  |
    | 10339 |  |
    | 3117 |  |
    | 5250 |  |
    | 8720 |  |
    
     A média salarial utilizada para preenchimento foi:
    
    - **Sem filhos:**
        - Ensino médio: 50.086,22
        - Ensino superior: 66.134,94
        - Pós-graduação: 69.137,55
    - **Com filhos:**
        - Ensino médio: 41.855,93
        - Ensino superior: 52.732,38
        - Pós-graduação: 54.803,54
    
    Essas médias foram aplicadas aos respectivos perfis para substituir os valores nulos. 
    Também notei um valor em `salario_anual_dolar` que destoava da maioria: **666.666**. Por isso, substituí esse outlier pela **mediana da distribuição**, que era **52.732,38**.
    
    ---
    
    - Transações:
        
        ### `transacoes_dados_limpos`
        
    
    Foram encontrados 7 valores nulos na coluna `id_cliente`, conforme mostrado na tabela abaixo.
    
    Optei por excluí-los, pois não comprometem as análises, dado que não há vínculo relevante com outras informações.
    
    | id_transacao | id_cliente | data_transacao | lugar_transacao |
    | --- | --- | --- | --- |
    | 805088942 |  | 2022-07-06 | loja online |
    | 410352875 |  | 2022-03-16 | loja online |
    | 788057945 |  | 2022-05-06 | loja online |
    | 601858527 |  | 2021-05-17 | loja física |
    | 345606837 |  | 2021-12-13 | loja física |
    | 179794745 |  | 2022-04-27 | loja física |
    | 531229465 |  | 2022-11-16 | loja física |
    
    ---
    
    - Compras:
        
        ### `compras_dados_limpos`
        
    
    Não foram encontrados valores nulos.
    
    Após o tratamento de nulos, realizei a limpeza de duplicatas. Apenas o conjunto `compras` apresentava linhas duplicadas — 9 no total — que foram removidas.
    
    ---
    
    Durante a verificação de consistência, identifiquei três datas de nascimento altamente discrepantes:
    
    - 1900 → 125 anos
    - 1899 → 126 anos
    - 1893 → 132 anos
    
    | **id_cliente** | **idade** | **ano_nascimento** |
    | --- | --- | --- |
    | *7829* | 125 | 1900 |
    | *11004* | 132 | 1893 |
    | *1150* | 126 | 1899 |
    
    Considerando que o intervalo dos dados vai de 30/07/2020 a 31/12/2022, decidi excluir esses registros por destoarem significativamente do restante da base.
    
    ---
    
- Variáveis e Refinamento
    
    ### Variáveis:
    
    - **Planilha `clientes_dados_limpos`:**
    
    Na pasta `clientes_dados_limpos`, criei variáveis que, possivelmente, respondem às minhas hipóteses, sendo elas: **`idade`, `qtd_filhos` e `salario_mensal`.**
    
    A fórmula **`ARRAYFORMULA` e `SE`** foi essencial nesse processo para **automatizar, calcular e transferir os dados para uma nova coluna, dentro da mesma planilha, de maneira rápida e eficiente.**
    
    ---
    
    ### **`idade`**
    
    Refere-se ao cálculo da idade de cada *id_cliente*, para ajudar na precisão da faixa etária:
    
    `=ARRAYFORMULA(SE(B3:B=""; ""; ANO(HOJE()) - B3:B))`
    
    ---
    
    ### `faixa_etaria`
    
    Categoria que classifica os clientes em grupos de idade para facilitar a análise de comportamento e preferências.
    
    **Categorias:**
    
    - 18 a 25 anos
    - 26 a 35 anos
    - 36 a 45 anos
    - 46 a 55 anos
    - 56 a 65 anos
    - Acima de 65 anos
    
    `=ARRAYFORMULA(SE(M3:M2239>65;"Acima de 65 anos";SE(M3:M2239>=56;"56 a 65 anos";SE(M3:M2239>=46;"46 a 55 anos";SE(M3:M2239>=36;"36 a 45 anos";SE(M3:M2239>=26;"26 a 35 anos";SE(M3:M2239>=18;"18 a 25 anos";"")))))))`
    
    ---
    
    ### **`qtd_filhos`**
    
    Refere-se ao cálculo da quantidade de filhos nas duas colunas (*criancas_ate_dez_anos* e *criancas_mais_dez_anos*), visto que o importante não é a quantidade exata, mas sim se há filhos ou não:
    
    `=ARRAYFORMULA(F3:F2239+G3:G2239)`
    
    ---
    
    ### **`salario_mensal`**
    
    Ajuda na precisão e é relevante para o contexto socioeconômico-familiar:
    
    `=ARRAYFORMULA(E3:E2242/12)`
    
    ---
    
    - **Planilha `compras_dados_limpos`:**
    
    Adicionei as seguintes variáveis: `total_gasto`, `item_mais_comprado` e `item_menos_comprado`.
    
    Utilizei as fórmulas `SOMA`, `ÍNDICE`, `CORRESP`, `MÁXIMO` e `MÍNIMO`.
    
    ---
    
    ### **`total_gasto`**
    
    Soma dos gastos entre todos os produtos: total_vinhos, total_frutas, total_carnes, total_peixes e total_outros.
    
    `=SOMA(B3:G3)`
    
    ---
    
    ### **`item_mais_comprado`**
    
    Para cada cliente, identifica o item mais comprado, ajudando a entender os hábitos de consumo.
    
    `=ÍNDICE(B$2:G$2;CORRESP(MÁXIMO(B3:G3);B3:G3;0))`
    
    ---
    
    ### **`item_menos_comprado`**
    
    Com o mesmo propósito do `item_mais_comprado`, ajuda a entender hábitos e a direcionar esforços de marketing para promoções em categorias menos consumidas.
    
    `=ÍNDICE(B$2:G$2;CORRESP(MÍNIMO(B3:G3);B3:G3;0))`
    
    ---
    
    - **Planilha `transacoes_dados_limpos`:**
    
    Criei as variáveis: `qtd_transacoes`, `compras_online` ,`compras_fisica`e `dias_ultima_compra`.
    
    Utilizei `ARRAYFORMULA` ,`CONT.SES`e `SE`.
    
    ---
    
    ### **`compras_online`**
    
    Identifica quantas compras foram feitas no modo “loja online” para cada cliente, auxiliando no direcionamento de esforços e análise por faixa etária:
    
    `=ARRAYFORMULA(CONT.SES(B3:B22107;G3:G2239;D3:D22107;"loja online"))`
    
    ---
    
    ### **`compras_fisica`**
    
    Mesma lógica da variável anterior, para compras na “loja física”:
    
    `=ARRAYFORMULA(CONT.SES(B3:B22107;G3:G2239;D3:D22107;"loja física"))`
    
    ---
    
    ### `primeira_compra`
    
    Busca, no conjunto de datas de transações, a data da primeira compra feita para cada `id_cliente`.
    
    `=MINIFS(C:C; B:B; G3)`
    
    Nos clientes com dados vazios, coloquei “Não encontrado”.
    
    ---
    
    ### `ultima_compra`
    
    Seguindo a mesma lógica acima, busca a data da última compra feita para cada `id_cliente`.
    
    `=MAXIFS(C:C; B:B; G3)`
    
    Nos clientes com dados vazios, coloquei “Não encontrado”.
    
    ---
    
    ### `tempo_de_vida`
    
    Cálculo para contabilizar o ciclo de vida de cada `id_cliente`.
    
    `=ARRAYFORMULA(L3:L2239 - K3:K2239)`
    
    ---
    
    Além disso, observei na aba `transacoes_dados_limpos` que haviam *dez `id_cliente`* sem dados em `qtd_transacoes`, mas que possuíam histórico de compras e demais informações sobre hábitos de consumo.
    
    Mantive esses dados para garantir a completude da análise e preenchi com “Não encontrado” nas respectivivas células.
    
    ---
    
    **Exemplo dos clientes com 0 em qtd_transacoes:**
    
    | id_cliente | qtd_transacoes | compras_online | compras_fisica |
    | --- | --- | --- | --- |
    | 5376 | 0 | 0 | 0 |
    | 8475 | 0 | 0 | 0 |
    | 5555 | 0 | 0 | 0 |
    | 3955 | 0 | 0 | 0 |
    | 10749 | 0 | 0 | 0 |
    | 6862 | 0 | 0 | 0 |
    | 11110 | 0 | 0 | 0 |
    | 4931 | 0 | 0 | 0 |
    | 9931 | 0 | 0 | 0 |
    | 11181 | 0 | 0 | 0 |
    
    **E seus gastos correspondentes na planilha `compras_dados_limpos`:**
    
    | id_cliente | total_gasto |
    | --- | --- |
    | 3955 | 8197 |
    | 4931 | 2574 |
    | 5376 | 2140 |
    | 5555 | 9745 |
    | 6862 | 4953 |
    | 8475 | 6596 |
    | 9931 | 2285 |
    | 10749 | 9373 |
    | 11110 | 5376 |
    | 11181 | 2006 |
    
    ---
    
    ### Refinamento:
    
    Criei uma nova aba consolidando todas as informações e variáveis, chamada `dados_consolidados`.
    
    Para isso, utilizei novamente a fórmula `ARRAYFORMULA` para transferir os dados das seguintes planilhas: `clientes_dados_limpos`, `compras_dados_limpos` e `transacoes_dados_limpos`.
    

## Análise Exploratória

Criação da planilha `análise_exploratória`, com o proposito de classificar e agrupar corretamente os dados — através de tabelas dinâmicas, o Perfil do Cliente, Comportamento de Compra e Fatores de Influência e Engajamento, conforme hipóteses:

Perfil do Cliente

- Quais são as principais faixas etárias?
- O estado civil influencia no comportamento de compra?
- A quantidade de filhos impacta nas decisões de compra?
- Nível de escolaridade mais frequente entre os clientes
- Total de compras por faixa etária e nível de escolaridade
- Média salarial e média de gastos por faixa etária
- Média de compras por nível de educação

---

Comportamento de Compra

- Qual faixa etária apresenta maior volume de gastos?
- Comparativo entre nível de escolaridade e volume de compras por faixa etária
- Canal de compra preferido por faixa etária (online ou físico)

---

Fatores de Influência e Engajamento

- Porcentagem de respostas à campanha
- Respostas à campanha de acordo com a faixa etária

## Análise RFM

- **Cálculo de Quartis**
    - Criação da aba `analise_RFM`, com as informações extraídas da planilha `dados_consolidados`, utilizadas para o cálculo de quartis e segmentações por RFM.
        - Foi incluída a variável `dias_ultima_compra`, que calcula a quantidade de dias desde a última transação com base na data de corte (31/12/2022). A fórmula utilizada foi:
            
            `=ARRAYFORMULA(SE(L3:L2239="Não encontrado"; 999; O1 - L3:L2239))`
            
    
    ---
    
    Para clientes sem histórico de compras, foi atribuído o valor **999** como recência máxima, garantindo que sejam corretamente classificados no menor quartil de Recência.
    
    | **id_cliente** | **primeira_compra** | **ultima_compra** | **tempo_de_vida** | **dias_ultima_compra** |
    | --- | --- | --- | --- | --- |
    | 3955 | Não encontrado | Não encontrado | Não encontrado | 999 |
    | 4931 | Não encontrado | Não encontrado | Não encontrado | 999 |
    | 5376 | Não encontrado | Não encontrado | Não encontrado | 999 |
    | 5555 | Não encontrado | Não encontrado | Não encontrado | 999 |
    | 6862 | Não encontrado | Não encontrado | Não encontrado | 999 |
    | 8475 | Não encontrado | Não encontrado | Não encontrado | 999 |
    | 9931 | Não encontrado | Não encontrado | Não encontrado | 999 |
    | 10749 | Não encontrado | Não encontrado | Não encontrado | 999 |
    | 11110 | Não encontrado | Não encontrado | Não encontrado | 999 |
    | 11181 | Não encontrado | Não encontrado | Não encontrado | 999 |
    
    ---
    
    - Após devidas correções, estruturei duas pequenas tabelas para calcular os quartis, sendo assim:
        - Quartis de Recência
            
            Quanto menor o número de dias desde a última compra, melhor a pontuação, formulas utilizadas respectivamente:
            
            `=QUARTIL(F3:F2239; 1)`, `=QUARTIL(F3:F2239; 2)`, `=QUARTIL(F3:F2239; 3)` e `=MÁXIMO(F3:F2239)`.
            
            | Quartil | Recência |
            | --- | --- |
            | 4 | 54 |
            | 3 | 134 |
            | 2 | 245 |
            | 1 | 999 |
            
        
        ---
        
        - Quartis de Frequência e Valor Monetário
            
            Quanto maior o número de compras ou valor gasto, melhor a pontuação, formulas utilizadas para cada quartil:
            
            Frequência:
            
            `=QUARTIL(D3:D2239; 1)`, `=QUARTIL(D3:D2239; 2)`, `=QUARTIL(D3:D2239; 3)` e `=QUARTIL(D3:D2239;4)`.
            
            Monetário:
            
            `=QUARTIL(C3:C2239; 1)`, `=QUARTIL(C3:C2239; 2)`, `=QUARTIL(C3:C2239; 3)` e `=QUARTIL(C3:C2239;4)`.
            
            | Quartil | Frequência | Monetário |
            | --- | --- | --- |
            | 1 | 5 | R$ 69,00 |
            | 2 | 10 | R$ 396,00 |
            | 3 | 14 | R$ 1.045,00 |
            | 4 | 27 | R$ 2.525,00 |
    
    ---
    
- **RFM - Recência, Frequência e Valor Monetário**
    
    Após o cálculo dos quartis, realizei a categorização e segmentação dos valores RFM atribuídos a cada cliente, conforme a pontuação combinada. A segmentação foi organizada da seguinte forma:
    
    | **Categoria** | **Códigos RFM** |
    | --- | --- |
    | Campeões | 421, 422, 423, 431, 432, 433, 434, 443, 444 |
    | Leais | 311, 312, 313, 331, 332, 333, 334, 342, 343, 344, 442 |
    | Promissores | 411, 412, 413, 424 |
    | Em crescimento | 322, 323, 234, 324 |
    | Em risco | 221, 222, 223, 224, 231, 232, 233, 243, 244, 321 |
    | Perdidos/Dormindo | 111, 112, 121, 122, 123, 211, 212 |
    
    Essas categorias foram definidas com base em padrões de comportamento de compra, considerando os níveis de Recência, Frequência e Valor Monetário atribuídos a cada cliente, sendo assim:
    
    - **Campeões:** clientes que compraram recentemente, com alta frequência e alto valor de compra. São os melhores clientes.
    - **Leais:** compram com frequência e gastam bem, mas não necessariamente tão recentemente quanto os campeões.
    - **Promissores:** clientes relativamente recentes com bom potencial de engajamento, embora ainda sem histórico consistente.
    - **Em crescimento:** clientes com alguma recorrência ou valor de compra em ascensão, mas que ainda não atingiram os níveis mais altos.
    - **Em risco:** já foram ativos, mas estão deixando de comprar ou diminuíram seu valor/frequência. Precisam de atenção.
    - **Perdidos/Dormindo:** clientes inativos há muito tempo, com histórico fraco ou inexistente de compras.
    
    ---
    
    Logo após, foram criadas tabelas dinâmicas e gráficos para auxiliar na futura visualização em `dashboard`, sendo eles:
    
    1. Soma de gastos por segmento;
    2. Quantidade de clientes por segmento;
    
    | *Segmentação_RFM* | Soma de Gastos |
    | --- | --- |
    | Campeões | R$ 366.739,00 |
    | Em crescimento | R$ 145.119,00 |
    | Em risco | R$ 389.122,00 |
    | Leais | R$ 309.765,00 |
    | Perdidos/Dormindo | R$ 98.474,00 |
    | Promissores | R$ 45.829,00 |
    | **Total geral** | **R$ 1.355.048,00** |
    
    | *Segmentação_RFM* | Quantidade de Clientes | % de Clientes |
    | --- | --- | --- |
    | Campeões | 453 | 20,25% |
    | Em crescimento | 186 | 8,31% |
    | Em risco | 486 | 21,73% |
    | Leais | 414 | 18,51% |
    | Perdidos/Dormindo | 588 | 26,29% |
    | Promissores | 110 | 4,92% |
    | **Total geral** | **2237** | **100,00%** |

## Resultados e Conclusões

- Resultados
    - A empresa “O Mercado” possui uma base ativa de 2.237 clientes, sendo a maioria composta por pessoas entre 46 e 55 anos.
    - A análise indica que 64,57% dos clientes são casados ou vivem em união estável, o que influencia diretamente seus hábitos de consumo.
    - A quantidade de filhos também impacta nas decisões de compra: clientes com 1 ou 2 filhos representam juntos 64,75% dos gastos totais. No entanto, o maior ticket médio está entre pessoas casadas sem filhos.
    - O nível de escolaridade mais frequente é o Ensino Superior, mas os clientes com pós-graduação apresentam maior poder aquisitivo.
    - A faixa etária com maior volume de compras é a de 46 a 55 anos, especialmente entre os que possuem Ensino Superior.
    - O produto mais consumido é o vinho, seguido da carne — com destaque para clientes casados e sem filhos como os principais consumidores dessas categorias.
    - Apenas **14,93%** aderiram às campanhas, abaixo da média esperada no varejo (20–30%). Isso sinaliza baixa efetividade nas ações atuais.
    - A loja física é o canal de compra mais utilizado, principalmente entre os clientes de 46 a 55 anos.
- Recomendações
    1. Realizar pesquisa mercadológica para compreender os motivos que levaram à baixa adesão às campanhas de Marketing e Retenção, já que apenas 14,93% dos clientes responderam a elas.
    2. Desenvolver promoções e incentivos para os produtos menos explorados, como Frutas e Doces, com ações temáticas, por exemplo: “Quarta da Feirinha” e “Fim de Semana dos Doces”, visando diversificar o consumo.
    3. Criar ofertas direcionadas para clientes casados e/ou com filhos, que concentram a maior parte dos gastos. Vale destacar que casados sem filhos possuem o maior ticket médio individual, merecendo atenção especial.
    4. Aumentar a taxa de conversão nos canais digitais por meio de ações personalizadas, como frete grátis, cupons e cashbacks. O objetivo é atrair um público mais jovem, especialmente entre 26 e 35 anos, incentivando a compra.
    5. A segmentação permitiu identificar três grupos principais: Campeões, Leais e Em risco.
        - **Campeões**: clientes com alta frequência e volume de compras.
            - A estratégia é investir no marketing de relacionamento para criar conexões fortes e duradouras com a marca, fortalecendo a relação por meio de promoções e cashbacks exclusivos, brindes e sorteios.
        - **Leais**: compram com boa frequência e gastam bem, mas não são os mais recorrentes. É importante reforçar a presença da marca na mente desses clientes e estimular o desejo de compra para torná-los Campeões.
            - Estratégias recomendadas incluem cupons sazonais, cashbacks e marketing de conteúdo em plataformas digitais ou físicas.
        - **Em risco**: clientes inativos há bastante tempo, mas com histórico relevante de compras, que podem ser reativados com ações direcionadas.
            - Recomenda-se o uso de cupons com ofertas exclusivas e incentivos com prazo limitado para gerar senso de urgência.
    6. Nas demais segmentações: Em Crescimento, Promissores e Perdidos/Dormindo.
        - **Em crescimento:** clientes que estão aumentando compras.
            - Oferecer promoções e incentivos para consolidar o hábito e aumentar o ticket médio.
        - **Perdidos/Dormindo:** clientes inativos com histórico baixo.
            - Investir em campanhas de reativação com cupons e ofertas limitadas para estimular o retorno.
        - **Promissores:** clientes recentes com potencial.
            - Incentivar a segunda compra com descontos e comunicação direta para fortalecer o vínculo.
    

## Limitações

- Ausência de dados demográficos importantes, como **gênero**, **localização** e **ocupação**, que poderiam enriquecer a segmentação e permitir ações mais direcionadas.
- Falta de informações sobre as **campanhas de marketing realizadas**, impedindo uma análise mais precisa de performance e impacto.
- Os dados disponíveis são **limitados no tempo**, o que pode comprometer a representatividade do cenário atual de consumo.

## Referências

- Links
    - [Função IMPORTRANGE](https://support.google.com/docs/answer/3093340?hl=pt)
    - [Valores nulos](https://docs.google.com/document/d/1kiUVEx6n9gwu5BcyfTtFMR9UkgICJd2bdjMS7u9Laws/edit?tab=t.0#heading=h.lmfjyfwp7thz)
    - [Função CONTAR.VAZIO](https://support.google.com/docs/answer/3093403?hl=pt)
    - [Valores fora do escopo de análise](https://docs.google.com/document/d/1c__WRov6ZvLsrGuznpsGthOYb3jGwTtnmOFe5zCP3X4/edit?tab=t.0#heading=h.1uzqud4ztnk8)
    - [Unir tabelas](https://docs.google.com/document/d/1IWN0CAJ0TIRQWYLX9lyfRbX6CaXhNN5caj9wvKFT1hQ/edit?tab=t.0#heading=h.qsm4pl9aun3o)
    - [Vídeo: Query](https://www.youtube.com/watch?v=fXFNPH__nkg)
    - [Função PROCV](https://support.google.com/docs/answer/3093318?hl=pt)
    - [Medidas separatizes](https://docs.google.com/document/d/1-rB-GOLd1X0YD4iYoAbOgXMrp19KWkRQ66c8cLbadq8/edit?tab=t.0#heading=h.ib70w4u2p7sg)
    - [Função QUARTIL](https://support.google.com/docs/answer/3094041?hl=pt)
    - [Vídeo: Quartil](https://www.youtube.com/watch?v=qlBk00ismYE)
    - [Segmentação de clientes](https://docs.google.com/document/d/1jlNb9Tj_5oajgIkNd3ALEMaC9pwzVrR6AWEU3suHtm8/edit?tab=t.0#heading=h.cw86ivhsovwo)
    - [Como criar Dashboard](https://www.youtube.com/watch?v=f2EG9Sjdq4U)
