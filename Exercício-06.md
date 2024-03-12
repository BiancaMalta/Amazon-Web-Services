# Exercicio 06

## 1. Crie uma role
* 	A partir do console da AWS, navegue até Identidade e Acesso Gerenciado (IAM).
* 	Clique em Funções no menu à esquerda.
* 	Clique em Criar função.
* 	Selecione CloudFormation como o serviço que utilizará esta função.
* 	Clique em Próximo: Permissões.
* 	Selecione a caixa de seleção para a política de permissões AdministratorAccess.
* 	Clique em Próximo: Tags.
* 	Clique em Próximo: Revisão.
* 	Digite pipelineperms4CF como o nome da função.
* 	Clique em Criar função.
## 2. Criar Repositório
*   Criar um Repositório AWS CodeCommit
* 	No console da AWS, navegue até o CodeCommit e clique em Criar repositório.
* 	Digite pipeline4cf como o nome do repositório.
* 	Clique em Criar.
## 3. Suba os arquivos
* 	Em uma nova aba ou janela do navegador, acesse https://github.com/Herikamachado/helloworldpipe/blob/main/index.html.
* 	Clique em Raw.
* 	Selecione todo o conteúdo do arquivo raw e depois copie e cole em um novo arquivo local em seu computador. Salve o arquivo como index.html.
* 	Clique em Adicionar arquivo.
* 	Clique em Carregar arquivo.
* 	Clique em Escolher arquivo.
* 	Acesse https://github.com/Herikamachado/helloworldpipe/tree/main/S3Retain.yaml
* 	Selecione o arquivo S3Retain.yaml que foi salvo em seu computador local.
* 	Digite seu nome como o nome do autor.
* 	Digite seu endereço de e-mail como o endereço de e-mail.
* 	Clique em Confirmar alterações.
## 4. Crie um Tópico SNS
* 	Navegue até o Serviço de Notificação Simples (SNS).
* 	Na caixa Criar tópico na página principal do SNS, digite manualapprove como o nome do tópico.
* 	Clique em Próxima etapa.
* 	Aceite as configurações padrão na próxima página clicando em Criar tópico.
* 	Clique em Criar assinatura.
* 	Escolha E-mail como o protocolo.
* 	Digite seu endereço de e-mail como o endpoint.
* 	Clique em Criar assinatura.
* 	Navegue até sua caixa de entrada, abra a mensagem AWS Notification - Subscription Confirmation e clique no link Confirmar assinatura.
## 5. Crie um bucket
*   Com o seguinte nome:s3bucketretain
## 6. Crie a Pipeline
* 	Criar um Pipeline AWS CodePipeline
* 	Navegue até o console do CodePipeline.
* 	Clique em Criar pipeline.
* 	Digite ManualApprovalPipeline como o nome do pipeline.
* 	Certifique-se de que New Service Role esteja selecionado.
* 	Certifique-se de que a opção Permitir que o AWS CodePipeline crie uma serviceRole para que possa ser usado com este novo pipeline esteja marcada.
* 	Expanda a seção Configurações avançadas e certifique-se de que as opções Localização padrão e Chave AWS Gerenciada padrão estejam selecionadas.
* 	Clique em Próximo.
   * Na página Adicionar estágio de origem, defina os seguintes valores:
   * Provedor de origem: AWS CodeCommit
   * Nome do repositório: pipeline4cf
   * Nome do branch: main
   * Opções de detecção de alterações: Eventos do Amazon CloudWatch (recomendado)
* 	Clique em Próximo.
* 	Clique em Pular estágio de compilação.
* 	Clique em Pular.
    * Na página Adicionar estágio de implantação, defina os seguintes valores:
    * Provedor de implantação: AWS CloudFormation
    * Região: US East - (N. Virginia)
    * Modo de ação: Criar ou atualizar uma pilha
    * Nome da pilha: s3bucketretain
    * Nome do artefato: SourceArtifact
    * Nome do arquivo: S3Retain.yaml
    * Nome da função: pipelineperms4CF
* 	Clique em Próximo > Criar pipeline.
## 7. Editei a pipeline
* 	Clique no link AWS CloudFormation no painel Implantar.
* 	Assim que o CloudFormation mostrar completo, retorne ao serviço CodePipeline.
* 	Verifique se o status do pipeline manualapprove mostra Sucedido no painel Implantar.
* 	Selecione nosso pipeline.
* 	Clique em Editar.
* 	Clique em + Adicionar estágio entre os painéis Origem e Implantar.
* 	Digite manualapproval como o nome do estágio e clique em Adicionar estágio.
* 	Clique em + Adicionar grupo de ações.
   * Na caixa de diálogo Editar ação, defina os seguintes valores:
   * Nome da ação: manualapproval
   * Provedor de ação: Aprovação manual
   * ARN do tópico SNS: Selecione o ARN do tópico SNS listado que criamos anteriormente
* 	Clique em Concluído > Salvar > Salvar.
* 	Clique em Lançar alteração para reiniciar o pipeline.
* 	Clique em Lançar.
## 8. Aprove manualmente
* 	Navegue até sua caixa de entrada e abra a mensagem APROVAÇÃO NECESSÁRIA... para ver o que sua equipe receberia em um ambiente do mundo real.
* 	Navegue de volta ao CodePipeline.
* 	Clique em Revisão no painel Aprovação manual.
* 	Digite Está bom - aprovado. nos comentários e clique em Aprovar.
Publicar sua app em html no s3
## 9. Faça mais uma alteração
* Clique em editar a pipe acima
* Add um stage
	* Inclua nome: TesteHTML
	* Action name: TesteHTML
	* Actionprovider Amazon S3
	* Input Artifacts - SourceArtifacts
	* Inclua o nome do bucket criado acima 
	* Clique em Extract file before deploy
## 10. Testando a Pipeline
Agora que você configurou a pipeline, ela será acionada automaticamente sempre que houver uma alteração no repositório CodeCommit. Para testar:
* 	Faça uma alteração no arquivo index.html em seu repositório CodeCommit (altere a cor da pagina ou adicione uma nova linha, ou altere os textos do html).
* 	Aguarde alguns momentos para que a pipeline seja acionada automaticamente.
* 	Após a conclusão da pipeline, verifique se o arquivo index.html foi atualizado no bucket S3.
* 	Acesse o URL público do bucket S3 para confirmar se o "Hello World" está sendo exibido corretamente.
