 <a id="topo"></a>
# protaleducacional
Projeto de geração e análise de avaliação para acompanhamento do desempenho dos estudantes. 
 ## Mentoria de ![Arthur Henrique](https://github.com/artu-hnrq)
  ~~~ janeiro/2024

  - [x] 08 - Migrar modelagem da ferramenta DrawSQL para dbdiagram.io
  - [x] 05 - Exportar as pessoas para a tabela auth.users
  - [x] 04 - Criação da Tabela Alocação para gerar histórico do curso
  - [x] 03 - Não houve mentoria
  - [x] 02 - Uso da ferramenta DrawSQL para geração da modelagem
~~~
~~~ dezembro/2023
 - [x] 29 - Modelagem física(rascunho) do BD da aplicação
~~~
 ## Tarefas
 ### 08/01/2024 - nº 02/02
 - [x] Migrar modelagem da ferramenta DrawSQL para dbdiagram.io
  *  - [x] Consultar ![documentação do DbDiagram.io](https://dbml.dbdiagram.io/docs/#index-settings)
     - [x] ![Vídeo sobre DBDiagram.io] (https://youtu.be/l_yTCfhFxdQ?si=Dp7_1063_-Auf_61)
  *  - [x] ![Modelagem DBDiagram.io concluida](https://dbdiagram.io/d/portal_educ-659c5f01ac844320ae7c62ae)
  *  - [x] Erros ou falhas corrigidas.
  *  - [x] [Código do Diagrama (abaixo)](#modelagemDBDiagram.io)
  *  - [x] [Documentação de Consulta](#doc) 

 ### 08/01/2024- nº 01/02
 - [x] Retirar as tabelas pessoas da modelagem (Fazendo as foreing keys que as apontavam apontarem para auth.users).
  *  - [x] Criada a Tabela auth.users[Obj.: Permissões de acesso as tabelas do banco de dados]
  *  - [x] Apagadas as Tabelas **Estudante** e **Professor** por não serem mais necessárias.
  *  - [x] ~~Feitas as relações (um para muitos) das Tabelas Estudantes e Professor para a Tabela auth.users~~
  *  - [X] Criadas as relações **auth.users.id -> Resultado.id_estudante_fk** e **auth.users.id-> Professor_disciplina.id_professor_fk**
  *  - [X] Recriadas as **Tabelas Alternativa** e **Tabela Curso**. 
 - [x] Sintetizar brevemente aprendizados em markdown num repositorio no github.
 - [x] Compartilhar acesso a esse repositório com artu-hnrq.
 
 - ![Modelagem do Banco de Dados no DrawSQL](https://drawsql.app/teams/dev-tst/diagrams/p-educ/embed)
## ~~Pendências~~
 - [x]  ~~Lembrete: DrawSQL permite apenas 15 tabelas~~
 - [x] ~~Tabela Alternativa deu lugar a Tabela Alocação~~
 - [x] ~~Tabela Curso deu lugar a Tabela auth.users(Tabela Pessoa)~~

## Consultas requeridas
* Quais os **estudantes** fizeram a atividade? [Obj.: Saber a frequência do estudante nas atividades ao longo do tempo]
* Quais **estudantes** NÃO fizeram a atividade? [Obj.: ter lista de quais estão com pendências nas atividades]
* Quais **estudantes**  - QUE FIZERAM - não obteram nota acima de 6? [Obj.: quem apresenta dificuldade - estatística]
* Quais **estudantes** (RE)FIZERAM as novas atividades sugeridas pelo portal? [Obj.: quem foi persistente?]
* Quais **estudantes** tiraram 10. [Obj.: destacar o empenho].
* Relação decrescente das **questões(assuntos)** mais erradas [Obj.: saber onde a turma mais errou].
* Relação crescente dos **estudantes** com maior nota na atividade [Obj.: criar classificação por atividade]
* Relação crescente dos **estudantes** com maiores médias. [Obj.: criar classificação geral]
* Relação dos **estudantes** que mais acessaram ao portal [Obj.: criar classificação]
* Quantas **questões** tenho de cada assunto? [Obj.: gerenciar o excesso ou a falta de perguntas sobre o assunto]
* Quais são os **professores** estão na turma?
* Quais as **disciplinas** da turma?
* Quais **professores ministram(ou ministraram) as disciplinas** na turma?
* Quais as **notas do estudante** no módulo?
* Qual a **média final** do estudante no módulo?
* 

  <a id="modelagemDBDiagram.io"></a>
# Anexo I - Comando do DBDiagram.io
[Topo](#topo)
```
// Use DBML to define your database structure
// Docs: https://dbml.dbdiagram.io/docs

Table auth.users {
  id integer [primary key]
  nome varchar
  email varchar
  telefone varchar
  login varchar
  senha varchar 
}

Table resultado {
  id integer [primary key]
  id_estudante_fk integer [foreign key]
  id_atividade_fk integer [foreign key]
  nrAcessos integer
  data timestamp
  acertos integer
  erros integer
  percentual float
  }

Table disciplina {
  id integer [primary key]
  nome varchar
  sigla varchar
}

Table modulo {
  id integer [primary key]
  id_disciplina_fk integer
  id_curso_fk integer
}

Table atividade{
  id integer [primary key]
  id_disciplina_fk integer
  sigla varchar
  tipo varchar
}

Table assunto {
  id integer [primary key]
  id_disciplina_fk integer
  objetivo varchar
  explicacao varchar
  exemplo varchar
}

Table curso {
  id integer [primary key]
  nome varchar
  sigla varchar

}

Table professor_disciplina {
  id integer [primary key]
  id_disciplina_fk integer [foreign key]
  id_professor_fk integer [foreign key]
}

Table alocacao {
  id integer [primary key]
  id_profesor_disciplina_fk integer [foreign key]
  id_turma_modulo_fk integer [foreign key]
}

Table turma_modulo {
  id integer [primary key]
  id_turma_fk integer [foreign key]
  id_modulo_fk integer [foreign key]
  semestre integer
}
Table turma {
  id integer [primary key]
  id_curso_fk integer
  sigla varchar
}

Table atividade_questao {
  id integer [primary key]
  id_atividade_fk integer [foreign key]
  id_questao_fk integer [foreign key]
}

Table questao_assunto {
  id integer [primary key]
  id_assunto_fk integer [foreign key]
  id_questao_fk integer [foreign key]
}

Table questao {
  id integer [primary key]
  id_alternativa_fk integer
  enunciado varchar
  gabarito varchar
}

Table curso {
  id integer [primary key]
  nome varchar
}

Ref: posts.user_id > users.id // many-to-one

Ref: users.id < follows.following_user_id

Ref: users.id < follows.followed_user_id

```
[Topo](#topo)
 <a id="doc"></a>
# Anexo II - Documentação de consulta

* [Criando um arquivo Markdown com links internos](https://medium.com/thiagogmta/criando-um-arquivo-markdown-com-links-internos-3ad5da825ccd)
* [Guia básico de Markdown](https://docs.pipz.com/central-de-ajuda/learning-center/guia-basico-de-markdown#open)
