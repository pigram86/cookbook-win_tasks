Description
===========

TODO: Enter the cookbook description here.

Supported Platforms
===================


Cookbooks
=========

* windows

Attributes
==========
default.rb
----------
*default['task']['path'] = "c:\\chef"
*default['task']['user'] = "domain\\username"
*default['task']['pwd'] = "<password>"

* I create a new <domain>.rb for each domain

Recipes
=======
default.rb
----------
*windows_task 'Chef client' do
*  user node['task']['user']
*  password node['task']['pwd']
*  cwd 'C:\chef\bin'
*  command 'chef-client -L C:\tmp'
*  run_level :highest
*  frequency :minute
*  frequency_modifier 15
*end

* I create a <domain>_task.rb for each domain


Usage
=====

### win_tasks::default

Include `win_tasks` in your node's `run_list`:

```json
{
  "run_list": [
    "recipe[win_tasks::default]"
  ]
}
```

Contributing
============

1. Fork the repository on Github
2. Create a named feature branch (i.e. `add-new-recipe`)
3. Write your change
4. Write tests for your change (if applicable)
5. Run the tests, ensuring they all pass
6. Submit a Pull Request

License and Authors
===================

Author:: Todd Pigram (<todd@toddpigram.com>)

Copyright:: 2013-2015, Todd Pigram

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
