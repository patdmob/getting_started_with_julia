# How to start a new project with Julia using VS Code

1. `Shift+Cmd+P` Julia: Start REPL
2.  `]` to enter package mode, and `activate .` to activate a new environment
3.  `add DataFrames Query VegaLite VegaDatasets` to add project libraries
    - Notice there are now a *Project.toml* and *Manifest.toml* files in your directory which describe your requirements and dependencies respectively for this project
4. Now click on the `Julia env: v1.x` button in the status bar and select this directory as the environment. Your environment should update your directory's name: `Julia env: <your_dir_name>`.
5. To get back to the Julia REPL, press `backspace` or `^C`
6. Create a new file in the VS Code Directory Explorer with the name **main.jl** 


Things to know: 
1. To executed code interactively from the file into the terminal, use Control+Enter. This is different than in Python where users press Shift+Enter. 


How do I restart/clear the terminal? 