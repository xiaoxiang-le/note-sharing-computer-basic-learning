## 基本查询语句

SQL（结构化查询语言）中最基本、最常用的查询语句是 `SELECT`，用于从数据库中检索数据。其基本结构如下：
```sql
SELECT 列1, 列2, ...
FROM 表名
WHERE 条件;

```
### 各关键字含义：

- **`SELECT`**：指定要查询的列（可以用 `*` 代表所有列）。
    
- **`FROM`**：指定要查询的表名。

- **`WHERE`**：在 **分组之前** 过滤行，不能使用聚合函数（如 `SUM`、`COUNT`、`AVG` 等）。
    
- **`HAVING`**：在 **分组之后** 过滤分组，可以使用聚合函数。

### 示例：

```sql
-- 查询所有列
SELECT * FROM 员工;
-- 查询指定列，并添加条件
SELECT 姓名, 工资
FROM 员工
WHERE 部门 = '销售';
```

### 其他常用扩展：

- **`ORDER BY`**：排序（`ASC` 升序/`DESC` 降序）。
    
- **`GROUP BY`**：分组聚合（常配合 `COUNT`、`SUM`、`AVG` 等函数）。
    
- **`LIMIT`**（MySQL） / `TOP`（SQL Server） / `ROWNUM`（Oracle）：限制返回行数。
    
- **`DISTINCT`**：去重。
    

#### 带排序和限制的例子：

```sql
SELECT 姓名, 工资
FROM 员工
WHERE 部门 = '销售'
ORDER BY 工资 DESC
LIMIT 5;   -- 仅返回前5条
```

