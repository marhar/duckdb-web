---
layout: community_extension_doc
title: quack
excerpt: |
  DuckDB Community Extensions
  Provides a hello world example demo

extension:
  name: quack
  description: Provides a hello world example demo
  version: 0.0.1
  language: C++
  build: cmake
  license: MIT
  maintainers:
    - hannes

  # (Optional) param that specifies required extra toolchains
  requires_toolchains: "rust"
  # (Optional) param that specifies a precise vcpkg commit to use
  vcpkg_commit: "a1a1cbc975abf909a6c8985a6a2b8fe20bbd9bd6"
  # (Optional) this extension requires additional custom toolchain setup
  custom_toolchain_script: true

repo:
  github: duckdb/extension-template
  ref: f89d2663d9788dc27f3a77bcdf638ace6357a459

docs:
  hello_world: |
    SELECT quack('world');
  extended_description: |
    The quack extension is based on DuckDB's [Extension Template](https://github.com/duckdb/extension_template/), and it's a great starting point to get started building more advanced extensions.

extension_star_count: 132

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

|     function_name     | function_type | description | comment | example |
|-----------------------|---------------|-------------|---------|---------|
| quack                 | scalar        |             |         |         |
| quack_openssl_version | scalar        |             |         |         |



---
