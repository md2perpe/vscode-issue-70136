# Demo of [VS Code issue 70136](https://github.com/Microsoft/vscode/issues/70136)

Do the following steps to reproduce.

1. Create empty repository

    ```bash
    mkdir vscode-issue-70136
    cd vscode-issue-70136
    ```

2. Initialize repository

    ```bash
    git init
    ```

3. Setup remote

    ```bash
    git remote add upstream git@github.com:md2perpe/vscode-issue-70136.git
    git config remote.upstream.fetch '+refs/heads/path/to/*:refs/remotes/upstream/*'
    git config remote.upstream.push '+refs/heads/*:refs/heads/path/to/*'
    ```

4. Create a local branch `foo` for `path/to/foo` on the remote

    ```bash
    git fetch upstream
    git checkout -b foo upstream/foo
    ```

5. See that `git pull` works

    ```bash
    git pull
    ```

6. Start VS Code

    ```bash
    code .
    ```

7. See that "Git: Pull" fails

    Inside VS Code, run the command "Git: Pull". It fails.
