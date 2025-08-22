### 8. Sistema de Gestão de Treinamentos
**Descrição:** Plataforma para gerenciar cursos e treinamentos.

**Requisitos Funcionais:**
1. Cadastro de cursos.
2. Inscrição de alunos.
3. Controle de progresso.
4. Emissão de certificados.

**Requisitos Não Funcionais:**
- Compatível com e-learning.
- Geração automática de certificados.

**Histórias de Usuário:**
- **Como aluno**, quero ver meu progresso **para que** eu saiba o que falta completar.
  - **Critérios de Aceite:** Barras de progresso; certificado liberado ao final.

**Etapas/Sprints:**
- Sprint 1: Cadastro de cursos.
- Sprint 2: Progresso.
- Sprint 3: Certificados.

------------------------------------------------------------------------

**Entidades:**

-   **Curso**
    -   `id` (PK)\
    -   `titulo`\
    -   `descricao`\
    -   `carga_horaria` (inteiro \> 0)
-   **Aluno**
    -   `id` (PK)\
    -   `nome`\
    -   `email` (único)
-   **Inscricao**
    -   `id` (PK)\
    -   `curso_id` (FK → Curso)\
    -   `aluno_id` (FK → Aluno)\
    -   `status` (enum: `MATRICULADO`, `CONCLUIDO`, `CANCELADO`)
-   **Progresso**
    -   `id` (PK)\
    -   `inscricao_id` (FK → Inscricao)\
    -   `percentual` (0--100)
-   **Certificado**
    -   `id` (PK)\
    -   `inscricao_id` (FK → Inscricao, único)\
    -   `data_emissao`
