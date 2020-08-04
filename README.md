# AMD - Automated Music Downloader 

[RandomNinjaAtk/amd](https://github.com/RandomNinjaAtk/docker-amd) AMD is a Lidarr Companion script to automatically download and tag music files for use in various media applications

[![RandomNinjaAtk/amd](https://raw.githubusercontent.com/RandomNinjaAtk/unraid-templates/master/randomninjaatk/img/amd.png)](https://github.com/RandomNinjaAtk/docker-amd)

### Audio (AMD) + Video (AMVD) (Plex Example )
![](https://raw.githubusercontent.com/RandomNinjaAtk/Scripts/master/images/plex-musicvideos.png)

## Supported Architectures

The architectures supported by this image are:

| Architecture | Tag |
| :----: | --- |
| x86-64 | amd64-latest |

## Version Tags

| Tag | Description |
| :----: | --- |
| latest | Newest release code |


## Parameters

Container images are configured using parameters passed at runtime (such as those above). These parameters are separated by a colon and indicate `<external>:<internal>` respectively. For example, `-p 8080:80` would expose port `80` from inside the container to be accessible from the host's IP on port `8080` outside the container.

| Parameter | Function |
| --- | --- |
| `-e PUID=1000` | for UserID - see below for explanation |
| `-e PGID=1000` | for GroupID - see below for explanation |
| `-v /config` | Configuration files for Lidarr. |
| `-e DOWNLOADS="/path/to/downloads"` | Destination location for temporary downloaded files :: IMPORTANT!!! lidarr needs access to this directory... |
| `-e AUTOSTART="true"` | true = Enabled :: Runs script automatically on startup |
| `-e LidarrUrl="http://127.0.0.1:8686"` | Set domain or IP to your Lidarr instance including port. If using reverse proxy, do not use a trailing slash. Ensure you specify http/s. |
| `-e LidarrAPIkey="08d108d108d108d108d108d108d108d1"` | Lidarr API key. |
| `-e MBRAINZMIRROR="https://musicbrainz.org"` | OPTIONAL :: Only change if using a different mirror |
| `-e MBRATELIMIT=1` | OPTIONAL: musicbrainz rate limit, musicbrainz allows only 1 connection per second, max setting is 10 |
| `-e ARL_TOKEN="08d108d108d108d108d108d108d108d1"` | User token for dl client, for instructions to obtain token: https://notabug.org/RemixDevs/DeezloaderRemix/wiki/Login+via+userToken |
| `-e quality=FLAC` | FLAC or 320 or 128 :: 320/128 are MP3 downloads, FLAC is lossless... |
| `-e FolderPermissions=766` | Based on chmod linux permissions |
| `-e FilePermissions=666` | Based on chmod linux permissions |

# Script Information
* Script will automatically run when enabled, if disabled, you will need to manually execute with the following command:
  * From Host CLI: `docker exec -it amvd /bin/bash -c 'bash /config/scripts/download.bash'`
  * From Docker CLI: `bash /config/scripts/download.bash`
  
## Directories:
* <strong>/config/scripts</strong>
  * Contains the scripts that are run
* <strong>/config/logs</strong>
  * Contains the log output from the script
* <strong>/config/cache</strong>
  * Contains the artist data cache to speed up processes
* <strong>/config/coookies</strong>
  * Store your cookies.txt file in this location, may be required for youtube-dl to work properly
<br />
<br />
<br />
<br /> 
 
##### Attribution 
Icons made by <a href="http://www.freepik.com/" title="Freepik">Freepik</a> from <a href="https://www.flaticon.com/" title="Flaticon"> www.flaticon.com</a>
