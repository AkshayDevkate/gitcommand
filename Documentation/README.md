

Add .ignore file 

Open terminal and navigate to SWORDS-UP 

Cd SWORDS-UP 



Copy and paste the following command 
 find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch



Find and list files  .env, .idea, .DS_Store .

```
 find . -name .DS_Store -print0 | xargs -0 git rm -r -f --ignore-unmatch
```


```
echo .DS_Store >> .gitignore  
echo .env >> .gitignore  
echo .idea >> .gitignore 
```
    
```
git add .gitignore   
git commit -m"remove .DS_Store"  
Git push   
```


