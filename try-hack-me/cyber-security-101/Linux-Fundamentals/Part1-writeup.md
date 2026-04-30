# 🐧 Linux Fundamentals — Part 1

**Plataforma:** TryHackMe  
**Trilha:** Cyber Security 101  
**Módulo:** 2 — Linux Fundamentals  
**Parte:** 1 de 3  
**Dificuldade:** 🟢 Fácil  
**Status:** ✅ Concluído  
**Badge:** [Terminaled 🏅](https://tryhackme.com/nicolasreitz46/badges/terminaled)

---

## 🎯 Objetivo

Aprender a interagir com sistemas Linux via terminal, dominando os comandos fundamentais de navegação, busca e manipulação de arquivos — sem depender de interface gráfica.

---

## 🧰 Ferramentas / Comandos Utilizados

| Comando | Descrição |
|---------|-----------|
| `echo` | Exibe texto no terminal |
| `whoami` | Mostra o usuário logado atualmente |
| `ls` | Lista arquivos e diretórios |
| `cd` | Navega entre diretórios |
| `cat` | Exibe o conteúdo de um arquivo |
| `pwd` | Mostra o diretório atual |
| `find` | Localiza arquivos e diretórios |
| `grep` | Busca por conteúdo dentro de arquivos |
| `wc -l` | Conta o número de linhas de um arquivo |

---

## 📚 Conteúdo

### 1. Por que o Terminal?

Sistemas Linux como o Ubuntu são conhecidos por serem leves e eficientes. Em muitos ambientes (servidores, máquinas virtuais, CTFs), não há interface gráfica disponível — toda interação acontece pelo **Terminal**, uma interface puramente textual.

```bash
tryhackme@linux1:~$ 
```

Apesar de intimidador no início, o terminal se torna natural com a prática.

---

### 2. Primeiros Comandos

#### `echo` — Exibir texto
```bash
tryhackme@linux1:~$ echo Hello
Hello

tryhackme@linux1:~$ echo "Hello Friend!"
Hello Friend!
```
> 💡 Palavras simples não precisam de aspas. Frases com espaços devem ser envolvidas em `" "`.

#### `whoami` — Identificar o usuário atual
```bash
tryhackme@linux1:~$ whoami
tryhackme
```

---

### 3. Navegando pelo Sistema de Arquivos

| Comando | Nome completo | Função |
|---------|--------------|--------|
| `ls` | listing | Lista arquivos e pastas do diretório atual |
| `cd` | change directory | Navega para outro diretório |
| `cat` | concatenate | Exibe o conteúdo de um arquivo |
| `pwd` | print working directory | Mostra o caminho do diretório atual |

```bash
tryhackme@linux1:~$ pwd
/home/tryhackme

tryhackme@linux1:~$ ls
folder1  access.log  passwords.txt

tryhackme@linux1:~$ cd folder1
tryhackme@linux1:~/folder1$

tryhackme@linux1:~/folder1$ cat passwords.txt
admin:password123
```

---

### 4. Encontrando Arquivos com `find`

O `find` localiza arquivos pelo nome, extensão ou outros critérios.

**Buscar por nome exato:**
```bash
tryhackme@linux1:~$ find -name passwords.txt
./folder1/passwords.txt
```

**Buscar por extensão com wildcard (`*`):**
```bash
tryhackme@linux1:~$ find -name *.txt
./folder1/passwords.txt
./notes.txt
```

> 💡 O `*` funciona como coringa — substitui qualquer sequência de caracteres.

---

### 5. Buscando Conteúdo com `grep`

O `grep` pesquisa o **conteúdo** de arquivos por um valor específico. Muito útil para analisar logs.

**Contar linhas de um arquivo com `wc -l`:**
```bash
tryhackme@linux1:~$ wc -l access.log
244 access.log
```

**Filtrar entradas por IP no log:**
```bash
tryhackme@linux1:~$ grep "81.143.211.90" access.log
81.143.211.90 - - [25/Mar/2021:11:17+0000] "GET / HTTP/1.1" 200 417 "-" "Mozilla/5.0 (Linux; Android 7.0; Moto G(4))"
```

**Busca recursiva em múltiplos arquivos com `-R`:**
```bash
grep -R "PRETTY_NAME" /etc/
grep: /etc/sudoers: Permission denied
/etc/os-release:PRETTY_NAME="Ubuntu"
```

> 💡 O `-R` faz o grep percorrer todos os arquivos e subdiretórios automaticamente — ideal quando não sabemos em qual arquivo está a informação.

---

### 6. Operadores do Shell

Operadores permitem combinar e redirecionar comandos de forma poderosa.

| Operador | Descrição |
|----------|-----------|
| `&` | Executa um comando em segundo plano |
| `&&` | Executa o segundo comando **somente se** o primeiro tiver sucesso |
| `>` | Redireciona a saída para um arquivo **(sobrescreve)** |
| `>>` | Redireciona a saída para um arquivo **(acrescenta ao final)** |

**Exemplos:**
```bash
# Redirecionar saída para um arquivo
echo "Hello" > arquivo.txt

# Acrescentar ao arquivo existente
echo "World" >> arquivo.txt

# Executar dois comandos em sequência
mkdir pasta && cd pasta

# Rodar processo em segundo plano
ping google.com &
```

---

## 📚 O que aprendi

- Por que o terminal é essencial em ambientes Linux sem interface gráfica
- Usar `echo` e `whoami` para primeiras interações com o sistema
- Navegar pelo sistema de arquivos com `ls`, `cd`, `pwd` e `cat`
- Localizar arquivos por nome e extensão com `find` e wildcards
- Filtrar conteúdo de arquivos e logs com `grep`, incluindo busca recursiva com `-R`
- Usar operadores do shell (`&`, `&&`, `>`, `>>`) para combinar e redirecionar comandos

---

*TryHackMe — Cyber Security 101 | Módulo 2 — Linux Fundamentals Part 1 concluído* 🐧
