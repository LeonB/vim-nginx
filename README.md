# Vim Nginx Syntax Highlighting

Extraction of the Nginx Vim syntax files from http://hg.nginx.org/nginx/.

## How this repository is created

``` shell
git init
git remote add nginx git@github.com:nginx/nginx.git
git pull -u nginx master
git filter-branch --subdirectory-filter contrib/vim HEAD -- --all
git reset --hard
git gc
git prune
```

## Updating

``` shell
git checkout -b rebase
git fetch nginx master
git reset --hard nginx/master
git filter-branch -f --subdirectory-filter contrib/vim HEAD -- --all
git checkout master
git merge rebase
git branch -D rebase
```

## License

Same terms as [Nginx itself](http://nginx.org/LICENSE).
