# get mysql enum values

sql

```sql

/* get enum values from column of table */
SHOW COLUMNS FROM integration_authentication WHERE Field =  'type';

SELECT COLUMN_TYPE AS anyAliasName
FROM INFORMATION_SCHEMA.COLUMNS
WHERE TABLE_SCHEMA = 'freighttracker_teamcontainers' AND TABLE_NAME = 'integration_authentication' AND COLUMN_NAME = 'type';

DESC `freighttracker_teamcontainers` `type`;
```
php
```php
function get_enum_values( $table, $field )
{
    $type = $this->db->query( "SHOW COLUMNS FROM {$table} WHERE Field = '{$field}'" )->row( 0 )->Type;
    preg_match("/^enum\(\'(.*)\'\)$/", $type, $matches);
    $enum = explode("','", $matches[1]);
    return $enum;
}
```
