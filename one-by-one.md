# Tutorial 

## Wait for proper hands-on  

```bash
/workspaces/ddd-seoul-2024 (playground) $ hugo version
hugo v0.139.3-2f6864387cd31b975914e8373d4bf38bddbd47bc+extended linux/amd64 BuildDate=2024-11-29T15:36:56Z VendorInfo=gohugoio
```

## Install Linter

- markdownlint

![image](https://github.com/user-attachments/assets/a3147e27-e21d-47c9-a711-aafe50cbbc87)

## Add Remote  

```bash
git remote
# origin  
git checkout playground
# Already on 'playground'
# Your branch is up to date with 'origin/playground'.
```

- SOURCE CONTROL > Remote > Add Remote  
  - Add Remote from GitHub > Allow (The extension 'GitHub' wants to sign in using GitHub.)  
- SOURCE CONTROL > Remote > Add Remote > Select <USERNAME>   
  - <USERNAME>.github.io  
  - Type `blog`    

![image](https://github.com/user-attachments/assets/7bfb42c8-5376-4735-9a9a-3ae2fa3682be)


```bash
git remote
# remote  
# origin
```

## Bootstrapper  

```bash
pwd
# Confirm that we are in `/workspaces/ddd-seoul-2024`
mkdir srcs && cd srcs
hugo new site . 
```

## Import theme as Submodule

```bash
pwd
# Confirm that we are in `/workspaces/ddd-seoul-2024/srcs`  
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```

### Playground

```bash
pwd
# Confirm that we are in `/workspaces/ddd-seoul-2024/srcs`
git submodule deinit -f themes/ananke
rm -rf .git/modules/themes/ananke
git rm -f themes/ananke
git submodule add --depth 1 --force https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```

## Check folder tree

```bash
pwd
# Confirm that we are in `/workspaces/ddd-seoul-2024/srcs`
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
├── README.md
├── static
└── themes
    └── ananke
```  

## Edit `hugo.toml`  

```bash  
pwd
# Confirm that we are in `/workspaces/ddd-seoul-2024/srcs`
echo "theme = 'ananke'" >> hugo.toml
```

```yaml
baseURL = 'https://<USERNAME>.github.io/'  
languageCode = 'ko-kr'  
title = '<TYPE WHAT YOU WANT>'  
theme = 'ananke'  
```

## HELLO WORLD  

```
hugo server
# Stop with Ctrl+C
hugo new content content/posts/my-first-post.md
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
