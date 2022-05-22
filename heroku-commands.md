# Návod na deployment na heroku - www.heroku.com

Doporučuju nejprve si zkusit nasadit tuto funkční aplikaci a až pak případně 
tu vlastní. Ta by samozřejmě měla nejprve 100% fungovat lokálně.

### vytvořte si účet na Heroku
https://signup.heroku.com/

### nainstalujte si heroku client
https://devcenter.heroku.com/articles/heroku-cli

curl https://cli-assets.heroku.com/install.sh | sh

## od této chvíle dál používejte terminál a zadávejte přikazy 

Musíte být v adresáři s projektem, který chcete uložit na Heroku. 
Tedy například zde v adresáři s aplikací.

### přihlášení klienta
heroku login steep 1111111111111111111111111111

### vytvořte git repozitář a zapište do něj všechny soubory v adresáři
git init
git add -A
git commit -m "ready to deploy"  step 222222222222222222222222 s random zprávou místo readyto deploy 

### vytvořte aplikaci v heroku - tato by se jmenovala my-app
heroku create my-app 

### create Postgres db for app
heroku addons:create heroku-postgresql:hobby-dev --app my-app
### check config
heroku config --app my-app

### push app to the cloud
git push heroku master step 333333333333333333333333333333333 

### přepneme config aplikace na produkční
heroku config:set --remote heroku SECRET_KEY=mkjkljkl3231498jlkjlkjaa APP_SETTINGS=config.ProductionConfig

nebo

heroku config:set --app my-app SECRET_KEY=mkjkljkl3231498jlkjlkjaa APP_SETTINGS=config.ProductionConfig

### vytvoříme databázi
heroku run python init_db.py

### otevřeme aplikaci
heroku open

