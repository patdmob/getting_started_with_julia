# How to Start a New Project with Julia using VS Code

This project was just first attempt creating a Julia Project. Workflow is super important to me so I generally try to understand that first when learning a new language. I found the [video](https://www.youtube.com/watch?v=IdhnP00Y1Ks&ab_channel=TheJuliaProgrammingLanguage) by David Anthoff and decided to follow along and take notes along the way. This repository is the result. If you watch the video, he assumes you already have some familiarity with VS Code and glosses over certain keyboard shortcuts. I try my best to explicitly explain the steps below. 

That being said, I assume you have already installed julia and the VS Code julia language extension. I also noticed that not all of the features worked for me as I followed along. I can only assume that there were some breaking changes in either the language, extension, or VS Code.

## Creating an New Project

1. Within VS Code, pressing `shift+cmd+p` (`control+shift+p` on Windows) will open the command palette; after which type `Julia: Start REPL` to start a julia terminal
2. Within the REPL type `]` to enter package mode, and `activate .` to activate a new environment
3.  Type `add DataFrames Query VegaLite VegaDatasets` to add the desired project libraries
    - Notice there are now a *Project.toml* and *Manifest.toml* files in your directory which describe your requirements and dependencies respectively for this project
    - If you are working in a previously created project, you can call `instantiate` (which will use the existing *Project.toml* and *Manifest.toml* files) instead of `add DataFrames ...`. 
4. Now click on the `Julia env: v1.x` button in the status bar and select this directory as the environment. Your environment should update your directory's name: `Julia env: <your_dir_name>`.
5. To get back to the Julia REPL, press `backspace` or `^C`


### Things to Know

1. To executed code interactively from the file into the terminal, use `control+enter`. This is different than in Python where users press `shift+enter`.
2. To restart the terminal, you can close the existing terminal by selecting the trash can or by `shift+cmd+p` and typing `Julia: Stop REPL` before creating a new one by `shift+cmd+p` and typing `Julia: Start REPL`. I did not find an easy way to restart the session. 
3. Devcontainers are a great way to create an isolated environment. All you need is a `.devcontainer` folder with a `devcontainer.json` file. In this case we had the following simple code to direct the creation of a dev docker container:

```json
{
    "image": "julia", 
    "extensions": ["julialang.language-julia"]
}
```

This tells VS Code to build a container and install using the julia image with the julialang VS Code extension. After the docker container is built, a user can `activate .` and `instatiate` to start working in the clean environment. 
