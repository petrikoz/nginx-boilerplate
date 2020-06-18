Use unique [Diffie-Hellman Group](https://weakdh.org/sysadmin.html):

```shell

openssl dhparam -out /etc/nginx/ssl/dhparams.pem 3096
```

Install your certificates in this directory:

```shell

mkdir /etc/nginx/ssl/example.com

acme.sh --install-cert -d example.com \
        --fullchain-file /etc/nginx/ssl/example.com/fullchain.pem \
        --key-file       /etc/nginx/ssl/example.com/key.pem \
        --reloadcmd      "service nginx reload"
```
