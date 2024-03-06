# Exercício 03
## Para essa atividade foi solicitado:
- Criar um repositório utilizando aws cli
- Habilitar um usuário para acesso ao CodeCommit
- Clonar o repositório criado
- Subir o print da última aula
- Criar outro repositório e anexar os arquivos do módulo de versionamento de código
##### É importante lembrar que a atividade não pode ser executada no CloudShell, pois ele atribui a permissão de root. Visando aprender boas práticas, o intuito do exercício é criar um usuário com uma permissão específica para realizar o solicitado.
### Tudo foi acessado direto da minha máquina, não houve a necessidade de criar uma role ou uma instância, apenas segui os seguintes passos:
#### 1. Criei um usuário `herikamachado` com a police `AWSCodeCommitPowerUser`.Logo após, habilitei a chave de acesso e as credenciais HTTPS do Git para o AWS CodeCommit.
#### 2. Acessei a instância com a chave de acesso e criei o primeiro repositório
```
aws configure
aws sts get-caller-identity
aws codecommit create-repository --repository-name RepoBianca
```
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/92246a15-7de2-453a-86ff-bd4d56af7478)

#### 3. Clonei o meu repositório
```
git clone <urlhttp disponibilizado na criação do repositório>
cd RepoBianca
```
#### 4. Adicionei o print da última aula e subi todas as alterações:
##### Obs: No momento em que utilizamos o push, o terminal solicitará o username e o password criados na credencial AWS CodeCommit

```
git add .
git commit -m "primeiro repositório criado"
git config --global user.name "bianca"
git config --global user.email "meuemail"
git push
```
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/d1b6f95e-1bd4-4f9d-a612-5bb458ff00e8)
#### 5. Por fim, criei o segundo repositório e coloque os arquivos do módulo de versionamento de código

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/ce77ea8e-6e48-487c-8d6d-a03a1bb904ef)
#### Para acessar cada repositório, deixarei seus respectivos links:
#### RepoBianca -> https://git-codecommit.us-east-1.amazonaws.com/v1/repos/RepoBianca
#### RepoBianca2 -> https://git-codecommit.us-east-1.amazonaws.com/v1/repos/RepoBianca2
