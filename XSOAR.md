https://knowledgebase.paloaltonetworks.com/KCSArticleDetail?id=kA10g000000PPsBCAW

https://docs-cortex.paloaltonetworks.com/r/Cortex-XSOAR/6.6/Cortex-XSOAR-Administrator-Guide/Configure-the-Server-Log

### Debugging XSOAR containers

To access the docker/podman containers of the XSOAR change default shell of demisto user from /bin/false

### Installer flags 

Here is the formatted text in Markdown:

```
## Flags that follow the -- separator

| Flag | Type | Description |
| --- | --- | --- |
| -C | N/A | (CentOS) Tells yum to run entirely from system cache, and does not download or update any headers unless it has to perform the requested action. |
| -backup | Boolean | Whether to back up server data when upgrading the Cortex XSOAR server. Default is true. |
| -backup-tenants | Boolean | Whether to back up server data for tenants when upgrading the Cortex XSOAR server. Default is true. |
| -conffile | String | The server .conf file. The default location is /etc/demisto.conf. |
| -data-dir | String | Used to provide a custom installation path, different from the default /var/lib/demisto directory. Example: sudo ./demisto.sh -- -data-dir /xsoar. |
| -demisto-no-gpg-check | N/A | Tells yum to disable the GPG signature when checking for the Cortex XSOAR RPM. |
| -distro | String | Forces the Linux distro (such as CentOS, Debian, or Debian New). |
| -do-not-start-server | N/A | Prevents starting the server when the installation or upgrade is complete. |
| -dr | N/A | Sets up the disaster recovery server. |
| -elasticsearch-url | String | Elasticsearch URL addresses (comma-separated). For example, http://test1:9200,http://test2:9200 |
| -elasticsearch-api-key | String | The Elasticsearch API key, which should be used in licensed versions. |
| -elasticsearch-username | String | The Elasticsearch username. |
| -elasticsearch-password | String | The Elasticsearch password. |
| -elasticsearch-proxy | Boolean | Whether to use a proxy when communicating with Elasticsearch. Can be true or false. Default is false. |
| -elasticsearch-insecure | Boolean | Whether to trust any certificate when communicating with Elasticsearch. Can be true or false. Default is false. |
| -elasticsearch-timeout | Integer | The amount of time (in seconds) before Elasticsearch times out. Default is 20 seconds. |
| -elasticsearch-prefix | String | Defines the unique prefix a Cortex XSOAR server uses when naming the Elasticsearch indices it creates. |
| -external-address | String | The external address of the instance during installation. |
| -h | N/A | Displays installation help. |
| -index-entries | Boolean | Whether to index entries. |
| -otc | String | The one-time configuration file. The default location is /var/lib/demisto/otc.conf.json. |
| -prev-uninstall-script | String | The path for the uninstall script. The default location is /var/lib/dpkg/info/demistoserver.postrm. |
| -purge | N/A | Removes the existing Cortex XSOAR installation. |
| -restore-entries | Boolean | Restores the entries index. If false, it prevents restoring the entries index. The default is true. |
| -system-user-name= | String | When installing the Server you can now select the default Cortex XSOAR user name. |
| -temp-folder | String | Replaces the temp folder (located in /var/lib/demisto/temp) with temp-folder at installation. Useful when you cannot access the temp folder due to permission or storage issues. |
| -tools | Boolean | Installs the required tools. The default is true. |
| -use-prev-uninstall-script | N/A | (For Cortex XSOAR upgrades) The script that deletes the Cortex XSOAR user and group is not run. |
| -y | N/A | Answer all installer questions with y/yes, including the Cortex XSOAR EULA. |

## Flags that precede and include the -- separator

Use the following flags to get help or information about the ./demistoserver-6.X-XXXXX.sh file.

| Flag | Description |
| --- | --- |
| --help | Prints a message. |
| --info | Prints embedded information, including title, default target directory, or embedded script. |
| --lsm | Prints an embedded LSM entry, if one exists. |
| --list | Prints a list of files located in the archive. |
| --check | Checks the integrity of the archive. |

Use the following flags to run the ./demistoserver-6.X-XXXXX.sh file.

| Flag | Description |
| --- | --- |
| --confirm | Prompts you to confirm before running an embedded script. |
| --quiet | Prints only error messages. |
| --accept | Accepts the Cortex XSOAR license. |
| --noexec | Embedded scripts are not run. |
| --keep | The target directory is not deleted after running an embedded script. |
| --noprogress | Progress is hidden during decompression. |
| --nox11 | An xterm is not spawned. |
| --nochown | Extracted files are not given to users. |
| --nodiskspace | Disk space is not checked for available space. |
| --target dir | Extracts directly to an absolute or relative target directory. |
| --tar arg1[arg2...] | Accesses the archive contents. |
```
