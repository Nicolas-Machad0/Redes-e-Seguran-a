# Markdown
## 30 comandos essenciais do Linux utilizando a linguagem Markdown.
## date
Esse comando permite a visualização e edição da Data e Hora do Sistema, mas para fazer essa modificação se é necessario estar como usuario root.
`date MesDiaHoraMinuto[AnoSegundos]` : São respectivamente os números do mês, dia, hora e minutos sem espaços.
`date +%d` : Dia do Mês (00-31).
`date +%m` : Mês do Ano (00-12).
`date +%y`: Ano (dois dígitos).
`date +%Y`: Ano (quatro dígitos).
`date +%H` : Hora (00-24).
`date +%I` : Hora (00-12).
`date +%M` : Minuto (00-59).
`date +%j` : Dia do ano (1-366).
`date +%p` : AM/PM (útil se utilizado com %d).
`date +%r` : Formato de 12 horas completo (hh:mm:ss AM/PM).
`date +%T` : Formato de 24 horas completo (hh:mm:ss).
`date +%w` : Dia da semana (0-6).
**Exemplo**:
Se quiser mostrar a hora atual digite: `date +%H`
Exemplo de saida: 16
Ou seja é 16 horas ou 4 horas da tarde
## df
Mostra o espaço livre e ocupado do disco.Este comando contém códigos que mostram ou executam certos comandos.
`df -h` ou `df--human-readable`: Mostra o espaço livre/ocupado em MB, KB, GB
`df -H`: Idêntico a -h mas usa 1000 ao invés de 1024 como unidade de cálculo.
`df -k`: Lista em Kbytes.
`df -l`: Somente lista sistema de arquivos locais.
`df -m`: Lista em Mbytes
`df --sync`: Executa o **sync** antes de mostrar os dados.
`df -T`: Lista o tipo de sistema de arquivos de cada partição
`df -t` casa : Lista somente sistema de arquivos do tipo *casa*
`df -x`casa : Não lista sistemas de arquivos do tipo *casa*
**Exemplo** : 
Se quiser saber o numero de KB livres no disco digite: `df -k /var`
Exemplo de saida: /dev/sda1 52428800 52000000 428800 99% /var
Significa que tem apenas 428.800 KB livres.
## clear
Limpa a tela do terminal, removendo o texto visível anteriormente e posicionando o cursor no canto superior esquerdo.
**Exemplo** :
O terminal está cheio de comandos e após isso o usuário digitou `clear` como resultado a tela do terminal fica limpa, facilitando a visualização dos próximos comandos.
## ln
Cria links para arquivos e diretórios no sistema. O link é um mecanismo que faz referência a outro arquivo ou diretório em outra localização, podendo também fazer cópias.
`ln [opções] [origem] [link]` esta é a forma a qual é montado o comando onde:
*origem* : Diretório ou arquivo de onde será feito o link.
*link* : Nome do link que será criado.
*opções*, `-s` : Cria um link simbólico. Usado para criar ligações com o arquivo/diretório de destino.
`ln -v` : Mostra o nome de cada arquivo antes de fazer o link.
`ln -d` : Cria um hard link para diretórios. Somente o root pode usar esta opção.
**Exemplo** :
Ao digitar `ln -s /dev/ttyS1 /dev/modem` Cria o link /dev/modem para o arquivo /dev/ttyS1.
## du
irá mostrar o espaço ocupado por arquivos e sub-diretórios do diretório atual.
du [opções] novamente é desta forma ao qual o comando é montado onde:
*opções*, `-a`, `--all` : Mostra o espaço ocupado por todos os arquivos.
`-b`, `--bytes` : Mostra o espaço ocupado em bytes.
`-c`, `--total` : Faz uma totalização de todo espaço listado.
`-D` : Não conta links simbólicos.
`-h`, `--human` : Mostra o espaço ocupado em formato legível por humanos (Kb, Mb) ao invés de usar blocos.
`-H` : Como o anterior mas usa 1000 e não 1024 como unidade de cálculo.
`-k` : Mostra o espaço ocupado em Kbytes.
`-m` : Mostra o espaço ocupado em Mbytes.
`-S`, `--separate-dirs` : Não calcula o espaço ocupado por sub-diretórios.
`-x` : Não faz a contagem de diretórios em sistemas de arquivos diferentes do atual.
**Exemplo** : `du -h`, `du -hc`.
## find
O find é quem procura por arquivos ou diretórios. Ele também pode procurar arquivos através de sua data de modificação, tamanho, etc através do uso de opções
find [diretório] [opções/expressão] esta é a forma a qual é montado o comando onde:
*diretório* : Inicia a procura neste diretório, percorrendo seu sub-diretórios.
*opções/expressão*, `-name [expressão]` : Procura pelo nome [expressão] nos nomes de arquivos e diretórios processados.
`-depth` : Processa os sub-diretórios primeiro antes de processar os arquivos do diretório principal.
`-maxdepth [num]` : Faz a procura até [num] sub-diretórios dentro do diretório que está sendo pesquisado.
`-mindepth [num]` : Não faz nenhuma procura em diretórios menores que [num] níveis.
`-mount, -xdev` : Não faz a pesquisa em sistemas de arquivos diferentes daquele de onde o comando find foi executado.
`-amin [num]` : Procura por arquivos que foram acessados [num] minutos atrás. Caso for antecedido por "-", procura por arquivos que foram acessados entre [num] minutos atrás até agora.
`-atime [num]` : Procura por arquivos que foram acessados [num] dias atrás. Caso for antecedido por "-", procura por arquivos que foram acessados entre [num] dias atrás e a data atual.
` -gid [num]` : Procura por arquivos que possuam a identificação numérica do grupo igual a [num].
`-group [nome]` : Procura por arquivos que possuam a identificação de nome do grupo igual a [nome].
`-uid [num]` : Procura por arquivos que possuam a identificação numérica do usuário igual a [num].
`-user [nome]` : Procura por arquivos que possuam a identificação de nome do usuário igual a [nome].
`-inum [num]` : Procura por arquivos que estão localizados no inodo [num].
`-links [num]`: Procura por arquivos que possuem [num] links como referência.
`-mmin [num]` : Procura por arquivos que tiveram seu conteúdo modificado há [num] minutos. Caso for antecedido por "-", procura por arquivos que tiveram seu conteúdo modificado entre [num] minutos atrás até agora.
`-mtime [num]` : Procura por arquivos que tiveram seu conteúdo modificado há [num] dias. Caso for antecedido por "-", procura por arquivos que tiveram seu conteúdo modificado entre [num] dias atrás até agora.
`-ctime [num]` : Procura por arquivos que teve seu status modificado há [num] dias. Caso for antecedido por "-", procura por arquivos que tiveram seu conteúdo modificado entre [num] dias atrás até agora.
`-nouser` : Procura por arquivos que não correspondam a identificação do usuário atual.
`-nogroup` : Procura por arquivos que não correspondam a identificação do grupo do usuário atual.
`-perm [modo]` : Procura por arquivos que possuam os modos de permissão [modo]. Os [modo] de permissão pode ser numérico (octal) ou literal.
`-used [num]` : O arquivo foi acessado [num] vezes antes de ter seu status modificado.
`-size [num]` : Procura por arquivos que tiverem o tamanho [num]. [num] pode ser antecedido de "+" ou "-" para especificar um arquivo maior ou menor que [num]. A opção -size pode ser seguida de:
**b** - Especifica o tamanho em blocos de 512 bytes. É o padrão caso [num] não seja acompanhado de nenhuma letra.
**c** - Especifica o tamanho em bytes.
**k** - Especifica o tamanho em Kbytes.
`-type [tipo]` : Procura por arquivos do [tipo] especificado. Os seguintes tipos são aceitos:
**b** - bloco
**c** - caracter
**d** - diretório
**p** - pipe
**f** - arquivo regular
**l** - link simbólico
**s** - sockete
A maior parte dos argumentos numéricos podem ser precedidos por "+" ou "-".
**Exemplo**: Ao digitar `find . -size +1000k` Procura no diretório atual e sub-diretórios um arquivo com tamanho maior que 1000 kbytes.
## time
Mede o tempo necessário para ser gasto na execução de um processo(programa).
`time [comando]` : Onde o *comando* é o comando/programa que deseja medir o tempo gasto para ser concluído.
**Exemplo** : 
Se quiser medir tempo de compactação de arquivos digite: `time tar -czf backup.tar.gz /home/usuario` Assim você descobre quanto tempo o backup levou.
## tail
Mostra as linhas finais de um arquivo texto.
`tail [opções]` no caso: 
`-c [numero]` : Mostra o [numero] de bytes do final do arquivo.
`-n [numero]` : Mostra o [numero] de linhas do final do arquivo.
`-f` : Mostra continuamente linhas adicionadas no final do arquivo.
**Exemplo**:
Caso queira ver apenas as 5 linhas finais digite: `tail -5 arquivo.txt`
## sort
Este comando irá organizar a linha de um arquivo de texto ou de uma entrada padrão. A organização é feita por linhas e as linhas são divididas em campos que é a ordem que as palavras aparecem na linha separadas por um delimitador.
`sort [opções] [arquivo]` esta é a forma a qual é montado o comando onde:
*arquivo* : É o nome do arquivo que será organizado. Caso não for especificado, será usado o dispositivo de entrada padrão (normalmente o teclado ou um "|").
*opções*, `-b`: Ignora linhas em branco.
`-d` : Somente usa letras, dígitos e espaços durante a organização.
`-f` : Ignora a diferença entre maiúsculas e minúsculas.
`-r` : Inverte o resultado da comparação.
`-n` : Caso estiver organizando um campo que contém números, os números serão organizados na ordem aritmética.
`-c` :Verifica se o arquivo já esta organizado. Caso não estiver, retorna a mensagem "disorder on arquivo".
`-o arquivo` : Grava a saída do comando sort no arquivo.
`-m arquivo1 arquivo2` : Combina o conteúdo de arquivo1 e arquivo2 gerando um único arquivo. Os dois arquivos precisam estar ordenados antes de se utilizar esta opção.
`-i` : Ignora os caracteres fora da faixa octal ASCII 040-0176 durante a organização.
`-t caracter` : Usa caracter como delimitador durante a organização de linhas. Por padrão é usado um espaço em branco como delimitador de caracteres.
`-k num1, num2` : Esta é uma alternativa ao método acima para especificar as chaves de organização. O uso é idêntico, mas o delimitador é iniciado em "1".
**Exemplo**:
Caso queira organizar o arquivo texto.txt em ordem crescente utilize: sort texto.txt
## free
Demonstra a utilização da memória RAM do sistema
`free [opções]`esta é a forma a qual é montado o comando onde:
*opções*, `-b` : Mostra o resultado em bytes.
`-k` : Mostra o resultado em Kbytes.
`-m` : Mostra o resultado em Mbytes.
`-o` : Oculta a linha de buffers. 
`-t` : Mostra uma linha contendo o total.
`-s [num]` : Mostra a utilização da memória a cada [num] segundos.
**Exemplo**:
Caso queira verificar se o servidor está sem RAM utilize: `free -h` se a memória livre estiver muito baixa e swap em uso alto, pode haver lentidão.
## less
Permite fazer a paginação de arquivos ou da entrada padrão. O comando less pode ser usado como comando para leitura de arquivos que ocupem mais de uma tela.
`less [arquivo]` esta é a forma a qual é montado o comando onde:
*arquivo* : É o arquivo que será paginado.
**Exemplo** :
Para visualizar diretamente arquivos texto compactados pelo utilitário gzip (arquivos .gz), use o comando `zless`.
## more
Permite fazer a paginação de arquivos ou da entrada padrão. O comando more pode ser usado como comando para leitura de arquivos que ocupem mais de uma tela.
`more [arquivo]` esta é a forma a qual é montado o comando onde:
*arquivo* : É o arquivo que será paginado.
**Exemplo**:
Para visualizar diretamente arquivos texto compactados pelo `gzip .gz` use o comando `zmore`.
## nl 
Mostra o numero de linhas totais junto com o conteudo de um arquivo
`nl [opções] [arquivo]` esta é a forma a qual é montado o comando onde:
*opções*, `-f [opc]` : Faz a filtragem de saída de acordo com [opc], os seguintes opc aceitos são:
**a** - Numera todas as linhas.
**t** - Não numera linhas vazias.
**n** - Numera linhas vazias.
**texto** - Numera somente linhas que contém o [texto].
`-v [num]` : Número inicial (o padrão é 1).
`-i [num]` : Número de linhas adicionadas a cada linha do arquivo (o padrão é 1).
**Exemplo** : Se quiser uma ajuda para identificar em qual linha ocorreu erro utilize o código: nl script.sh
## head
Demonstra as linhas iniciais de um arquivo texto.
`head [opções]` esta é a forma a qual é montado o comando onde:
`-c [numero]` : Mostra o [numero] de bytes do inicio do arquivo.
`-n [numero]` : Mostra o [numero] de linhas do inicio do arquivo. Caso não for especificado, o head mostra as 10 primeiras linhas.
**Exemplo** : Se quiser ver as 10 primeiras linhas do arquivo banco.txt utilize - head banco.txt
## grep
Ele realiza uma procura por um texto dentro de um arquivo ou no dispositivo de entrada padrão.
`grep [expressão] [arquivo] [opções]` esta é a forma a qual é montado o comando onde:
*expressão*: palavra ou frase que será procurada no texto. Se tiver mais de 2 palavras você deve identifica-la com aspas "" caso contrário o grep assumirá que a segunda palavra é o arquivo!
*arquivo*: Arquivo onde será feita a procura.
*opções*, `-A [número]` : Mostra o [número] de linhas após a linha encontrada pelo grep.
`-B [número]` : Mostra o [número] de linhas antes da linha encontrada pelo grep.
`-f [arquivo]` : Especifica que o texto que será localizado, esta no arquivo [arquivo].
`-h`, `--no-filename` : Não mostra os nomes dos arquivos durante a procura.
`-i`, `--ignore-case`: Ignora diferença entre maiúsculas e minúsculas no texto procurado e arquivo.
`-n`, `--line-number` : Mostra o nome de cada linha encontrada pelo grep.
`-E` : Ativa o uso de expressões regulares.
`-U`, `--binary` : Trata o arquivo que será procurado como binário.
**Exemplo**: Use o comando zgrep para pesquisar diretamente em arquivos compactados com gzip, os comandos e opções são as mesmas.
## dmesg
Mostra mensagens do sistema, principalmente sobre hardware e inicialização.
**Exemplo:**
dmesg | less

## mesg  
Controla se outros usuários podem enviar mensagens para o seu terminal.
**Exemplo:**
mesg n

## echo
Exibe um texto na tela ou escreve texto em arquivos.
**Exemplo:**
echo "Olá mundo"

## su
Permite trocar de usuário no sistema, geralmente para administrador.
**Exemplo:**
su root


## sync
Força o sistema a salvar dados pendentes no disco.
**Exemplo:**
sync

## uname
Mostra informações sobre o sistema operacional.
**Exemplo:**
uname -a

## reboot
Reinicia o sistema.
**Exemplo:**
reboot

## cmp
Compara dois arquivos e mostra se são diferentes.
**Exemplo:**
cmp arquivo1.txt arquivo2.txt

## dirname
Mostra o diretório de um caminho de arquivo.
**Exemplo:**
dirname /home/user/arquivo.txt

## pr
Formata textos para leitura ou impressão organizada.
**Exemplo:**
pr arquivo.txt

## whereis
Localiza onde estão os arquivos de um comando (binário, código-fonte e manual).
**Exemplo:**
whereis ls

## which
Mostra o caminho completo de um comando que será executado no terminal.
**Exemplo:**
which python

## zforce
Força arquivos a serem tratados como compactados no formato gzip.
**Exemplo:**
zforce arquivo.txt

## gzexe
Comprime arquivos executáveis para economizar espaço.
**Exemplo:**
gzexe programa

## whoami
Mostra o nome do usuário atualmente logado no sistema.
**Exemplo:**
whoami