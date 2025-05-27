# 🧱 Diagrama de Pacotes — Detalhado

🎯 **Objetivo**: Organizar as classes em pacotes modulares e mostrar dependências lógicas.

---

## 📦 Pacote: `usuario`

### Classes:
- `Cliente`
- `Administrador`

### Interfaces:
- `Autenticavel`  
  Métodos: `login()`, `cadastro()`

---

## 📦 Pacote: `produto`

### Classes:
- `Produto`
- `Promocao`

### Interfaces:
- `Visualizavel`  
  Métodos: `visualizarProdutos()`, `visualizarDetalhes()`

---

## 📦 Pacote: `carrinho`

### Classes:
- `Carrinho`
- `ItemCarrinho` *(opcional, para controle de quantidade)*

### Métodos:
- `adicionarProduto()`
- `removerProduto()`
- `calcularTotal()`

---

## 📦 Pacote: `pedido`

### Classe:
- `Pedido`

### Atributos:
- `id`, `data`, `itens`, `total`

### Métodos:
- `criarPedido()`
- `confirmarPedido()`
- `cancelarPedido()`

---

## 📦 Pacote: `sistema`

### Componentes:
- `InterfaceSupermercado`
- `BancoDeDados` *(simulado)*
- Classes de controle, sessões e validações

---

## 🔁 Dependências Lógicas

```text
carrinho --<<import>>--> produto  
carrinho --<<access>>--> usuario  
pedido   --<<import>>--> carrinho  
pedido   --<<import>>--> produto  
sistema  --<<import>>--> todos os pacotes
