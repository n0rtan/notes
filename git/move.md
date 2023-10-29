# Mirror repo
* git clone --mirror <old_repo>.git <new_repo>_mirror
* cd <new_repo>_mirror
* git remote set-url --push origin <new_repo>.git

#### Sync data
* git fetch -p origin
* git push --mirror

#### Example:

```
git clone --mirror ssh://git@old.host.com/sites/yii.git yii_mirror
git remote set-url --push origin ssh://git@new.host.com/sites/yii.git
git remote set-url origin ssh://git@new.host.com/sites/yii.git
```



# Links
* https://docs.github.com/en/repositories/creating-and-managing-repositories/duplicating-a-repository