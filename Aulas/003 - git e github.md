# Git e Github (Otávio Reis - OPerkles)
- Git é Sistema de controle de versão distribuído (versionamento de código, cvs - controel de versão concorrentes)
- os benefícios:
    1. controle de versão
    2. armazenamento em nuvem
    3. trabalho em equipe
    4. melorar seu código
    5. reconhecimento
## Comandos CLI
- cd acessar pasta (windows /unix)
- verificar conteudo: dir /ls
- criar diretório: mkdir / mkdir
- del/rmdir / rm -rf(-r é recurssivo e -f é o force)
- limpar tela: cls / clear (ou ctrl+L)
- printar 1 comando no terminal; echo
- echo hello>hello.txt
- no windows o comando del o conteudo do diretorio
## Entendo o Git por baixo dos panos
- SHA1 gera 1 chave de 40 dígitos
### Objetos internos do git
- BLOBS, TREES, COMMITS
- os arquivos ficam guardados num objeto guardado num blob q contém o tipo do objeto, o tamanho, um \0 e o conteudo do arquivo, exemplo:
    - Blob \\ tamanho 42 \\ \0 \\ conteudo
- echo 'conteudo' | git hash-object --stdin
-echo -e 'conteudo | openssl sha1
- um sha1 do hasj-object seria 'blob [tanmanho do conteudo]\0[conteudo]
- As trees armazenam blobs
- Os blobs não armarzenam os arquivos, só o sha1.
    - Tree \\ <tamanho>\\ \0 \ blob hashSha1DoBlob NomeDoBlob
- O objeto commit é o que dá sentido a tudo
    - Commit \\ tamanho \\ tree hashTree \\ parente hashDoùltimoCommit \\ autor tal \\ mensagem DoCommit \\ timestamp
### Chave SSH e Token
- Chave ssh é uma forma segura de estabelecer conexão entre duas máquinas (através de 1 chave pública e 1 privada)
- commando gerar chave: ssh-keygen -t ed25519 -C adriano.romerofco@gmail.com
- após isso é para iniciar o ssh agent
- comando: eval $(ssh-agent -s)
- ssh-add id_ed25519
- quando há um ssh não pode simplesmente clonar html, tem que clonar o ssh.
- **token de acesso pessoal**
- é uma forma similar ao ssh, marque a opção repo se for só fazer o padrão
- com isso pode usar o clone https normal
### Primeiros comandos git
- git init / git add / -git commit
- git config --global user.email ="emailmeu"
- git config --global user.name ="nomemeu"
- git config --list
- git add *
- git commit -m "mensagem"
### Ciclo de vida arquivos no git
- Os arquivos rastreados pelo git se dividem em 3 estágios diferentes:
    - unmodified, modified e staged
- Há também os arquivos untracked ()
- Unmodified e modified são auto explicatórios, staged é os arquivos prontos para o commit
- Os arquivos modified são feitos comparando o sha1, se rodar o git add de novo ele vai para staged.
- git add coloca os arquivos direto pra staged
- após o commit o ciclo recomeça, os arquivos staged viram unmodified.
- Servidor é o remote repository
- no Seu ambiente de desenvolvimento ficam o working directory, staging area e o local repository, os arquivos ficarão trocando entre os 2 primeiros até um commit.
### Github
- comando para setar: 
    - git remote add origin [endereço] ||| onde origin é só um nickname para facilitar
    - git push origin main
### Resolução de conflitos
- o git não irá mudar o código em caso de conflito, indicará onde está as diferenças e mandar juntar antes de enviar
- tb é conhecido como conflito de merge (duas alterações na mesma linha)
- quando dá conflito no merge, as alterações mais recentes do local repo ficam entre <<< Head e  ====== , em baixo de === é a alteração do github/remota
- para clonar é git clone url
- para trocar os remotes (que vocoe pode ver em git remote -v) usa o comando:
- git remote set-url <remote_name> <remote_url>