# Otimização de operações de sondas

#### Aluno: [Agnaldo Silva](https://github.com/AgnaldoMagnum)
#### Orientador: [Felipe Borges](https://github.com/FelipeBorgesC).


---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

<!-- para os links a seguir, caso os arquivos estejam no mesmo repositório que este README, não há necessidade de incluir o link completo: basta incluir o nome do arquivo, com extensão, que o GitHub completa o link corretamente -->
- [Link para o modelo](https://github.com/AgnaldoMagnum/proj/blob/main/proj.xlsx). 


---

### Resumo
O planejamento de operações com unidades marítimas pode viabilizar projetos e otimizar os insumos necessários às operações. A quantidade limitada de unidades, o impacto dos atrasos e os altos custos envolvidos nesse tipo de cenário somente reforça a necessidade de investir em uma programação robusta. 

### 1. Introdução

Após a comprovação do potencial exploratório de uma área a perfuração de poços é a primeira fase na etapa de desenvolvimento da produção. Para uma melhor utilização dos recursos marítimos, que normalmente são operados por empresas terceiras e utilizados através de contratos, é preciso um bom planejamento das etapas a serem realizadas e as ferramentas necessárias. 
Para o caso estudado foi considerada a necessidade de otimizar a utilização de embarcações conhecidas como Sondas Marítimas para operações em um determinado projeto. O projeto possui 30 poços a serem executados e há flexibilidade no número de sondas a serem dedicadas ao projeto, porém o tempo é algo crucial nesse desenvolvimento e faz-se necessário que essas sejam realizadas entre quatro e seis meses.


### 2. Modelagem
Para atender a demanda do planejamento foi solicitada ao projeto uma estimativa de tempo de operação por poço. Foi informado que uma média de tempo de operação é de 30 dias por poço, e que dependendo das facilidades encontradas na unidade esse tempo pode ser diminuído ou estendido. O custo das unidades também varia de acordo com as facilidades presentes na mesma.
Considerando a execução de 30 poços com um período médio de operação de 30 dias por poço, foi obtido um tempo de operação de 900 dias de sonda. A partir desse dado foi estabelecido que uma quantidade de 5 a 7 sondas seriam suficientes para o atendimento do projeto. Com essa premissa foi fornecida, pelo projeto, uma matriz em que foram correlacionados os tempos de operação nos poços para sete sondas, conforme abaixo:


![image](https://user-images.githubusercontent.com/108281978/176030179-fe93a392-25d2-4ed5-8d4b-f2246d84a9c3.png)



Esse dado de entrada foi utilizado para a otimização do planejamento das sondas a serem contratadas para atendimento ao projeto. Na solução adotada foram simulados modelos com atendimento por 5, 6 e 7 unidades. Foi também considerado como dado de entrada a distância (já convertida em dias de operação) entre os poços onde serão realizadas as intervenções. Além disso foi também considerada a possibilidade de impor restrição temporal em que determinado poço precisa ser atendido anteriormente a outro.
A função objetivo do problema foi o custo de operação total para a campanha dos 30 poços, a restrição temporal foi modelada de forma a “punir” o custo em 2% cada vez que uma restrição não fosse atendida.

### 3. Resultados

Durante as simulações realizadas o melhor resultado financeiro foi observado com a utilização de seis sondas, e sem restrição temporal, totalizando um valor total de R$169.288.000,00. As simulações com cinco e sete sondas obtiveram os valores de R$174.582.000,00 e R$170.721.000,00, respectivamente. A modelagem fornece também a unidade que atenderá determinado poço e a ordem em que eles serão realizados.
A estimativa inicial foi obtida considerando-se que o poço seguinte para operação de cada sonda fosse o de menor distância a partir do poço atual. As figuras abaixo mostram os resultados comparativos entre a estimativa inicial de custo da operação sem otimização e o custo final após a aplicação da otimização.


5 Sondas

![image](https://user-images.githubusercontent.com/108281978/177996448-d2eeedca-8744-429e-bd5f-1b4e0612a5cd.png)
![image](https://user-images.githubusercontent.com/108281978/177996468-7d699581-1548-4c9e-93c5-ba56bad30b9e.png)

Redução de 9,0% do custo total da campanha

6 Sondas

![image](https://user-images.githubusercontent.com/108281978/177996533-00192889-ff7e-4236-9f5f-f9b6d4a2b235.png)
![image](https://user-images.githubusercontent.com/108281978/177996554-bf3fd49a-05f7-4195-8a31-242b50c6e0b1.png)
 
Redução de 6,3% do custo total da campanha

7 Sondas

![image](https://user-images.githubusercontent.com/108281978/177996588-76b81995-5f3b-414e-b2a7-2de822e589f6.png)
![image](https://user-images.githubusercontent.com/108281978/177996614-db52ac3e-f007-4dd4-9026-5da581ed2c0a.png)
 
Redução de 7,5% do custo total da campanha

Além da análise financeira é possível também analisar o tempo de operação para realização das operações. Com a adoção de cinco sondas o maior tempo de operação é de 219 dias, o que extrapola a previsão inicial para realização em até seis meses. A adoção de seis sondas reduz o tempo de operação total para 181 dias e com sete sondas esse tempo é de 152 dias, deve também ser levado em conta o menor tempo de operação para uma unidade que é de 136, 114 e 85 dias para 5, 6 e 7 sondas, respectivamente. Esse tempo pode ter impacto na contratação, haja vista que um tempo muito curto pode não ser atrativo para a celebração de um contrato.

### 4. Conclusões

Através da análise dos resultados é observado que é possível utilizar as ferramentas de algoritmos genéticos para otimizar o planejamento das atividades das unidades marítimas em poços. A utilização desses algoritmos é útil em problemas que possuem um espaço de busca extenso, possibilitando um grande conjunto de soluções viáveis. 
Com a ajuda da modelagem adotada é possível realizar a programação para operações obtendo uma redução dos custos de algo em torno de 7%, além de atender critérios pré-estabelecidos. Também foi possível concluir que a operações com 6 sondas possui uma vantagem financeira em relação aos outros cenários analisados.

---

Matrícula: 202.100.089

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
