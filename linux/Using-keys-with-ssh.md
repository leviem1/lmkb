# Using Key Based Authentication with SSH

Using public keys can allow for password-less SSH logins, which can prove to be very
useful for automated applications. To configure your systems to use key based authentication
follow the steps below.

1. Generate your key pair on your local computer
    * Most systems use the `ssh-key-gen` command to handle the generation of key pairs
    * **BEWARE** `ssh-key-gen` may overwrite your existing keys; use with caution.

2. Install your public key on the remote server
    * Many systems have the `ssh-copy-id` command available, and this should
      be used where possible
    * Alternatively, you can manually copy the key to the server, possible using `scp`
      or `sftp`, however copy-and-paste should be avoided. The key should be appended
      to the `.ssh/authorized_keys` file in the user's home folder. The file should have `600` permissions.

3. Confirm you are no longer prompted for password using SSH