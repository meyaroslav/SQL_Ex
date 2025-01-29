# SQL_Ex

Вопросы по экзамену SQL.

## Contents

1. [Chapter I](#chapter-i)
2. [Chapter II](#chapter-ii)

# Chapter I

1. Что такое атрибуты в ER-модели? — Характеристики сущности
2. Какой из языков использовался для описания логических моделей данных? — SQL
3. Какое понятие описывает связь между двумя сущностями в логической модели данных? — Внешний ключ
4. Что представляет собой первичная нормальная форма 1NF в реляционном дизайне баз данных? — Все значения атрибутов в таблице уникальны 
5. Что такое первичный ключ в физической модели данных? — Уникальный идентификатор записи в таблице
6. Что если CHECK CONSTRAINTS не пройдет при вставке данных? — Операция будет отклонена
7. Какая команда используется для создания CHECK CONSTRAINTS? — `ALTER TABLE`
8. Какая команда используется для создания FOREIGN KEY? — `ADD CONSTRAINT`
9. Какая команда поможет создать составной индекс? — `CREATE INDEX composite_index ON table_name`
10. Какое действие выполняет команда COMMIT? — Подтягивает все изменения, сделанные в текущей транзакции 
11. Что такое реляционная база данных? — Структура, основанная на связях между таблицами
12. Какую из этих баз данных можно отнести к нереляционным? — MongoDB
13. Какая служба управляет доступом к данным в реляционной базе данных? — SQL Server
14. Что означает аббревиатура CAP в контексте CAP-теоремы? — Consistency Availability Partition tolerance
15. Какой принцип ACID гарантирует, что если транзакция прошла успешно, изменения будут сохранены даже в случае сбоя системы? — Атомарность

# Chapter II

1. Какое значение будет возвращено? — `'e'`

```sql
SELECT CASE WHEN NULL=5 THEN 'A'
            WHEN NULL <>5 THEN 'B'
                ELSE 'e'
            END AS result;
```

2. Какое значение будет возвращено? — Синтаксическая ошибка

```sql
SELECT sum(t.1 value)
      FROM(SELECT NULL INTEGER AS value) AS t1;
```

3. Какое значение будет возвращено? — Ни одной строки

```sql
SELECT 1+1 AS value
      WHERE 1=1 AND 2=1;
```

4. Какое значение будет возвращено? — 2

```sql
SELECT COUNT(*)
      FROM Student AS s
    WHERE EXISTS(SELECT NULL FROM Hobby AS h WHERE h.stud_id=s.id LIMIT 1);
```

5. Какое значение будет возвращено? — Синтаксическая ошибка

```sql
SELECT COUNT(*)
      FROM Student AS s
    WHERE id IN(SELECT * FROM Hobby);
```

6. Какое значение будет возвращено? — 123

```sql
SELECT reg_num
      FROM Student ORDER BY reg_num NULLS LAST LIMIT 1;
```
