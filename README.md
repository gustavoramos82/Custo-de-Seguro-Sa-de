# Custo do Seguro Saúde

Será feito um entendimento sobre os custos do seguro de saúde a partir de um dataset obtido no kaggle (pode ser acessado [aqui](https://www.kaggle.com/datasets/mirichoi0218/insurance?select=insurance.csv) , fazendo um entendimento do negócio, e partir disso, criar um modelo de machine learning que tenha uma melhor estimativa acerca dos preços.

Para entender melhor o que representa data coluna, segue o dicionario de dados para o melhor entendimento:

Dicionário dos dados:

- **age** - Idade do beneficiário primário.
- **sex** - genero que contratou o seguro.
- **bmi** - indice de massa corporal.
- **children** - número de crianças cobridas pelo seguro.
- **smoker** - Se fuma (sim ou não).
- **region** - Área residencial que o beneficiario mora nos Estados Unidos.
- **charges** - Custos médicos individuais por seguro seguro de saúde.

![image](https://user-images.githubusercontent.com/39843884/175406209-e5dd73bb-987b-408f-b200-8f763fda9da4.png)

Observando os dados acimas, temos que

- a maioria das pessoa dataset é formado por fumantes;
- cerca de 600 pessoas não tem filhos;
- As idades estão por volta de 20 a 30 anos que é onde se concentra a maior quantidade de clientes.
- e o preço dos custo estão concentrados por volta de 10 mil.

- A partir desse tabela de imc (fonte [aqui](https://www.saudenaosepesa.com.br/diagnostico.html?utm_source=g-search&utm_medium=cpc&utm_content=texto&utm_term=normal&utm_campaign=ogilvybr_novo-nordisk_always-on-performance_g-search_cliques_202205_texto_cpc_calcule-imc&gclid=Cj0KCQjw2MWVBhCQARIsAIjbwoM_742If-6JDY6FZdC8b-cUypjydzxEYzI0v0AC1zBoeQtkfmb6vTkaAjCcEALw_wcB)) temos que a maioria das pessoas tem sobrepeso e obesidade.

![imc](https://i.ibb.co/8B1zRLc/2022-06-21-21-17.png)

![image](https://user-images.githubusercontent.com/39843884/175406578-717f8523-57a6-4120-bd93-d8b54f3c17b4.png)

A idade parece não ter muita relação com o preço mas, uma fato importante foi observado, abaixo de 10 mil, só temos pessos não fumantes, e a partir de 30 mil só tem pessoas fumantes, então a variavel fumante deve ser um fator importante que consideram no preço.

![image](https://user-images.githubusercontent.com/39843884/175406712-951a00a5-25de-463d-988d-6f953461f219.png)

Podemos ver nesse gráfico de boxplot q realment se a pessoa é fumantes, o custo vai ser mais caro.

![image](https://user-images.githubusercontent.com/39843884/175406845-91d59e4c-9a6a-4eec-a219-04ffe6c588de.png)

Podemos ver pelas correlaões que variaveis importantes são skmoke e a age, enquanto as outras não temos uma correlação muito forte.

![image](https://user-images.githubusercontent.com/39843884/175406997-85ca43de-81e9-47db-a4d2-6dc42c5d6b15.png)![image](https://user-images.githubusercontent.com/39843884/175407017-fe4eb5df-4ba6-41ed-af67-070c79f815af.png)

Podemos ver pelos grafico de boxplot e barras e de correlação que a região não tem um efeito nos target, então a mesma será desconsiderada.

Dentre os modelos aplicados, a que teve a melhor performace foi o *Gradiente Boosting*:
![image](https://user-images.githubusercontent.com/39843884/175407286-f9b88192-9e77-4a8f-8300-377f7105efd7.png)

Podemos ver abaixo no gráfico a esquerda que o modelo tem uma boa perfomace, mas como posso ser visto no histograma ao lado que tem muito valores próximos a 10 mil, o modelo tende a estimar valores pŕóximos a este, assim, necessitando de uma coleta de dados com valores maiores a 10 mil para que asim o modelo possa ter uma melhora na estimativa.

![image](https://user-images.githubusercontent.com/39843884/175407779-2c5dd798-55be-4db5-8116-88316c13cb29.png)


