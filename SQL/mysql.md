## 参考
1. https://github.com/dfeich/org-babel-examples/blob/master/tables/tables.org
2. https://github.com/tbanel/orgtbljoin
3. https://github.com/fosskers/org-table-color
4. https://github.com/tbanel/orgaggregate
5. https://github.com/jplindstrom/emacs-org-transform-tree-table

## 基础

```markdown
#+name: my-query
#+header: :engine mysql
#+header: :dbhost 127.0.0.1
#+header: :dbport 3307
#+header: :dbuser root
#+header: :dbpassword (getenv "MYSQL_PASSWORD")
#+header: :database company :eval yes
#+begin_src sql
SET NAMES utf8mb4;
use company;
SELECT * FROM departments;
#+end_src

#+results: my-query
| id | department_name | created_at          | updated_at          |
|----+-----------------+---------------------+---------------------|
|  1 | 销售部           | 2023-08-15 19:48:38 | 2023-08-15 20:00:45 |
|  2 | 市场部           | 2023-08-15 19:48:55 | 2023-08-15 19:48:55 |
```
