# 🔐 Cyber Security 101 — Módulo 1: Start Your Cyber Security Journey

**Plataforma:** TryHackMe  
**Trilha:** Cyber Security 101  
**Módulo:** 1 — Start Your Cyber Security Journey  
**Dificuldade:** 🟢 Fácil  
**Status:** ✅ Concluído

---

## 🎯 Objetivo

Introduzir os fundamentos de cibersegurança, abordando os dois lados da área: segurança ofensiva (encontrar e explorar vulnerabilidades) e segurança defensiva (detectar e bloquear ataques), além de ensinar técnicas e ferramentas essenciais de pesquisa.

---

## 🧰 Ferramentas Utilizadas

| Ferramenta | Uso |
|-----------|-----|
| `dirb` | Enumeração de URLs/diretórios ocultos em aplicações web |
| Shodan | Busca de dispositivos e serviços expostos na internet pública |
| VirusTotal | Análise de arquivos com 72+ antivírus |
| CVE / NVD | Base de dados de vulnerabilidades conhecidas |
| `man` | Documentação oficial de ferramentas no Linux |
| GitHub | Pesquisa de PoCs e análises de vulnerabilidades |

---

## 📚 Conteúdo do Módulo

### 1. Introdução à Segurança Ofensiva

O foco da segurança ofensiva é pensar como um atacante: encontrar falhas antes que alguém mal-intencionado o faça.

**Ferramenta: `dirb`**  
Usado para descobrir URLs e diretórios ocultos em uma aplicação web por força bruta, testando palavras de uma wordlist contra o servidor.

```bash
dirb http://target.com
```

No lab, utilizamos o `dirb` para encontrar uma página escondida no site-alvo e, em seguida, acessamos essa URL manualmente para explorar o conteúdo exposto.

---

### 2. Introdução à Segurança Defensiva

A segurança defensiva foca em **detectar, analisar e responder** a ataques em andamento ou já ocorridos.

No lab, praticamos:
- Identificar o **IP do atacante** a partir dos logs
- Reconhecer o **tipo de ataque** realizado
- **Bloquear o IP** do atacante no firewall para interromper a ameaça

> 💡 Enquanto o time ofensivo tenta entrar, o time defensivo monitora, detecta e reage.

---

### 3. Search Skills — Habilidades de Pesquisa

Uma das competências mais importantes em cibersegurança é saber **onde e como buscar informações**.

#### 🔍 Shodan
Mecanismo de busca para dispositivos conectados à internet. Diferente do Google (que indexa páginas), o Shodan indexa **servidores, câmeras, roteadores, sistemas industriais** e qualquer dispositivo com IP público.

Útil para:
- Encontrar serviços expostos (FTP, SSH, RDP abertos)
- Mapear a superfície de ataque de um alvo
- Pesquisar dispositivos vulneráveis por versão de software

#### 🦠 VirusTotal
Plataforma que analisa arquivos e URLs utilizando **mais de 72 antivírus** simultaneamente. Essencial para verificar se um arquivo é malicioso antes de executá-lo ou para analisar amostras de malware.

#### 📋 CVE e Bases de Dados de Vulnerabilidades
- **CVE (Common Vulnerabilities and Exposures):** sistema padronizado de identificação de vulnerabilidades. Cada falha recebe um ID único no formato `CVE-ANO-NÚMERO` (ex: `CVE-2026-13337`).
- **NVD (National Vulnerability Database):** base oficial com detalhes técnicos, severidade (CVSS) e referências de cada CVE.

Útil para pesquisar se uma versão de software que você está analisando possui vulnerabilidades conhecidas.

#### 📖 MAN Pages — Documentação do Linux
O comando `man` exibe a documentação oficial de qualquer ferramenta instalada no Linux.

```bash
man <comando>
```

**Exemplo — `man nc` (netcat):**

```
NAME
    nc - arbitrary TCP and UDP connections and listens

DESCRIPTION
    The nc (or netcat) utility is used for just about anything under
    the sun involving TCP or UDP. It can open TCP connections, send
    UDP packets, listen on arbitrary TCP and UDP ports, do port
    scanning, and deal with both IPv4 and IPv6.

Common uses include:
    · simple TCP proxies
    · shell-script based HTTP clients and servers
    · network daemon testing
    · a SOCKS or HTTP ProxyCommand for ssh(1)
```

Principais flags do `nc`:

| Flag | Função |
|------|--------|
| `-l` | Modo escuta (listen) — aguarda conexão entrante |
| `-p` | Define a porta de origem |
| `-v` | Modo verbose — exibe mais detalhes |
| `-u` | Usa UDP ao invés de TCP |
| `-z` | Scan de portas sem enviar dados |
| `-w` | Define timeout de conexão |
| `-n` | Não realiza lookup de DNS |

#### 🐙 GitHub como fonte de inteligência
O GitHub é uma fonte valiosa para se manter atualizado sobre ameaças e vulnerabilidades. Pesquisadores publicam **Provas de Conceito (PoC)** frequentemente antes dos canais oficiais.

Pesquisar um CVE diretamente no GitHub (`CVE-2026-13337`) geralmente revela:
- Repositórios com código de exploração (PoC)
- Scripts de scanner para detectar o problema
- Análises técnicas detalhadas da vulnerabilidade

> ⚠️ PoCs devem ser usadas apenas em ambientes autorizados e para fins educacionais.

---

## 📚 O que aprendi

- A diferença prática entre segurança **ofensiva** (atacar para descobrir falhas) e **defensiva** (monitorar e bloquear ameaças)
- Como usar o `dirb` para enumerar diretórios ocultos em aplicações web
- Como identificar e bloquear um atacante pelo IP no firewall
- Como usar **Shodan** para mapear dispositivos expostos na internet
- Como usar **VirusTotal** para análise de arquivos suspeitos
- Como navegar pelo sistema de **CVEs** e bases de vulnerabilidades
- Como ler a documentação de ferramentas com `man` no Linux
- Como usar o **GitHub** para encontrar PoCs e pesquisar vulnerabilidades recentes

---

*TryHackMe — Cyber Security 101 | Módulo 1 concluído*
