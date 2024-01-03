# LDAP

## Instalação



## Configuração

Para criar as OUs No menu iniciar do cliente, pesquise por active e clique em "Usuários e Computadores do Active Directory"

![Alt text](image-8.png)


Na janela que abriu, clique no servidor pernambuco.lab

![Alt text](image.png)


Em seguida, clique com o botão direito no espaço em branco do container e clique em "novo" e em seguida, no submenu clique em "Unidade Organizacional"

![Alt text](image-1.png)

Dê o nome desejado a sua OU e clique em OK

![Alt text](image-2.png)

Para mover os grupos criados e seus usuários para a OU desejada, clique com o botão direito no grupo desejado e em seguida clique em mover... Em seguida repita o processo nos usuários.

![Alt text](image-3.png)

Na janela que abriu selecione a OU de destino desejada

![Alt text](image-4.png)


Incluir o(s) nome(s) e o conteúdo do(s) arquivo(s) de configuração.

- Criar duas OU: `vendedores` e `rh`;
- Mover o grupo `sobrenome1` e seus membros para a OU `vendedores`;
- Mover os grupo `sobrenome2` e seus membros para a OU `rh`.

## Teste

Clique na OU desejada para verificar se os grupos e usuários estão em seus lugares.

![Alt text](image-5.png)

Vá na opção para trocar de usuário e faça login com um dos usuários criados.

![Alt text](image-6.png)

Insira as credenciais de login

![Alt text](image-7.png)

no menu iniciar, digite \\\noronha e aperte enter. uma janela com as pastas compartilhadas deve abrir.

![Alt text](image-11.png)

![Alt text](image-10.png)

Se toda configuração estiver correta, ao clicar na pasta do grupo ao qual o login pertence, a pasta deve abrir normalmente, e ao clicar na pasta do grupo ao qual o usuário do login não pertence, ele pedirá um login e senha.

![Alt text](image-9.png)

![Alt text](image-12.png)

