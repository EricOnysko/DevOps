MEDIA_PATH=  varwwwlocalhost 
INDEX_PATH= $MEDIA_PATH  index.html 
HTTPD_CONF_PATH=  etchttpdconf.d 

sudo mkdir -p $MEDIA_PATH  && sudo торкніться $INDEX_PATH
sudo cat homevagrantsharedindex.html   $INDEX_PATH

sudo mkdir -p $HTTPD_CONF_PATH
sudo cat homevagrantsharedlocalhost.conf  etchttpdconf.dlocalhost.conf

chcon -Rt httpd_sys_content_t $MEDIA_PATH

sudo openssl req -x509 -nodes -days 365 -newkey rsa2048 -keyout etcsslcertsapache-selfsigned.key -out etcsslcertsapache-selfsigned.crt -subj  C=UA CN=localhostL=LvivO=ITSU 

sudo yum install -y epel-release

sudo yum install -y httpd

sudo yum install -y mod_ssl

sudo httpd -t

sudo systemctl запуск httpd