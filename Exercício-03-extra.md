# Exercício 03 - Extra
## Para essa atividade foi solicitado:
- Executar o exercício anterior com a utilização de uma EC2

### Para efetuar a atividade via serviço, segui os seguintes passos:
#### 1. Criei uma role com a police `AWSCodeCommitPowerUser`
#### 2. Criei uma instância e adicionei a role acima
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/4d76d9d5-ffc4-4460-a882-fb7ad910daed)
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/eb5bc34f-e156-4ce1-b275-d7e5f72f1096)
#### 3. Através do ssh me conectei e criei um novo repositório
```
chmod 400 "teste.pem"
ssh -i "teste.pem" ec2-user@ec2-174-129-101-238.compute-1.amazonaws.com
aws codecommit create-repository --repository-name RepoBianca3
```
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/dd3dca8c-d771-4d04-94e2-977fc7f78e19)

#### 5. Instalei o git
![image](https://github.com/BiancaMalta/Amazon-Web-Services/assets/92928037/0ea8a1e0-e35a-4330-81b6-e963f1b74245)
#### 6. Tentei clonar o repositório e percebi que era necessário apresentar um usuário para efetuar os comandos Git. Logo, reutilizei o criado no exercício anterior que possuia a police `AWSCodeCommitPowerUser`. Dessa forma, finalmente consegui clonar. 
#### Para acessar o repositório:
#### RepoBianca3 -> https://git-codecommit.us-east-1.amazonaws.com/v1/repos/RepoBianca3
