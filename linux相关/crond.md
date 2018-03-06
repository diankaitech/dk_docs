#查看当前用户的cron配置，使用 crontab -l
#编辑当前用户的cron配置，使用 crontab -e
#删除当前用户的cron配置，使用 crontab -r
#以root身份查看/编辑/删除某用户的cron配置，在命令后加上 -u USERNAME
#配置系统级的任务，编辑 /etc/crontab 文件
#举例
以下是cron语句中的字段与字段说明：

字段	说明
1	分钟（0-59）
2	小时（2-24）
3	日期（1-31）
4	月份（1-12；或英文缩写Jan、Feb等）
5	周几（0-6，0为周日；或单词缩写Sun、Mon等）
6	用户名（执行命令时以此用户的身份）
7	要执行的命令（路径）
现在来看第一行：

12 3 * * * root tar czf /usr/local/backups/daily/etc.tar.gz /etc >> /dev/null 2>&1
这条语句将在每天的凌晨3点12分（03:12）运行 tar czf /usr/local/backups/daily/etc.tar.gz /etc 命令。>> /dev/null 2>&1
表示把所有标准输出发送到 /dev/null（linux的回收站），把标准错误输出（2）发送到和标准输出（1）同样的地方（即 /dev/null）。
运行这行命令将不会产生任何输出。
