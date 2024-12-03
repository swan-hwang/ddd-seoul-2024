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
git submodule add --depth 1 --force https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
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

## Post  

```bash
    1  hugo version
    2  git remote
    3  git checkout remote
    4  git checkout remote/gh-pages
    5  git status
    6  ll
    7  git remote origin/main
    8  git checkout origin/main
    9  git branch
   10  git checkout playground
   11  pwd
   12  mkdir srcs && cd srcs
   13  hugo new site .
   14  pwd
   15  git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
   16  rm -rf .git/modules/themes/ananke
   17  git rm -f themes/ananke
   18  git submodule add --depth 1 https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
   19  git submodule deinit -f themes/ananke
   20  git submodule add --depth 1 https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke --force
   21  tree -L 2
   22  git submodule add --depth 1 https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
   23  git submodule add --depth 1 --force  https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
   24  pwd
   25  echo "theme = 'ananke'" >> hugo.toml
   26  hugo server
   27  hugo new content content/posts/my-first-post.md
   28  hugo server
   29  history
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
