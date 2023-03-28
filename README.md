# Walmart:
### Índice

- [Contextualização](#contextualização)
- [Metodologia Aplicada](#metodologia-aplicada)
- [Entendimento do Negócio Aplicada](#metodologia-aplicada)
  - [Metricas](#metricas)
- [Entendimento dos Dados](#entendimento-dos-dados)
  - [Variáveis](#variáveis)
  - [Variáveis Escolhidas](#variáveis-escolhidas)
- [Preparação dos Dados](#preparação-dos-dados)
  - [Faturamento total, por loja](#faturamento-total-por-loja)
  - [Média de vendas semanais, por loja](#média-de-vendas-semanais-por-loja)
  - [Venda nos feriados, por loja](#venda-nos-feriados-por-loja)
  - [Loja 20, Faturamento 2010, mês a mês](#loja-20-faturamento-2010-mês-a-mês)
  - [Loja 20, Faturamento 2011, mês a mês](#loja-20-faturamento-2011-mês-a-mês)
  - [Loja 20, Faturamento 2012, mês a mês](#loja-20-faturamento-2012-mês-a-mês)
  - [Loja 20, Faturamento nos últimos 3 anos](#loja-20-faturamento-nos-últimos-3-anos)
- [Modelagem](#modelagem)
    - [Ranqueamento das lojas](#ranqueamento-das-lojas)
- [Avaliação](#avaliação)
- [Implantação](#implantação)
- [Conclusão](#conclusão)
    - [Loja 20](#loja-20)
- [Ambiente virtual e Dependências](#ambiente-virtual-e-dependências)


### Contextualização:
Walmart, Inc., é uma multinacional estadunidense de lojas de departamento.
A companhia foi fundada por Sam Walton em 1962, incorporada em 31 de outubro de 1969 e feita capital aberto na New York Stock Exchange, em 1972.
No ano de 2021, obteve um um lucro de $13.51 Bilhões.
Sendo uma das principais lojas de varejo do mundo, os dados contemplam as vendas semanais de 45 lojas espalhadas pelos Estados Unidos.

### Metodologia Aplicada:
A análise foi realizada utilizando o modelo CRISP-DM, o CRISP-DM (Cross Industry Standard Process for Data Mining) é um modelo padrão de processo para projetos de mineração de dados que define um conjunto de fases e tarefas que devem ser executadas para desenvolver soluções de mineração de dados efetivas.

![CRISP-DM](/core/img/CRISP-DM.png)

O modelo CRISP-DM é uma abordagem sistemática e estruturada para a mineração de dados que ajuda as empresas a desenvolver soluções de mineração de dados de maneira eficiente e eficaz, reduzindo o tempo e os custos do projeto.

### Entendimento do Negócio:
O Walmart está buscando realizar um levantamento do faturamento de suas lojas nos Estados Unidos e identificar qual delas seria a melhor opção para expandir. Para isso, contratou uma consultoria estratégica especializada nesse tipo de trabalho.

### Metricas:
1. Faturamento anual.
2. Faturamento total.
3. Vendas durante os feriados (Super Bowl, o Dia do Trabalho, o Dia de Ação de Graças e o Natal).
4. Média de vendas semanais.
5. Crescimento do faturamento ano a ano.

## Entendimento dos Dados:
### Variáveis:
![Data Frame](/core/img/descrição_do_df.png)

### Variáveis Escolhidas:
![Data Frame](/core/img/variáveis_escolhidas.png)

## Preparação dos Dados:
O data frame apresentou uma organização surpreendentemente boa, exigindo pouco esforço para a limpeza dos dados. No entanto, durante a análise, algumas variáveis foram descartadas, tais como Temperature, Fuel_Price, CPI e Unemployment.


### Faturamento total, por loja:
![Data Frame](/core/img/faturamento_total_por_loja.png)

### Média de vendas semanais, por loja:
![Data Frame](/core/img/média_de_vendas_semanais_por_loja.png)

### Venda nos feriados, por loja:
![Data Frame](/core/img/venda_total_nos_feriados_por_loja.png)

### Loja 20, Faturamento 2010, mês a mês:
![Data Frame](/core/img/2010.png)

### Loja 20, Faturamento 2011, mês a mês:
![Data Frame](/core/img/2011.png)

### Loja 20, Faturamento 2012, mês a mês.:
![Data Frame](/core/img/2012.png)

### Loja 20, Faturamento nos últimos 3 anos:
![Data Frame](/core/img/gráfico_ano_a_ano.png)





## Modelagem:
### Ranqueamento das lojas:
Por fim, mas não menos importante, criei um algoritmo de ranqueamento de lojas. Esse algoritmo consiste em atribuir notas às lojas. Cada critério estipulado tem um peso maior ou menor dependendo do caso, sendo que a nota máxima que uma loja pode receber é 320. Chegou o momento de ranquear as lojas.

Os critérios utilizados para ranqueá-los foram:
- **Faturamento Total**, a loja que tiver o maior faturamento ganhará 30 pontos.
- **Faturamento em 2010**, a loja que tiver o maior faturamento em 2010 ganhará
mais 10 pontos.
- **Faturamento em 2011**, a loja que tiver o maior faturamento em 2011 ganhará
mais 10 pontos.
- **Faturamento em 2012**, a loja que tiver o maior faturamento em 2012 ganhará
mais 10 pontos.
- **Crescimento do Faturamento**, a loja que tiver o maior Crescimento do
Faturamento nos últimos 3 anos ganhará mais 50 pontos.
- **Venda Total Nos Feriados**, a loja que tiver a maior Venda Total Nos Feriados
ganhará 30 pontos.
- **Venda Nos Feriados em 2010**, a loja que tiver a maior Venda Nos Feriados em
2010 ganhará mais 20 pontos.
- **Venda Nos Feriados em 2011**, a loja que tiver a maior Venda Nos Feriados em
2011 ganhará mais 20 pontos.
- **Venda Nos Feriados em 2012**, a loja que tiver a maior Venda Nos Feriados em
2012 ganhará mais 20 pontos.
- **Crescimento das Vendas Nos Feriados**, a loja que tiver o maior Crescimento
das Vendas Nos Feriados nos últimos 3 anos ganhará mais 50 pontos.
- **Média de vendas semanais**, a loja que tiver a maior Média de vendas
semanais nos últimos 3 anos ganhará mais 20 pontos.

Critérios  | Notas
---------- | ----
Faturamento Total   | 30
Faturamento em 2010 | 10
Faturamento em 2011 | 10
Faturamento em 2012 | 10
Crescimento do Faturamento | 50
Venda Total Nos Feriados | 30
Venda Nos Feriados em 2010 | 20
Venda Nos Feriados em 2011 | 20
Venda Nos Feriados em 2012 | 20
Crescimento das Vendas Nos Feriados | 50
Média de vendas semanais | 20

## Avaliação:
Para realizar o levantamento do faturamento das lojas nos USA, é importante ter acesso aos dados financeiros de cada uma das lojas da empresa. Esses dados devem incluir informações sobre as vendas totais da loja, bem como as vendas em feriados e a média de vendas semanais nos últimos 3 anos.

Para realizar a análise, podemos utilizar ferramentas de visualização de dados, como gráficos e tabelas. Essas ferramentas permitem que identifiquemos padrões e tendências nas informações, bem como as diferenças entre as lojas.

Com base nos dados coletados, é possível utilizar o algoritmo de ranqueamento de lojas para determinar qual é a melhor opção para expandir o negócio. O algoritmo utiliza vários critérios, como o faturamento total e o crescimento das vendas nos feriados, para determinar a pontuação de cada loja. A loja com a maior pontuação é escolhida como a melhor opção para expansão.

No caso apresentado, a loja 20 obteve a maior pontuação no ranking em comparação com as outras lojas, o que a torna a melhor opção para expandir o negócio. Isso se deve principalmente ao seu alto faturamento, sua performance em vendas nos feriados e sua média de vendas semanais. No entanto, é importante ressaltar que outros fatores, como a localização da loja e a concorrência na região, também devem ser considerados antes de tomar a decisão final de expansão.

## Implantação:
Primeiro, nosso objetivo é definir qual é a melhor loja para expandir o seu tamanho com base no seu desempenho nos últimos 3 anos. Tendo isso em mente, é preciso obter mais informações além do faturamento nos últimos anos para definir se a loja em questão deve ou não ser expandida. Por exemplo, é importante considerar o lucro, o custo operacional da loja, a quantidade de funcionários, a localização, a taxa de desemprego na região e a legislação da área. Por exemplo, na Califórnia, uma lei transformou pequenos delitos avaliados em até US$ 950 em contravenção, o que significa que há uma penalidade, mas os criminosos não são presos.

Segundo, com exceção dos dados cuja fonte é o próprio Walmart, como Store, Date, Weekly_Sales e Holiday_Flag, todos os outros dados não são confiáveis, pois não há como verificar nenhum deles. Estamos falando do Walmart, uma empresa multinacional. Como posso tomar uma decisão com base em variáveis como Temperature, fuel_Price, CPI e Unemployment, se não sei onde cada uma das lojas está localizada?

Terceiro, partindo do pressuposto de que as seguintes informações (Temperature, fuel_Price, CPI e Unemployment) são verdadeiras, não encontrei nenhuma correlação positiva ou negativa que afete as vendas semanais.

Como pode ver, há várias variáveis que influenciam na nossa tomada de decisão. Portanto, antes de determinarmos qual é a melhor loja para investir, precisamos responder a todas as perguntas anteriores ou, pelo menos, à maioria delas.

## Conclusão:
### Loja 20:
A loja 20 é a melhor opção para expandir o seu negócio! Com o maior faturamento e as maiores vendas nos feriados, sua média de vendas por semana supera as demais. Em geral, a loja 20 obteve o maior ranking em comparação com as outras lojas.

![Data Frame](/core/img/walmart-loja.jpg)


## Ambiente virtual e Dependências:
Criando ambiente virtual:
```
python3 -m venv core/.venv
```

Entrando no ambiente virtual:
```
source core/.venv/bin/activate
```

Instale as dependências:
```
pip install -r core/requirements.txt
```
---
Linkedin: <https://www.linkedin.com/in/samuel-barbosa-dev/> 

E-mail: <samueloficial@protonmail.com>