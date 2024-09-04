# Analise_de_Vendas_Farmaceuticas

## Descrição

Este é um projeto em formato de tarefa pela PoD Academy que tem como o objetivo tomar os primeiros passos em fazer uma análise de dados, desde a limpeza de dados até a análise exploratória e vizualização de dados, em um contexto de vendas farmacêuticas e por fim realizar uma apresentação de slides para simular o repasse de informações de um meio técnico para um meio corporativo. Vale ressaltar que é possível realizar a análise de forma bem mais aprofundada e com mais dados, no entanto aqui estou apenas me adaptando a como realizar uma análise.

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
   - Principais insights obtidos durante a análise exploratória (EDA):
      - De acordo com o 'SEXO' pudemos ver que em geral quem compra remédios é o que possui valor '2', e de forma mais específica, no 'TIPO_RECEITUARIO = 4' temos a única contagem em que o 'SEXO = 1' fez mais compras
      - Vemos também que com exceção dos valores muito baixos de idade, que faz com que a curva KDE cresca perto do 0, temos os maiores picos de compras entorno de 23 , e entorno de 43, podendo ser melhor analisado observado cruzando esse intevalo de 'IDADE' com outras variáveis.
      - Em relação à localidade, vemos que de longe temos um consummo muito maior de medicamentos a região 'SUDESTE', em especial nos estados do Rio de Janeiro e São Paulo, provavelmente devido à quantia massiva de pessoas nesses lugares em relação ao resto do Brasil, podemos até realizar uma normalização e analisar a proporção de medicamentos em razão da população.
      - É possível também analisar o tipo de problemas temos em certos sexos, idades e localidades baseado no principio ativo e sua urgencia baseado na quantidade de venda caso soubesse a utilidade de cada valor para essa variável
      - O número gigante de valores nulos na variável CID10 indica simplesmente que esse valor não é obrigatório para a compra de um medicamento, a não ser que o tipo de receita seja diferente, como é o caso de remédios psiquiátricos que causam dependencia.


 *(Auto-nota[Serve para o criador desse documento melhorar em análises futuras]: Pesquisar mais a fundo algumas variáveis antes de começar a análise, ir além no que pode ser feito como citado nos itens anteriores, e implementar a análise com mais dados do que os disponíveis)*
   - Gráficos e correlações importantes:
       - ![image](https://github.com/user-attachments/assets/91b63ae0-d56d-42eb-bf31-b670b0c3efed)
       - ![image](https://github.com/user-attachments/assets/0a4123ff-895f-4d8e-84c0-a095d2379fc3)
       - ![image](https://github.com/user-attachments/assets/ea9854c9-f6a1-41ff-8a64-25dbe84d4f34)
       - ![image](https://github.com/user-attachments/assets/774de6e0-0e1c-42ab-96f3-eccf6c597ce2)
       - ![image](https://github.com/user-attachments/assets/ab1fe029-6b49-4282-9de8-8450592e90fb)
