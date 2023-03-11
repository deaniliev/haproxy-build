# haproxy-build
```
yum install -y rpm-build rpmdevtools pcre-devel openssl-devel zlib-devel redhat-rpm-config \
               gcc gcc-c++ make libstdc++-devel wget rpmlint vim rpmdev-setuptree \
               lua-devel systemd-devel systemd-devel pcre2-devel
cd ~
rm -rf rpmbuild
rpmdev-setuptree
git clone -b 2.6 https://github.com/deaniliev/haproxy-build.git
cp -a haproxy-build rpmbuild/SOURCES
mv rpmbuild/SOURCES/haproxy.spec rpmbuild/SPECS
spectool -R -g ~/rpmbuild/SPECS/haproxy.spec
rpmlint ~/rpmbuild/SPECS/haproxy.spec
rpmbuild -ba ~/rpmbuild/SPECS/haproxy.spec
yum install ~/rpmbuild/RPMS/x86_64/haproxy-2.6.9*.rpm
```
