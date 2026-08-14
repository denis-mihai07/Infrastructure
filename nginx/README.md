
# SSL Self-Signed Certificate

openssl req -x509 -nodes -days [NUMBER OF DAYS] -newkey rsa:2048 -keyout [PATH OF .key FILE] -out [PATH OF .crt FILE] -subj "/CN=[DOMAIN NAME]"

Example: openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout ./selfsigned.key -out ./selfsigned.crt -subj "/CN=[DOMAIN NAME]"

# Nginx Configuration for Certificate


server {
   listen 80 ssl; *<- ADD ssl to the listen*
   ...
 
   ssl_certificate_key [PATH to .key FILE];
   ssl_certificate [PATH TO .crt FILE];

   ssl_protocols TLSv1.2 TLSv1.3;

  ...
}
