# Exercício 05
## Objetivo do exercício é criar uma pipeline simples que irá subir um arquivo html do codecommit para s3, controlando aprovação.

### Passo 1: Configurar o Bucket S3
Primeiro, você precisa criar um bucket S3 onde o HTML será armazenado. Siga estes passos:
* Acesse o Console de Gerenciamento da AWS e vá para o serviço S3.
* Crie um novo bucket, dando-lhe um nome único.
* Mantenha as configurações padrão para o bucket
* Guarde o nome do bucket

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/49bb76e2-6126-4fa9-9cf7-57874f0f7851)


### Passo 2: Criar um Repositório no AWS CodeCommit
Você precisará de um repositório para armazenar o código-fonte do seu projeto HTML. Aqui está como fazer isso:
* Acesse o Console de Gerenciamento da AWS e vá para o serviço CodeCommit.
* Crie um novo repositório.
* Siga as instruções para clonar o repositório em seu ambiente local.
* Crie um arquivo HTML chamado index.html com o conteúdo "Hello World".

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/7b9c7f02-7438-49ee-9294-2459f247fc59)


### Passo 3: Configurar o AWS CodePipeline com Aprovação Manual
* Acesse o Console de Gerenciamento da AWS e vá para o serviço CodePipeline.
* Clique em "Criar pipeline".
* Escolha um nome para a sua pipeline e clique em "Next".
* Selecione "New service role" para a função do serviço e clique em "Next".
* No estágio "Source", escolha o provedor "AWS CodeCommit" e selecione o repositório que você criou anteriormente. Em seguida, clique em "Next".
* No estágio "Build", clique em "Skip build stage" e, em seguida, clique em "Next".
* No estágio "Deploy", escolha o provedor "Amazon S3" e selecione o bucket S3 que você criou anteriormente.  Clique em "Next".
* Revise as configurações e clique em "Criar pipeline".

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/acab5145-480b-4de6-8907-9ea1aa27a5f5)

### Passo 4: Agora, vamos adicionar um novo estágio para a aprovação manual:
* Clique em "Adicionar estágio".
* Nomeie o estágio como "Aprovação Manual" e clique em "Next".
* No novo estágio, clique em "Adicionar ação".
* Nomeie a ação como "Aprovação Manual".
* Escolha o provedor "Manual approval" para a ação.
* Preencha as informações necessárias e clique em "Next".

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/7d9fc801-21d1-4f04-8a69-c3be6361cd1f)


### Passo 5: Testando a Pipeline
Agora que você configurou a pipeline, ela será acionada automaticamente sempre que houver uma alteração no repositório CodeCommit. Para testar:
* Faça uma alteração no arquivo index.html em seu repositório CodeCommit (por exemplo, adicione uma nova linha, ou altere os textos do html).
* Aguarde alguns momentos para que a pipeline seja acionada automaticamente.
* Após a conclusão da pipeline, verifique se o arquivo index.html foi atualizado no bucket S3.
* Acesse o URL público do bucket S3 para confirmar se o "Hello World" está sendo exibido corretamente.

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/2211ff15-0145-4683-b94d-b9f2c850009b)

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/6fa5a892-2deb-4f37-b137-28160614fd69)

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/26f171d3-60db-41ca-b41e-862a7feda56b)

