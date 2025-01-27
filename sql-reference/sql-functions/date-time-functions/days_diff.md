# days_diff.md

## 功能

计算开始时间和结束时间相差几天 （`expr1` - `expr2`），结果精确到天。

## 语法

```Haskell
BIGINT days_diff(DATETIME expr1,DATETIME expr2);
```

## 参数说明

`expr1`: 结束时间，支持的数据类型为 DATETIME。

`expr2`: 开始时间，支持的数据类型为 DATETIME。

## 返回值说明

返回值的数据类型为 BIGINT。如果日期不存在，则返回 NULL。如果相差不满一天，则返回 0。

## 示例

```Plain Text
select days_diff('2010-11-30 23:00:00', '2010-11-29 23:00:00')
+---------------------------------------------------------+
| days_diff('2010-11-30 23:00:00', '2010-11-29 23:00:00') |
+---------------------------------------------------------+
| 1                                                       |
+---------------------------------------------------------+

select days_diff('2010-11-30 23:00:00', '2010-11-29 23:10:00')
+---------------------------------------------------------+
| days_diff('2010-11-30 23:00:00', '2010-11-29 23:10:00') |
+---------------------------------------------------------+
| 0                                                       |
+---------------------------------------------------------+
```
