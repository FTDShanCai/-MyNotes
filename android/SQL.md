### DISTINCT 筛选单列中不同的值
必须为单列  SELECT DISTINCT user_info.sex FROM user_info  

### LIMIT 过滤
SELECT * FROM user_info  LIMIT 5  取前5条数据
SELECT * FROM user_info  LIMIT 5，5  从第6个开始，取前5条数据

### ORDER BY 排序
SELECT * FROM user_info ORDER BY user_info.cardid 

SELECT * FROM user_info ORDER BY user_info.cardid, user_info.id 多行排序 cardid 相同的时候按照，id进行排序

### DESC 降序
SELECT * FROM user_info ORDER BY user_info.username DESC

### ASC 升序(默认升序)
SELECT * FROM user_info ORDER BY user_info.username ASC
