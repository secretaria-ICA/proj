# Otimização de operações de sondas

#### Aluno: [Agnaldo Silva](https://github.com/AgnaldoMagnum)
#### Orientador: [Felipe Borges](https://github.com/FelipeBorgesC).


---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

<!-- para os links a seguir, caso os arquivos estejam no mesmo repositório que este README, não há necessidade de incluir o link completo: basta incluir o nome do arquivo, com extensão, que o GitHub completa o link corretamente -->
- [Link para o código](https://github.com/AgnaldoMagnum/proj/blob/main/proj.xlsx). 


---

### Resumo
O planejamento de operações com unidades marítimas pode viabilizar projetos e otimizar os insumos necessários às operações. A quantidade limitada de unidades, o impacto dos atrasos e os altos custos envolvidos nesse tipo de cenário somente reforça a necessidade de investir em uma programação robusta. 

### 1. Introdução

Após a comprovação do potencial exploratório de uma área a perfuração de poços é a primeira fase na etapa de desenvolvimento da produção. Para uma melhor utilização dos recursos marítimos, que normalmente são operados por empresas terceiras e utilizados através de contratos, é preciso um bom planejamento das etapas a serem realizadas e as ferramentas necessárias. 
Para o caso estudado foi considerada a necessidade de otimizar a utilização de embarcações conhecidas como Sondas Marítimas para operações em um determinado projeto. O projeto possui 30 poços a serem executados e há flexibilidade no número de sondas a serem dedicadas ao projeto, porém o tempo é algo crucial nesse desenvolvimento e faz-se necessário que essas sejam realizadas entre quatro e seis meses.


### 2. Modelagem
Para atender a demanda do planejamento foi solicitada ao projeto uma estimativa de tempo de operação por poço. Foi informado que uma média de tempo de operação é de 30 dias por poço, e que dependendo das facilidades encontradas na unidade esse tempo pode ser diminuído ou estendido. O custo das unidades também varia de acordo com as facilidades presentes na mesma.
Considerando a execução de 30 poços com um período médio de operação de 30 dias por poço, foi obtido um tempo de operação de 900 dias de sonda. A partir desse dado foi estabelecido que uma quantidade de 5 a 7 sondas seriam suficientes para o atendimento do projeto. Com essa premissa foi fornecida, pelo projeto, uma matriz em que foram correlacionados os tempos de operação nos poços para sete sondas, conforme abaixo:

Nome	Sonda 1	Sonda 2	Sonda 3	Sonda 4	Sonda 5	Sonda 6	Sonda 7
Poço 1	28	30	24	36	36	30	36
Poço 2	29	33	24	38	31	29	38
Poço 3	29	34	24	39	29	24	39
Poço 4	30	29	26	36	39	28	36
Poço 5	29	31	25	40	37	29	40
Poço 6	25	36	22	36	35	30	36
Poço 7	29	34	24	38	39	29	38
Poço 8	30	34	26	37	40	30	37
Poço 9	27	30	22	39	30	25	39
Poço 10	29	33	24	40	31	23	40
Poço 11	27	35	27	38	39	30	38
Poço 12	26	33	22	37	38	24	37
Poço 13	27	33	23	36	40	26	36
Poço 14	25	36	26	39	31	20	39
Poço 15	30	29	22	37	39	25	37
Poço 16	26	34	22	37	29	29	37
Poço 17	28	36	24	38	36	27	38
Poço 18	28	32	24	36	30	26	36
Poço 19	26	36	26	36	31	27	36
Poço 20	27	36	23	39	37	22	39
Poço 21	26	33	24	39	28	23	39
Poço 22	30	34	26	39	28	30	39
Poço 23	29	31	27	36	36	22	36
Poço 24	29	30	26	40	30	26	40
Poço 25	28	36	22	36	36	22	36
Poço 26	25	36	28	39	34	24	39
Poço 27	25	31	23	38	30	20	38
Poço 28	25	36	25	40	37	21	40
Poço 29	25	34	24	40	37	30	40
Poço 30	29	36	27	36	40	23	36

Esse dado de entrada foi utilizado para a otimização do planejamento das sondas a serem contratadas para atendimento ao projeto. Na solução adotada foram simulados modelos com atendimento por 5, 6 e 7 unidades. Foi também considerado como dado de entrada a distância (já convertida em dias de operação) entre os poços onde serão realizadas as intervenções. Além disso foi também considerada a possibilidade de impor restrição temporal em que determinado poço precisa ser atendido anteriormente a outro.
A função objetivo do problema foi o custo de operação total para a campanha dos 30 poços, a restrição temporal foi modelada de forma a “punir” o custo em 2% cada vez que uma restrição não fosse atendida.

### 3. Resultados

Durante as simulações realizadas o melhor resultado financeiro foi observado com a utilização de seis sondas, e sem restrição temporal, totalizando um valor total de R$ 169.288.000,00. As simulações com cinco e sete sondas obtiveram os valores de R$ 174.582.000,00 e R$ 170.721.000,00, respectivamente. A modelagem fornece também a unidade que atenderá determinado poço e a ordem em que eles serão realizados.
Além da análise financeira é possível também analisar o tempo de operação para realização das operações. Com a adoção de cinco sondas o maior tempo de operação é de 219 dias, o que extrapola a previsão inicial para realização em até seis meses. A adoção de seis sondas reduz o tempo de operação total para 181 dias e com sete sondas esse tempo é de 152 dias, deve também ser levado em conta o menor tempo de operação para uma unidade que é de 136, 114 e 85 dias para 5, 6 e 7 sondas, respectivamente. Esse tempo pode ter impacto na contratação, haja vista que um tempo muito curto pode não ser atrativo para a celebração de um contrato.

### 4. Conclusões

Através da análise dos resultados é observado que é possível utilizar as ferramentas de algoritmos genéticos para otimizar o planejamento das atividades das unidades marítimas em poços. A utilização desses algoritmos é útil em problemas que possuem um espaço de busca extenso, possibilitando um grande conjunto de soluções viáveis. 
Com a ajuda da modelagem adotada é possível realizar a programação para operações de forma a otimizar os custos das unidades e atendendo a critérios pré-estabelecidos. 

---

Matrícula: 202.100.089

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
