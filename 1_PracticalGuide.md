# Practical guide: how to contribute to open source Julia projects 🟣💻

## Introduction
When I first got interested in Julia, I was very much looking forward to contribute to open-source projects. 
However, I came to realise that I had no clue how to do this. I asked for advice, and I was told to just create a "PR". As you can imagine, this is more complex than it sounds.

After I learnt the general concepts behind [How to contribute to open source](https://opensource.guide/how-to-contribute/), I was still confused about the steps to take before making such a "Pull Request".

It turns out that contributing to open-source projects involves steps that are natural for experienced coders but a total mystery for beginners.
Therefore, I decided to write this post to make the process less confusing.

Here I present a practical guide that explains the steps to contribute to existing open source Julia projects.

## 1. Load package in developers mode

In the Julia Pkg REPL type: `dev <PackageName>`
```julia
   _       _ _(_)_     |  Documentation: https://docs.julialang.org
  (_)     | (_) (_)    |
   _ _   _| |_  __ _   |  Type "?" for help, "]?" for Pkg help.
  | | | | | | |/ _` |  |
  | | |_| | | | (_| |  |  Version 1.8.5 (2023-01-08)
 _/ |\__'_|_|_|\__'_|  |  Official https://julialang.org/ release
|__/                   |

(@v1.8) pkg> dev <PackageName>
```
This will allow for your version of the code to run separately from the registered/original package.

* **Switch to the registered version** 

In the Julia Pkg REPL `add <PackageName>`

`st` --> `<PackageName> <version>`
  
* **Switch to the developer's version**
  
In the Julia Pkg REPL `dev <PackageName>`
  
`st`--> `<PackageName> <version> ~/.julia/dev/PackageName`

_Note: always do this to run the dev version of the package_

## 2. Fork the original repository and link it to the dev path
  
**2.1 Fork the original repository, in order to have a copy of it in my own GitHub account**

Just click the `Fork` button in the GitHub website of the original repo.

**2.2 Go to the folder where the package is located for development**

`~/.julia/dev/PackageName`

_Tip: use `Command+Shift+Dot` in mac to show hidden files (e.g. to view then in Finder)_

**2.3 Connect the local folder to your fork**

Set `origin` and `upstream` for the repo via the terminal

`git remote set-url origin <my_fork_ssh>`

`git remote add upstream <my_fork_ssh>`

_Note: `set-url` modifies an origin/upstream that already exists, `add` creates a new connection_

## 3. Develop on my computer

**3.1 Open project in VSCode**

_Tip: use `Command+Shift+Dot` in mac to show hidden files (to view then in Finder)_

**3.2 Open a Julia console associated with the project**

Type `alt+J+O` in mac

**3.3 Activate Revise.jl**

Revise.jl is package that live-reloads the code you are working on.
It automatically reloads the branch that you are working on.

In the Julia REPL:

`using Revise`

`using <PackageName>`

_Tip: to find a function in the project type `edit(<function_name>)`_ 

## 4. Create a new branch

To create and switch to the new branch `git checkout -b <branch-name>`

To switch branches `git checkout <branch-name>`

To view branches `git branch`
  
_Note: always be aware of the branch you are working on_

## 5. Code
Code your contribution

## 6. Test code
It is a good practice to test your code.

**6.1 In the test folder create your @testset with different @test**

**6.2 Run test in the Julia Pkg REPL: `test <PackageName>`**

## 7. Upload contribution
Push the new contribution to my GitHub (fork of the original repo) on the newly created branch

`git add *`

`git commit`

`git push`

## 8. Open a Pull Request (PR) on the original repo
This is done on the GitHub website of the original repo. Typically, a `Compare and pull request` button appears automatically to perform this process.

## Contribution approved ✅ 🎉

* If your contribution has been approved, describe it in the [`changelog.md` file](https://keepachangelog.com/en/1.0.0/).
This is a file that contains text, not code, with "an ordered list of notable changes for each version of a project".

* If in your contribution you: add a new function, or change the name of an existing one, add it in `api.md`

* Once your contribution has been merged, you can safely delete your branch if you don't want to continue development within it


For additional practical information, you can check out this [video](https://www.youtube.com/watch?v=QVmU29rCjaA).


Feel free to create an issue to share any questions or suggestions :)
