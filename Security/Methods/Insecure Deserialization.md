- Serialization:
    - How data in a programming language is converted into a database-compatible format (easier to transport over network)
- Deserialization: database -> object

## PHP
```php
<?php
class User{
    public $username;
    public $isadmin;
}
$user = new User;
$user->username = 'test'
$user->status = 'no';
echo serialize($user); # the fn that serializes the data to be transferred over network

unserialize(serialize($user)) # unserializes the data
?>
```

- Serialized types:
    - `b: boolean`
    - `i: integer`
    - `d: float`
    - `s: string` REQUIRES A LENGTH: `s:ln_str:"str"`
    - `a: array` REQUIRES A LENGTH: `a:num_elements":{elements}`
    - `0: class name` REQUIRES PROPERTIES `0:length_name:"name":num_properties:{properties}`
- result:
    - `0:4:"User":2:{s:8:"username";s:4:"test";s:7:"isadmin";s:2:"no";}`
- When serialized strings are unserialized, PHP makes a copy of the original object that was serialized
    - Thus, one can occasionally pass in a custom object and serialize it
    - For instance, `__wakeup()` is a magic called when an object is constructed, which `unserealize()` does

