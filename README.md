# Telegraf GeoIP plugin role for Ansible

## Variables

```yaml
telegraf_geoip:
  config: geoip.conf.j2
  db_version: 2021.08.07 # latest if not specified
```

`db_version` key have to refer to release tag from https://github.com/P3TERX/GeoLite.mmdb/releases

Plugin config have to contain path to DB:
```toml
[[processors.geoip]]
db_path = "{{ telegraf_geoip_db_path }}"
```

Other plugin configuration options described here: https://github.com/a-bali/telegraf-geoip#configuration

Plugin loaded with such Telegraf block:
```toml
[[processors.execd]]
command = {{ telegraf_geoip_command }}
```
