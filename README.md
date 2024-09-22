<h1 align="center"> t3ern



![image](https://raw.githubusercontent.com/t3rn/t3rn/refs/heads/development/specification/assets/t3rn_Logo_Black.png)

# t3rn



### Yönetici Dosyasını İndirin ve Çıkartın

```
wget https://github.com/t3rn/executor-release/releases/download/v0.21.1/executor-linux-v0.21.1.tar.gz
tar -xvf executor-linux-v0.21.1.tar.gz
```
```
cd executor/executor/bin
chmod +x executor
```
### Değişkenlerini Yapılandırın
```
export NODE_ENV=testnet
```
### Günlük ayarlarınızı yapın
```
export LOG_LEVEL=debug
export LOG_PRETTY=false
```
### Yöneticinin kullanacağınız cüzdanın özel anahtarını ayarlayın. 
### your_private_key_here yerine kullanacağınız cüzdan anahtarınızı yazın.
```
export PRIVATE_KEY_LOCAL=your_private_key_here
```
### Kullanacağınız ağları ekleyin
```
export ENABLED_NETWORKS='arbitrum-sepolia,base-sepolia,optimism-sepolia,l1rn'
```
### Servis oluşturalım
```
nano /etc/systemd/system/executor.service
```
```
[Unit]
Description=Executor Service
After=network.target

[Service]
Type=simple
User=root
WorkingDirectory=/root/executor/executor/bin/
Environment="NODE_ENV=testnet"
Environment="LOG_LEVEL=debug"
Environment="LOG_PRETTY=false"
Environment="PRIVATE_KEY_LOCAL=private-yaz"
Environment="ENABLED_NETWORKS=arbitrum-sepolia,base-sepolia,optimism-sepolia,l1rn"
ExecStart=/root/executor/executor/bin/executor
Restart=always

[Install]
WantedBy=multi-user.target
EOF
```
```
sudo systemctl daemon-reload
sudo systemctl enable executor.service
sudo systemctl start executor.service
```
### Logları başlatalım
```
sudo journalctl -u executor.service -f
```

### Testnet üzerinde işlem siparişlerine teklif vermek için BRN jetonları gereklidir. Testnet BRN jetonlarını faucetten alın
```
https://faucet.t3rn.io/
```












