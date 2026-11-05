# Aula_CMD

# Avaliações e Técnicas de Teste de Segurança de Rede

> **Aviso ético e legal:** todos os testes deste repositório foram feitos no meu próprio computador ou em ambientes próprios e autorizados. Nada aqui deve ser usado contra redes ou sistemas de terceiros sem autorização, o que pode ser crime (Lei 12.737/2012). Este repositório não contém senhas, dados pessoais nem informações de redes de empresas ou da escola.

## Índice

- [Avaliações de segurança](#avaliações-de-segurança)
- [Comandos de rede: Windows e Linux](#comandos-de-rede-windows-e-linux)
- [Técnicas de teste de segurança de rede](#técnicas-de-teste-de-segurança-de-rede)

---

## Avaliações de segurança

**O que é:** uma avaliação reúne informações e mede o nível de segurança de um sistema ou de uma rede.

**Tipos:**

- **Avaliação de vulnerabilidades:** procura falhas.
- **Teste de penetração:** tenta explorar as falhas.
- **Avaliação de risco:** calcula o quanto cada falha pode custar.
- **Auditoria:** verifica se as regras estão sendo seguidas.

Para coletar dados e diagnosticar a conectividade, usamos comandos:

- `ipconfig` (Windows) ou `ip a` (Linux): mostra o endereço IP do equipamento.
- `ping`: testa se um destino responde.
- `tracert` (Windows) ou `traceroute` (Linux): mostra o caminho até o destino.
- `nslookup`: consulta o DNS (traduz nome em IP).
- `netstat` (Windows) ou `ss` (Linux): mostra conexões e portas abertas.
- `arp -a` (Windows) ou `ip neigh` (Linux): mostra a tabela de IP e endereço físico (MAC) dos vizinhos.

<img width="1906" height="250" alt="image" src="https://github.com/user-attachments/assets/23c5be37-83b9-417b-91f2-b87e4d7438af" />

---

## Comandos de rede: Windows e Linux

| O que quero ver | Windows | Linux |
|---|---|---|
| IP do computador | `ipconfig` (detalhes: `ipconfig /all`) | `ip a` |
| Gateway (roteador) | Aparece no `ipconfig` | `ip route` |
| Testar se responde | `ping 8.8.8.8` | `ping -c 4 8.8.8.8` |
| Caminho até o destino | `tracert www.cisco.com` | `traceroute www.cisco.com` |
| Consultar o DNS | `nslookup www.google.com` | `nslookup www.google.com` ou `dig www.google.com` |
| Conexões e portas abertas | `netstat -an` | `ss -tuln` |
| Vizinhos da rede (IP e MAC) | `arp -a` | `ip neigh` |
| Hash de um arquivo | `certutil -hashfile arquivo.txt SHA256` | `sha256sum arquivo.txt` |

### Observações

- No Linux, o `ping` só para com **Ctrl+C**. O `-c 4` limita a 4 pacotes.
- No Linux Mint, para instalar o que faltar:

```bash
sudo apt update
sudo apt install traceroute dnsutils net-tools
```

---

## Técnicas de teste de segurança de rede

**O que é:** formas de examinar a rede.

| Técnica | O que faz |
|---|---|
| Varredura de rede | Descobre dispositivos ativos |
| Varredura de portas | Vê quais portas estão abertas |
| Varredura de vulnerabilidades | Procura falhas conhecidas |
| Captura de tráfego (sniffing) | Observa os pacotes que passam |
| Quebra de senhas | Verifica se as senhas são fracas |
| Verificação de integridade (hash) | Confirma que os arquivos não foram alterados |
| Simulação de ataque | Imita o atacante |



**Exemplo:** uma varredura de portas em um servidor encontra a porta 23 (Telnet, sem criptografia) aberta. É uma falha: o ideal é usar a 22 (SSH, criptografado).

**O que acontece:** cada técnica revela um tipo diferente de risco, por isso usamos várias em conjunto.

Continua…
---

> Execute estes comandos e técnicas apenas no seu próprio computador ou em ambientes com autorização.
