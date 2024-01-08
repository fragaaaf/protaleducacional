# protaleducacional
Projeto de geração e análise de avaliação para acompanhamento do desempenho dos estudantes. 
 ## Tarefas
 - [ ] Retirar as tabelas pessoas da modelagem (Fazendo as foreing keys que as apontavam apontarem para auth.users).
  *  - [x] Criada a Tabela auth.users (Nota: Substituiu a Tabela Curso).
  *  - [x] Atualizadas as Tabelas **Estudante** e **Professor**.
  *  - [x] Feitas as relações (um para muitos) das Tabelas Estudantes e Professor para a Tabela auth.users
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
