---
warning: DO NOT CHANGE THIS MANUALLY, THIS IS GENERATED BY https://github/duckdb/community-extensions repository, check README there
title: gsheets
excerpt: |
  DuckDB Community Extensions
  Read and write Google Sheets using SQL

extension:
  name: gsheets
  description: Read and write Google Sheets using SQL
  version: 0.0.1
  language: C++
  build: cmake
  license: MIT
  excluded_platforms: "windows_amd64_rtools;wasm_mvp;wasm_eh;wasm_threads"
  maintainers:
    - archiewood

repo:
  github: evidence-dev/duckdb_gsheets
  ref: 7f7c6e2f85edd9ad9c2f16f2075818627fca8405

docs:
  hello_world: |
    -- Authenticate with Google Account in the browser (easiest)
    CREATE SECRET (TYPE gsheet, PROVIDER oauth);
    
    -- OR create a secret with your Google API access token (boring, see extension docs)
    CREATE SECRET (TYPE gsheet, TOKEN '<your_token>');
    
    -- Read a spreadsheet by full URL
    FROM read_gsheet('https://docs.google.com/spreadsheets/d/11QdEasMWbETbFVxry-SsD8jVcdYIT1zBQszcF84MdE8/edit');
    
    -- Read a spreadsheet by full URL, implicitly
    FROM 'https://docs.google.com/spreadsheets/d/11QdEasMWbETbFVxry-SsD8jVcdYIT1zBQszcF84MdE8/edit';
    
    -- Read a spreadsheet by spreadsheet id
    FROM read_gsheet('11QdEasMWbETbFVxry-SsD8jVcdYIT1zBQszcF84MdE8');
    
    -- Read a spreadsheet with no header row
    SELECT * FROM read_gsheet('11QdEasMWbETbFVxry-SsD8jVcdYIT1zBQszcF84MdE8', headers=false);
    
    -- Read a sheet other than the first sheet using the sheet name
    SELECT * FROM read_gsheet('11QdEasMWbETbFVxry-SsD8jVcdYIT1zBQszcF84MdE8', sheet='Sheet2');
    
    -- Read a sheet other than the first sheet using the sheet id in the URL
    SELECT * FROM read_gsheet('https://docs.google.com/spreadsheets/d/11QdEasMWbETbFVxry-SsD8jVcdYIT1zBQszcF84MdE8/edit?gid=644613997#gid=644613997');
    
    -- Write a spreadsheet from a table by spreadsheet id
    COPY <table_name> TO '11QdEasMWbETbFVxry-SsD8jVcdYIT1zBQszcF84MdE8' (FORMAT gsheet);
    
    -- Write a spreadsheet from a table by full URL
    COPY <table_name> TO 'https://docs.google.com/spreadsheets/d/11QdEasMWbETbFVxry-SsD8jVcdYIT1zBQszcF84MdE8/edit?usp=sharing' (FORMAT gsheet);
    
    -- Write a spreadsheet to a specific sheet using the sheet id in the URL
    COPY <table_name> TO 'https://docs.google.com/spreadsheets/d/11QdEasMWbETbFVxry-SsD8jVcdYIT1zBQszcF84MdE8/edit?gid=1295634987#gid=1295634987' (FORMAT gsheet);
  
  extended_description: |
    The DuckDB GSheets Extension allows reading and writing of data in Google Sheets from DuckDB.
    For detailed setup and usage instructions, visit the docs at [duckdb-gsheets.com](https://duckdb-gsheets.com).

extension_star_count: 21
extension_star_count_pretty: 21
extension_download_count: 23
extension_download_count_pretty: 23
image: '/images/community_extensions/social_preview/preview_community_extension_gsheets.png'
layout: community_extension_doc
---

### Installing and Loading
```sql
INSTALL {{ page.extension.name }} FROM community;
LOAD {{ page.extension.name }};
```

{% if page.docs.hello_world %}
### Example
```sql
{{ page.docs.hello_world }}```
{% endif %}

{% if page.docs.extended_description %}
### About {{ page.extension.name }}
{{ page.docs.extended_description }}
{% endif %}

### Added Functions

<div class="extension_functions_table"></div>

| function_name | function_type | description | comment | example |
|---------------|---------------|-------------|---------|---------|
| read_gsheet   | table         |             |         |         |



---
