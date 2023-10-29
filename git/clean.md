## Remove remote merged branches

* git branch -r --merged | grep -v origin/HEAD | grep -v origin/master | cut -d/ -f2- | xargs -n 1 git push --delete origin
#### Experiments
```
git branch -r --no-merged | cut -d/ -f2- | xargs -n 1 git push origin 
for branch in $(git branch -r --no-merged master | cut -c 3-); do git push origin $branch; done
git branch -r --no-merged master | xargs -n 1 git push origin
```
## Check
* git branch -r --merged

## Start git gc
* git gc --aggressive









