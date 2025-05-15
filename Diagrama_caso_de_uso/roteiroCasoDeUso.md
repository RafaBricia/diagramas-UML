# 🔹 1. Diagrama de Casos de Uso – com Cliente

## 🎭 Atores

- **Administrador** – controla o sistema (gerencia usuários e produtos)
- **Cliente** – visualiza os produtos, seus detalhes e descontos

---

## 📌 Casos de Uso Atualizados

### Cliente

- Visualizar Produtos  
- Visualizar Detalhes do Produto  
- Ver Produtos em Promoção  
- Realizar Cadastro *(opcional, se houver login de cliente)*  
- Fazer Login *(se aplicável)*  
- Recuperar Senha *(se aplicável)*  

### Administrador

- Fazer Login  
- Recuperar Senha  
- Acessar Home  

#### Produtos

- Cadastrar Produto  
- Editar Produto  
- Remover Produto  
- Aplicar Desconto  
- Listar Produtos  

#### Usuários

- Cadastrar Usuário  
- Editar Usuário  
- Remover Usuário  
- Listar Usuários  

#### Perfil

- Editar Perfil  
- Alterar Senha  

---

## 🔁 Relacionamentos

- `Cliente` se associa aos casos de **visualização**
- `Administrador` se associa aos casos de **gestão**
- Ambos podem herdar de um caso genérico **"Acessar Sistema"** (usando generalização, se desejado)
