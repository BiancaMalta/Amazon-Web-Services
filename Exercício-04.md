# Exercício 04
## Nesse exercício foi solicitado:
- Criar um repositório no codecommit
- Clonar o conteúdo do git abaixo para o repositorio do codecommit
- Criar um bucket onde enviaremos os arquivos compilados
- Criar um build, colocar em environment variable o path do seu bucket S3_BUCKET_PATH
- Direcione os arquivos do seu build para um bucket S3
#### Utilize o código/ estrutura criada nesse git: https://github.com/Herikamachado/meubuild.git

### Para isso, executei os seguintes passos:
#### 1. Criei o repositório e clonei todo o conteúdo do git para ele
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/7abe156f-379e-464c-928c-d69d49295d02)
#### 2. Criei um bucket, alterei o comando de build na buildspec.yml e criei o build
 ![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/bdef8cb3-5810-4510-9e6a-9768f1771695)

#### 3. Editei as permissões em CodeBuildBasePolicy
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/55d5966d-7ab7-4997-a399-9ce731f8e986)

#### 4. Iniciei o build

![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/f441a98b-c9f6-4bc4-970f-579d54c3ce97)

#### 5. Como resultado, todos os arquivos buildados estão dentro do S3
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/3700f84c-166b-4c90-94b1-f2d525d38da5)


