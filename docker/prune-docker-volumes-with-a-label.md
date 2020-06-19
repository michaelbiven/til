# Prune docker volumes with a label

By adding a lablel to any volume that you do not want pruned (e.g. `dont_auto_prune`) you can exclude it from `docker system prune` with the `--filter` option. Create an alias with the `--filter` option set to skip any volume wit the `dont_auto_prune` label.

```
alias docker-prune="docker system prune && \
                    docker volume prune --filter 'label!=dont_auto_prune'"
```

h/t [Thomas Klausner](https://domm.plix.at/perl/2020_06_docker_prune_volumes_by_label.html)
