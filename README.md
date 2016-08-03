# linguaPdoTools
List only translated Resources in the current Language within Lingua with pdoTools - snippets

### Requirements
- pdoTools and Lingua has to be installed

### Installation

- Install linguaPdoTools from package-management
- Update pdoTools-systemsetting pdoFetch.class to 'linguapdotools.linguafetch'
- Update pdoTools-systemsetting pdofetch_class_path to '{core_path}components/linguapdotools/model/'

### Setup Instructions

- Create listbox-TV 'lang_published'
  - Input-Option-Values: no==no||yes==1
  - Default Value: no
  - Add this TV to translated Lingua-TVS
  - Now you can use pdoTools-snippets with:
  
  ```
  &includeTVs=`lang_published`
  &where=`{"TVlang_published.value":"1"}`  
  ```
  
### Usage with Archivist

```
[[!pdoResources? 
&includeTVs=`lang_published`
&where=`{"TVlang_published.value":"1"}`
&parents=`0`
&tpl=`@INLINE [[+id]]`
&outputSeparator=`,`
&toPlaceholder=`translated_ids`
]]
 
debug the output: [[+translated_ids]]
 
[[!Archivist? 
&parents=`0,0` 
&target=`[[*id]]`
&where=`{"id:IN":[ [[+translated_ids]] ]}`
]]
```

```
[[!getArchives?
&parents=`123`
&tpl=`YourTemplateName`
&grSnippet=`pdoResources`
&includeTVs=`lang_published`
&where=`{"TVlang_published.value":"1"}` 
]]
```

