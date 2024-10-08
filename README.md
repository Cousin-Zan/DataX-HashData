![Datax-logo](https://github.com/alibaba/DataX/blob/master/images/DataX-logo.jpg)



# DataX

DataX 是阿里巴巴集团内被广泛使用的离线数据同步工具/平台，实现包括 MySQL、Oracle、SqlServer、Postgre、HDFS、Hive、ADS、HBase、TableStore(OTS)、MaxCompute(ODPS)、DRDS 等各种异构数据源之间高效的数据同步功能。



# Features

DataX本身作为数据同步框架，将不同数据源的同步抽象为从源头数据源读取数据的Reader插件，以及向目标端写入数据的Writer插件，理论上DataX框架可以支持任意数据源类型的数据同步工作。同时DataX插件体系作为一套生态系统, 每接入一套新数据源该新加入的数据源即可实现和现有的数据源互通。



# DataX详细介绍

##### 请参考：[DataX-Introduction](https://github.com/alibaba/DataX/blob/master/introduction.md)



# Quick Start

##### Download [DataX下载地址](https://github.com/HashDataInc/DataX/releases/download/v1.0.0/datax-v1.0.0-hashdata.tar.gz)

##### 请点击：[Quick Start](https://github.com/alibaba/DataX/blob/master/userGuid.md)



# Support Data Channels 

DataX目前已经有了比较全面的插件体系，主流的RDBMS数据库、NOSQL、大数据计算系统都已经接入，目前支持数据如下图，详情请点击：[DataX数据源参考指南](https://github.com/alibaba/DataX/wiki/DataX-all-data-channels)

| 类型         | 数据源             | Reader(读) | Writer(写) |                                                                                           文档                                                                                           |
|------------|-----------------|:---------:|:---------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| RDBMS 关系型数据库 | MySQL           |     √     |     √     |           [读](https://github.com/alibaba/DataX/blob/master/mysqlreader/doc/mysqlreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/mysqlwriter/doc/mysqlwriter.md)           |
|             | Oracle          |     √     |     √     |         [读](https://github.com/alibaba/DataX/blob/master/oraclereader/doc/oraclereader.md) 、[写](https://github.com/alibaba/DataX/blob/master/oraclewriter/doc/oraclewriter.md)         |
|            | SQLServer       |     √     |     √     |   [读](https://github.com/alibaba/DataX/blob/master/sqlserverreader/doc/sqlserverreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/sqlserverwriter/doc/sqlserverwriter.md)   |
|            | PostgreSQL      |     √     |     √     | [读](https://github.com/alibaba/DataX/blob/master/postgresqlreader/doc/postgresqlreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/postgresqlwriter/doc/postgresqlwriter.md) |
|            | Greenplum      |          |     √     |  [写](gpdbwriter/doc/gpdbwriter.md) |
|            | DRDS            |     √     |     √     |             [读](https://github.com/alibaba/DataX/blob/master/drdsreader/doc/drdsreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/drdswriter/doc/drdswriter.md)             |
|            | 达梦              |     √     |     √     |                                                                                      [读]() 、[写]()                                                                                      |
|            | 通用RDBMS(支持所有关系型数据库) |     √     |     √     |                                                                                      [读]() 、[写]()                                                                                      |
| 阿里云数仓数据存储  | ODPS            |     √     |     √     |             [读](https://github.com/alibaba/DataX/blob/master/odpsreader/doc/odpsreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/odpswriter/doc/odpswriter.md)             |
|            | ADS             |           |     √     |                                                      [写](https://github.com/alibaba/DataX/blob/master/adswriter/doc/adswriter.md)                                                      |
|            | OSS             |     √     |     √     |               [读](https://github.com/alibaba/DataX/blob/master/ossreader/doc/ossreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/osswriter/doc/osswriter.md)               |
|            | OCS             |     √     |     √     |               [读](https://github.com/alibaba/DataX/blob/master/ocsreader/doc/ocsreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/ocswriter/doc/ocswriter.md)               |
| NoSQL数据存储  | OTS             |     √     |     √     |               [读](https://github.com/alibaba/DataX/blob/master/otsreader/doc/otsreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/otswriter/doc/otswriter.md)               |
|            | Hbase0.94       |     √     |     √     |   [读](https://github.com/alibaba/DataX/blob/master/hbase094xreader/doc/hbase094xreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/hbase094xwriter/doc/hbase094xwriter.md)   |
|            | Hbase1.1        |     √     |     √     |     [读](https://github.com/alibaba/DataX/blob/master/hbase11xreader/doc/hbase11xreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/hbase11xwriter/doc/hbase11xwriter.md)     |
|            | MongoDB         |     √     |     √     |           [读](https://github.com/alibaba/DataX/blob/master/mongoreader/doc/mongoreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/mongowriter/doc/mongowriter.md)           |
|            | Hive            |     √     |     √     |             [读](https://github.com/alibaba/DataX/blob/master/hdfsreader/doc/hdfsreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/hdfswriter/doc/hdfswriter.md)             |
| 无结构化数据存储   | TxtFile         |     √     |     √     |       [读](https://github.com/alibaba/DataX/blob/master/txtfilereader/doc/txtfilereader.md) 、[写](https://github.com/alibaba/DataX/blob/master/txtfilewriter/doc/txtfilewriter.md)       |
|            | FTP             |     √     |     √     |               [读](https://github.com/alibaba/DataX/blob/master/ftpreader/doc/ftpreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/ftpwriter/doc/ftpwriter.md)               |
|            | HDFS            |     √     |     √     |             [读](https://github.com/alibaba/DataX/blob/master/hdfsreader/doc/hdfsreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/hdfswriter/doc/hdfswriter.md)             |
|            | Elasticsearch   |           |     √     |                     [写](https://github.com/alibaba/DataX/blob/master/elasticsearchwriter/doc/elasticsearchwriter.md)                                            |
|  时序数据库     | InfluxDB v1     |    √      |           |                  [读](influxdbreader/doc/README.md)       
|       | InfluxDB v2     |    √      |           |                  [读](influxdb2httpreader/doc/README.md)     |

# 我要开发新的插件
请点击：[DataX插件开发宝典](xxx)

# 项目成员

核心Contributions:  光戈、一斅、祁然、云时

感谢天烬、巴真、静行对DataX做出的贡献。

# License

This software is free to use under the Apache License [Apache license](https://github.com/alibaba/DataX/blob/master/license.txt).

# 更新
根据 [@felix.wang](https://github.com/felix-thinkingdata) 的 PR[（https://github.com/alibaba/DataX/pull/584）](https://github.com/alibaba/DataX/pull/584)，在 HashData 版本的 DataX 上，更新了 hdfsreader 对于 parquet 文件读取的支持。
本次代码修改旨在验证利用 DataX 迁移腾讯云COS桶中的 parquet 文件数据至 Greenplum 数据库中

感谢[@felix.wang](https://github.com/felix-thinkingdata)作者提交的关于hdfs parquet文件格式支持的代码分支

感谢[@Tooi6](https://github.com/Tooi6)作者有关InfluxDB在DataX中的集成代码
