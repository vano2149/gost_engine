# gost_engine
Settings OpenSSL GOST for Ubuntu 18.04 / 20.04

## Step 1. Istall !
1. Install Gost package encryption! `sudo apt install libengine-gost-openssl1.1`

## Step 2. Modified config in an openssl.cnf file!
2. `sudo nano /enc/ssl/openssl.cnf`

## Step 3. Changes at the biginning of the file!
3. 
    ```
    openssl_conf = openssl_def
    ```

## Step 4. Changes to the end of the file!
4. 
    ```
    [openssl_def]
    engines = engine_section

    [engine_section]
    gost = gost_section

    [gost_section]
    engine_id = gost
    dynamic_path = /usr/lib/x86_64-linux-gnu/engines-1.1/gost.so
    default_algorithms = ALL
    CRYPT_PARAMS = id-Gost28147-89-CryptoPro-A-ParamSet
    ```
## Step 5. dynamic_path location!
---
5. You can find the location of the dynamic_path parameter using the command!

```shell
sudo find / -name "gost.so"
```
---

## Step 6. Checking the correct settings!

6. To check the correctness of the settings, you can use command

```shell
openssl ciphers | tr ':' '\n' | grep GOST
```
Example of the correct answer!
```shell
> GOST2012-GOST8912-GOST8912  
> GOST2001-GOST89-GOST89
```
