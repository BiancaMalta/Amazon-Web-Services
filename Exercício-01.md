# Exercício 01
## Foi solicitado: 
- Criar 3 usuários
- Criar 3 grupos - associe as policies de permissão conforme descrito na tabela
- Associar cada usúario ao respectivo grupo
- Escolha o user-1, faça login no console com este usuário e acesse o serviço EC2

| User | In Group | Permissions |
| --- | --- | --- |
| user-1 | S3-Support | Read-only acess to S3 | 
| user-2 | EC2-Support | Read-only acess to EC2 |
| user-3 | EC2-Admin | View, start, and stop EC2 instances|


## Como executei:
### Para começar tive que acessar o serviço IAM
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/347592bf-572f-4005-b727-14c80734b269)
### Na aba `Gerenciamento de acesso` cliquei na opção `Usuários`
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/bf6f57df-fcea-4a7c-9851-a34c607c13d7)
### E criei os 3 usuários solicitados
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/22193dd7-97ee-435e-8fb4-54b0b36eeb94)

### Após esse passo, entrei em `Grupos de usuários` para criar os grupos com suas respectivas polices. Na imagem abaixo, estava selecionando a permissão `Read-only acess to S3` para o grupo `S3-Support`
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/fe4d5f5f-2cd2-491b-8a9c-4f07b60e30ca)
### Logo em seguida, associei cada usúario ao seu respectivo grupo
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/2f2dbca3-4711-4aa3-905a-1aa9a614d79c)
### E por fim, habilitei o console do user-1 e com o hash disponibilizado, fiz login nele
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/cdab40d9-ca74-4a7f-9f12-cc3c74dfb292)
### Como resultado da restrições `Read-only acess to S3`, não foi permitido executar uma instância
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/d2b723fb-d39f-49e5-94cb-1a56758f78b0)





