# Instalasi-HA-Cluster-Tomcat
High Availability merupakan topik penting saat ini, karena matinya layanan aplikasi ataupun web dalam beberapa detik akan menjadi masalah besar. Mengantisipasi berhentinya layanan akan sangat membantu tersedianya layanan. 
Dengan PACEMAKER stack kita dapat mengkonfigurasi HA-cluster  untuk application server maupun web server yang ada.
Pacemaker adalah cluster resource manager. Pacemaker yang akan mengelola semua cluster services (resources) 
dan  menggunakan kemampuan messaging serta membership yang menjadi dasar cluster engine menggunakan Corosync. 
Resources memiliki resource agent, yang merupakan external program dalam hal ini TOMCAT yang merupakan abstraksi dari service aslinya tomcat.
Pada active-passive cluster, semua services berjalan pada system utama. Jika system utama mati, 
semua service akan diarahkan ke backup system. Dengan demikian proses maintenance system utama tidak mengganggu layanan yang ada.
Pada tutorial ini, kita akan belajar bagaimana membangun high availability TOMCAT active-passive cluster. 
Tomcat cluster menggunakan virtual IP dan  secara automatis melakukan fail over jika system yang gagal berjalan.
User akan mengakses aplikasi web melali virtual IP, yang dikelola  Pacemaker. 
Tomcat service dan virtual IP selalu berada pada host yang sama. 
Ketika host ini gagal, akan dimigrasi ke host kedua dan user tidak akan melihat adanya kegagalan. 
(Disadur dan dimodifikasi dari: 
https://www.digitalocean.com/community/tutorials/how-to-set-up-an-apache-active-passive-cluster-using-pacemaker-on-centos-7#step-9-%E2%80%94-configuring-colocation-constraints)

