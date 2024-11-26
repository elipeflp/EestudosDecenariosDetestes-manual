## Execução de testes funcionais no sistema de e-commerce SauceDemo. 

###### Acesse o site clicando [aqui!](https://www.saucedemo.com/)
************************************************************

### Qual o objetivo dos testes ? 

 O objetivo dos testes é garantir que todos os recursos presentes no site estejam funcionando corretamente e proporcionando uma experiência consistente e intuitiva para os usuários. Isso inclui funcionalidades essenciais, como login, logout, adição de produtos ao carrinho, fluxo de compra completo e navegação entre páginas. <br><br>Além disso, os testes têm como meta identificar potenciais problemas ou falhas que possam impactar negativamente a experiência do usuário ou comprometer o desempenho do sistema no futuro, garantindo assim a confiabilidade e usabilidade da aplicação antes de seu lançamento em produção.
***

### Quais cenários de testes teremos?

1.Login<br>2. Ordenação e filtragem de produtos<br>3. Fluxo completo de compra<br>4. Remoção de itens do carrinho<br>5. Navegação entre páginas<br>6. Logout
*************************************************
### O que será abordado em cada teste:<br>
* Login com Diferentes Tipos de Usuários Disponíveis.<br><br>Objetivo: Verificar se diferentes tipos de usuários conseguem logar no sistema com suas respectivas credenciais e acessar as funcionalidades permitidas para cada perfil.
***********
* Ordenação e Filtragem de Produtos.<br><br>Objetivo: Verificar se os produtos podem ser ordenados e filtrados de acordo com os critérios disponíveis, e se os resultados da busca são relevantes.
***********
* Fluxo Completo de Compra.<br>
Objetivo: Verificar se todo o processo de compra, desde a adição de produtos ao carrinho até a finalização do pedido, funciona corretamente.
*************  
* Navegação entre Páginas.<br>
Objetivo: Verificar se a navegação entre as diferentes páginas do site é fluida e intuitiva.
************
* Logout
Objetivo: Verificar se a função de logout funciona corretamente e se a sessão do usuário é encerrada.
****************************
****************************

### Executando os testes de login:

Passos|Resultado esperado|Status|Resultado encontrados|Bug Report 
---|---|---|---|---
Login com usuário `Standard User`|Login realizado com sucesso.|Aprovado.|Login efetuado e redirecionando para a página de produtos.| N/D
Login com usuário `locked_out_user`| Login não realizado.| **Reprovado.**| *Epic sadface: Sorry, this user has been locked out.*| Quando clicamos em "Login" para carrgar a pagina, aparece a mensagem *Epic sadface: Sorry, this user has been locked out*, (usuário bloqueado).
Login com usuário `problem_user`.| Login realizado com sucesso.	| Aprovado.|Login efetuado e redirecionando para a página de produtos.| N/D
Login com usuário `performance_glitch_user`| Login realizado com sucesso.| Aprovado| Lentidão para redirecionar à pagina de produtos.| Quando clicamos em "Login" a pagina demora para entrar na pagina de produtos e não dá informações de que está carregando. 
Login com o usuário `error_user`| Login realizado com sucesso.| Aprovado |Login efetuado e redirecionando para a página de produtos.| N/D
Login com o usuário `secret_sauce`| Login realizado com sucesso| Aprovado| Login efetuado e redirecionando para a página de produtos.|N/D

### Executando os testes de ordenação e filtragem de produtos:

###### Login utilizado para realizar o teste: `Standard User`
Passos|Resultado esperado|Status|Resultado encontrados|Bug Report 
---|---|---|---|---
Clique no icone do filtro (*canto superior direito*) e filtre pelo preço `baixo para alto`. | Produtos exibidos em ordem crescente de preço.| Aprovado| Produtos aparecem de acordo com o que foi filtrado | No icone do filtro, a "seta preta" que indica onde é para clicar não está funcionando.
Clique no icone do filtro (*canto superior direito*) e filtre pelo preço `alto para baixo`.|Produtos exibidos em ordem decrescentete de preço.| Aprovado | Produtos aparecem de acordo com o que foi filtrado.| No icone do filtro, a "seta preta" que indica onde é para clicar não está funcionando.
Clique no icone do filtro (*canto superior direito*) e filtre pelo nome de `A-Z`.|Produtos exibidos na ordem solicidata.| Aprovado| Produtos aparecem em ordem alfabética.| N/D
Clique no icone do filtro (*canto superior direito*) e filtre pelo nome de `Z-A`.|Produtos não exibidos na ordem solicitada.| **Reprovado.**| Produtos aparecem sem ordem alfabética decrescente.| Começa com Test.allTheThings (letra T) e depois Sauce Labs Onesie (letra S).

*************************************

### Executando os testes de fluxo de compras:

###### Login utilizado para realizar o teste: `Standard User`

Passos|Resultado esperado|Status|Resultado encontrados|Bug Report 
---|---|---|---|---
Selecionar um produto e clicar no botão `Add to Cart`.| Produto adicionado ao carrinho.| Aprovado| Produto aparece no carrinho para efetuar a compra.| N/D.
Clicar no `ícone do carrinho` no canto superior direito.| A Página do carrinho é exibida, listando os produtos que foram adicionados.| Aprovado.| Produto aparece na pagina do carrinho.| N/D.
Na página do carrinho, clicar no botão `Checkout`.| A Página irá ser redirecionada para o preenchimento das informações do cliente.| Aprovado| Pagina redirecionada para inserir campos obrigatórios `nome`, `sobrenome` e `CEP`.| N/D
Clicar em "Continue".| Redirecionar para a página de resumo do pedido.|Aprovado| O cliente é redirecionado para o resumo da compra.| N/D.
Revisar os detalhes do pedido (produtos, preços, total). <br> 2º Clicar no botão `Finish`.| Exibir mensagem de confirmação: `Thank you for your order!`. |Aprovado|Mensagem exibida confirme o esperado.|N/D
Verificar se a página exibe a mensagem de sucesso e o botão `Back Home`.|Página final exibe a confirmação e permite retornar à home.|Aprovado.|A pagina retorna para a home.|N/D.


### Executando os testes de remoção de itens do carrinho :
###### Login utilizado para realizar o teste: `Standard User`

Passos|Resultado esperado|Status|Resultado encontrados|Bug Report 
---|---|---|---|---
Adicione um produto ao carrinho, vá para o carrinho e clique em Remove.|Produto é removido do carrinho, e o total é atualizado.|Aprovado| Carrinho fica vazio.|Não aparece nenuhma mensagem, como por exemplo: " Seu carrinho está vazio".
Adicione vários produtos ao carrinho, remova-os individualmente.| Produtos são removidos do carrinho.| Aprovado.| Carrinho fica vazio.| Sem mensagem informando que o carrinho está vazio.

### Executando os testes de navegação entre páginas:
###### Login utilizado para realizar o teste: `Standard User`

Passos|Resultado esperado|Status|Resultado encontrados|Bug Report 
---|---|---|---|---
Cliquei no ícone do carrinho na página de produtos.|Pagina redirecionada para o carrinho de compras.| Aprovado.| Pagina acessou o carrinho de compras.| N/D
Cliquei em Continue Shopping na página do carrinho.|Voltar para a pagina de produtos. | Aprovado| Página de produtos carregada corretamente.| N/D
Cliquei no botão Checkout na página do carrinho.|Exibir pagina de checkout | Aprovado.| Página de checkout exibida corretamente. |N/D

### Executando os testes de Logout:
###### Login utilizado para realizar o teste: `Standard User`

Passos|Resultado esperado|Status|Resultado encontrados|Bug Report 
---|---|---|---|---
 Clique no menu lateral na parte esquerda e em seguida, na opção **Logout**| Página será redirecionada para o login.|Aprovado| Página redirecionada para o login.| N/D



**************************************************************

**Impactos dos Problemas e Melhorias de UX/UI:**<br><br>

##### Login utilizado para realizar o teste: `Standard User`

* Ícone de Filtro (Canto Superior Direito)
**Impacto:** A falta do "ícone de mão" ao passar sobre a seta preta pode fazer com que o usuário pense que o botão não está funcional, gerando confusão e frustração.
**Consequência:** Abandono da interação com o filtro, dificultando a busca por produtos.<br><br>
* Desalinhamento do Preço na Camiseta Test.allTheThings() (Vermelha)
**Impacto:** O desalinhamento causa uma aparência amadora ao site, afetando a percepção de qualidade da plataforma.
**Consequência:** Reduz a confiança do cliente no e-commerce.<br><br>

* Botões na Página de Checkout
**Impacto:** A posição distante dos botões dificulta o fluxo natural do checkout.
**Consequência:** Pode levar a desistências por dificuldade de localização ou falta de acessibilidade.<br><br>

* Permitir Checkout Sem Produtos no Carrinho
**Impacto:** Permitir finalizar uma compra sem itens no carrinho resulta em um comportamento inesperado e confuso.
**Consequência:** Frustração para o cliente, aumento de suporte ao consumidor e possíveis reclamações.<br><br>
* Botões de Terms of Service e Privacy Policy Não Funcionais
**Impacto:** Botões não clicáveis comprometem a transparência e a conformidade legal.
**Consequência:** Reduz a confiança no site e pode causar problemas jurídicos.<br><br>
* Parênteses Vazios no Nome do Produto
**Impacto:** Nome inconsistente causa desconfiança sobre a atenção aos detalhes no site.
**Consequência:** Reduz a credibilidade e confunde o cliente.<br><br>
***********
* **Login com Usuário** `Locked_out_user`
**Impacto:** A falta de instruções claras para desbloqueio da conta impede o usuário de prosseguir com suas compras.
**Consequência:** Perda de clientes devido à falta de suporte.<br><br>
***************
* **Login com Usuário** `Problem_user`
**Impactos:** Imagens de cachorro dificultam a identificação de produtos.
* Impossibilidade de remover itens ou usar filtros torna o site pouco funcional.
* Erros no checkout impedem a finalização da compra.
**Consequências:** Abandono do site, perda de vendas e impacto negativo na reputação do e-commerce.<br><br>
*********************
* **Login com Usuário** `Performance_glitch_user`
**Impactos:** Navegação lenta prejudica a experiência do cliente.
* Permitir compras sem produtos no carrinho gera confusão e frustração.
**Consequências:** Clientes podem abandonar o site e migrar para concorrentes.<br><br>
********************************
* **Login com Usuário** `Error_user`
**Impactos:** Produtos não podem ser adicionados ao carrinho, impedindo a compra.
* Delay no menu reduz a agilidade de navegação.
* Ícone do Twitter inativo prejudica a confiança na integração social.
**Consequências:** Perda de usuários e redução no engajamento do site.
* **Login com Usuário** `Secret_sauce`
* Imagens inconsistentes geram confusão sobre os produtos.
* Filtragem incorreta prejudica a busca eficiente.
* Problemas de alinhamento reduzem a percepção de qualidade da interface.
**Consequências:** Experiência do usuário prejudicada, levando a desistências ou falta de confiança no site.<br><br>
**************************************
**Resumo dos Impactos**
Os problemas relatados no SauceDemo afetam diretamente a experiência do usuário (UX), confiança no e-commerce, eficiência do site e retenção de clientes. Falhas no checkout, problemas de navegação e performance, entre outros, resultam em perda de receita, diminuição da taxa de conversão, aumento de custos com suporte e risco de penalidades. 
Ajustá-los melhorará a navegação, aumentará a taxa de conversão, fortalecerá a imagem da marca e contribuirá para a fidelização dos clientes. 
Isso, por sua vez, aumentará a competitividade da empresa no mercado de e-commerce, garantindo uma experiência de compra mais eficiente e agradável, o que é essencial para o crescimento e a sustentabilidade do negócio.

