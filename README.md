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
### Yöneticiyi Başlatın
```
./executor
```
### Testnet üzerinde işlem siparişlerine teklif vermek için BRN jetonları gereklidir. Testnet BRN jetonlarını faucetten alın
```
https://faucet.t3rn.io/
```












