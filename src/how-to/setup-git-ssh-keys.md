# Setup git ssh-keys
See [connecting-to-github-with-ssh](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh) for more details.

1. Generate a new key:
    ```sh
    ssh-keygen -t ed25519 -C "your_email@example.com"
    ```
2. Start ssh-agent in the background
    ```sh
   eval "$(ssh-agent -s)"
   ```
3. Edit `~/.ssh/config` and add the following
    ```sh
    Host *.github.com
      AddKeysToAgent yes
      IdentityFile ~/.ssh/id_ed25519
    ```
4. Add the key to the ssh-agent 
    ```sh
    ssh-add ~/.ssh/id_ed25519
    ```
5. Login to github
    ```sh
    gh auth login
    ```
6. Add the key to github
    ```sh
    gh ssh-key add ~/.ssh/id_ed25519.pub --title "<insert optional title>"
    ```

