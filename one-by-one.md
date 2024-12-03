# Tutorial 

## Add Remote  

- SOURCE CONTROL > Remote > Add Remote  

```bash
git remote  
git checkout devkimchi
```

## Bootstrapper  

```bash
pwd
# Confirm that we are in `/workspaces/codespaces-scp-2024`
hugo new site . --force
```

## Submodule

```bash
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```

### Playground

```bash
git submodule deinit -f themes/ananke
rm -rf .git/modules/themes/ananke
git rm -f themes/ananke
git submodule add --depth 1 https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```

## Check folder tree

```bash
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
