# Conhecimentos básicos de DevOps

## O que é Linux e comandos básicos

### 🐧 O que é Linux?

Linux é um sistema operacional de código aberto, inspirado no sistema Minix, criado por Linus Torvalds. Ele é conhecido por sua segurança, estabilidade e alto nível de personalização, sendo muito utilizado por desenvolvedores e empresas. 

#### Principais características:
- **Gratuito e livre**: pode ser baixado, modificado e distribuído por qualquer pessoa.
- **Seguro por padrão**.
- **Diversas distribuições**: Ubuntu, Fedora, Debian, entre outras.
- **Vários compiladores e interpretadores já instalados** por padrão.

---

## 💻 Comandos básicos do terminal Linux

### 📍 Navegação
- `pwd`  
  Exibe o caminho completo do diretório atual.

- `cd <diretório>`  
  Acessa o diretório especificado.  
  Exemplos:
  - `cd ..` → Volta um diretório.
  - `cd` → Volta para a home do usuário.

- `ls`  
  Lista o conteúdo do diretório atual.  
  Argumentos úteis:
  - `ls -l` → Lista com detalhes.
  - `ls -a` → Exibe arquivos ocultos.
  - `ls -la` → Lista detalhada com ocultos.

---

### 📁 Gerenciamento de diretórios e arquivos

- `mkdir <nome>`  
  Cria um novo diretório.  
  Use `-p` para criar diretórios em árvore.  
  Ex: `mkdir -p pasta1/pasta2`.

- `touch <arquivo>`  
  Cria um arquivo vazio ou atualiza a data de modificação.

- `cp <origem> <destino>`  
  Copia arquivos.  
  Use `-r` para copiar diretórios e `-p` para manter os atributos.  
  Ex: `cp -rp pasta1 pasta2`.

- `mv <origem> <destino>`  
  Move ou renomeia arquivos e diretórios.

---

### 🗑️ Remoção

- `rm <arquivo>`  
  Remove um arquivo.

- `rm -r <diretório>`  
  Remove um diretório com seu conteúdo.

- `rm -rf <diretório>`  
  Remove forçadamente sem pedir confirmação (perigoso!).

- `rm *.txt`  
  Remove todos os arquivos `.txt` no diretório atual (uso de expressões regulares).

---

## Parte 2: Comandos de edição e gestão de arquivos no Linux

### 📦 Gerenciador de Pacotes com APT
- `apt-get update`: atualiza a lista de pacotes disponíveis.
- `apt install <nome>`: instala um pacote.
- `apt remove <nome>`: remove um pacote (mantém arquivos de config).
- `apt purge <nome>`: remove o pacote e arquivos de configuração.

---

### 🌳 Visualização em árvore de diretórios
- `tree`: exibe a estrutura de pastas em forma de árvore.
  - `tree -L 2`: exibe até dois níveis.
- Pode ser necessário instalar com `apt install tree`.

---

### 📝 Edição de arquivos com `vi` ou `vim`
- `vi arquivo.txt`: abre o arquivo no modo leitura.
- Tecla `i`: entra no modo de inserção (edição).
- `Esc`: sai do modo de inserção.
- `:w`: salva alterações.
- `:q`: sai do editor.
- `:wq`: salva e sai.
- `:q!`: sai sem salvar.
- `/palavra`: busca palavra no texto.
- `n`: busca próxima ocorrência.
- `dd`: deleta uma linha.
- `u`: desfaz última ação.
- `gg`: vai para o início do arquivo.
- `G`: vai para o fim do arquivo.

---

### 📖 Leitura e visualização de arquivos
- `cat arquivo.txt`: exibe todo o conteúdo.
- `cat -e arquivo.txt`: mostra quebras de linha com `$`.
- `more arquivo.txt`: navega página por página.
- `less arquivo.txt`: navegação com mais recursos.
- `head -n 5 arquivo.txt`: exibe as 5 primeiras linhas.
- `tail -n 5 arquivo.txt`: exibe as 5 últimas linhas.
- `tail -f arquivo.log`: acompanha em tempo real novas linhas adicionadas.

---

### 🔍 Buscas com `grep`
- `grep "termo" arquivo.txt`: busca por “termo”.
- `grep -n "termo" arquivo.txt`: mostra número da linha.
- `grep -v "termo" arquivo.txt`: exclui linhas com o termo.
- `grep -E "erro1|erro2"`: usa expressão regular para múltiplas palavras.

---

### 📦 Compactação e descompactação de arquivos
- `tar -cf arquivo.tar pasta/`: compacta pasta em .tar.
- `tar -xf arquivo.tar`: extrai conteúdo do .tar.
- `tar -czf arquivo.tar.gz pasta/`: compacta em .tar.gz.
- `tar -xzf arquivo.tar.gz`: descompacta .tar.gz.
- `zip arquivo.zip pasta/`: compacta com zip.
- `unzip arquivo.zip`: descompacta zip.

---

## Parte 3: Comandos de rede e processos no Linux

### 🌐 Verificando IP e rede
- `hostname -I`  
  Mostra os IPs atribuídos à máquina.

- `ip addr show`  
  Exibe todas as interfaces e IPs disponíveis.

---

### 📶 Testes de conectividade
- `ping google.com`  
  Testa a conectividade com um endereço.  
  (Alguns servidores como o Google podem bloquear as respostas, mas resolver o DNS já mostra que está funcionando.)

- `telnet <host> <porta>`  
  Testa conexão com uma porta específica.  
  Ex: `telnet google.com 80`

---

### 🔐 Acesso remoto via SSH
- `ssh usuario@host`  
  Conecta a um servidor remoto via SSH.  
  Ex: `ssh jose@meuservidor.com`

- Executar comandos remotos:  
  `ssh usuario@host comando`  
  Ex: `ssh jose@meuservidor.com pwd`

---

### 🔎 Verificando portas e processos
- `netstat -tulnp`  
  Lista conexões ativas, portas em escuta e processos associados.

- `ps aux`  
  Lista todos os processos em execução.

- `kill -9 <PID>`  
  Força a finalização de um processo.  
  Use `kill -15 <PID>` para encerrar normalmente.

- `top`  
  Interface dinâmica que mostra uso da CPU, memória e processos ativos.

---

### 💾 Verificando espaço em disco
- `df -h`  
  Mostra o uso de disco em formato legível (GB/MB).

- `du -sh *`  
  Mostra o tamanho de cada diretório no local atual.

---

### ⚙️ Variáveis de ambiente
- `echo $NOME_VARIAVEL`  
  Exibe o valor de uma variável de ambiente.

- `export TESTE=ola`  
  Define uma variável de ambiente personalizada.

- `env`  
  Lista todas as variáveis de ambiente ativas.

---

### ✅ Recapitulando os comandos úteis da Parte 3:
- `hostname -I`, `ip addr`, `ping`, `telnet` → Conectividade e rede
- `ssh`, `ssh user@host comando` → Acesso remoto
- `netstat`, `ps aux`, `kill`, `top` → Monitoramento de processos e portas
- `df -h`, `du -sh *` → Espaço em disco
- `export`, `env`, `echo $VAR` → Variáveis de ambiente

---


