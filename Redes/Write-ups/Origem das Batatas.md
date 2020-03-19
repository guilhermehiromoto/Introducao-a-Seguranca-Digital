# Origem das Batatas

### PARTE 1

Rodando o arquivo fornecido é informado que o programa está ouvindo (listening) em uma determinada porta, isso significa que a porta está aberta.

 Uma porta aberta é simplesmente uma porta que possui uma aplicação esperando por conexões nela. Se não houvesse uma aplicação ouvindo naquela porta, qualquer tentativa de conexão nela seria automaticamente rejeitada pelo sistema operacional.
 
As portas são identificadas por números e pelo protocolo de comunicação usado, como TCP ou UDP. No caso desse challenge, o protocolo é o TCP.

> Netcat é uma ferramenta utilizada para estabelecer conexões utilizando os protocolos TCP ou UDP como meio de tráfego.

Como já sabemos qual porta está sendo escutada (dada pelo código), rodamos o comando para se conectar a essa porta aberta:

$ nc localhost <NÚMERO DA PORTA> 

:ballot_box_with_check: Dessa forma obtemos a flag.

### PARTE 2

Nesta segunda etapa também temos um programa escutando em alguma porta, porém desta vez não é informado qual é o número dela. Para descobrir qual porta está escutando utilizaremos a ferramente netstat.

> Netstat (Network Statistics) é uma ferramenta utilizada para monitorar redes e, como o próprio nome diz, gerar estatísticas. 

Algumas informacoes que conseguimos obter com o netstat são, por exemplo, quais portas de comunicacão TCP e UDP estão abertas na nossa maquina e quais os programas ouvindo nessas portas.

Dessa forma, conseguimos utilizar alguns comandos como:

`$ netstat -a`
Lista todas as conexões e portas abertas.

`$ netstat -at`
Aplica um filtro (-t) no comando anterior, listando apenas as portas TCP.

`$ netstat -at -p`
Mostra também o programa que está sendo executado em cada porta

Com esse último comando é possivel ver quais portas TCP estão abertas e verificar qual é a porta que esta ouvindo (na qual o programa está rodando).

:ballot_box_with_check: Sabendo qual a porta que está ouvindo podemos fazer a mesma coisa que foi feita na parte 1 (com o netcat) para obtermos mais uma flag.