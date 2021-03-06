# Models

Deixaremos em bold o primarykey do Modelo. Caso não esteja marcado, será o id
Em parênteses, ao lado dos dos colchetes, será mostrado a relação de cardinalidade
entre o modelo que esta sendo descrito e seu relacionado(dentro do parenteses).

## **Subject** [Disciplina]
*dacParser/models.py*

O Modelo que armazena informações sobre um disciplina da faculdade

### Atributos
| nome atributo | tipo         | descrição                       |
| ------------- | ------------ | ------------------------------  |
| ***code***    | ***String*** | ***Código da disciplina. Ex: MC102*** |
| name          | String       | Nome da matéria                 |
| type  	    | String       | Graducação: **U** Pós: **G**    |
| descryption   | String       | Ementa da matéria               |
| requeriments  | Subject      | Disciplinas necessárias para se cursar |


## **Offering** [Oferecimento]
*dacParser/models.py*

O modelo que armazena informações sobre um oferecimento de uma disciplina

### Atributos
|nome atributo| tipo          | descrição                          |
| ----------- | ------------- | ---------------------------------- |
| subject     | Subject [n:1] \(Oferecimentos: Matéria\)   | Código da disciplina. Ex: MC102    |
| offering_id  | String        | Determinada turma do modelo. Ex: A |
| semester    | String        | Semestre do oferecimento           |
| year        | String        | Ano do oferecimento                |
| time        | ??            | Colocar o horário e dia da semana  |
| teacher     | Teacher [1:n] \(professor,oferecimento\) | Professordo oferecimento           |
| vacancies   | int           | Capacidade de uma turma              |
| registered  | int           | Número de alunos matriculados        |
| students    | Student [n:n] | Alunos registrados no oferecimento   |
| giveups     | Student [n:n] | Alunos que desistiram do oferecimento|


## **Student** [Aluno]
*dacParser/models.py*

O modelo que armazena informações sobre um estudante

### Atributos
|nome atributo| tipo          | descrição               |
| ----------- | ------------- | ----------------------- |
|***ra***     | ***String***  | ***RA de um aluno***    |
| name        | String        | Nome                    |
| course      | String        | Curso de graduação [pós]|
| course_type | String        | Modalidade do Curso     |
|stu_offerings| Ofering [n:n] \(aluno,disciplina\)| Oferecimentos cursados pelo aluno|


## **Institute** [Instituto]
*dacParser/models.py*


### Atributos
|nome atributo| tipo          | descrição                        |
| ----------- | ------------- | -------------------------------- |  
|    name     | String        | Nome do instituto                |
| ***code***  | ***String***  | ***Código do instituto. Ex: IC***|


## **Teacher** [Professor]
*dacParser/models.py*


### Atributos
|nome atributo| tipo          | descrição           |
| ----------- | ------------- | ------------------- |
|   ***name***| ***String***  | ***Nome do professor***   |
| email       | String        | Email academico do prof.|


## **Token**
*stalkeador/models.py*

Modelo que armazena os tokens gerados para cada aluno

### Atributos
|nome atributo| tipo          | descrição                           |
| ----------- | ------------- | ----------------------------------- |
|   student   | Student [1:1] \(aluno,token\)| Nome do professor                   |
| ***token*** | ***String***  | ***Código do token***               |
|  discipline |Discipline[1:n] \(token, disciplina\) | Disciplina a que pertence o token   |
|     used    | Boolean       | afirma se já foi usada ou não       |


## **Answer**
*gda/models.py*

Modelo que armazena uma resposta de uma questão com as perguntas

### Atributos
|nome atributo| tipo          | descrição                           |
| ----------- | ------------- | ----------------------------------- |
|             |               |                                     |


## **Questionnaire**
*gda/models.py*

Modelo que armazena um questionário com as perguntas

### Atributos
|nome atributo| tipo          | descrição                           |
| ----------- | ------------- | ----------------------------------- |
|             |               |                                     |


## **Question**
*gda/models.py*

Modelo que armazena uma pergunta

### Atributos
|nome atributo| tipo          | descrição                           |
| ----------- | ------------- | ----------------------------------- |
|             |               |                                     |


## **Choice**
*gda/models.py*

Modelo que armazena uma opção de resposta para uma pergunta

### Atributos
|nome atributo| tipo          | descrição                           |
| ----------- | ------------- | ----------------------------------- |
|             |               |                                     |
