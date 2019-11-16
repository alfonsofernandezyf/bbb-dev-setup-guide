# bbb-dev-setup-guide
Setup guide for BBB development environment


/*
*
*/

crea 
mkdir /etc/nginx/ssl

/* Crear un certificado */

openssl genrsa -out bbb.test.key 4096
openssl req -new -x509 -key bbb.test.key -out bbb.test.crt -days 3650 -subj /CN=bbb.test

/*copiar el certificcado al folder de nginx*/

cp bbb.test.key  /etc/nginx/ssl/bbb.test.key
cp bbb.test.crt  /etc/nginx/ssl/bbb.test.crt
/* openssl dhparam -out /etc/nginx/ssl/dhp-4096.pem 4096 */


poner todo como https


sed -e 's|playback_protocol: http|playback_protocol: https|g' /usr/local/bigbluebutton/core/scripts/bigbluebutton.yml








