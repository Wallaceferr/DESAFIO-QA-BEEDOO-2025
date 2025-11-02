# 📘 User Story – Módulo de Cadastro e Listagem de Cursos Beedoo

## Descrição da User Story

**Como** usuário da plataforma  
**Quero** cadastrar novos cursos e visualizar a lista de cursos criados  
**Para** gerenciar facilmente os cursos disponíveis e acompanhar suas informações básicas.

---

🎯 Descrição

O módulo de cursos permite ao usuário criar novos cursos informando dados como nome, descrição, datas, tipo (presencial ou online), endereço ou link de inscrição, imagem e número de vagas.
Após criados, os cursos são listados na tela inicial. O usuário também pode excluir cursos existentes.

---

## 🧩 Critérios de Aceite

1. Deve ser possível cadastrar cursos informando todos os campos obrigatórios.  
2. O sistema não deve permitir campos vazios em nome, descrição, imagem, datas, endereço/link e número de vagas.  
3. A data final deve ser igual ou posterior à data inicial.  
4. O número de vagas deve ser maior que zero.    
5. O campo de endereço só aparece se o tipo de curso for presencial e deve ser obrigatório.  
6. O campo de link só aparece se o tipo de curso for online e deve conter uma URL válida.
7. Após cadastro, o curso deve aparecer na listagem corretamente formatado.
8. Ao excluir um curso, ele deve desaparecer da listagem e exibir mensagem de sucesso.
9. Quando não houver cursos, deve exibir mensagem: “Nenhum curso cadastrado no momento”.
10. O layout deve permanecer consistente, independentemente do tamanho da descrição ou da imagem.

---

## 🧠 Decisões Tomadas

- A User Story foi baseada na observação direta da aplicação disponível em https://creative-sherbet-a51eac.netlify.app/.
- Não há autenticação, portanto o fluxo inicia diretamente na tela de listagem de cursos. 
- O foco principal é validar **a criação, listagem e exclusão de cursos**, garantindo consistência dos dados e boas práticas de usabilidade.  
- Os critérios de aceitação foram definidos com base em práticas comuns de UX e validação de dados em sistemas de cadastro.  

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
