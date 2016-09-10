# hackmarthon
--install nginx

yum install readline-devel pcre-devel openssl-devel gcc -y
tar xvf openresty-1.11.2.1.tar.gz
cd openresty-1.11.2.1
./configure
gmake
gmake install
cd ../
tar xvf dabao.tar.gz
mv dabao /usr/local/openresty/nginx/html/


--install pythonenv
yum install python-setuptools.noarch
easy_install  Flask
yum install -y postgresql-devel*
yum install python-dev*
tar xvf psycopg2_2.6.2.orig.tar.gz
cd psycopg2-2.6.2
python setup.py install

--start service
/usr/local/openresty/nginx/sbin/nginx
python app.py &
