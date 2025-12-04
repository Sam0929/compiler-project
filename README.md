# 📦 Compilador de Linguagem Simplificada em Português

![C](https://img.shields.io/badge/language-C-blue)
![Status](https://img.shields.io/badge/status-Concluido-success)
![License](https://img.shields.io/badge/license-MIT-green)

Este repositório contém o código-fonte de um compilador de passo único desenvolvido em **C** para uma linguagem de programação simplificada com sintaxe em português. O projeto adota uma arquitetura modular, separando claramente as fases de análise léxica, sintática, semântica e geração de código.

## 📋 Sobre o Projeto

O objetivo deste projeto é processar código escrito em uma linguagem proprietária (em PT-BR) e convertê-lo para código de máquina ou código intermediário. O compilador implementa o pipeline clássico de compilação:

1.  **Análise Léxica:** Conversão do código fonte em tokens.
2.  **Análise Sintática (Parser):** Verificação da gramática e construção da árvore sintática.
3.  **Análise Semântica:** Verificação de tipos e escopo de variáveis.
4.  **Geração de Código:** Tradução para a linguagem alvo.
5.  **Interface de Erro:** Sistema robusto para reportar erros ao programador.

## 📂 Estrutura de Arquivos

A organização do projeto segue o padrão de separação entre interfaces (headers), implementações e testes:

```text
.
├── include/              # Arquivos de cabeçalho (.h)
│   ├── code_generator/   # Definições para o gerador de código
│   ├── error_UI/         # Definições para a interface de erros
│   ├── lexical/          # Definições do analisador léxico
│   ├── parser/           # Definições do analisador sintático
│   └── semantic/         # Definições do analisador semântico
│
├── src/                  # Código fonte da implementação (.c)
│   ├── code_generator/   # Lógica da geração de código
│   ├── error_UI/         # Implementação das mensagens de erro
│   ├── lexical/          # Implementação da máquina de estados/tokens
│   ├── semantic/         # Lógica de verificação de tipos
│   └── syntactic/        # Implementação do parser e regras gramaticais
│
└── tests/                # Casos de teste
    ├── lexical/          # Entradas para testar tokens
    └── syntactic/        # Entradas para testar a gramática

```
## 🛠️ Tecnologias utilizadas

* **C**
* **GCC**
* **MAKE**

## 🚀 Como Compilar e Executar

### Pré-requisitos
Certifique-se de ter o `gcc` instalado no seu ambiente.

### 1. Compilação

Você pode compilar o projeto utilizando o `make` ou rodando o comando manual do GCC.

**Opção A: Usando Make (Recomendado)**

```bash
make
```
**Opção B: Usando GCC**
```bash
gcc src/syntactic/parser.c src/lexical/lexer.c src/semantic/semantic.c src/code_generator/generator.c src/code_generator/instructions.c ./src/error_UI/error.c -o parser
```

## ▶️💻 Execução

Após a compilação, execute o binário gerado (parser). O programa aguardará que você informe o caminho do arquivo de teste.

Execute o parser
```bash
./parser
```
Quando solicitado, insira o caminho do seu programa, por exemplo:
```bash
tests/syntactic/sint1.txt
```

## 🧪 Testes

Os arquivos de teste estão localizados na pasta tests/.

* **Lexical**: Testes focados na identificação correta dos tokens.

* **Syntactic**: Testes focados na gramática da linguagem (ex: sint1.txt).

## 📝 Licença

Este projeto está sob a licença MIT. Consulte o arquivo [LICENSE](LICENSE) para mais informações.




