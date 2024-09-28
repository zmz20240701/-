SFTP（Secure File Transfer Protocol）也有命令行工具，通常可以在 Unix 系统（包括 macOS 和 Linux）中找到。SFTP 命令行工具提供了一个交互式界面，用于在本地和远程主机之间传输文件。以下是如何使用 SFTP 命令行工具的基本指南：

### 使用 SFTP 命令行工具

#### 1. **连接到远程服务器**

要使用 SFTP 连接到远程服务器，你需要在终端中输入以下命令：

```bash
sftp username@remote_host
```

**示例**：

```bash
sftp user@ubuntu-server
```

这将连接到 `ubuntu-server` 上的 SFTP 服务，使用 `user` 作为用户名。

#### 2. **常用 SFTP 命令**

连接到远程服务器后，你会看到 SFTP 提示符 `sftp> `，可以使用以下常用命令进行文件操作：

- **`ls`**：列出远程目录的文件和文件夹。
  
  ```bash
  sftp> ls
  ```

- **`cd`**：更改远程目录。

  ```bash
  sftp> cd /path/to/remote/directory
  ```

- **`pwd`**：显示远程当前工作目录。

  ```bash
  sftp> pwd
  ```

- **`lcd`**：更改本地目录。

  ```bash
  sftp> lcd /path/to/local/directory
  ```

- **`get`**：从远程服务器下载文件到本地。

  ```bash
  sftp> get remote_file
  ```

- **`put`**：将本地文件上传到远程服务器。

  ```bash
  sftp> put local_file
  ```

- **`mget`**：下载多个文件到本地。

  ```bash
  sftp> mget *.txt
  ```

- **`mput`**：上传多个文件到远程服务器。

  ```bash
  sftp> mput *.jpg
  ```

- **`rm`**：删除远程服务器上的文件。

  ```bash
  sftp> rm remote_file
  ```

- **`rmdir`**：删除远程服务器上的目录。

  ```bash
  sftp> rmdir remote_directory
  ```

- **`mkdir`**：在远程服务器上创建目录。

  ```bash
  sftp> mkdir remote_directory
  ```

- **`exit` 或 `bye`**：退出 SFTP 会话。

  ```bash
  sftp> exit
  ```

#### 3. **示例会话**

以下是一个完整的 SFTP 会话示例：

```bash
$ sftp user@ubuntu-server
Connecting to ubuntu-server...
user@ubuntu-server's password:
sftp> ls
file1.txt  file2.txt  folder1
sftp> cd folder1
sftp> ls
file3.txt  file4.txt
sftp> get file3.txt
Fetching /path/to/remote/folder1/file3.txt to file3.txt
sftp> lcd /path/to/local/directory
sftp> put file4.txt
Uploading file4.txt to /path/to/local/directory/file4.txt
sftp> exit
```

### 总结

SFTP 命令行工具提供了简单且强大的方式来传输文件，你可以通过上述命令在本地和远程系统之间高效地管理文件。
