# **Code bites**

Category: Scripting

Author: Adithya Rajesh

Answer : `MAZE{24712798}`


## Problem Statement

Find the size(in bytes) of all files with '.py' extension (Python code files) of the github user "AnirudhAchal" in all of the user's repositories which are not archived and are not a fork of other repositories.

## Solution
* Manual: Clone all the source repos and count the size of .py files.
* The easiest way to find the answer would be to write a script utilizing github API to get the details. For example, Python has a library [PyGithub](https://github.com/PyGithub/PyGithub) to access all the required details. Note that you might have to authenticate since the rate limit for the unauthenticated API access is only 60 requests/hr.

```python
#!/usr/bin/env python3

import click
from github import Github

g = Github("<access_token>")

def printrepos(repos, language):
    #only dispay original repos of user
    ans = 0
    for repo in repos:
        if repo.fork is False and repo.archived is False:
            lang = repo.get_languages()
            if language in lang:
                contents = repo.get_contents("")
                while contents:
                    f = contents.pop(0)
                    if f.type == "dir":
                        contents.extend(repo.get_contents(f.path))
                    elif f.path[-3:] == ".py": # .js, .cpp ...
                        ans += f.size
    print(ans)
                    
@click.command()
@click.argument('username')
@click.argument('language')
def main(username, language):
    user = g.get_user(username)
    repos = user.get_repos()
    printrepos(repos, language)


if __name__ == "__main__":
    main()
```
