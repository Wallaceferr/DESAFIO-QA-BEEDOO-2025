# 🐞 Relatório de Bugs – Beedoo QA Challenge 2025

## 📋 Metodologia Utilizada
Os bugs foram reportados seguindo o modelo **IEEE 829**, que padroniza a documentação de incidentes em testes de software.  
Essa metodologia foi escolhida por sua clareza e objetividade, permitindo a fácil compreensão por desenvolvedores e gestores de produto.

Cada bug documentado contém:
- Identificador único  
- Severidade e prioridade  
- Descrição  
- Passos para reprodução  
- Resultado esperado e obtido  
- Causa possível

---

## BUG-001 – Cadastro de curso sem nome

**Severidade:** Alta  
**Prioridade:** Alta  

**Descrição:**  
O sistema permite cadastrar um curso sem preencher o campo “Nome do curso”.

**Passos para reprodução:**  
1. Acessar “Cadastrar Curso”.  
2. Deixar o campo “Nome do curso” em branco.  
3. Preencher os demais campos válidos.  
4. Clicar em “Cadastrar Curso”.

**Resultado esperado:**  
O sistema deve exibir mensagem de erro e impedir o cadastro sem nome.

**Resultado obtido:**  
Curso é cadastrado normalmente, mesmo sem nome.

**Causa possível:**  
Ausência de validação obrigatória no campo “Nome do curso”.

---

## BUG-002 – Cadastro de curso com vagas negativas

**Severidade:** Média  
**Prioridade:** Alta  

**Descrição:**  
O sistema aceita valores negativos no campo “Número de vagas”.

**Passos para reprodução:**  
1. Acessar “Cadastrar Curso”.  
2. Inserir um número negativo no campo de vagas (ex: -10).  
3. Cadastrar o curso.

**Resultado esperado:**  
Deve ser exibida uma mensagem de erro informando que o número de vagas precisa ser positivo.

**Resultado obtido:**  
Curso é cadastrado normalmente com valor negativo.

**Causa possível:**  
Falta de validação numérica para valores menores que zero.

---

## BUG-003 – Cadastro de curso com data final anterior à data inicial

**Severidade:** Alta  
**Prioridade:** Alta  

**Descrição:**  
É possível cadastrar um curso com a data final menor que a data inicial.

**Passos para reprodução:**  
1. Acessar “Cadastrar Curso”.  
2. Inserir uma data inicial maior que a data final (ex: início 30/11/2025, fim 01/11/2025).  
3. Cadastrar o curso.

**Resultado esperado:**  
Deveria ser exibida uma mensagem de erro alertando que a data final deve ser posterior à data inicial.

**Resultado obtido:**  
Curso é cadastrado com sucesso, mesmo com as datas inválidas.

**Causa possível:**  
Ausência de validação lógica entre os campos de data.

---

## BUG-004 – Cadastro de curso sem imagem de capa

**Severidade:** Média  
**Prioridade:** Média  

**Descrição:**  
O sistema permite cadastrar cursos sem preencher o campo “URL da imagem de capa”.

**Passos para reprodução:**  
1. Acessar “Cadastrar Curso”.  
2. Deixar o campo de imagem em branco.  
3. Cadastrar o curso.

**Resultado esperado:**  
O campo deve ser obrigatório ou apresentar uma imagem padrão (placeholder).

**Resultado obtido:**  
Curso é cadastrado sem imagem, resultando em falha visual na listagem.

**Causa possível:**  
Campo não definido como obrigatório ou ausência de fallback padrão.

---

## BUG-005 – Lista de cursos sem mensagem quando vazia

**Severidade:** Baixa  
**Prioridade:** Média  

**Descrição:**  
Quando não há cursos cadastrados, a tela de listagem permanece vazia sem qualquer mensagem.

**Passos para reprodução:**  
1. Acessar a aplicação pela primeira vez (sem cursos cadastrados).  
2. Observar a tela “Lista de cursos”.

**Resultado esperado:**  
Deveria exibir mensagem informando: “Nenhum curso cadastrado no momento.”

**Resultado obtido:**  
A tela permanece vazia, sem indicar ausência de dados.

**Causa possível:**  
Falta de tratamento condicional para lista vazia.

---

## BUG-006 – Layout quebrado com descrições longas na lista de cursos

**Severidade:** Média  
**Prioridade:** Baixa  

**Descrição:**  
Quando a descrição do curso é muito extensa, o layout da listagem é quebrado, alongando o cartão do curso e distorcendo a grade.

**Passos para reprodução:**  
1. Acessar “Cadastrar Curso”.  
2. Inserir uma descrição longa (ex: 10 linhas de texto).  
3. Cadastrar o curso e voltar à “Lista de cursos”.

**Resultado esperado:**  
A descrição deve ser limitada visualmente (2–3 linhas) com truncamento (...).

**Resultado obtido:**  
O curso ocupa toda a tela, desorganizando o layout.

**Causa possível:**  
Ausência de restrição CSS ou de truncamento de texto.

---

## BUG-007 – Curso não é realmente excluído após mensagem de sucesso

**Severidade:** Alta  
**Prioridade:** Alta  

**Descrição:**  
Ao clicar em “Excluir Curso”, é exibida uma mensagem de sucesso, mas o curso continua listado e reaparece após atualizar a página.

**Passos para reprodução:**  
1. Acessar “Lista de cursos”.  
2. Clicar em “Excluir Curso”.  
3. Atualizar a página.

**Resultado esperado:**  
O curso deve ser removido definitivamente.

**Resultado obtido:**  
Mensagem “Curso excluído com sucesso” é exibida, mas o curso permanece na lista.

**Causa possível:**  
Falha no mecanismo de exclusão — ausência de persistência no localStorage ou estado não atualizado.

---

## BUG-008 – Campo “Endereço” permite valores inválidos em cursos presenciais

**Severidade:** Alta  
**Prioridade:** Alta  

**Descrição:**  
Ao selecionar o tipo de curso **Presencial**, o campo “Endereço” é exibido, porém não é obrigatório e aceita valores inválidos ou vazios.

**Passos para reprodução:**  
1. Acessar “Cadastrar Curso”.  
2. Selecionar tipo “Presencial”.  
3. Deixar o campo “Endereço” em branco ou preencher com caracteres inválidos.  
4. Cadastrar o curso.

**Resultado esperado:**  
Deveria exibir erro informando que o endereço é obrigatório e deve ser válido.

**Resultado obtido:**  
Curso é cadastrado normalmente, sem validação do campo.

**Causa possível:**  
Validação condicional não implementada para o tipo de curso “Presencial”.

---

## BUG-009 – Campo “Link de inscrição” permite valores inválidos em cursos online

**Severidade:** Alta  
**Prioridade:** Alta  

**Descrição:**  
Ao selecionar o tipo de curso **Online**, o campo “Link de inscrição” é exibido, porém o sistema permite deixá-lo em branco ou preencher com texto sem formato de URL.

**Passos para reprodução:**  
1. Acessar “Cadastrar Curso”.  
2. Selecionar tipo “Online”.  
3. Deixar o campo “Link de inscrição” vazio ou preencher com texto qualquer (ex: “teste”).  
4. Cadastrar o curso.

**Resultado esperado:**  
O sistema deve exigir um link válido (ex: https://example.com).

**Resultado obtido:**  
Curso é cadastrado com sucesso mesmo com campo inválido.

**Causa possível:**  
Ausência de validação de URL e obrigatoriedade condicional para cursos online.

---

## ✅ Conclusão Geral

Durante os testes exploratórios e funcionais do módulo de cursos, foram identificados **9 bugs** no total, distribuídos entre falhas:
- **Funcionais:** 6  
- **Validação de dados:** 2  
- **Visuais/Usabilidade:** 1  

Esses problemas indicam ausência de validações críticas e inconsistências na persistência e renderização dos dados.  
A priorização recomendada é corrigir primeiro as falhas funcionais de **validação e exclusão**, pois impactam diretamente a integridade do sistema.

