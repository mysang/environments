#### Connect to server
- `ssh -i <secret_key> <user>@<ip_or_host>`

#### Connect MySQL
- `mysql -u<user> -p -h <ip_or_host>`

#### Export database
- `mysqldump -u<user> -p -h <ip_or_host> <database> > <path_to_file>.sql`

#### Export table in database
- `mysqldump -u<user> -p -h <ip_or_host> <database> <table> > <path_to_file>.sql`

#### Copy file from server
- `scp -i <secret_key> <user>@<ip_or_host>:<path_to_file_on_server> <path_to_file_on_local>`
