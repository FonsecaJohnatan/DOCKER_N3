**Avaliação N3 - Redes**

**Equipe: Johnatan, Guilherme Meiring, Iago e Thomas**
 
Configuração de ambiente com Docker Compose para os serviços: WordPress, MySQL, phpMyAdmin e nginx como proxy reverso.

📌 **Objetivo**

Criar um ambiente funcional com 4 serviços integrados:
 
- nginx como proxy reverso
- WordPress acessível em http://localhost/prova
- MySQL como banco de dados
- phpMyAdmin para administração do banco de dados
  

⚙️ **Serviços configurados**

| Serviço    | Imagem                | Porta          | Observação                                                          |
| ---------- | --------------------- | -------------- | ------------------------------------------------------------------- |
| nginx      | nginx\:latest         | 80             | Proxy reverso para o WordPress                                      |
| wordpress  | wordpress\:latest     | interno (80)   | Site acessível via [http://localhost/prova](http://localhost/prova) |
| mysql      | mysql:5.7             | interno (3306) | Banco de dados para WordPress e phpMyAdmin                          |
| phpmyadmin | phpmyadmin/phpmyadmin | 8080           | Acessível via [http://localhost:8080](http://localhost:8080)        |



**📁 Estrutura do projeto**

1. Clone este repositório:
   git clone https://github.com/seu-usuario/nome-do-repo.git
   cd nome-do-repo
   
2. Suba os containers com:
   docker compose up -d
   
3. Acesse no navegador:
   WordPress: http://localhost/prova
   phpMyAdmin: http://localhost:8080

**🛠️ Detalhes técnicos**
- O nginx atua como proxy reverso, redirecionando as requisições da URL http://localhost/prova para o container do WordPress.

- O WordPress foi configurado com as constantes WP_HOME e WP_SITEURL apontando para http://localhost/prova para funcionar corretamente fora da raiz.

- O phpMyAdmin se conecta diretamente ao container MySQL na rede interna.
