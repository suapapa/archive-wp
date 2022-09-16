# Resouces to resotre Suapapa's blog

This repository has Wordpress backup of Suapapa's blog
which is on-lined from 2008 to 2013.

Now all contents (without comment) are migrated to
[Homin Lee's Blog](https://homin.dev/blog)

## Image restore

- 452objects, 37M

## Fix content links in WP exported xml

Convert upload links to `https://homin.dev/asset/suapapa-blog/wp-content_uploads`:
- http://web.suapapa.net:8080/wordpress/wp-content/uploads
- http://www.suapapa.net/wordpress/wp-content/uploads
- /wordpress/wp-content/uploads
- wp-content/uploads

Convert wordpress address to `https://homin.dev/wp`
- http://web.suapapa.net:8080/wordpress
- http://www.suapapa.net/wordpress

Convert site address to `https://homin.dev`
- http://web.suapapa.net:8080
- http://www.suapapa.net


## TODO

- [x] Import old posts to [Homin Lee's Blog](https://homin.dev/blog)
- [x] Export Wordpress to Hugo
- [x] Remove Blogger blog
- [x] Test wordpress with docker composer in local machine
- [x] Make cache server for GCS bucket
- [x] Move contents to GCS bucket

## Reference

- [WordPress to Hugo Exporter](https://github.com/SchumacherFM/wordpress-to-hugo-exporter)
- [Original address](http://web.suapapa.net:8080/wordpress)
- [suapapa's blog](http://suapapas-blog.blogspot.com/)
- [Suapapa's blog setting](https://www.blogger.com/blog/settings/6032755754556829594)

### Mysql backup

```bash
$ docker compose up
$ docker exec -it wordpress-db-1 /bin/sh
```
```
# mysqldump --add-drop-table -u wordpress -p wordpress > /var/lib/mysql/suapapasblog.sql
```
```bash
$ cp ~/.local/share/docker/volumes/wordpress_db_data/_data/suapapasblog.sql ~/ws/suapapa-blog/

```

### Docker reference

- wordpress_db_data path : `~/.local/share/docker/volumes/wordpress_db_data`
