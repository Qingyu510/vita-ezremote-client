# ezRemote Client

ezRemote Client is a File Manager application that allows you to connect the VITA to remote FTP, SMB, NFS, WebDAV servers to transfer  and manage files. The interface is inspired by Filezilla client which provides a commander like GUI.

![Preview](/screenshot.jpg)

## Usage
To distinguish between FTP, SMB, NFS, WebDAV or HTTP, the URL must be prefix with **ftp://**, **smb://**, **nfs://**, **webdav://**, **webdavs://**

 - The url format for FTP is
   ```
   ftp://hostname[:port]

     - hostname can be the textual hostname or an IP address. hostname is required
     - port is optional and defaults to 21(ftp) if not provided
   ```

 - The url format for SMB is
   ```
   smb://hostname[:port]/sharename

     - hostname can be the textual hostname or an IP address. hostname is required
     - port is optional and defaults to 445 if not provided
     - sharename is required
   ```

 - The url format for NFS is
   ```
   nfs://hostname[:port]/export_path[?uid=<UID>&gid=<GID>]

     - hostname can be the textual hostname or an IP address. hostname is required
     - port is optional and defaults to 2049 if not provided
     - export_path is required
     - uid is the UID value to use when talking to the server. Defaults to 65534 if not specified.
     - gid is the GID value to use when talking to the server. Defaults to 65534 if not specified.

     Special characters in 'path' are escaped using %-hex-hex syntax.

     For example '?' must be escaped if it occurs in a path as '?' is also used to
     separate the path from the optional list of url arguments.

     Example:
     nfs://192.168.0.1/my?path?uid=1000&gid=1000
     must be escaped as
     nfs://192.168.0.1/my%3Fpath?uid=1000&gid=1000
   ```

 - The url format for WebDAV is
   ```
   webdav://hostname[:port]/[url_path]
   webdavs://hostname[:port]/[url_path]

     - hostname can be the textual hostname or an IP address. hostname is required
     - port is optional and defaults to 80(webdav) and 443(webdavs) if not provided
     - url_path is optional based on your WebDAV hosting requiremets
   ```
  
Tested with following WebDAV server:
 - **(Recommeded)** [RClone](https://rclone.org/) - For hosting your own WebDAV server. You can use RClone WebDAV server as proxy to 70+ public file hosting services (Eg. Google Drive, OneDrive, Mega, dropbox, NextCloud etc..)
 - [Dufs](https://github.com/sigoden/dufs) - For hosting your own WebDAV server.
 - [SFTPgo](https://github.com/drakkan/sftpgo) - For local hosted WebDAV server. Can also be used as a webdav frontend for Cloud Storage like AWS S3, Azure Blob or Google Storage.

## Features Native Application##
 - Transfer files back and forth between VITA and FTP/SMB/NFS/WebDAV server
 - File management function include cut/copy/paste/rename/delete/new folder/file for files on VITA local drives

## Controls
```
Triangle - Menu (after a file(s)/folder(s) is selected)
Cross - Select Button/TextBox
Circle - Un-Select the file list to navigate to other widgets or Close Dialog window in most cases
Square - Mark file(s)/folder(s) for Delete/Rename/Upload/Download
R1 - Navigate to the Remote list of files
L1 - Navigate to the Local list of files
```

## Multi Language Support
The appplication support following languages.

The following languages are auto detected.
```
Dutch
English
French
German
Italiano
Japanese
Korean
Polish
Portuguese_BR
Russian
Spanish
Simplified Chinese
Traditional Chinese
```

The following aren't standard languages supported by the PS4, therefore requires a config file update.
```
Arabic
Catalan
Croatian
Euskera
Galego
Greek
Hungarian
Indonesian
Romanian
Ryukyuan
Thai
Turkish
```
User must modify the file **ux0:/data/RMTCLI001/config.ini** and update the **language** setting with the **exact** values from the list above.

**HELP:** There are no language translations for the following languages, therefore not support yet. Please help expand the list by submitting translation for the following languages. If you would like to help, please download this [Template](https://github.com/cy33hc/vita-ezremote-client/blob/master/lang/English.ini), make your changes and submit an issue with the file attached.
```
Finnish
Swedish
Danish
Norwegian
Czech
Vietnamese
```
or any other language that you have a traslation for.
