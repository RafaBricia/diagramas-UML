# 🔹 Modelo de Classes – Sistema CasaHorti

## 🔹 Cliente
### Atributos:
- nome: String  
- email: String  
- cpf: Int  
- senha: String  

### Métodos:
- getNome(): String  
- getEmail(): String  
- getCPF(): Int  
- getSenha(): String  
- setNome(nome: String): void  
- setEmail(email: String): void  
- setCPF(cpf: Int): void  
- setSenha(senha: String): void  
- cadastrar(): void  
- fazerLogin(): void  

---

## 🔹 Administrador
### Atributos:
- nome: String  
- email: String  
- cpf: Int  
- senha: String  

### Métodos:
- getNome(): String  
- getEmail(): String  
- getCPF(): Int  
- getSenha(): String  
- setNome(nome: String): void  
- setEmail(email: String): void  
- setCPF(cpf: Int): void  
- setSenha(senha: String): void  
- gerenciarProduto(): void  
- gerenciarUsuarios(): void  
- aplicarDesconto(): void  
- cadastrar(): void  
- fazerLogin(): void  

---

## 🔹 Produto
### Atributos:
- id: Int  
- nome: String  
- preco: Float  
- promocao: Boolean  
- descricao: String  

### Métodos:
- getId(): Int  
- getNome(): String  
- getPreco(): Float  
- getPromocao(): Boolean  
- getDescricao(): String  
- setId(id: Int): void  
- setNome(nome: String): void  
- setPreco(preco: Float): void  
- setPromocao(promocao: Boolean): void  
- setDescricao(descricao: String): void  
- visualizarProdutos(): void  
- visualizarDetalhes(): void  

---

## 🔹 Carrinho
### Atributos:
- id: Int  
- itens: List<Produto>  
- total: Float  

### Métodos:
- getId(): Int  
- getTotal(): Float  
- getItens(): List<Produto>  
- setId(id: Int): void  
- setTotal(total: Float): void  
- setItens(itens: List<Produto>): void  
- adicionarProduto(p: Produto): void  
- removerProduto(p: Produto): void  
- calcularTotal(): Float  
- finalizarCompra(): void  

---

## 🔹 Pedido
### Atributos:
- id: Int  
- data: Date  
- itens: List<Produto>  
- total: Float  

### Métodos:
- getId(): Int  
- getData(): Date  
- getTotal(): Float  
- getItens(): List<Produto>  
- setId(id: Int): void  
- setData(data: Date): void  
- setTotal(total: Float): void  
- setItens(itens: List<Produto>): void  
- criarPedido(): void  
- confirmarPedido(): void  

---

## 🔹 Relacionamentos

- **Cliente** possui um **Carrinho** (1:1)  
- **Cliente** visualiza **Produto** (*:*)  
- **Carrinho** contém vários **Produtos** (*:*)  
- **Carrinho** gera um **Pedido** (1:1)  
- **Pedido** contém vários **Produtos** (*:*)  
- **Administrador** gerencia **Produto** (*:*)  

---