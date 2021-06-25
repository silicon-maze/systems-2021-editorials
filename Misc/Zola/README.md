# Zola's Secrets

Category: Git

Author: Gaurang Velingkar (gaurang2001)

Answer / Flag: `MAZE{HA1l_DR_ZOLA}`

## Problem Statement

Before Hydra was wiped out, Dr. Zola stored a secret in a Tree that is currently Unreachable. Steve has been trying search but is lost. You are provided with Zola's directory. Can you help Steve find it?

## Relevant files / links

[ZolaSecrets.zip](https://drive.google.com/file/d/1nVG6v-HEytZ-_F47SD25fxn4gAziDR8h/view?usp=sharing)

## Hint

Is there something odd/unique about the contents in the `.git` folder?

## Solution

The problem statement and the README in the zip file points to a "tree" being "unreachable". To search for unreachable objects, git uses [git fsck](https://git-scm.com/docs/git-fsck). Using the command `git fsck --unreachable` would give a long list of objects. Since we're searching for a git [tree](https://git-scm.com/book/en/v2/Git-Internals-Git-Objects), a simple grep command can be used alongside. `git fsck --unreachable | grep tree` gives a hash corresponding to the tree we're looking for. Post that, `git cat-file -p <hash>` will list all the blobs within that tree. One of the blobs is a `flag.txt` file. `git show <blob_hash>` will give the final flag.

