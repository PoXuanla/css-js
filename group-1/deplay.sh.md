# deplay.sh

```sh
npm run build 

cd dist

git init
git add .
git commit -m "deploy"
git push -f https://github.com/PoXuanla/my-vue-app main:gh-pages

cd - 
```
