# Exercício 04
## Nesse exercício foi solicitado:
- Criar um repositório no codecommit
- Clonar o conteúdo do git abaixo para o repositorio do codecommit
- Criar um bucket onde enviaremos os arquivos compilados
- Criar um build, colocar em environment variable o path do seu bucket S3_BUCKET_PATH
- Direcione os arquivos do seu build para um bucket S3
- Tirar print do bucket com os arquivos
#### Utilize o código/ estrutura criada nesse git: https://github.com/Herikamachado/meubuild.git

### Para isso, executei os seguintes passos:
#### 1. Criei uma role com a permissão de S3 Full e CodeCommit Power user

#### 2. Criei uma EC2 e uma chave de acesso

#### 3. Criei um usuário para poder usar o Git 

#### 4. Acessei a instância e criei o repositório
```
chmod 400 "teste.pem"
ssh -i "teste.pem" ec2-user@ec2-174-129-101-238.compute-1.amazonaws.com
aws codecommit create-repository --repository-name RepoBianca4
```
#### 5. Criei um bucket
```
aws s3 mb s3://bucket-03-ada
```
#### 6. Clonei o conteúdo do git
```
cd RepoBianca4
git clone https://github.com/Herikamachado/meubuild.git
```
#### 7. Criei um build

