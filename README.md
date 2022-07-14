# gost_engine
Settings OpenSSL GOST for Ubuntu 18.04 / 20.04

## Step 1. Istall !
1. Install Gost package encryption! `sudo apt install libengine-gost-openssl1.1`

## Step 2. Modified config in an openssl.cnf file!
2. `sudo nano /enc/ssl/openssl.cnf`

## Step 3. Changes at the biginning of the file!
3. 
    ```
    openaal_conf = openssl_def
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
    CRYPT_PARAMS = id-Gost28147-89-CriptoPro-A-ParamSet
    ```
