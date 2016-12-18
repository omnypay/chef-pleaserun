pleaserun Cookbook
==================
A library cookbook to help interact with pleaserun.

Requirements
------------

Shouldn't require anything special.


Attributes
----------

* `node['pleaserun']['platform']` - which platform to use.  e.g. 'upstart', 'runit', 'sysv'

TODO: List you cookbook attributes here.

Usage
-----
#### pleaserun::default

Just include `pleaserun` in your node's `run_list`:

```json
{
  "name":"my_node",
  "run_list": [
    "recipe[pleaserun]"
  ]
}
```

#### lwrp


```
include_recipe 'pleaserun::default'

pleaserun 'test' do
  name        'test'
  program     '/bin/echo'
  args        [ 'hello', 'world' ]
  description 'test app'
  action      :create
end
```

##### Resource Attriubtes

* `name` - The name of the program / service
  * Type String
  * Is the name_attribute of the Resource
* `user` - The user to use for executing this program
  * Type: String
  * Default: nil
* `group` - The group to use for executing this program
  * Type: String
  * Default: nil
* `description` - The group to use for executing this program
  * Type: String
  * Default: nil
* `umask` - The umask to apply to this program
  * Type: String
  * Default: nil
* `runas` - 
  * Type: String
  * Default: nil
* `chroot` - The directory to chroot to
  * Type: String
  * Default: nil
* `chdir` - The directory to chdir to before running
  * Type: String
  * Default: nil
* `nice` - The nice level to add to this program before running
  * Type: String
  * Default: nil
* `prestart` - A command to execute before starting and restarting. A failure of this command will cause the start/restart to abort. This is useful for health checks, config tests, or similar operations
  * Type: String
  * Default: nil
* `program` - The program to execute. This can be a full path, like /usr/bin/cat, or a shorter name like 'cat' if you wish to search $PATH.
  * Type: String
  * Default: true
* `args` - The arguments to pass to the program
  * Type: Array
  * Default: ['']
* `platform` - Which platform to use.  e.g. 'upstart', 'runit', 'sysv'
  * Type: String
  * Default: node['pleaserun']['platform']
* `target_version`
  * Type: String
  * Default: node['pleaserun']['target_version']
* `limit_coredump` - Largest size (in blocks) of a core file that can be created. (setrlimit RLIMIT_CORE)
  * Type: String
  * Default: nil
* `limit_cputime` - Maximum amount of cpu time (in seconds) a program may use. (setrlimit RLIMIT_CPU)
  * Type: String
  * Default: nil
* `limit_data` - Maximum data segment size (setrlimit RLIMIT_DATA)
  * Type: String
  * Default: nil
* `limit_file_size` - Maximum size (in blocks) of a file receiving writes (setrlimit RLIMIT_FSIZE)
  * Type: String
  * Default: nil
* `limit_locked_memory` - Maximum amount of memory (in bytes) lockable with mlock(2) (setrlimit RLIMIT_MEMLOCK)
  * Type: String
  * Default: nil
* `limit_open_files` - Maximum number of open files, sockets, etc. (setrlimit RLIMIT_NOFILE)
  * Type: String
  * Default: nil
* `limit_user_processes` - Maximum number of running processes (or threads!) for this user id. Not recommended because this setting applies to the user, not the process group. (setrlimit RLIMIT_NPROC)
  * Type: String
  * Default: nil
* `limit_physical_memory` - Maximum resident set size (in bytes); the amount of physical memory used by a process. (setrlimit RLIMIT_RSS)"
  * Type: String
  * Default: nil
* `limit_stack_size` - Maximum size (in bytes) of a stack segment (setrlimit RLIMIT_STACK)
  * Type: String
  * Default: nil

Contributing
------------

e.g.
1. Fork the repository on Github
2. Create a named feature branch (like `add_component_x`)
3. Write your change
4. Write tests for your change (if applicable)
5. Run the tests, ensuring they all pass
6. Submit a Pull Request using Github

License and Authors
-------------------
Authors: 

* Paul Czarkowski ( username.taken@gmail.com)

License:

Apache2 blurb goes here.
