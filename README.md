# postgres-with-decoderbufs
支持decoderbufs逻辑订阅logical

## 编译
```shell
docker build -t postgres-with-decoderbufs .
```

## vi postgresql.conf
``` text
wal_level = logical
max_wal_senders = 4
wal_keep_segments = 64
max_replication_slots = 4
shared_preload_libraries = 'decoderbufs'
```

## vi pg_hba.conf
``` text
host replication all all trust
```
