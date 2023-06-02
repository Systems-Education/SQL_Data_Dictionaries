SELECT
  c.table_name as "Таблица",
  t.table_comment as "Комментарий к таблице",
  c.ordinal_position as "№ п.п",
  c.column_name as "Поле",
  c.column_comment as "Комментарий к полю",
  c.column_type as "Тип",
  CASE WHEN c.column_key = 'PRI' THEN 'PK' END as "Ключ",
  c.is_nullable as "NULL"
FROM
  information_schema.columns c
  JOIN information_schema.tables t ON c.table_name = t.table_name
  AND c.table_schema = t.table_schema
WHERE
  t.table_type = 'BASE TABLE'
  AND t.table_schema = '<имя схемы, если надо>'
ORDER BY
  c.table_name,
  c.ordinal_position;
