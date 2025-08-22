# 🗂️ Projeto de Banco de Dados – Views e Triggers  

Este repositório organiza um projeto dividido em **duas partes principais**:  

1. **Personalizando acessos com Views**  
2. **Criando gatilhos (Triggers) para cenário de e-commerce**  

O objetivo é **aprimorar conhecimentos em SQL**, aplicando views para controle de acesso e triggers para manipulação automática de dados.  

---

## 📌 Parte 1 – Personalizando acessos com Views  

Neste desafio, você criará **visões (views)** para os seguintes cenários:  

- Número de empregados por **departamento e localidade**  
- Lista de **departamentos e seus gerentes**  
- **Projetos** com maior número de empregados (ordenados em ordem decrescente)  
- Lista de **projetos, departamentos e gerentes**  
- Quais empregados possuem **dependentes** e se são **gerentes**  

### 🔐 Permissões de acesso  

As views podem ser usadas para **controlar permissões de acesso**. Lembre-se:  
- Uma view é armazenada no banco como uma tabela virtual  
- Podemos definir **quem pode visualizar cada view**  

Exemplo de controle de acesso:  
- Criar um usuário **gerente** que terá acesso às informações de `employee` e `department`  
- Criar um usuário **employee** que **não terá acesso** às informações relacionadas a departamentos ou gerentes  

**Exemplo de criação de usuário e permissão (MySQL):**
```sql
-- Criando usuário gerente
CREATE USER 'gerente'@'localhost' IDENTIFIED BY 'senha123';
GRANT SELECT ON company.employee TO 'gerente'@'localhost';
GRANT SELECT ON company.department TO 'gerente'@'localhost';

-- Criando usuário employee sem acesso a informações de gerentes
CREATE USER 'employee'@'localhost' IDENTIFIED BY 'senha123';
GRANT SELECT ON company.employee TO 'employee'@'localhost';
