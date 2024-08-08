https://knowledgebase.paloaltonetworks.com/KCSArticleDetail?id=kA10g000000PPsBCAW

https://docs-cortex.paloaltonetworks.com/r/Cortex-XSOAR/6.6/Cortex-XSOAR-Administrator-Guide/Configure-the-Server-Log

### Debugging XSOAR containers

To access the docker/podman containers of the XSOAR change default shell of demisto user from /bin/false

### Setting up engines

engine config can be found at `/usr/local/demisto/<engine-name>/d1.conf`

part of config
```
{
        "AgentURLs": null,
        "ArtifactsFolder": "",
        "BindAddress": ":0",
        "EngineID": "46317e6c-a478-4da4-861e-87014ae1b7db",
        "EngineURLs": [
                "wss://xsoar-dev:44333/acc_integration-development/d1ws"
        ],
        "InstallLogFile": "/tmp/d1_demolab-developer/demisto_install.log",
        "LogFile": "/var/log/demisto/d1_demolab-developer/d1.log",
        "LogLevel": "info",
```

`xsoar-dev` is a machine hostname engine expects. I have had no success putting IP in the hostname's place, instead modify `/etc/hosts` to whatever IP is required. 

### Installer flags 
version 6.12

Here is the formatted text in Markdown:


#### Flags that follow the `--` separator

| Flag | Description |
| --- | --- |
| -C | (For CentOS) Tells yum to run entirely from system cache - does not download or update any headers unless it has to to perform the requested action. |
| -add-system-user | Add the os user running the server (default true) |
| -backup | Backup server data on upgrade (default true) |
| -backup-tenants | For backup on upgrade on multi-tenant - also backup tenants data (default true) |
| -cluster-address string | App server address to be used for in cluster communication |
| -conffile string | Server conf file (default "/etc/demisto.conf") |
| -container-engine string | Force the type of container engine to use (docker or podman) |
| -data-dir string | Data directory path (default "/var/lib/demisto") |
| -db-address string | Remote database address, you can enter the hostname or IP |
| -db-any-certificate | Trust any certificate when communicating with database (default true) |
| -db-conn-port string | Remote database secure connection port (default: 50001) |
| -db-node | DB Node installer - for internal use only |
| -db-only | Setup Demisto database server only (when using remote database) (defualt: false) |
| -db-port string | Remote database port (default: 443) |
| -db-secret string | Remote database secret |
| -db-use-proxy | Use proxy when communicating with database |
| -demisto-no-gpg-check | Tells yum to disable gpg signature checking for demisto rpm |
| -distro string | Force linux distro. (such as centos, debian, debianNew...) |
| -do-not-start-server | Do not start the server at the end of the installation/upgrade |
| -dr | Setup DR server |
| -elasticsearch-api-key string | ElasticSearch API key. if set, overrides username and password |
| -elasticsearch-insecure | Trust any certificate when communicating with ElasticSearch |
| -elasticsearch-master-prefix string | Master elastic prefix - for internal use only |
| -elasticsearch-password string | ElasticSearch password to establish connection |
| -elasticsearch-prefix string | ElasticSearch index names prefix |
| -elasticsearch-proxy | Use proxy when communicating with ElasticSearch |
| -elasticsearch-timeout int | ElasticSearch default timeout (default 90) |
| -elasticsearch-url string | ElasticSearch host address in format https://localhost:9200. if empty will not establish connection to ElasticSearch |
| -elasticsearch-username string | ElasticSearch username to establish connection |
| -external-address string | External address - to set the external address of the instance during installation |
| -git | Install required git (default true) |
| -h | Show help |
| -ha | Install high-availability app server |
| -host | Host installer - for internal use only |
| -hosted | Set to true for hosted environments |
| -hosting-secret string | Set the secret for hosted environments |
| -index-entries | Set to false to not index entries |
| -multi-tenant | Setup multi-tenant server |
| -otc string | One time conf file (default "/var/lib/demisto/otc.conf.json") |
| -overwrite-elastic-config | Overwrite Elasticsearch configuration during upgrade |
| -prev-uninstall-script string | Path to post uninstall script (default: /var/lib/dpkg/info/demistoserver.postrm ) (default "/var/lib/dpkg/info/demistoserver.postrm") |
| -purge | Remove existing installation |
| -purge-mount | Remove existing mounted installation, must come with purge |
| -restore-entries | Set to false to not restore entries index (default true) |
| -server-only | Setup Demisto server only (when using remote database) |
| -system-group-name string | The os group name running the server (default "demisto") |
| -system-user-name string | The os user name running the server (default "demisto") |
| -temp-folder string | Temp folder for that the product will use - should be local and not shared |
| -tools | Install required tools (default true) |
| -use-prev-uninstall-script | Would not run the script which deletes Demisto user and group (on upgrade) |
| -y | Answer all questions with y/yes, unless there is an error (will accept Palo Alto Networks Cortex XSOAR EULA) |

#### Flags that precede and include the -- separator

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

