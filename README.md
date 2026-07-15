# 📋 Sistema de Gestão de Cadastros

Sistema console em Java com CRUD completo, aplicando **Programação Orientada a Objetos**, validação rigorosa de entradas e tratamento de exceções.

![Java](https://img.shields.io/badge/Java-17%2B-orange)
![POO](https://img.shields.io/badge/POO-Completo-blue)
![License](https://img.shields.io/badge/license-MIT-green)

---

## ✨ Funcionalidades

- ✅ **Cadastrar** pessoa com validação completa de campos
- 🔍 **Buscar** por ID, nome ou e-mail
- 📋 **Listar** todos os cadastros com paginação
- ✏️ **Atualizar** dados de um cadastro existente
- 🗑️ **Excluir** cadastro com confirmação
- 🛡️ **Validação rigorosa** de CPF, e-mail, telefone e data de nascimento
- ⚠️ **Zero crash**: todos os inputs são tratados com try-catch e verificações
- 💾 **Persistência simples** em arquivo `.dat` (serialização Java)

---

## 🏗️ Arquitetura (POO)

```
src/main/java/com/cadastro/
│
├── model/
│   └── Pessoa.java              # Entidade principal (Serializable)
│
├── repository/
│   └── PessoaRepository.java    # Camada de acesso a dados (in-memory + arquivo)
│
├── service/
│   └── PessoaService.java       # Regras de negócio
│
├── validator/
│   └── InputValidator.java      # Validações de CPF, e-mail, telefone, data
│
├── exception/
│   ├── CadastroException.java   # Exceção de negócio customizada
│   └── ValidacaoException.java  # Exceção de validação customizada
│
├── util/
│   └── ConsoleUtil.java         # Formatação e helpers de console
│
├── ui/
│   └── Menu.java                # Interface do usuário (loop principal)
│
└── Main.java                    # Entry point
```

---

## 🚀 Como Executar

### Pré-requisito
- Java 17+

### Compilar e rodar

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/cadastro-system.git
cd cadastro-system

# Compilar tudo de uma vez
javac -d out $(find src -name "*.java")

# Executar
java -cp out com.cadastro.Main
```

### Ou com Maven (opcional)
```bash
mvn compile exec:java
```

---

## 🛡️ Estabilidade e Validações

| Campo       | Regras aplicadas                                      |
|-------------|-------------------------------------------------------|
| Nome        | 2–100 chars, apenas letras e espaços                 |
| CPF         | 11 dígitos, algoritmo oficial de validação           |
| E-mail      | Regex RFC-5322 simplificado                          |
| Telefone    | Formato (XX) XXXXX-XXXX ou (XX) XXXX-XXXX           |
| Nascimento  | Data válida, não futura, idade entre 0–150 anos      |
| Menus       | Qualquer entrada inválida é capturada, nunca crasha  |

---

## 📄 Licença

MIT License — veja [LICENSE](LICENSE)
