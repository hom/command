# date

 以给定的格式显示当前时间或者设置系统时间

## 用法

> `date [选项]... [+格式]`  

或者  

> `date [-u|--utc|--universal] [MMDDhhmm[[CC]YY][.ss]]`  

## 参数

### 命令参数

- `-d`, `--date=STRING`         display time described by STRING, not 'now'
- `-f`, `--file=DATEFILE`       like --date once for each line of DATEFILE
- `-I[TIMESPEC]`, `--iso-8601[=TIMESPEC]`  output date/time in ISO 8601 format.
                            TIMESPEC='date' for date only (the default),
                            'hours', 'minutes', 'seconds', or 'ns' for date
                            and time to the indicated precision.
- `-r`, `--reference=`文件  显示文件指定文件的最后修改时间  
- `-R`, `--rfc-2822`  以RFC 2822格式输出日期和时间  
 例如：2006年8月7日，星期一 12:34:56 -0600  
  `--rfc-3339=TIMESPEC`   output date and time in RFC 3339 format.
                            TIMESPEC='date', 'seconds', or 'ns' for
                            date and time to the indicated precision.
                            Date and time components are separated by
                            a single space: 2006-08-07 12:34:56-06:00
- `-s`, `--set=STRING`  set time described by STRING
- `-u`, `--utc`, `--universal`    print or set Coordinated Universal Time (UTC)
- `--help`  显示此帮助信息并退出
- `--version`  显示版本信息并退出

### 输出格式

> `+[format]`

- `%%` 一个文字的 %
- `%a` 当前locale 的星期名缩写(例如： 日，代表星期日)
- `%A` 当前locale 的星期名全称 (如：星期日)
- `%b` 当前locale 的月名缩写 (如：一，代表一月)
- `%B` 当前locale 的月名全称 (如：一月)
- `%c` 当前locale 的日期和时间 (如：2005年3月3日 星期四 23:05:25)
- `%C` 世纪；比如 %Y，通常为省略当前年份的后两位数字(例如：20)
- `%d` 按月计的日期(例如：01)
- `%D` 按月计的日期；等于%m/%d/%y
- `%e` 按月计的日期，添加空格，等于%_d
- `%F` 完整日期格式，等价于 %Y-%m-%d
- `%g` ISO-8601 格式年份的最后两位 (参见%G)
- `%G` ISO-8601 格式年份 (参见%V)，一般只和 %V 结合使用
- `%h` 等于%b
- `%H` 小时(00-23)
- `%I` 小时(00-12)
- `%j` 按年计的日期(001-366)
- `%k`   hour, space padded ( 0..23); same as %_H
- `%l`   hour, space padded ( 1..12); same as %_I
- `%m`   month (01..12)
- `%M`   minute (00..59)
- `%n` 换行
- `%N` 纳秒(000000000-999999999)
- `%p` 当前locale 下的"上午"或者"下午"，未知时输出为空
- `%P` 与%p 类似，但是输出小写字母
- `%r` 当前locale 下的 12 小时时钟时间 (如：11:11:04 下午)
- `%R` 24 小时时间的时和分，等价于 %H:%M
- `%s` 自UTC 时间 1970-01-01 00:00:00 以来所经过的秒数
- `%S` 秒(00-60)
- `%t` 输出制表符 Tab
- `%T` 时间，等于%H:%M:%S
- `%u` 星期，1 代表星期一
- `%U` 一年中的第几周，以周日为每星期第一天(00-53)
- `%V` ISO-8601 格式规范下的一年中第几周，以周一为每星期第一天(01-53)
- `%w` 一星期中的第几日(0-6)，0 代表周一
- `%W` 一年中的第几周，以周一为每星期第一天(00-53)
- `%x` 当前locale 下的日期描述 (如：12/31/99)
- `%X` 当前locale 下的时间描述 (如：23:13:48)
- `%y` 年份最后两位数位 (00-99)
- `%Y` 年份
- `%z +hhmm`  数字时区(例如，-0400)
- `%:z +hh:mm`  数字时区(例如，-04:00)
- `%::z +hh:mm:ss` 数字时区(例如，-04:00:00)
- `%:::z`  数字时区带有必要的精度 (例如，-04，+05:30)
- `%Z`  按字母表排序的时区缩写 (例如，EDT)

默认情况下，日期的数字区域以0 填充。
The following optional flags may follow '%':

- `-`  (hyphen) do not pad the field
- `_`  (underscore) pad with spaces
- `0`  (zero) pad with zeros
- `^`  use upper case if possible
- `#`  use opposite case if possible

在任何标记之后还允许一个可选的域宽度指定，它是一个十进制数字。
作为一个可选的修饰声明，它可以是E，在可能的情况下使用本地环境关联的
表示方式；或者是O，在可能的情况下使用本地环境关联的数字符号。

Examples:  
Convert seconds since the epoch (1970-01-01 UTC) to a date

```bash
date --date='@2147483647'
```

Show the time on the west coast of the US (use tzselect(1) to find TZ)

```bash
TZ='America/Los_Angeles' date
```

Show the local time for 9AM next Friday on the west coast of the US

```bash
date --date='TZ="America/Los_Angeles" 09:00 next Fri'
```

GNU coreutils online help: <http://www.gnu.org/software/coreutils/>
请向<http://translationproject.org/team/zh_CN.html> 报告date 的翻译错误
要获取完整文档，请运行：info coreutils 'date invocation'
