# Exercício 03
## Para essa atividade foi solicitado:
- Criar um repositório utilizando aws cli
-  Habilitar um usuário para acesso ao CodeCommit
- Clonar o repositório criado
- Subir o print da última aula
- Criar outro repositório e anexar os arquivos do módulo de versionamento de código
### Para isso, segui os seguintes passos:
#### Criei uma role `EC2commit` com as seguintes permissões:
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/fafdcdd6-a634-47cb-9b5a-7e0bd72a399b)
#### Criei uma instância e adicionei a role
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/4d76d9d5-ffc4-4460-a882-fb7ad910daed)
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/eb5bc34f-e156-4ce1-b275-d7e5f72f1096)
#### Separadamente, criei um usuário `herikamachado` para dar acessso ao CodeCommit
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/b45b3aed-2d8f-4a1d-a831-8c15836fbc6c)
##### Lembre-se de habilitar a chave de acesso e a credencial AWS CodeCommit
#### Na minha máquina, acessei a instância com a chave de acesso e criei o primeiro repositório
```
aws configure
aws sts get-caller-identity
aws s3 ls
aws codecommit create-repository --repository-name RepoBianca
```
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/92246a15-7de2-453a-86ff-bd4d56af7478)

####  Instalei o git e clonei o meu repositório
```
yum install git
git clone clone <urlhttp disponibilizado na criação do repositório>
cd RepBianca
```
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/0ea8a1e0-e35a-4330-81b6-e963f1b74245)
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/1ed58149-2465-47d3-9cb9-4a6a079a5058)

#### Adicionei o print da última aula e subi todas as alterações:
##### Obs: No momento em que utilizamos o push, o terminal solicitará o username e o password criados na credencial AWS CodeCommit

```
git add .
git commit -m "primeiro repositório criado"
git config --global user.name "bianca"
git config --global user.email "meuemail"
git push
```
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/d1b6f95e-1bd4-4f9d-a612-5bb458ff00e8)
####  Por fim, criei o segundo repositório e coloque os arquivos do módulo de versionamento de código

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/ce77ea8e-6e48-487c-8d6d-a03a1bb904ef)


