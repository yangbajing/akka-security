RS256 使用 RSA 算法进行签名，可通过如下命令生成 RSA 密钥：

### 1. 生成 2048 位（不是 256 位）的 RSA 密钥
```
openssl genrsa -out rsa-private-key.pem 2048
```

### 2. 通过密钥生成公钥
```
openssl rsa -in rsa-private-key.pem -pubout -out rsa-public-key.pem
```

ES256 使用 ECDSA 算法进行签名，该算法使用 ECC 密钥，生成命令如下：

### 1. 生成 ec 算法的私钥，使用 prime256v1 算法，密钥长度 256 位。（强度大于 2048 位的 RSA 密钥）
```
openssl ecparam -genkey -name prime256v1 -out ecc-private-key.pem
```

### 2. 通过密钥生成公钥
```
openssl ec -in ecc-private-key.pem -pubout -out ecc-public-key.pem
```
