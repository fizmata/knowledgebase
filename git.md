## Git Submodules

submodules will get stuck if they're configured to use ssh and you don't have ssh configured or it can't be used. In that case:

1. Edit your .gitmodules file to use the HTTPS URL.

1. Run git submodule sync to reflect the change to your .git/config file.

1. Run the update command again.

1. Commit and push the changes in your .gitmodules file.

Example .gitmodules file:
```
[submodule "vendor/engines/fat_free_crm"]
path = vendor/engines/fat_free_crm
url = https://github.com/fatfreecrm/fat_free_crm.git
```
