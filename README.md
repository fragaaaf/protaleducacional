# protaleducacional
Projeto de geração e análise de avaliação para acompanhamento do desempenho dos estudantes. 
 ## Tarefas
 ### 08/01/2024 - nº 02/02
 - [ ] Migrar modelagem da ferramenta DrawSQL para dbdiagram.io
  *  - [ ] Consultar ![documentação do DbDiagram.io](https://dbml.dbdiagram.io/docs/#index-settings)
     - [ ] ![Vídeo sobre DBDiagram.io] (https://youtu.be/l_yTCfhFxdQ?si=Dp7_1063_-Auf_61)
  *  - [x] Modelagem escrita (Falta aparecer o diagrama.
  *  - [ ] Detalhes sobre a configuração.

 ### 08/01/2024- nº 01/02
 - [ ] Retirar as tabelas pessoas da modelagem (Fazendo as foreing keys que as apontavam apontarem para auth.users).
  *  - [x] Criada a Tabela auth.users[Obj.: Permissões de acsso as tabelas do banco de dados]
  *  - [x] Apagadas as Tabelas **Estudante** e **Professor** por não serem mais necessárias.
  *  - [x] ~~Feitas as relações (um para muitos) das Tabelas Estudantes e Professor para a Tabela auth.users~~
  *  - [X] Criadas as relações **auth.users.id -> Resultado.id_estudante_fk** e **auth.users.id-> Professor_disciplina.id_professor_fk**
  *  - [X] Recriadas as **Tabelas Alternativa** e **Tabela Curso**. 
 - [x] Sintetizar brevemente aprendizados em markdown num repositorio no github.
 - [x] Compartilhar acesso a esse repositório com artu-hnrq.
 
 - ![Modelagem do Banco de Dados](https://drawsql.app/teams/dev-tst/diagrams/p-educ/embed)
## Pendências
 - [ ] Lembrete: DrawSQL permite apenas 15 tabelas
 - [ ] Tabela Alternativa deu lugar a Tabela Alocação
 - [ ] Tabela Curso deu lugar a Tabela auth.users(Tabela Pessoa)

## Consultas requeridas
* Quais os estudantes fizeram a atividade? [Obj.: Saber a frequência do estudante nas atividades ao longo do tempo]
* Quais estudantes NÃO fizeram a atividade? [Obj.: ter lista de quais estão com pendências nas atividades]
* Quais estudantes  - QUE FIZERAM - não obteram nota acima de 6? [Obj.: quem apresenta dificuldade - estatística]
* Quais (RE)FIZERAM as novas atividades sugeridas pelo portal? [Obj.: quem foi persistente?]
* Quais estudantes tiraram 10. [Obj.: destacar o empenho].
* Relação decrescente das questões(assuntos) mais erradas [Obj.: saber onde a turma mais errou].
* Relação crescente dos estudantes com maior nota na atividade [Obj.: criar classificação por atividade]
* Relação crescente dos estudantes com maiores médias. [Obj.: criar classificação geral]
* Relação dos estudantes que mais acessaram ao portal [Obj.: criar classificação]
* Quantas questões tenho de cada assunto? [Obj.: gerenciar o excesso ou a falta de perguntas sobre o assunto]
* 
# Anexo I - Comando do DBDiagram.io

