# ircd-ratbox 3.0.10 (Updated)

IRC daemon for the Gh0stNet network.

## Changes from stock 3.0.10

### OpenSSL 3.x compatibility + TLS hardening (`libratbox/src/openssl.c`)

- **OpenSSL 3.x API updates** — replaced removed functions: `SSLv23_server_method()` → `TLS_server_method()`, `TLSv1_client_method()` → `TLS_client_method()`, `RAND_pseudo_bytes()` → `RAND_bytes()`, `SSLeay_version()` → `OpenSSL_version()`
- **Guarded legacy init calls** — `SSL_load_error_strings()` / `SSL_library_init()` wrapped for OpenSSL < 1.1.0 only
- **Enforced TLS 1.2 minimum** — disabled SSLv3, TLS 1.0, TLS 1.1
- **Stronger cipher suite** — `ECDHE+AESGCM:ECDHE+CHACHA20:DHE+AESGCM:DHE+CHACHA20:HIGH:!aNULL:!MD5:!RC4:!3DES`
- **OpenSSL 3.x ECDH auto curve selection**

No other code changes were made.

## Building

```bash
./configure --prefix=/path/to/install
make
make install
```

## Contact

Visit **irc.twistednet.org** — channels **#dev** and **#twisted** for help, questions, or to say hi.

Maintained by **gh0st**.

## Original

Based on ircd-ratbox 3.0.10 by the ircd-ratbox development team.
