# ✅ CENÁRIO: Cliente adiciona produtos ao carrinho e finaliza pedido

## Contexto
Uma cliente chamada Maria acessa o sistema, visualiza produtos, adiciona-os ao carrinho e finaliza a compra.  
Ela seleciona dois produtos: **Cenoura** (em promoção) e **Tomate** (sem promoção).  
O sistema calcula o total e gera um pedido com os itens escolhidos.

---

## 🔸 Objetos envolvidos e seus atributos

### cliente1: `Cliente`
- **nome**: "Maria"  
- **email**: "maria@email.com"  
- **cpf**: 12345678900  
- **senha**: "maria123"  

### produto1: `Produto`
- **id**: 182  
- **nome**: "Cenoura"  
- **preco**: 4.00  
- **promocao**: true  
- **descricao**: "Cenoura fresca e orgânica, pacote com 1kg"  

### produto2: `Produto`
- **id**: 932  
- **nome**: "Tomate"  
- **preco**: 5.00  
- **promocao**: false  
- **descricao**: "Tomate italiano, pacote com 1kg"  

### carrinho1: `Carrinho`
- **id**: 001  
- **total**: 9.00  
- **itens**: [produto1, produto2]  

### pedido1: `Pedido`
- **id**: 002  
- **data**: "2025-05-14"  
- **total**: 9.00  
- **itens**: [produto1, produto2]  

### administrador: `Administrador`
- **nome**: "Ana Admin"  
- **email**: "ana@admin.com"  
- **cpf**: 1112233344  
- **senha**: "admin123"  

---

## 🔹 Relações entre objetos

- `cliente1` interage com `produto1` e `produto2` (visualiza e escolhe produtos)  
- `cliente1` adiciona produtos ao `carrinho1`  
- `carrinho1` contém os produtos: `produto1` e `produto2`  
- `cliente1` finaliza a compra, gerando o `pedido1` a partir do `carrinho1`  
- `pedido1` contém os mesmos itens do `carrinho1`  
- `administrador` é responsável por gerenciar `produto1` e `produto2`
