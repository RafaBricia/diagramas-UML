# ✅ Diagrama de Sequência: Cliente Visualizando Produtos e Finalizando Compra

Link:<a href='https://lucid.app/lucidchart/454099f8-59b2-4c49-8a30-3b60802a3641/edit?invitationId=inv_e1c06659-949f-42df-b385-a397de3e8603&page=0_0#'>Lucidchart Sequência - UML</a>
<BR>

## 🎭 Atores

- **Cliente**: Usuário final que interage com a interface.
- **Sistema**: Backend que integra funcionalidades, banco de dados e validações.
- **Produto**: Serviço responsável pela listagem e detalhes.
- **Carrinho**: Gestor dos itens adicionados pelo cliente.
- **Pedido**: Responsável pela geração e conclusão do pedido.

---

## 🎯 Sequência de Interações

### Cliente solicita a visualização de produtos

```plaintext
Cliente → Interface Supermercado: solicitarListaDeProdutos()
Interface → Produto: listarProdutos()
Produto → Sistema: consultarListaProdutos()
Sistema → BancoDeDados: verificarExistenciaProdutos()
BancoDeDados → Sistema: retorna lista
Sistema → Produto: retorna produtos
Produto → Interface: retorna produtos
Interface → Cliente: exibirProdutos(produtos)
```

### Cliente seleciona um produto para ver os detalhes

```plaintext
Cliente → Interface: visualizarDetalhes(produto)
Interface → Produto: consultarDetalhesProduto(idProduto)
Produto → Sistema: consultarProduto(idProduto)
Sistema → BancoDeDados: verificarProduto(idProduto)
BancoDeDados → Sistema: retorna dados
Sistema → Produto: retorna dados
Produto → Interface: retorna detalhes
Interface → Cliente: exibirDetalhesProduto()
```

### Cliente adiciona o produto ao carrinho

```plaintext
Cliente → Interface: adicionarProduto(produto)
Interface → Carrinho: informarProduto(produto)
Carrinho → Sistema: consultarProduto(produto.id)
Sistema → BancoDeDados: verificarProduto(produto.id)
Sistema → Carrinho: retorna dados
Carrinho → Carrinho: atualizarQuantidade()
Carrinho → Interface: retorna confirmação
```

### Cliente visualiza o conteúdo do carrinho

```plaintext
Cliente → Interface: visualizarCarrinho()
Interface → Carrinho: consultarCarrinho()
Carrinho → Sistema: consultarItens(idCarrinho)
Sistema → BancoDeDados: verificarCarrinho(idCarrinho)
Sistema → Carrinho: retorna itens
Carrinho → Interface: retorna lista
Interface → Cliente: exibirCarrinho(itens)
```

### Cliente finaliza a compra

```plaintext
Cliente → Interface: finalizarCompra()
Interface → Pedido: criarPedido(itensCarrinho, total)
Pedido → Sistema: registrarPedido()
Sistema → BancoDeDados: atualizarPedido()
Sistema → Pedido: confirmação
Pedido → Interface: confirmação
Interface → Cliente: exibirConfirmacaoPedido()
```

---

## 🔄 Fluxo Narrativo Resumido

1. O cliente solicita visualizar produtos e recebe uma lista.
2. Seleciona um item e visualiza seus detalhes.
3. Adiciona o produto ao carrinho, que atualiza a quantidade.
4. Visualiza os itens adicionados ao carrinho.
5. Finaliza a compra, e o sistema gera o pedido.
6. O sistema confirma o pedido ao cliente.

---

## 🔎 Notas Técnicas

- Todas as comunicações envolvem chamadas entre camadas (Interface ↔ Produto/Carrinho ↔ Sistema ↔ BancoDeDados).
- A verificação de disponibilidade e consulta de dados ocorrem no **Sistema**, que acessa o **banco de dados**.
- O objeto `Pedido` é criado a partir dos dados do carrinho e enviado ao banco.
- O retorno ao cliente é sempre tratado pela **Interface**.
