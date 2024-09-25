# Protection

When Alice and Bob do it in public, they want to use protection.


## How to use protection

### Generate GPG key
```shell
gpg --full-generate-key
```

⚠️  **Use passphrase**
⚠️  Recommended to use ECC over RSA

### Export public key
```shell
gpg --list-keys
gpg --export --armor KEYID > out.asc
```

### Import key
```shell
gpg --import key.asc
```

### Verify key
```shell
gpg --fingerprint KEYID
gpg --sign-key KEYID
```


## Encrypt / Decrypt

```shell
echo TEXT | gpg --encrypt --armor -r user@email
gpg --output OUTPUT_FILE.gpg --encrypt --recipient user@email INPUT_FILE
```

## Decrypt
```shell
gpg --decrypt FILE
```


- - -

Now Alice cansafely publish her public key anywhere.
Bob will import it and use to sign messages for Alice.
Protection par excellence 👌️

> Bruce Schneier believes safewords are fundamentally insecure and recommends that you ask your partner to stop via public key signature.
[source](https://www.explainxkcd.com/wiki/index.php/1039:_RuBisCO) 
