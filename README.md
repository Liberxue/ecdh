yum -y install gcc gcc-c++

g++ -std=c++11 -fPIC -c -o ecdh.o ecdh.cpp -I./
ar cr libecdh.a ecdh.o
g++ -std=c++11 -shared -fPIC -o libecdh_x64.so -Wl,--whole-archive libecdh.a libssl.a libcrypto.a -Wl,--no-whole-archive

Linux��OpenSSL��̬����뼰ʹ��
https://www.linuxidc.com/Linux/2017-09/147117.htm

�Ȱ�װperl
yum install perl
yum install cpan

��

wget http://www.cpan.org/src/5.0/perl-5.26.2.tar.gz
tar -xzf perl-5.26.2.tar.gz
cd perl-5.26.2
./Configure -des -Dprefix=$HOME/localperl
make
make test
make install

wget https://www.openssl.org/source/old/1.0.2/openssl-1.0.2k.tar.gz
tar zxf openssl-1.0.2k.tar.gz
cd openssl-1.0.2k
./config -fPIC no-shared
make

���У�-fPIC��ָʾ����λ���޹صĴ��룬���ѡ�����ڰ�openssl���ɵľ�̬�����ӵ���̬���ʱ����ʾ������ӵģ�no-shared��ָʾ���ɾ�̬�⡣
�����ڵ�ǰĿ¼�»�����libssl.a��libcrypto.a�������ļ����ڿ�����ʱ��ֻ��Ҫ����ͷ����������������Ϳ����ˡ�