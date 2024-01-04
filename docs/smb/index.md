# SMB

## Instalação

Para instalar o SAMBA, execute os comandos a seguir:

Instalar o pcaote samba:

    $ apk add samba

Executar o servidor SAMBA:

    $ rc-service samba start

Se desejar que o serviço SAMBA inicie automaticamente no boot, você pode executar o comando:

    $ rc-update add samba


## Configuração

Agora vamos executar o comando abaixo para executar algumas configurações:

    $ samba-tool domain provision --user -rfc2307 --interactive

onde o comando "samba-tool domain provision" é usado para provisionar um novo controlador de domínio usando o Samba.

A opção "--user" especifica que você deseja adicionar um usuário administrador durante o processo de provisionamento.

A opção "--rfc2307" isso é comumente usado quando você deseja integrar sistemas Unix/Linux ao ambiente do Active Directory.

A opção "--interactive" faz com que o comando seja executado de forma interativa, solicitando informações adicionais durante o processo.

Em resumo, o comando está provisionando um controlador de domínio Samba, adicionando um usuário administrador, configurando atributos RFC2307 e executando de forma interativa para fornecer informações adicionais durante o processo. Este é um procedimento comum ao configurar um ambiente que requer a integração do Samba com o Active Directory para autenticação e compartilhamento de arquivos em ambientes mistos Unix/Linux e Windows.

Precisamos editar o arquivo smb.conf

![Alt text](image.png)

Neste caso, iremos inserir as seguintes informações:

![Alt text](image-1.png)

criar os diretórios que foram inseridos no smb.conf (diretórios que serão compartilhados):

![Alt text](image-2.png)

![Alt text](image-3.png)

Edite também o arquivo hosts em /etc/hosts para definirmos um domínio em nosso **DNS**.

![Alt text](image-17.png)

Vamos reiniciar o SAMBA

![Alt text](image-4.png)

Alterar o ip da máquina cliente

![Alt text](image-5.png)

ativa o compartilhamento de arquivos e pastas

![Alt text](image-6.png)

ir em iniciar > click direto em computador > propriedades > alterar configuração > alterar > marcar a opção domínio e colocar o domínio configurado pernambuco.lab

![Alt text](image-7.png)

Nomenu iniciar do cliente, pesquise por active e clique em "Usuários e computadores do Active Directory"

![Alt text](image-8.png)

Para criar os grupos e usuários você pode já criar nas OUs desejadas como também pode mover após criar, como fizemos no LDAP.

Para criar os Grupos, faça login como administrador, abra o active directory, selecione a OU desejada, clique no ícone "criar grupo no container atual" ou clique com o botão direito na área em branco do container > clique em novo > e em Grupo.

![Alt text](image-9.png)

Dê o nome desejado ao grupo e clique em OK.

![Alt text](image-10.png)

![Alt text](image-11.png)

Agora para criar os usuários, faça login como administrador, abra o active directory, selecione a OU desejada, clique no ícone "criar usuário no container atual" ou clique com o botão direito na área em branco do container > clique em novo > e em usuário.

Na janela que abriu, coloque as informações necessárias. e clique em avançar.

![Alt text](image-12.png)

cConfigure uma senha segura, marque ou desmarque as opções desejadas e clique em avançar.

![Alt text](image-13.png)

Confira se está os dados apresentados e clique em concluir.

![Alt text](image-14.png)

Para adicionar os usuários aos seus respectivos grupos, clique ocom o botão direito no usuário desejado > adicionar a um grupo > 

![Alt text](image-15.png)

Digite o nome do grupo desejado e clique em OK. Repita quantas vezes forem necessário para cada usuário que desejar adicionar a um grupo.

![Alt text](image-16.png)



Incluir o(s) nome(s) e o conteúdo do(s) arquivo(s) de configuração.

1. Criar 2 grupos para dois de seus sobrenomes;
2. Criar 4 usuários, dois para cada um dos sobrenomes;
3. Compartilhar duas pastas com dois de seus sobrenome, compartilhado para o grupo com o sobrenome correspondente. 

## Teste


