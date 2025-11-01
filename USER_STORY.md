# 📘 User Story – Módulo de Cadastro e Listagem de Cursos Beedoo

## Descrição da User Story

**Como** usuário da plataforma  
**Quero** cadastrar novos cursos e visualizar a lista de cursos criados  
**Para** gerenciar facilmente os cursos disponíveis e acompanhar suas informações básicas.

---

## 🧩 Critérios de Aceite

1. Ao acessar o sistema, o usuário deve visualizar a lista de cursos cadastrados.  
2. Caso não existam cursos, o sistema deve exibir uma mensagem informando “Nenhum curso cadastrado no momento.”  
3. O usuário deve conseguir acessar a página de **cadastro de curso** por meio do menu superior.  
4. Todos os campos do formulário devem ser validados antes do envio:  
   - Nome, descrição, imagem, datas, vagas e tipo de curso são obrigatórios. 
   - Ao selecionar tipo de curso, habilita o campo "Endereço" e "link de inscrição" que devem ser obrigatóris e válidos.
   - A data final deve ser **igual ou posterior** à data inicial.  
   - O número de vagas deve ser **maior que zero**.  
5. Ao cadastrar um curso válido, ele deve aparecer imediatamente na lista de cursos.  
6. O botão “Excluir Curso” deve remover corretamente o item da lista.

---

## 🧠 Decisões Tomadas

- A User Story foi criada considerando que o sistema é **aberto**, sem autenticação.  
- O foco principal é validar **a criação, listagem e exclusão de cursos**, garantindo consistência dos dados e boas práticas de usabilidade.  
- Foram incluídos critérios de aceite que cobrem **fluxos positivos** (cadastro válido) e **negativos** (valores inválidos, campos vazios).  
- O requisito de mensagem “Nenhum curso cadastrado” foi incluído por ser uma melhoria importante de **feedback ao usuário**.

---

## 🔍 Escopo de Teste

Os testes abrangerão:
- Validação dos campos obrigatórios no formulário de cadastro.  
- Regras de negócio para datas e número de vagas.  
- Comportamento de atualização da lista após novos cadastros e exclusões.  
- Exibição da mensagem informativa quando a lista estiver vazia.  
- Comportamento da interface e resposta aos erros.

---

## 🚫 Fora do Escopo

- Login, autenticação e controle de usuários.  
- Persistência de dados após recarregar a página (banco de dados).  
- Integrações externas.
