 <a id="topo"></a>
# Portal Educacional
Projeto de geração e análise de avaliação para acompanhamento do desempenho dos estudantes. 
 ## Mentoria de ![Arthur Henrique](https://github.com/artu-hnrq)

---
 
  <details> 
   <summary>janeiro/2024</summary>
    <DETAILS>
     <SUMMARY>SEMANA DE 29/01-04/02</SUMMARY>
    
  <details>
  <summary>- [ ] 30 - agendada</summary>
   
   - [x] Mentoria:
  </details>
  <details>
  <summary>- [ ] 29 - Agendada</summary>
   
   - [x] Mentoria:
   </details>
   </details>
    <DETAILS>
     <SUMMARY>SEMANA DE 22-28</SUMMARY>
    
  <details>
  <summary>- [ ] 26 - Agendada</summary>
   
   - [x] Mentoria:
   </details>
   
  <details>
  <summary>- [ ] 25 - Agendada</summary>
   
   - [x] Mentoria:
   </details>
  <details>
  <summary>- [ ] 23 - Agendada</summary>
   
   - [x] Mentoria:
   </details>
  <details>
  <summary>- [ ] 22 - Agendada</summary>
   
   - [x] Mentoria:
   </details>
   </details>
    <DETAILS>
     <SUMMARY>SEMANA DE 15-21</SUMMARY>
    
  <details>
  <summary>- [ ] 19 - Agendada</summary>
   
   - [x] Mentoria:
  </details>
  <details>
  <summary>- [ ] 18 - Agendada</summary>
   
   - [x] Mentoria:
  </details>
  <details>
  <summary>- [ ] 16 - Agendada</summary>
   
   - [x] Mentoria:
   </details>
  <details>
  <summary>- [ ] 15 - Agendada</summary>
   
   - [x] Mentoria:
   </details>
   </details>
   <DETAILS>
     <SUMMARY>SEMANA DE 08-14</SUMMARY>
    
  <details>
  <summary>- [ ] 12 - Agendada</summary>
   
   - [x] Mentoria:
   </details>
  <details>
  <summary>- [ ] 11 - Agendada</summary>
   
   - [ ] Mentoria: 11:30h
   - [ ] SQL(teste inciado): não concluído geração das tabelas e seus relacionamento. Muitos erros no SQL.
         
   <details>
   <summary> SQL: montando SQL para gerar banco<summary>
 
         ~~~ SQL
         -- Supabase AI is experimental and may produce incorrect answers
         -- Always verify the output before executing
         
         alter table turma
         add column id_curso_fk bigint references curso;
         
         alter table alocacao
         add column id_disciplina_professor_fk bigint references disciplina_professor;
         
         alter table alocacao
         add column id_modulo_turma_fk bigint references modulo_turma;
         
         alter table assunto
         add column id_disciplina_fk bigint references disciplina;
         
         alter table assunto_questao
         add column id_assunto_fk bigint references assunto;
         
         alter table assunto_questao
         add column id_questao_fk bigint references questao;
         
         alter table atividade
         add column id_disciplina_fk bigint references disciplina;
         
         alter table atividade_questao
         add column id_atividade_fk bigint references atividade;
         
         alter table atividade_questao
         add column id_questao_fk bigint references questao;
         
         alter table disciplina_professor
         add column id_disciplina_fk bigint references disciplina;
         
         alter table disciplina_professor
         add column id_professor_fk bigint references auth.users;
         
         alter table modulo
         add column id_disciplina_fk bigint references disciplina;
         
         alter table modulo
         add column id_curso_fk bigint references curso;
         
         alter table modulo_turma
         add column id_turma_fk bigint references turma;
         
         alter table modulo_turma
         add column id_modulo_fk bigint references modulo;
         
         alter table questao
         add column id_alternativa_fk bigint references alternativa;
         
         alter table resultado
         add column id_estudante_fk bigint references auth.users;
         
         alter table resultado
         add column id_atividade_fk bigint references atividade;
         ~~~
   </details>

   - [ ] Gerar politicas: falta
        - [ ] tb_x: select, insert, update, delete 
   </details>
   <details>
     <summary> - [x] 10 - Supabase: Continuando o BD baseado na modelagem</summary>

   - [x] Mentoria: NÃO HOUVE. 
   - [x] Tabelas criadas[12 de 15]: alocacao, alternativa, assunto, atividade_questao, curso, modulo, professor_disciplina, questao, questao_assunto, turma, turma_modulo, questao.
   - [x] relacionamentos criados[13/18]:
        
        - [x] 01-alternativa.id -> questao.id_alternativa_fk
        - [x] 02-assunto.id -> assunto_questao.id_assunto_fk
        - [x] 03-atividade.id -> atividade_questao.id_atividade_fk
        - [x] 04-curso.id -> modulo.id_curso_fk
        - [x] 05-curso.id -> turma.id_curso_fk
        - [x] 06-dicplina.id -> assunto.id_disciplina_fk
        - [x] 07-dicplina.id -> modulo.id_disciplina_fk
        - [x] 08-modulo.id -> modulo_turma.id_modulo_fk
        - [x] 09-disciplina_professor.id -> alocacao.id_disciplina_professor_fk
        - [x] 10-questao.id -> atividade_questao.id_questao_fk
        - [x] 11-questao.id -> assunto_questao.id_questao_fk
        - [x] 12-turma.id -> modulo_turma.id_turma_fk
        - [x] 13-modulo_turma.id -> alocacao.id_modulo_turma_fk
   - [x] Conferência de quantidade de tabelas[15] e relacionamentos[18]
  
   </details>
   <details>
     <summary> - [x] 09 - Supabase: criando o BD baseado na modelagem</summary>
    
   - [x] Mentoria: realizada.
   - [x] Tabelas criadas[3 de 15]: auth.users, disciplina, resultado, professor_disciplina, atividade
   - [x] relacionamentos criados[05/18]: 
        - [x] 01-auth.users.id -> resultado.id_estudante_fk
        - [x] 02-auth.users.id -> prodessor_disciplina.id_professor_fk
        - [x] 03-disciplina.id -> atividade.id_disciplina_fk
        - [x] 04-disciplina.id -> disciplina_professor.id_disciplina_fk
        - [x] 05-atividade.id -> resultado.id_atividade_fk 
   </details>
        
  - [x] 08 - Migrar modelagem da ferramenta DrawSQL para dbdiagram.io
</DETAILS>
  <DETAILS>
 <SUMMARY>SEMANA DE 01-07</SUMMARY>
   
  - [x] 05 - Exportar as pessoas para a tabela auth.users
  - [x] 04 - Criação da Tabela Alocação para gerar histórico do curso
  - [x] 03 - Não houve mentoria
  - [x] 02 - Uso da ferramenta DrawSQL para geração da modelagem
</DETAILS>
</details>

<details> 
   <summary>dezembro/2023</summary>
 
   - [x] 29 - Modelagem física(rascunho) do BD da aplicação
</details>

 ## Tarefas

<details>
<summary>08/01/2024 - nº 02/02</summary>

 - [x] Migrar modelagem da ferramenta DrawSQL para dbdiagram.io
  *  - [x] Consultar ![documentação do DbDiagram.io](https://dbml.dbdiagram.io/docs/#index-settings)
     - [x] ![Vídeo sobre DBDiagram.io] (https://youtu.be/l_yTCfhFxdQ?si=Dp7_1063_-Auf_61)
  *  - [x] ![Modelagem DBDiagram.io concluida](https://dbdiagram.io/d/portal_educ-659c5f01ac844320ae7c62ae)
  *  - [x] Erros ou falhas corrigidas.
  *  - [x] [Código do Diagrama (abaixo)](#modelagemDBDiagram.io)
  *  - [x] [Documentação de Consulta](#doc) 
</details>

<details>
<summary>08/01/2024- nº 01/02</summary>

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

</details>

## Consultas requeridas

<details>
<summary>Consultas requeridas</summary>
 
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
</details>

  <a id="modelagemDBDiagram.io"></a>
# Anexo I - Comando do DBDiagram.io
[Topo](#topo)

<details>
<summary>Código da Modelagem</summary>
 
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
  id_estudante_fk integer [ref:> auth.users.id]
  id_atividade_fk integer [ref:> atividade.id]
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
  id_disciplina_fk integer [ref:>  disciplina.id]
  id_curso_fk integer [ref:> curso.id]
}

Table atividade{
  id integer [primary key]
  id_disciplina_fk integer [ref:> disciplina.id]
  sigla varchar
  tipo varchar
}

Table assunto {
  id integer [primary key]
  id_disciplina_fk integer [ref:>  disciplina.id]
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
  id_disciplina_fk integer [ref:> disciplina.id]
  id_professor_fk integer [ref:>  auth.users.id]
}

Table alocacao {
  id integer [primary key]
  id_profesor_disciplina_fk integer [ref:>  professor_disciplina.id]
  id_turma_modulo_fk integer [ref:>  turma_modulo.id]
}

Table turma_modulo {
  id integer [primary key]
  id_turma_fk integer [ref:> turma.id]
  id_modulo_fk integer [ref:> modulo.id]
  semestre integer
}
Table turma {
  id integer [primary key]
  id_curso_fk integer [ref:> curso.id]
  sigla varchar
}

Table atividade_questao {
  id integer [primary key]
  id_atividade_fk integer [ref:> atividade.id]
  id_questao_fk integer [ref:> questao.id]
}

Table questao_assunto {
  id integer [primary key]
  id_assunto_fk integer [ref:> assunto.id]
  id_questao_fk integer [ref:> questao.id]
}

Table questao {
  id integer [primary key]
  id_alternativa_fk integer [ref:> alternativa.id]
  enunciado varchar
  gabarito varchar
}

Table alternativa {
  id integer [primary key]
  alternativa varchar
}
```
</details>

[Topo](#topo)

 <a id="doc"></a>

# Anexo II - Documentação de consulta

* [Criando um arquivo Markdown com links internos](https://medium.com/thiagogmta/criando-um-arquivo-markdown-com-links-internos-3ad5da825ccd)
* [Guia básico de Markdown](https://docs.pipz.com/central-de-ajuda/learning-center/guia-basico-de-markdown#open)
* [Uso do Markdown no VSCode](https://dev.to/azure/escrita-eficiente-de-artigos-com-vscode-1am4#:~:text=Escrevendo%20Arquivos%20Markdown,markdown%20ou%20md%20e%20pronto!)
