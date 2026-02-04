# Projeto de Testes Manuais - Swag Labs

## 📌 Objetivo

Validar as funcionalidades críticas de login, inventário e filtros da plataforma [Swag Labs](https://www.saucedemo.com/), garantindo a integridade dos dados e a experiência do usuário.

| ID  | Funcionalidade | Caso de Teste                              | Cenário (BDD)                                                                                                                                                                           | Status |
| :-- | :------------- | :----------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----: |
| 1   | Login          | Login com usuário padrão (Caminho feliz)   | **Dado** que o usuário está na tela de login **Quando** informar "standard_user" e a senha válida **Então** o sistema deve redirecionar para a página /inventory.html.                  | ✅ OK  |
| 2   | Login          | Login com usuário bloqueado                | **Dado** que o usuário está na tela de login **Quando** informar "locked_out_user" **Então** o sistema deve exibir a mensagem de bloqueio.                                              | ✅ OK  |
| 3   | Login          | Validação de senha incorreta               | **Dado** que o usuário está na tela de login **Quando** informar uma senha inválida **Então** o sistema deve exibir uma mensagem de erro amigável.                                      | ❌ NOK |
| 4   | Inventário     | Validação de carregamento de imagens       | **Dado** que o usuário está logado e visualiza a lista de produtos **Então** as imagens de cada produto devem ser correspondentes.                                                      | ❌ NOK |
| 5   | Inventário     | Alteração de estado do botão "Add to cart" | **Dado** que o usuário está na lista de produtos **Quando** clicar em "Add to cart" **Então** o botão deve mudar para "Remove".                                                         | ❌ NOK |
| 6   | Filtros        | Ordenação por Preço (Low to High)          | **Dado** que o usuário está na lista de produtos **Quando** selecionar o filtro "Price (low to high)" **Então** os produtos devem ser listados do menor para o maior valor.             | ✅ OK  |
| 7   | Checkout       | Compra com sucesso (Caminho Feliz)         | **Dado** que o usuário está no carrinho com itens **Quando** preencher dados válidos e finalizar **Então** o sistema deve exibir "Thank you for your order!".                           | ✅ OK  |
| 8   | Checkout       | Validar campos obrigatórios (First Name)   | **Dado** que o usuário está no checkout **Quando** deixar o campo "First Name" vazio **Então** o sistema deve retornar "Error: First Name is required".                                 | ✅ OK  |
| 9   | Checkout       | Validar campos obrigatórios (Last Name)    | **Dado** que o usuário está no checkout **Quando** deixar o campo "Last Name" vazio **Então** o sistema deve retornar "Error: Last Name is required".                                   | ✅ OK  |
| 10  | Checkout       | Validação do campo Postal Code (CEP)       | **Dado** que o usuário está preenchendo o endereço **Quando** inserir letras ou formatos inválidos no CEP **Então** o sistema deve barrar o avanço.                                     | ❌ NOK |
| 11  | Cart (UI)      | Integridade visual da tabela de produtos   | **Dado** que o usuário acessa o carrinho /cart.html **Então** o cabeçalho deve estar alinhado e as imagens dos produtos visíveis.                                                       | ❌ NOK |
| 12  | Interface (UX) | Feedback visual no ícone do carrinho       | **Dado** que o usuário passa o mouse sobre o ícone do carrinho **Então** o sistema deve apresentar um efeito de hover.                                                                  | ❌ NOK |
| 13  | Sessão         | Persistência e Expiração de Sessão         | **Dado** que o usuário está logado **Quando** atualizar a página (F5) ou sofrer timeout por inatividade **Então** o sistema deve manter os itens ou redirecionar para o login com erro. | ✅ OK  |

## 🔍 Principais Descobertas

- Integridade Visual: Falhas de carregamento de imagens e desalinhamento de componentes na página de carrinho (/cart.html).
- Validação de Dados: O campo de código postal (CEP) não possui máscara ou validação, permitindo a inserção de caracteres alfabéticos.
- UX/Interatividade: Ausência de feedback visual (efeito de hover) em elementos clicáveis críticos, como o ícone do carrinho.
- Segurança de Sessão: O sistema gerencia corretamente a expiração de sessão por inatividade, protegendo URLs restritas.

> **Nota:** Para detalhes técnicos sobre os erros encontrados (NOK), consulte o [Relatório de Bugs](./BUG_REPORTS.md).
