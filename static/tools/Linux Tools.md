### 🐧 Protocols & Linux Tools

|   # | Tool            | Common use case                                                         | Command example                             |
| --: | --------------- | ----------------------------------------------------------------------- | ------------------------------------------- |
|   1 | `ssh`           | Connect to your VPS / production server                                 | `ssh ubuntu@your-server-ip`                 |
|   2 | `nginx`         | Serve static files, HTTPS, proxy Node.js app from port `3000` to domain | `sudo systemctl restart nginx`              |
|   3 | `curl`          | Test REST APIs, health checks, webhooks                                 | `curl http://localhost:3000/api/health`     |
|   4 | `nmap`          | Check whether ports `22`, `80`, `443`, `3000` are open                  | `nmap your-domain.com`                      |
|   5 | `dig`           | Debug domain issues, inspect `A`, `CNAME`, `MX` records                 | `dig example.com`                           |
|   6 | `chmod`         | Make a script executable                                                | `chmod +x deploy.sh`                        |
|   7 | `chown`         | Fix permission errors after deploy                                      | `sudo chown -R ubuntu:ubuntu /var/www/app`  |
|   8 | `openssl`       | Create private keys, inspect TLS cert expiration                        | `openssl x509 -in cert.pem -text`           |
|   9 | `host`          | Quick domain → IP lookup                                                | `host google.com`                           |
|  10 | `route`         | Debug why traffic is not reaching gateway                               | `route -n`                                  |
|  11 | `apache`        | Host PHP sites, static websites, reverse proxy apps                     | `sudo systemctl status apache2`             |
|  12 | `sudo`          | Install packages, restart services                                      | `sudo apt install nginx`                    |
|  13 | `systemctl`     | Restart backend service after deployment                                | `sudo systemctl restart myapp`              |
|  14 | `htop`          | Find which process is eating RAM / CPU                                  | `htop`                                      |
|  15 | `du`            | Find huge folders in server                                             | `du -sh /var/log/*`                         |
|  16 | `df`            | Check if server disk is full                                            | `df -h`                                     |
|  17 | `wget`          | Download binaries, backups, releases                                    | `wget https://example.com/app.tar.gz`       |
|  18 | `ping`          | Check if server/domain is alive                                         | `ping google.com`                           |
|  19 | `telnet`        | Test whether a port is open                                             | `telnet example.com 443`                    |
|  20 | `traceroute`    | Diagnose slow routing path                                              | `traceroute google.com`                     |
|  21 | `tracepath`     | Same routing diagnostics on limited systems                             | `tracepath google.com`                      |
|  22 | `netstat`       | Check what app is bound to `3000`                                       | `netstat -tuln`                             |
|  23 | `nslookup`      | Verify DNS propagation                                                  | `nslookup example.com`                      |
|  24 | `ifconfig`      | Check local IP address / interfaces                                     | `ifconfig`                                  |
|  25 | `whois`         | Inspect domain registrar, expiry date                                   | `whois example.com`                         |
|  26 | `whoami`        | Confirm current shell user                                              | `whoami`                                    |
|  27 | `netcat` (`nc`) | Test ports, send raw HTTP, create listeners                             | `nc -zv localhost 3000`                     |
|  28 | `rsync`         | Deploy project files to server                                          | `rsync -av ./dist user@server:/var/www/app` |
|  29 | `lsof`          | Find process using port `3000`                                          | `lsof -i :3000`                             |
|  30 | `tcpdump`       | Debug incoming requests, DNS issues                                     | `sudo tcpdump -i any port 443`              |
|  31 | `ngrok`         | Test webhooks from Stripe / Telegram / GitHub                           | `ngrok http 3000`                           |
|  32 | `scp`           | Upload `.env`, backups, builds                                          | `scp .env user@server:/var/www/app`         |