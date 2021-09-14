# ansible-oauth2-proxy
An ansible role to install [oauth2 proxy](https://github.com/bitly/oauth2_proxy)

Variables
---------

```yaml
oaut2_proxy_http                         : "https://github.com/oauth2-proxy/oauth2-proxy/releases/download/v7.1.3/oauth2-proxy-v7.1.3.linux-amd64.tar.gz"
oaut2_proxy_http_sha256                  : "a491ca18059848c356935fe2ca9e665faafe4bba3ee1ecbac5a5f5f193195a82"
oauth2_user                              : "oauth2"
oauth2_dir                               : "/var/oauth2_proxy"
oauth2_dir_tmp                           : "/var/oauth2_proxy/tmp"
oauth2_dir_log                           : "/var/log/oauth2-proxy/"
oauth2_config_path                       : "/var/oauth2_proxy/oauth2_config.cfg"
oauth2_compress_filename                 : "{{ oaut2_proxy_http | basename }}"
oauth2_filename                          : "{{ oauth2_compress_filename |replace('.tar.gz', '') }}"

# See for all options https://raw.githubusercontent.com/bitly/oauth2_proxy/master/contrib/oauth2_proxy.cfg.example
oauth2_proxy_config                      :
    http_address                         : "127.0.0.1:5000"
    upstreams                            : [ "127.0.0.1:6060" ]
    provider                             : "github"
    email-domain                         : "*"
    cookie-secure                        : false
    cookie-domain                        : "localhost:5000"
    cookie_secret                        : "COOK_SECRET"
    client_id                            : "YOUR_CLIENT_ID"
    client_secret                        : "CLIENT_SECERET"

oauth2_config_cmdline_args               : "--github-org='MYCoolORg'"
```


License
--------
MIT
