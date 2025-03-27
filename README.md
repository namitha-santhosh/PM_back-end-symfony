Steps to run it locally:
1. Clone this project.
2. Run composer install
3. Create new database with correct user privileges.
4. Run doctrine:migrations:mirate to load migrations to db. Run php bin/console make:migration if migrations not present.
5. Run doctrine:fixtures:load to load fixtures to db.
6. Generate private and public jwt keys for authentication. Run these commands:
    mkdir -p config/jwt
    openssl genpkey -algorithm RSA -out config/jwt/private.pem -aes256 -pass pass:your_passphrase
    openssl rsa -pubout -in config/jwt/private.pem -out config/jwt/public.pem -passin pass:your_passphrase
    chmod 600 config/jwt/private.pem config/jwt/public.pem
9. Run symfony server:start to start running the server. It will be visible in port 8000
