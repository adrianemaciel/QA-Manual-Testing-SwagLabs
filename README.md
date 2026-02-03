# Projeto de Testes Manuais - Swag Labs

## 📌 Objetivo
Validar as funcionalidades críticas de login, inventário e filtros da plataforma [Swag Labs](https://www.saucedemo.com/), garantindo a integridade dos dados e a experiência do usuário.

| ID | Funcionalidade | Caso de Teste | Cenário (BDD) | Status |
| :-- | :--- | :--- | :--- | :---: |
| 1 | Login | Login com usuário padrão (Caminho feliz) | **Dado** que o usuário está na tela de login **Quando** informar "standard_user" e a senha válida **Então** o sistema deve redirecionar para a página /inventory.html. | ✅ OK |
| 2 | Login | Login com usuário bloqueado | **Dado** que o usuário está na tela de login **Quando** informar "locked_out_user" **Então** o sistema deve exibir a mensagem de bloqueio. | ✅ OK |
| 3 | Login | Validação de senha incorreta | **Dado** que o usuário está na tela de login **Quando** informar uma senha inválida **Então** o sistema deve exibir uma mensagem de erro amigável. | ❌ NOK |
| 4 | Inventário | Validação de carregamento de imagens | **Dado** que o usuário está logado e visualiza a lista de produtos **Então** as imagens de cada produto devem ser correspondentes. | ❌ NOK |
| 5 | Inventário | Alteração de estado do botão "Add to cart" | **Dado** que o usuário está na lista de produtos **Quando** clicar em "Add to cart" **Então** o botão deve mudar para "Remove". | ❌ NOK |
| 6 | Filtros | Ordenação por Preço (Low to High) | **Dado** que o usuário está na lista de produtos **Quando** selecionar o filtro "Price (low to high)" **Então** os produtos devem ser listados do menor para o maior valor. | ✅ OK |

## 🔍 Principais Descobertas
* Falhas de integridade visual com o 'problem_user'.
* Inconsistência funcional nos botões de adicionar ao carrinho.

> **Nota:** Para detalhes técnicos sobre os erros encontrados (NOK), consulte o [Relatório de Bugs](./BUG_REPORTS.md).
