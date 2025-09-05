Modelo Conceitual
1.	Entidades e atributos
Criei as entidades aluno, matrícula, curso (referente ao idioma escolhido), turma e professor.
- Atributos de Aluno: ID_Aluno(identificador), nome, CPF (identificador), telefone, email.
- Atributos de Matrícula: ID_Matrícula (identificador), DataPagamento e DataInício.
- Atributos de Curso: ID_Curso (identificador), valor (correspondente à mensalidade do curso do idioma escolhido) e nome (referente ao idioma do curso).
- Atributos de Turma: ID_Turma (identificador), nível (básico, avançado etc), horário (matutino, vespertino, norutno) e sala.
- Atributos de Professor: ID_Professor (identificador), nome, CPF (identificador), telefone, email.
Resolvi criar matrícula como entidade, apesar de achar que poderia apenas ser um atributo de aluno, porque nesse caso não sei um aluno poderia estar matriculado para estudar mais de um idioma (ou seja, em mais de um curso).

2.	Relacionamentos e cardinalidades
- O aluno realiza a matrícula, de forma que cada aluno pode ter várias matrículas ativas (1,n), e cada matrícula está associando a um aluno (1,1).
- A matrícula corresponde aos cursos, de forma que uma matrícula pode estar relacionadas a um único curso ou vários (1,n), enquanto cada curso pode ter várias matrículas associadas (1,n).
- Cada curso oferece turmas, de forma que um curso pode oferecer várias turmas (1,n) e cada turma pertence exclusivamente a um curso.
- O professor leciona turmas, de modo que cada turma possui um único professor (1,1) e um professor pode lecionar várias turmas (1,n).

Modelo Lógico
Aqui, criei as tabelas correspondentes às entidades: aluno, professor, matrícula, turma e curso, cada uma com os respectivos campos, tipos e restrições.
Na tabela Aluno temos o ID_Aluno como um inteiro e chave primária, o nome (varchar 100), CPF (char 11) e único, telefone (varchar 20) e email (varchar 100).
Já na tabela professor, encontramos o ID_Professor (inteiro e chave primária), o nome (varchar 100),  CPF (char 11) único, telefone (varchar 20) e email (varchar 100).
Para a tabela curso, criei os campos ID_Curso (inteiro e chave primária), nome (varchar 50) e valor (decimal 10,2).
Na tabela turma especifiquei o ID_Turma como inteiro e chave primária, o nível (varchar 50), horário (char 11) e sala (varchar 20). Aqui também temos as chaves estrangeiras ID_Curso como um inteiro herdando de curso e ID_Professor, também inteiro e herdando de professor.
Por fim, na tabela referente à matrícula, temos ID_Matrícula (inteiro e chave primária), DataPagamento (date) e DataInicio (date). Também adicionei as chaves estrangeiras ID_Aluno (inteira e herdando de aluno) e ID_Turma (inteira herdando de Turma).
