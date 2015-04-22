# linguaPdoTools
List only translated Resources in the current Language within Lingua with pdoTools - snippets

### Requirements
- pdoTools and Lingua has to be installed

### Installation

- Install linguaPdoTools from package-management
- Create a file core/model/modx/pdotools/linguafetch.class.php with this content:

```
<?php
require MODX_CORE_PATH . 'components/linguapdotools/model/linguapdotools/linguafetch.class.php';
```

- Update pdoTools-systemsetting pdoFetch.class to 'pdotools.linguafetch'

### Setup Instructions

- Create listbox-TV 'lang_published'
  - Input-Option-Values: no==no||yes==1
  - Default Value: no
  - Add this TV to translated Lingua-TVS
  - No you can use pdoTools-snippets with:
  
  ```
  &includeTVs=`lang_published`
  &where=`{"TVlang_published.value":"1"}`  
  ```

