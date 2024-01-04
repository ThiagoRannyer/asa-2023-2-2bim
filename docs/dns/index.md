# DNS

## Instalação

Precisamos instalar o servidor SAMBA e deixar ele ativo. O cliente Windows tem que está configrurado no mesmo domínio de DNS como nas configurações para o SAMBA. No meu caso **pernambuco.lab**

Instalação [SAMBA](/smb/)

## Configuração

Com o serviço SAMBA funcionando, vamos até a máquina cliente com Windows para as configurações de DNS

No cliente windows nas propiedades do adaptador de rede, configure o ip estático desejado. Lembre que ele precisa fazer parte da mesma rede do **SAMBA**. Também configure o **GATEWAY** e o **DNS**.

![Alt text](image-11.png)

No menu inicar pesquise por **DNS**

![Alt text](image-3.png)

Clique em **DNS**. Na janela que abrir, digite o dominio configurado no servidor **SAMBA** (pernambuco.lab).

![Alt text](image.png)

Se estiver tudo OK, irá abrir a seguinte janela:

![Alt text](image-2.png)

Clique em: servidor pernambuco.lab > Zonas de pesquisa direta > pernambuco.lab

![Alt text](image-4.png)

clique com o botão direito na área em branco e em seguida em Novo Host (A ou AAA). 

![Alt text](image-5.png)

Agora em **Nome** configure o nome do servidor da sua necessidadee coloque o ip da máquina desejada. MArque a opção PTR.

![Alt text](image-6.png)

![Alt text](image-7.png)

Agora, no mesmo local, clique mais uma vez com o botão direito e clique em **Novo alias (CNAME).

![Alt text](image-8.png)

Configure criando o nome desejado que no meu caso será `www` e no FQDN Procure pelo host desejado, que em nosso caso foi **kids**.

![Alt text](image-9.png)

Vamos criar mais um **Host** chamdo `Inspire` e mais um **CNAME** chamdo `docs`.

Hosts

![Alt text](image-1.png)

CNAME

![Alt text](image-12.png)

## Teste

Agora vamos realizar o teste do ping com **www** para ver se nosso **DNS** está funcionando corretamente.

Abra o **CMD** no cliente Windows e digite o comando:

Para pingar em www

    $ ping www

![Alt text](image-10.png)

Para pingar em docs

    $ ping docs

![Alt text](image-13.png)
















Incluir o(s) nome(s) e o conteúdo do(s) arquivo(s) de configuração.

Cinco registros (4 pontos cada):

- 2 do tipo A (Endereços);
- 2 do tipo CNAME (`www` e `docs`);