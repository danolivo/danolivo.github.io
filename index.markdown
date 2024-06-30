---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
Ph.D, senior software developer, open-source enthusiast  
Former mechanical engineer (high-enthalpy aka 'hypersonic' flows).

*e-mail*: lepihov(at)gmail(dot)com  
*telegram*: [@danolivo](t.me/danolivo)  

# Links
- [Facebook](https://www.facebook.com/avlepikhov/)
- [Github](https://github.com/danolivo)
- [Linkedin](https://www.linkedin.com/in/avlepikhov/)
- [Medium](https://medium.com/@andreylepikhov)
- [Twitter](https://twitter.com/avlepikhov)
- [VKontakte](https://vk.com/id5294240)

# Talks

## 2024
- pg_index_stats - an extension for managing extended statistics automatically. FOSSASIA'2024 (PGDay section). April 8-10 2024, Hanoi, Vietnam.
[[schedule](https://eventyay.com/e/55d2a466/session/9083)][[presentation](https://github.com/danolivo/conf/blob/main/2024-FossAsia/pg_index_stats.pdf)]

## 2023
- Query plan freezing extension: design, issues and lessons learned. Israeli PostgreSQL Jam'2023.
[[schedule](https://pgday.org.il)][[presentation](https://github.com/danolivo/conf/blob/main/2023-PGDay-Israel/sr-plan.pdf)]

- Real-time Query Replanning of Hopeless Queries. PGConf.SPB'2023.
[[schedule](https://pgconf.ru/en/talk/1589471)] [[presentation](https://github.com/danolivo/conf/blob/main/2023-PGConf-spb/PGConf-Spb-2023.pdf)]

# Projects
## Multimaster
This project is dedicated to inventing built-in HA based on PostgreSQL. It may be installed on different servers, leveraging global transaction ID and logical replication. From the application standpoint, all servers contain equivalent data up to MVCC with automatic conflict resolution. Some trade-offs exist: transactions by default have a REPEATABLE READ isolation level, and DML performance reduces with the increase in the number of instances. Distance between servers depends only on network speed and internal heartbeat timeout.
The project has an open-source [GitHub](https://github.com/postgrespro/mmts) version and integrated into the [Postgres Professional Enterprise](https://postgrespro.com/docs/enterprise/16/multimaster) database system.
