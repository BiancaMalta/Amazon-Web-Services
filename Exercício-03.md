# Exercício 03
## Para essa atividade foi solicitado:
- Criar um repositório utilizando aws cli
- Habilitar um usuário para acesso ao CodeCommit
- Clonar o repositório criado
- Subir o print da última aula
- Criar outro repositório e anexar os arquivos do módulo de versionamento de código
### Para isso, segui os seguintes passos:
#### 1. Criei uma role `EC2commit` com a permissão `AWSCodeCommitPowerUser`
#### 2. Não era necessário, mas resolvi criar uma instância para executar essa atividade. Dessa forma, o próximo passo envolveu adicionar a role criada a instância.
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/4d76d9d5-ffc4-4460-a882-fb7ad910daed)
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/eb5bc34f-e156-4ce1-b275-d7e5f72f1096)
#### 3. Criei um usuário `herikamachado` com a police `AWSCodeCommitPowerUser`.Logo após, habilitei a chave de acesso e as credenciais HTTPS do Git para o AWS CodeCommit.
#### 4. Na minha máquina, acessei a instância com a chave de acesso e criei o primeiro repositório
```
aws configure
aws sts get-caller-identity
aws s3 ls
aws codecommit create-repository --repository-name RepoBianca
```
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/92246a15-7de2-453a-86ff-bd4d56af7478)

#### 5. Instalei o git e clonei o meu repositório
```
yum install git
git clone <urlhttp disponibilizado na criação do repositório>
cd RepoBianca
```
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/0ea8a1e0-e35a-4330-81b6-e963f1b74245)
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/1ed58149-2465-47d3-9cb9-4a6a079a5058)

#### 6. Adicionei o print da última aula e subi todas as alterações:
##### Obs: No momento em que utilizamos o push, o terminal solicitará o username e o password criados na credencial AWS CodeCommit

```
git add .
git commit -m "primeiro repositório criado"
git config --global user.name "bianca"
git config --global user.email "meuemail"
git push
```
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/d1b6f95e-1bd4-4f9d-a612-5bb458ff00e8)
#### 7. Por fim, criei o segundo repositório e coloque os arquivos do módulo de versionamento de código

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/ce77ea8e-6e48-487c-8d6d-a03a1bb904ef)
#### Para acessar cada repositório, deixarei seus respectivos links:
#### RepoBianca -> https://git-codecommit.us-east-1.amazonaws.com/v1/repos/RepoBianca
#### RepoBianca2 -> https://git-codecommit.us-east-1.amazonaws.com/v1/repos/RepoBianca2
