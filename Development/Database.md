# Database

Currently, the database includes the `jieba` segmentation extension for Chinese word segmentation and full-text search. To add other extensions, please refer to the `zbook_database/zbook_database.Dockerfile` file. Additionally, the data is imported into the `ip2geo` geographic table, which currently includes city names only for English and Simplified Chinese.

If you have a `GeoLite2-City.mmdb` data file, you can import the data into the psql database using the following command:

```bash
make mmdb2psql
```

To add support for new languages, you can modify the corresponding data tables in `zbook_backend/db/migration` and update the conversion commands in `zbook_backend/cmd/mmdb2psql/main.go`.