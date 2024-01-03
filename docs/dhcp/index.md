# DHCP

## Instalação

Primeiramente, precisamos instalar o dnsmasq

    $ apk add dnsmasq



## Configuração

Verifique o ip da interface de rede 

    $ ip -br -c a

Altere o ip da interface se necessário

    $ nano /etc/network/interfaces

No meu caso, alterei o ip da minha interface para 192.168.8.254

![Alt text](image-8.png)

Reinicie a interface de rede com os comandos 

Para derrubar a interface:

    ifdown eth1

Para subir a interface:

    ifup eth1

Verifique se a interface reiniciou com o IP configurado

![Alt text](image-11.png)


Acesse o diretório do dnsmasq e crie um arquivo de configuração

    /etc/dnsmasq.d/exemplo.conf

Insira as seguintes configurações:

![Alt text](image-1.png)

    

Após as configurações realizadas, vamos executar os comandos para ver o status do serviço e dar o start no mesmo.

Para ver o status execute:

![Alt text](image-3.png)

    rc-service dnsmasq status

Para startar o serviço, execute:

![Alt text](image-2.png)

    rc-service dnsmasq start

Verifique novamente o status do serviço para se certificar que está tudo bem.

![Alt text](image-4.png)


Se realizar qualquer alteração, reinicie o serviço do dnsmasq:

![Alt text](image-9.png)

Agora vamos testar o serviço DNS em uma outra maquina windows na mesma rede.


Nas configurações do adaptador de rede do windows, verifique se está configurada com um ip fixo:

![Alt text](image-5.png)

Se sim, que é o meu caso, vou alterar para Obter um endereço de IP e DNS automaticamente  e Clique em Ok.

![Alt text](image.png)


## Teste

Para verificar se a maquina está pegando o IP Dinâmico, iremos abrir o cmd e executar o comando nas duas máquinas criadas para os testes:

    $ ipconfig

![Alt text](image-12.png)

Agora vamos reservar 02 ips fixos. Para necessidades como impressora e servidor.

Para isso precosamos alterar o arquivo dnsmasq.conf acrescentando o endereço MAC e o IP desejado.

    dhcp-host=<Endereço MAC>,IP

![Alt text](image-13.png)

Obs: Lembre de reiniciar o serviço do dnsmasq

Vamos executar o comando ipconfig nas duas VMs que criamos para os testes:

![Alt text](image-6.png)


![Alt text](image-7.png)


Incluir o(s) nome(s) e o conteúdo do(s) arquivo(s) de configuração.

- Distribuir um intervalo (*range* em inglês) de endereços IP; (15 pontos)
- Reservar 2 endereços (IP fixo) fora do intervalo do item anterior. (5 pontos)
