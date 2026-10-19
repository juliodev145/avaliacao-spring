Julio Cezar

Aplicação para testar conhecimentos com Spring Boot e requisições.

- Erro 1: pom.xml, estava rodando o escopo de teste, descobri pelo log "ClassNotFoundException: org.h2.Driver", corrigi colocando o escopo runtime.
- Erro 2: ProfessorController.java, o requestMapping estava incompleto, descobri pelo erro 404 no post, corrigi completando de "/professor" para "/professores".
- Erro 3: Professor.java, não tinha o auto-incremento, descobri pelo erro 500 no post, corrigi colocando a anotação GenerateValue.
- Erro 4: application-test.properties, o hibernate não criou as tabelas, descobri pela log "Table "PROFESSORES" not found (this database is empty)", corrigi trocando "spring.jpa.hibernate.ddl-auto=none" para "spring.jpa.hibernate.ddl-auto=update".  
- Erro 5: Aluno.java, tinha dados duplicados, descobri pelo GET de um aluno com ra: ADS e curso: ADS, corrigi de this.ra = dados.cursos() para this.ra = dados.ra().
- Erro 6: AlunoController.java, faltou a anotação Transaction, descobri pois não estava invocando o método atualizar, corrigi colocando a anotação.
- Erro 7: Matricula.java, faltou a anotação JOIN de ManyToOne, retornou 500 com "Unique index or primary key ... MATRICULAS(ALUNO_ID)", troquei @OneToOne por @ManyToOne no campo aluno.
- Erro 8: DadosCadastroMatricula.java, o campo se chamava idAluno mas o JSON envia alunoId, descobri com o o POST /matriculas e dava 500 com a mensagem "The given id must not be null", corrigi trocando IdAluno para alunoId.

Para rodar localmente:

- IDEs: VsCode, STS, IntelliJE
- Simulador de requisições ou navegador
- Spring Boot
- Clonar o repositório
- Testar
