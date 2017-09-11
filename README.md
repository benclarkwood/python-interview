# Server Gen Library

This toy library creates fictitious "servers" in a convenient manner for managing a fleet of role-specific hosts.

## API

To use the library:
```
import server

new = server.new_instance(role, existing_hosts=None, attributes=None)
```

Where:
 - `role` is a string (e.g. `"web"`)
 - `existing_hosts` is a list of all existing instances (values returned by
   `new_instance()`) of all roles.
 - `attributes` is a list of attributes (strings) to describe the instances.
   attributes have the form type:value, e.g. "color:red".

 `new_instance` returns one value with the structure:
 ```
{
    "host_name": str
    "attributes": [...]
}
 ```

 Where `host_name` will have the form `<role>-<#>.domain.com`.

 Note that `#` will be the lowest unused integer within the role.

## But...
The current implementation has a few bugs. There's a minimal set of tests that demonstrate 2 of the N bugs. Finding additional bugs will probably require writing additional tests!
