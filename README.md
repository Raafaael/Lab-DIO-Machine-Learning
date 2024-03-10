
# Trabalhando com Machine Learning na Prática no Azure ML

Passo a passo para a resolução do desafio "Trabalhando com Machine Learning na Prática no Azure ML" da DIO.


## Passo 1: Criando o recurso
Clique em "Criar Recurso", pesquise por "Machine Learning" e clique em "Azure Machine Learning"
## Passo 2: Configurando o recurso
### Subscrição

Selecione a assinatura desejada e crie um novo grupo de recursos com o nome que preferir.

Em "Nome" coloque algo relacionado com o projeto e depois selecione a região "EAST US". Não precisa alterar mais nada nessa parte. Pode clicar em "Consultar + criar".

### Iniciando
Após criar, pode clicar em "Ir para recurso".

Nessa nova página, clique em "Iniciar o estúdio".
## Passo 3: Criando o modelo
Nessa página, procure a parte "ML automatizado" na barra lateral.

Clique em "Novo trabalho de ML automatizado"

### Configurações básicas
Preencha os campos "Nome do trabalho", "Novo nome do experimento" e "Descrição". Após isso, clique em "Avançar".

### Tipo de tarefa e dados
Selecione o tipo de tarefa como Regressão e em seguida, em "Selecionar dados", clique em "Criar". No modal aberto, em "Tipos de dados", preencha os campos "Nome", "Descrição" e escolha "Tipo" como Tabular. Clique em "Avançar" e no passo "Fonte de dados", escolha "De arquivos da Web" e clique em avançar novamente.

Em "URL da Web", informe a URL https://aka.ms/bike-rentals.

Em "Configurações de tarefas", escolha o conjunto de dados importado. Após, em "Coluna de destino" escolha a coluna rentals.

### Configurações de tarefas
Nos campos de "Limite", preencha com os valores abaixo e marque "Habilitar encerramento antecipado".

* Máximo de avaliações: 3;

* Máximo de avaliações  simultaneas: 3;

* Máximo de nós: 3;

* Limite de pontuação de métrica: 0.085;

* Limite de tempo de experimento: 15;

* Limite e tempo de iteração: 15.

Em "Validar e testar", em "Tipo de validação" escolhi "Divisão de validação de treinamento".

### Computação 
Apenas clique em "Avançar" até finalizar tudo.

### Examinar 
Após avançar e examinar as configurações do trabalho, clique em "Enviar trabalho de treinamento".

Após finalizar o trabalho de treinamento, crie o modelo. Para isso, acesse a página do trabalho realizado e cliquei em "Modelo de registro". Deixe as opções padrões para "Selecionar saída". Em "Configurações do modelo", somente preencha o nome e a versão. Após isso, clique em criar o modelo.



## Passo 4: Métricas
Para acessar as métricas do modelo treinado, na página do modelo, acesso o link informado em "Criado por trabalho". Também é possível acessar o trabalho informado na opção do menu "Tarefas (jobs)".

Na página da tarefa, acesse a aba métricas.


## Passo 5: Testando o modelo
Na página do modelo, acesse a aba "Pontos de extremidade" e em seguida clique em "Implantar".

Logo após a implantação, acesse a aba "Testar" do ponto de extremidade criado para o modelo.

Para o teste, pode utilizar o json abaixo:

```
{
  "input_data": {
    "data": [
       {
         "day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3 
       }
     ]
  }
}
```

