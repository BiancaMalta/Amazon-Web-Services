# Exercício 02
## Foi solicitado:
- Criar uma role de acesso da EC2 para ter acesso s3 full
- Criar uma EC2| Imagem:ami-0440d3b780d96b29d | Type:t2.micro
- Criar uma chave para conectar vai ssh
- Veja se existe um IP externo para se conectar via ssh
- Acesse a instância via ssh
- Crie um bucket
- Liste o bucket
- Associe a role criada na instancia EC2
- Crie dois buckets S3 utilizando AWS CLI
- Através da AWS console, suba um arquivo para o bucket
- Através da AWS CLI copie o arquivo do bucket 1 para o bucket 2
- De um print na copia dos arquivos e liste os arquivos nos 2 bucket


1. Criei uma role:
  - Especificando EC2 como caso de uso </br>
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/89c5b107-47b4-4a5c-8703-32fc4359cd4e)
  - Com a permissão de S3 full </br>
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/5688af9f-71fb-4f68-931f-5981257f04ef) 
2. Criei uma EC2 com as devidas especificações solicitadas e uma chave de acesso </br>
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/c27ea9cb-17ae-43df-a957-a425e87f5435)
3. Acessei a instância </br>
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/bb33a5cb-6801-4ad0-a555-598dbbcfa680)
4. Entrei no serviço S3, criei um bucket e uppei uma imagem </br>
  ![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/44e6aa49-6046-42b6-8feb-1dc8fa442d5d)
5. Para listar o bucket:
  - criei um usuário taxado com a police AdministratorAccess </br>
   ![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/2fa1d95b-784d-42ff-8472-2719f05d8854) 
  - Criei uma chave de acesso via Command Line Interface </br>
  ![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/41b65533-03e6-4f72-ad99-d814d5e791c4)
  - Listei o bucket dentro do terminal da minha máquina </br>
  ![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/a47026ff-7822-4e0c-b473-3e2beee9717a)
6. Adicionei a role criada na instância </br>
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/6ec85cfa-63d7-40e1-9210-18c4aad6955a)
7. Criei os dois buckets S3


