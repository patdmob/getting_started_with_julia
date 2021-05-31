# How to start a new project with Julia using VS Code

1. `shift+cmd+p` and typing `Julia: Start REPL`
2.  `]` to enter package mode, and `activate .` to activate a new environment
3.  `add DataFrames Query VegaLite VegaDatasets` to add project libraries
    - Notice there are now a *Project.toml* and *Manifest.toml* files in your directory which describe your requirements and dependencies respectively for this project
    - If you are working in a previously created project, you can call `instantiate` (which will use the existing *Project.toml* and *Manifest.toml* files) instead of `add DataFrames ...`. 
4. Now click on the `Julia env: v1.x` button in the status bar and select this directory as the environment. Your environment should update your directory's name: `Julia env: <your_dir_name>`.
5. To get back to the Julia REPL, press `backspace` or `^C`


Things to know: 
1. To executed code interactively from the file into the terminal, use `Control+Enter`. This is different than in Python where users press `Shift+Enter`.
2. To restart the terminal, you can close the existing terminal by selecting the trash can or by `shift+cmd+p` and typing `Julia: Stop REPL` before creating a new one by `shift+cmd+p` and typing `Julia: Start REPL`. 
3. Devcontainers are a great way to create an isolated environment. All you need is a `.devcontainer` folder with a `devcontainer.json` file. In this case we had the following simple code to direct the creation of a dev docker container:

```json
{
    "image": "julia", 
    "extensions": ["julialang.language-julia"]
}
```

This tells VS Code to build a container and install using the julia image with the julialang VS Code extension. After the docker container is built, a user can `activate .` and `instatiate` to start working in the clean environment. 