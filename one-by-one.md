# Tutorial 

## Add Remote  

- SOURCE CONTROL > Remote > Add Remote  

```bash
git remote  
git checkout playground
```

## Bootstrapper  

```bash
pwd
# Confirm that we are in `/workspaces/codespaces-scp-2024`
mkdir srcs && cd srcs
hugo new site . 
```

## Submodule

```bash
pwd
# Confirm that we are in `/workspaces/codespaces-scp-2024/srcs`  
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```

### Playground

```bash
pwd
# Confirm that we are in `/workspaces/codespaces-scp-2024/srcs`
git submodule deinit -f themes/ananke
rm -rf .git/modules/themes/ananke
git rm -f themes/ananke
git submodule add --depth 1 https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```

## Check folder tree

```bash
pwd
# Confirm that we are in `/workspaces/codespaces-scp-2024/srcs`
tree -L 2
.
├── archetypes
│   └── default.md
├── assets
├── content
├── data
├── hugo.toml
├── i18n
├── layouts
├── one-by-one.md
├── README.md
├── static
└── themes
    └── ananke
```  

```bash  
pwd
# Confirm that we are in `/workspaces/codespaces-scp-2024/srcs`
echo "theme = 'ananke'" >> hugo.toml  
hugo server  
```  

## Chores  

### Stackoverflow  

- <https://stackoverflow.com/a/26752628>  

- Original  

```bash  
mv subfolder subfolder_tmp  
git submodule deinit subfolder  
git rm --cached subfolder  
mv subfolder_tmp subfolder  
git add subfolder  
```  

- Derived  

```bash  
mv themes/ananke/ themes/bianchi
git submodule deinit themes/ananke
git rm --cached themes/ananke
rm -rf themes/ananke  
mv themes/bianchi/ themes/ananke/
```  

### diff

```bash
tree resources
# resources
# └── _gen
#     └── assets
#         └── ananke
#             └── css
#                 ├── main.css_9d7c906d8fe82fddbbd923faebb24419.content
#                 └── main.css_9d7c906d8fe82fddbbd923faebb24419.json
```

```html
<link rel="stylesheet" href="/ananke/css/main.min.d05fb5f317fcf33b3a52936399bdf6f47dc776516e1692e412ec7d76f4a5faa2.css" >
```
