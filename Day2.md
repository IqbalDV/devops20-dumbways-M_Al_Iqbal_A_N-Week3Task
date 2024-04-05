# Task
1. Jelaskan apa itu Web server dan gambarkan bagaimana cara webserver bekerja.
2. Buatlah Reverse Proxy untuk aplilkasi yang sudah kalian deploy kemarin. (wayshub), untuk domain nya sesuaikan nama masing" ex: alvin.xyz .
3. Jelaskan apa itu load balance.
4. implementasikan loadbalancing kepada aplikasi wayshub yang telah kalian gunakan.

# Webserver
Web Server: software yang memberikan layanan berupa data. Berfungsi untuk menerima permintaan HTTP atau HTTPS dari client yang direspon dengan halaman web.

Client -request-> web server -> Database server
Client <-web page- web server <- Database server

terdapat 3 fungsi utama
  - Memberi Cache
  - Security
  - Memberikan data kepada client
# Buatlah Reverse Proxy untuk aplilkasi yang sudah kalian deploy kemarin. (wayshub), untuk domain nya sesuaikan nama masing" ex: alvin.xyz 
server {
      server_name iqbal.xyz;

      location / {
               proxy_pass http://http://192.168.1.139:3000;
      }
}
# Jelaskan apa itu load balance
Load Balance adalah Metode mendistribusikan beban server agar seimbang dan tidak overload dengan membagikan beban ke beberapa server.

# Implementasikan Loadbalancing kepada aplikasi wayshub yang telah kalian gunakan

scriptnya:

Upstream LoadBalance { 
    server 192.168.1.139:3000;
    server 192.168.1.144:3000;
}
server {
      server_name iqbal.xyz;

      location / {
               proxy_pass http://LoadBalance;
      }
}
