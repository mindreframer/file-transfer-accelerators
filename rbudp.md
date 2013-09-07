#### RBUDP
http://www.evl.uic.edu/cavern/RBUDP/Reliable%20Blast%20UDP.html




•Sender:
  tar cf - /vagrant/doc | sendstream 176.9.111.198 600m 1460
•Receiver
  recvstream 176.9.111.198 1460 | tar xvpf -


##### Installation
wget http://www.evl.uic.edu/cavern/RBUDP/Reliable%20Blast%20UDP_files/RBUDP-v1.tar.gz
tar xvfz RBUDP-v1.tar.gz
cd RBUDP
make


mkdir bin
mv recvfile bin/
mv recvfilelist bin/
mv recvstream bin/
mv sendfile bin/
mv sendfilelist bin/
mv sendstream bin/
mv urecv bin/
mv usend bin/
mv bin/* /usr/local/bin
cd ..
rm -rf RBUDP*


#####
cat /dev/urandom > rand.bin


cat rand.bin | sendstream 176.9.111.198 600m 1460
recvstream 176.9.111.198 1460 | echo - > rand.bin