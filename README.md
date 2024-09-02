# Analise_de_Vendas_Farmaceuticas

## Descrição

Este é um projeto em formato de tarefa pela PoD Academy que tem como o objetivo tomar os primeiros passos em fazer uma análise de dados, desde a limpeza de dados até a análise exploratória e vizualização de dados, em um contexto de vendas farmacêuticas e por fim realizar uma apresentação de slides para simular o repasse de informações de um meio técnico para m corporativo. 

## Estrutura do Projeto

- `data/`: 
  - `EDA_Industrializados_202111_sample/`: Conjunto de dados para novembro de 2021.
- `Projeto-Analise_de_Vendas_Farmaceuticas/`: Notebooks Jupyter para EDA (Análise Exploratória de Dados), vizualização dos dados e experimentações.
- `PPT-Vendas_Farmaceuticas/`: PowerPoint relacionado aos resultados da análise de dados juntamente com os insights e recomendações de negócios.
  
## Metodologia

Descrição detalhada das etapas seguidas no projeto, desde a coleta e limpeza dos dados até a modelagem e avaliação. Isso ajuda a entender o fluxo de trabalho e as decisões tomadas.

1. **Coleta de Dados:**
   - Fonte dos dados retirada do portal de dados abertos na área de vendas de medicamentos controlados e antimicrobianos do link: https://dados.gov.br/dados/conjuntos-dados/venda-de-medicamentos-controlados-e-antimicrobianos---medicamentos-industrializados.
   - A amostra da base de dados é composta de informações de vendas farmacêuticas que podem ser divididas em informações de localização, do cliente, dos fármacos e quem os receitou.
   - A descrição de variáveis é tal que:
       - Ano_Venda: Ano que foi realizada aquela venda
       - Mes_Venda: Mes que foi realizada aquela venda
       - UF_Venda: Estado que foi realizada aquela venda
       - Municipio_Venda: Município que foi realizada aquela venda
       - Principio_Ativo: A principal substância química responsável por agir no corpo ao tomar o fármaco
       - Descrição_Apresentação: Posologia, que é a quantidade a ser dada para o paciente
       - QTD_Vendida: Quantas unidades do mesmo medicamento foi vendido de uma vez
       - Unidade_Medida: Em que tipo de embalagem o fármaco está dividio em "Caixa" ou "Frasco" 
       - Conselho_Prescritor: Órgão ou grupo de especialistas que tem a função de avaliar, recomendar e, em alguns casos, aprovar medicamentos.
       - UF_Conselho_Prescritor: Estado ao qual o Conselho Prescritor pertence
       - Tipo_Receituario: Normalmente os tipos de receita dados por médicos são divididos por cores, dependendo do tipo de medicamento, no entanto na base de dados temos valores de 1 a 5 para esta variável
       - CID10: Permite a identificação de todas as doenças conhecidas, bem como de sintomas
       - Sexo: Sexo dos clientes com valores 1 e 2 para separação entre feminino e masculino não necessariamente nessa ordem
       - Idade: Idade em semanas dos clientes das respectivas vendas de fármacos
       - Unidade_Idade: de acordo com uma pesquisa pode ser uma padronização para assegurar a compatibilidade entre diferentes conjuntos de dados a idade foi registrada em dias, meses ou anos. Assim, a "unidade_idade" permite que a idade seja compreendida corretamente, independentemente da unidade de medida utilizada
  
2. **Limpeza de Dados:**
   - Valores nulos:
       - Principio_Ativo: como para esta variável foi contabilizado apenas 0.19% de valores nulos, foi determinado que não teriam grande influência nos tratamentos estatísticos e foram desconsideradas essas linhas
       - CID10: como não é obrigatório o CID10 nas receitas sua taxa de nulos na base de dados foi de 99.9%, portanto, considerando que não atrapalharia ou teria relevância estatísticamente desconsideramos essa variável para os tratamentos estatísticos
       - Sexo, Idade, Unidade_Idade: Todos possuem as mesmas porcentagens de valores nulos (34.44%) e nas mesmas linhas, portanto foi possível assumir que esses valores vieram de uma mescla de tabelas e não desconsideramos os nulos para futuros cálculos
         
   - Outliers:
       - Foram identificadso diversos outliers através de Boxplots apenas para as variáveis de quantidades vendidas e para idade, esses outliers foram interpretados como empreseas ao invés de pessoas físicas, mas dependendo do objetivo da análise usariamos os outliers ou não, portanto não houve um tratamento propriamente dito além da interpretação deles
  
3. **Exploração de Dados:**
   - Principais insights obtidos durante a análise exploratória (EDA).
   - Gráficos e correlações importantes.
     
4. **Vizualização de Dados**
   - a
   - a
   
