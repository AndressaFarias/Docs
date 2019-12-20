# GERANDO CHAVES PÚBLICA E PRIVADA SSH NO LINUX
_Gabriel Gouvea_ 


Uma maneira de acessar os servidore via SSH sem utilizar senha.  Para isso precisamos gerar chaves SSH, uma pública e uma privada. 

* Primeiro verifique se você não possui nenhuma chave gerada: 
    Para isso de uma olhada na pasta `“.ssh”` que fica dentro do diretório `“/home/seuusuário”`,
    você também pode usar o comando `“ls ~/.ssh”`.
    Caso não exista nenhum arquivo chamado **“id_rsa”** e **“id_rsa.pub”** significa que não existem chaves geradas para o seu usuário.

> Obs: quando for trabalhar com chaves SSH evite usar o root uma vez que as chaves são geradas para o usuário que está logado no momento e usar o root pode trazer problemas com permissões e ,claro, as chaves serão geradas no diretório “/root” e não na sua home, então só use o root se for realmente esse o interesse.

* Para gerar as chaves use o comando:
    `ssh-keygen -t rsa -b 2048`
    `ssh-keygen -t rsa -f ~/.ssh/ansible_key -C ansible`

Onde ssh-keygen é o comando de geração de chaves de fato e -t especifica o tipo de chave que estamos gerando, nesse caso o tipo é RSA, -b é força dessa chave em bits, aqui pode-se estipular um valor de até 4096 bits.
    [Questionamentos](!https://ideatip.com.br/wp-content/uploads/2018/05/Capturar.png)

Ao pressionar enter você será questionado sobre algumas coisas, são elas:

Como gerar chaves SSH
Como gerar chaves SSH

1 – O diretório/arquivo que deseja salvar a chave | Deixe o padrão “/home/seunome/.ssh/id_rsa”, basta apertar enter

2- O passphrase | Seria como se fosse uma senha para a chave, se você usar um passphrase deverá digitá-lo toda vez que for se conectar. Existem formas de deixar esse passphrase salvo mas você pode deixar em branco que já será mais seguro que usar apenas a sua senha. Apenas aperte enter para deixar em branco

3-Repetir o passphase | se deixou em branco apenas apenas aperte enter novamente.

Feito isso você deverá se deparar com uma algo parecido com a imagem ao lado. Agora se você executar novamente o comando “ls ~/.ssh” verá que foram criados dois arquivos, o “id_rsa” e o “id_rsa.pub”, o primeiro contém a sua chave privada e nunca deve sair da sua máquina, sugiro inclusive alterar as permissões para somente leitura com o comando “chmod 400 ~/.ssh/id_rsa”. O segundo arquivo contém a sua chave pública, e é ele quem será enviado para onde quer que você queira se conectar.

Para enviar a sua chave publica para outro computador use o comando

ssh-copy-id usuario@IPdocomputador

Veja um exemplo:



Aqui utilizei um computador que está dentro da minha rede local mas o processo é exatamente o mesmo para um computador remoto, apenas trocaria o IP local por um IP Externo ou por um DDNS. Note que utilizo um adicional no final do comando, o “-p 2225” isso é porque eu não uso a porta padrão do SSH, a 22, se você usa a porta padrão ( o que não recomendo) não é necessário especificar nada. Se quiser saber como alterar a porta padrão do SSH confira esse outro post que ensino isso clicando aqui.

Após digitar a senha do computador, pela ultima vez, ele irá enviar a sua chave pública e você já poderá se conectar sem a necessidade de usar a senha, veja o exemplo:

Como gerar chave SSH
Como gerar chave SSH

Obrigado por visitar o blog, não deixe de conhecer o canal no YouTube clicando aqui.

Confira também a nossa página no Facebook e Instagram

Até a próxima 🙂

# Referencia 

https://ideatip.com.br/gerando-chaves-publica-e-privada-ssh-no-linux/