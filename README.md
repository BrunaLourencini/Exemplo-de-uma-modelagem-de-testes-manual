# Exemplo-de-uma-modelagem-de-testes-manual



## 💻 Sobre o projeto

Neste exemplo, você recrutador poderá visualizar como é meu pensamento analítico e como modelo um teste a partir da história descrita.

---
## 💡 Modelo 01 - Levantamento e Análise

Realize uma análise de testabilidade na história a seguir, pontuando se ela possui informações suficientes para elaboração dos Casos de Testes.
Caso não possua, descreva como seria a melhor abordagem para levantar esses pontos e quais as informações que faltaram para deixar a história mais completa.

⚙️ História:
 - Padronização de telefone
 
⚙️ Introdução:
 - Como forma de padronização e centralização de validações de Telefone, a biblioteca foi criada de forma a permitir uma série de validações e boas práticas em torno deles.
 
⚙️ Formato padrão de telefone:
 - Para utilização dos telefones para envio de SMS, serão considerados apenas números de telefone celular.
 - Formados por: DDD com dois dígitos + 9 + número com 8 dígitos, sem espaços nem caracteres especiais (“+”, “-“, etc...). Totalizando 11 dígitos: [DDD]9[00000000]
 
⚙️ Regras de validação:
- [x] Remover todos os caracteres especiais do DDD e do telefone;

- [x] Remover todos os zeros à esquerda do DDD e do telefone;

- [x] Regras de acordo com a quantidade de caracteres:

- [x] 10 ou menos dígitos: Número inválido;

- [x] 11 dígitos: Número composto por 2 dígitos de DDD + 9 + 8 dígitos do telefone:

- [x] O oitavo dígito (8D) do telefone não pode iniciar com 0;

- [x] Caso o (9D) não seja o 9, número inválido.
 
### Serão considerados critérios de aceite:

Telefone final obrigatoriamente com 11 dígitos sendo DDD (2D) +Telefone(9D);

Ausência de DDDs inválidos


## 🚀 RESPOSTA Modelo 01:

### Análise de Testabilidade: História/Funcionalidade Padronizar formato de telefone.

- Entradas:
1. Tipo de envio Envio de SMS
2. Tipo de telefone Celular
3. Formato de Telefone Sem espaços no Telefone
4. Sem caracteres especiais do DDD e Telefone
5. Sem zeros à esquerda do DDD e Telefone
6. Telefone com 10 dígitos
7. Telefone com 11 dígitos sendo 2 dígitos do DDD + 9 + 8 dígitos do telefone
8. O oitavo dígito (8D) não pode iniciar com 0
9. Se o (9D) não for o 9

- Saídas:
1. Telefone com 11 dígitos sendo DDD (2D) + Telefone (9D)
2. Ausência de DDDs inválidos
3. Telefone Inválido

### Pontos que, na minha visão, faltaram na história:

• Mencionar as validações dos campos onde é imputado esse número de telefone

• Relatar como é extraído essas informações de telefone

• Garantir que o número de telefone pertence a determinado usuário

• Informar quais seriam os ambientes de testes, exemplo: versão do aparelho de celular, versão do sistema operacional, etc.

### Descrição da abordagem que, na minha visão, faltou na história:

Faltou uma descrição mais detalhada sobre a Visão do Usuário e Visão de Negócio.
Na Visão do Usuário, precisa relatar sobre o desejo/necessidade do(a) PO/Squad, em incluir esta história na sprint, detalhando melhor o objetivo da padronização de telefone.
E na Visão de Negócio, faltou explanar mais sobre as necessidades da padronização de telefone, contemplando possíveis problemas ocorridos, detalhando mais sobre a origem das informações de captura desses telefones.
E melhor clareza nas descrições das regras de validação, pois os dois pontos abaixo não declaram qual seria ponto de partida para realizar a contagem dos dígitos e realmente identificar qual seria o nono e o oitavo dígito.

“O oitavo dígito (8D) do telefone não pode iniciar com 0;”

“Caso o (9D) não seja o 9, número inválido”

---

## 🛠 Modelo 02 - Modelagem de Teste

Escrita de Casos de Testes - Dado a História do Exercício 1, elabore a construção dos cenários de testes contendo os pré-requisitos necessários para a execução.

## 🚀 RESPOSTA Modelo 02:

<table>
  <tr>
    <td align="center">Caso de Teste</td>
    <td align="center">NR</td>
    <td align="center">História/Funcionalidade</td>
    <td align="center">Nome do Caso de Teste (Cenário)</td>
    <td align="center">Gherkin</td>
    
  </tr>
  <tr>
    <td align="center">CT</td>
    <td align="center">001</td>
    <td align="left">Padronização de telefone</td>
    <td align="left">Validar DDD válido e número de telefone celular válidos com 11 dígitos</td>
    <td align="left">				
        Dado que preciso enviar um sms</br>
				E possuo um número de telefone celular para contato</br>
				Quando informo um número de telefone celular com 11 dígitos sendo 2 dígitos do DDD + 9 + 8 dígitos do
				telefone</br>
				E não possui espaços no DDD e Telefone</br>
				E não possui caracteres especiais no DDD e Telefone</br>
				E não possui zeros à esquerda no DDD e Telefone</br>
				E o oitavo dígito (8D) não inicia com zero</br>
				E o nono dígito (9D) é igual a 9</br>
				E os dígitos são apenas números</br>
				E realizo o envio do sms</br>
				Então número de telefone é válido</td>
    
  </tr>
  <tr>
    <td align="center">CT</td>
    <td align="center">002</td>
    <td align="left">Padronização de telefone</td>
    <td align="left">Validar DDD válido e número de telefone celular válido</td>
    <td align="left">				
        Dado que preciso enviar um sms</br>
				E possuo um número de telefone celular para contato</br>
				Quando informo um número de telefone que não possui espaços no DDD e Telefone</br>
				E não possui caracteres especiais no DDD e Telefone</br>
				E não possui zeros à esquerda no DDD e Telefone</br>
				E o oitavo dígito (8D) não inicia com zero</br>
				E o nono dígito (9D) é igual a 9</br>
				E os dígitos são apenas números</br>
				E o total de dígitos são 11</br>
				E realizo o envio do sms</br>
				Então número de telefone é válido</td>
    
  </tr>  
  <tr>
    <td align="center">CT</td>
    <td align="center">003</td>
    <td align="left">Padronização de telefone</td>
    <td align="left">Validar DDD válido com número de telefone inválido</td>
    <td align="left">
        Dado que preciso enviar um sms</br>
				E possuo um número de telefone celular para contato</br>
				Quando informo um número de telefone que seja inválido</br>
				E o número de DDD é válido</br>
				E realizo o envio do sms</br>
				Então número completo de DDD + telefone é inválido</td>
    
  </tr>  
  <tr>
    <td align="center">CT</td>
    <td align="center">004</td>
    <td align="left">Padronização de telefone</td>
    <td align="left">Validar DDD inválidos com número de telefone válido</td>
    <td align="left">
        Dado que preciso enviar um sms</br>
				E possuo um número de telefone celular para contato</br>
				Quando informo um número de telefone que contenha zero à esquerda do DDD/ DDD inexistente no Brasil/ DDD com
				caracter além de número</br>
				E o número de telefone é válido</br>
				E realizo o envio do sms</br>
				Então número completo de DDD + telefone é inválido</td>
    
  </tr>
  <tr>
    <td align="center">CT</td>
    <td align="center">005</td>
    <td align="left">Padronização de telefone</td>
    <td align="left">Validar número de telefone celular que contenha números e outros caracteres</td>
    <td align="left">
        Dado que preciso enviar um sms</br>
				E possuo um número de telefone celular para contato</br>
				Quando informo o número de celular que contenha caracteres especiais/ espaços/ letras além de números</br>
				E realizo o envio do sms</br>
				Então recebo um retorno de telefone inválido.</td>
    
  </tr>
  <tr>
    <td align="center">CT</td>
    <td align="center">006</td>
    <td align="left">Padronização de telefone</td>
    <td align="left">Validar número de telefone celular com 10 dígitos</td>
    <td align="left">
        Dado que preciso enviar um sms</br>
				E possuo um número de telefone celular para contato</br>
				Quando informo o número de celular com 10 dígitos</br>
				E realizo o envio do sms</br>
				Então recebo um retorno de telefone inválido.</td>
    
  </tr>  
  <tr>
    <td align="center">CT</td>
    <td align="center">007</td>
    <td align="left">Padronização de telefone</td>
    <td align="left">Validar número de telefone celular com 12 dígitos</td>
    <td align="left">				
        Dado que preciso enviar um sms</br>
				E possuo um número de telefone celular para contato</br>
				Quando informo o número de celular com 12 dígitos</br>
				E realizo o envio do sms</br>
				Então recebo um retorno de telefone inválido.</td>
    
  </tr>  
  <tr>
    <td align="center">CT</td>
    <td align="center">008</td>
    <td align="left">Padronização de telefone</td>
    <td align="left">Validar o nono dígito do número de telefone celular</td>
    <td align="left">
        Dado que preciso enviar um sms</br>
				E possuo um número de telefone celular para contato</br>
				Quando informo um número de telefone celular que o nono dígito (9D), é diferente de 9</br>
				E realizo o envio do sms</br>
				Então número de telefone é inválido</td>
    
  </tr>  
  <tr>
    <td align="center">CT</td>
    <td align="center">009</td>
    <td align="left">Padronização de telefone</td>
    <td align="left">Validar o oitavo dígito do número de telefone celular</td>
    <td align="left">
        Dado que preciso enviar um sms</br>
				E possuo um número de telefone celular para contato</br>
				Quando informo um número de telefone celular que o oitavo dígito (8D), é igual a zero</br>
				E realizo o envio do sms</br>
				Então número de telefone é inválido</td>
    
  </tr> 
  
</table>

---


# 🦸 Autor

<a href="https://www.linkedin.com/in/bruna-l-a5068b128/">
 <img style="border-radius: 50%;" src="https://media.licdn.com/dms/image/C4D03AQHExWC0GKRyhQ/profile-displayphoto-shrink_200_200/0/1658924806138?e=1684972800&v=beta&t=u94kTuUiVDuDX4zaN8cgCGM63LJpFXGQIb6gj8vPJjg" width="100px;" alt=""/>
 <br />
 <sub><b>Bruna Lourencini</b></sub></a> 🚀</a>
 <br />

[Linkedin Bruna](https://www.linkedin.com/in/bruna-l-a5068b128/) 



💜 Obrigada por me visitar!!!

---
