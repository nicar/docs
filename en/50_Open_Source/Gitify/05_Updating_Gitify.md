If you followed the procedure to install Gitify from Git, updating Gitify to a newer version is as simple as pulling in the recent changes. 

Just pull in the latest changes, rerun composer in case anything changed with regards to the dependencies, and off you go.

````
cd /path/to/Gitify/
git pull
composer install
````

## Dealing with breaking changes

Especially in early releases, it's not uncommon for breaking changes to occur. These changes might be related to how the files get written - or read - and can break your workflow. Any potentially breaking changes are tagged with `[BC]` in [the changelog](https://github.com/modmore/Gitify/blob/master/CHANGELOG.md).

The easiest way to deal with changes like this is to make sure that, before updating, there are no differences between your data files and the database. So extract or build before updating.

After the update, extract again so files are written anew and are compatible with whatever changed in the new release. Otherwise you may not be able to build later.

Remember to update all your Gitify installs (local, staging and production) as close to each other as possible to be safe from changes between versions. It's also possible to install Gitify into your project files (as git submodule - tho we might add it to composer later), so you have a copy of Gitify local to the project, but then you lose the ability to run it anywhere.