# WordPressOnHeroku
Material and tutorial to install WordPress on Heroku

## Quick List
1. Download WordPress (or fork from wordpress repo)
2. Inicialize a git repo on wordpress folder
3. Create a Heroku project and add a PostgreSQL Database to it
4. Add PostgreSQL support to WordPress (PG4WP - fork by *github: kevinoid*)
5. Change or create the wp-config.php file to match the new database settings
  Pelo que percebi tem de ser assim por causa de correr o setup já com a base de dados postgreSQL mas ainda não experimentei com o fork do PG4WP, apenas com a oficial
  adicionar dinamicamente porque o heroku roda os hosts de tempo a tempo , há um repo que faz isso
  questão daquilo do salt que ainda não percebi no fim do documento
  
6. Push local repo to a new repo on GitHub
7. Deploy to Heroku by connecting to GitHub account
8. Open your site and configure your personal details
  Não é referente ao config porque já tratámos disso
9. Config HTTPS
    1. Add `REDIRECT_HTTPS = true` to Heroku's Config Vars 
    https://stackoverflow.com/questions/54730213/failed-to-load-css-in-https-protocol
    é o mesmo que adicionar enviornment variables ao ficheiro `.env` (exemplo do shiffman para o glitch)
    2. Add the "SSL Insecure Content Fixer" plugin to WordPress, and config the settings
    
    3. Change the website address protocol on WP Settings > General
    fazer isto sem fazer mais nada dá merda porque depois não consigo voltar a trocar porque o site fica inacessível com os erros

Dúvidas - 
onde é que os ficheiros ficam guardados? 
porque é que não consigo alteral o wp_config através do form usual?



o CSS estava a falhar e a dar mixed content errors então achei que pudesse ser isto: https://laracasts.com/discuss/channels/laravel/heroku-not-loading-appcss-or-appjs

  
