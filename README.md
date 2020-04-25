# WordPressOnHeroku
Material and tutorial to install WordPress on Heroku

## Quick List
1. Download WordPress (or fork from wordpress repo)
2. Inicialize a git repo on wordpress folder
3. Create a Heroku project and add a PostgreSQL Database to it
4. Add PostgreSQL support to WordPress (PG4WP - fork by *github: kevinoid* https://github.com/kevinoid/postgresql-for-wordpress)
5. Change or create the wp-config.php file to match the new database settings
  -Pelo que percebi tem de ser assim por causa de correr o setup já com a base de dados postgreSQL mas ainda não experimentei com o fork do PG4WP, apenas com a oficial
  -adicionar dinamicamente porque o heroku roda os hosts de tempo a tempo , há um repo que faz isso
  -questão daquilo do salt que ainda não percebi no fim do documento
  -precisei de adicionar o port no host
6. Push local repo to a new repo on GitHub
7. Deploy to Heroku by connecting to GitHub account
8. Open your site and configure your personal details
  -Não é referente ao config porque já tratámos disso
9. Config HTTPS
    1. Add `REDIRECT_HTTPS = true` to Heroku's Config Vars 
    -https://stackoverflow.com/questions/54730213/failed-to-load-css-in-https-protocol
    -é o mesmo que adicionar enviornment variables ao ficheiro `.env` (exemplo do shiffman para o glitch)
    2. Add the "SSL Insecure Content Fixer" plugin to WordPress, and config the settings
    
    3. Change the website address protocol on WP Settings > General
    -fazer isto sem fazer mais nada dá merda porque depois não consigo voltar a trocar porque o site fica inacessível com os erros




Dúvidas - 
onde é que os ficheiros ficam guardados? 
porque é que não consigo alteral o wp_config através do form usual?



o CSS estava a falhar e a dar mixed content errors então achei que pudesse ser isto: https://laracasts.com/discuss/channels/laravel/heroku-not-loading-appcss-or-appjs




#### SITES ÚTEIS

https://www.wpbeginner.com/plugins/how-to-fix-the-mixed-content-error-in-wordpress-step-by-step/
https://wordpress.org/plugins/ssl-insecure-content-fixer/

https://stackoverflow.com/questions/54730213/failed-to-load-css-in-https-protocol
https://github.com/kevinoid/postgresql-for-wordpress


#### Outras abordagens possiveis
https://laracasts.com/discuss/channels/laravel/heroku-not-loading-appcss-or-appjs


Existe um repo que parece que já tem tudo configurado mas que eu ainda não experimentei
Fiz fork desse Repo, é aqui que o wp-config.php é alterado com base na variável gerada pelo Heroku para a base de dados
Utiliza a versão original do PG4WP (https://wordpress.org/plugins/postgresql-for-wordpress/) 
Pelos vistos também tem nos requisitos um plugin chamado WordPress HTTPS por isso se calhar também trata desses problemas
github repo: https://github.com/mhoofman/wordpress-heroku
tutorial utilizando esse repo: https://youtu.be/d4EndQrrcPA



#### Stresses

Ao depois disto tudo apagar o `REDIRECT_HTTPS = true` das CONFIG VARS do heroku deu merda e todo o site ficou inacessível (mesmo depois de a voltar a introduzir), por isso é necessário apagar toda a base de dados e voltar a fazer tudo do início. (provavelmente será possível apenas aceder à base de dados e trocar o address do site de https:// de novo para http://, caso isto aconteça mais à frente. De qualquer forma isto é estranho porque não alterei nada no código em que tivesse em conta esta variável (deve lá estar já de partida).


Ao pesquisar formas de resolver o problema do HTTPS muitas das fonte encontradas diziam que seria necessário comprar um certificado SSL, o que achei estranho porque na outra app que tinha feito upload para o heroku o HTTPS era default e funcionava bem em todas as directorias. 
  
