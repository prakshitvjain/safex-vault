# safex-password-vault
A no-nonsense password vault developed using the LAMP stack with security as primary focus, with admittedly poor frontend.

# SafeX
https://github.com/user-attachments/assets/edcb6bf7-7cc4-47a0-bbd6-ed464a0a4f25

## Security Focus

- Passwords hashed with bcrypt (`password_hash`), never stored in plaintext.
- Usernames and password hashes encrypted at rest with AES-256-CBC before being written to the database.
- All SQL queries use prepared statements preventing SQLi.
- Strict Input validation on client side and server side
- Session ID regenerated on login to prevent session fixation.

# Installation and Setup

### Server and MariaDB (Fedora)
Link:https://tecadmin.net/install-lamp-on-fedora/ 

### Clone the repo
```
https://github.com/prakshitvjain/safex-password-vault.git
cd safex-password-vault
```
### Setup MariaDB
Change the default password values in the `DB_setup.sql` file
```
mysql -u root -p < DB_setup.sql
```

### Create a .env file in with same variable names from below file
([.env_sample](https://github.com/prakshitvjain/safex-password-vault/blob/main/.env_sample))

### Load environment variables into the PHP web app
```
composer init
composer require vlucas/phpdotenv
```

### Make the script executable and run
```
chmod +x start_safex.sh
./start_safex.sh
```

The project will be accessible at the provided link

note: works best on google chrome
