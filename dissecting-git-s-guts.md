# DISSECTING GIT'S GUTS

@emilyxxie

- For most people, Git is complete sorcery
- *Git happens* :laughing:
- Why dissect Git? Gain comfort, better mental model. E.g. what is at the heart of a branch? What is a detached HEAD state?
- *Git Porcelain*: the high-level commands we use on a daily basis
- *Plumbing*: the internal, low-level commands


## Agenda
- Git directory
- Git objects
- Git references
- Git packfiles

- **Git directory**
	- `.git`
	- `git init` puts the scaffolding in place needed to work with git on a project
	- A `git clone` just copies the `.git` folder
	- `ls .git`
		- objects
		- refs
		- …

- **Objects**
	- Where the content is!
	- Git’s database
		- Content-addressable filesystem
		- Git gives you a key to retrieve content from the database
		- `git hash-object -w hello_world.txt` plumbing command, gives  use the SHA-1! :boom:
		- For a given set of content, you reliably generate the same hash
			- A *fingerprint*
		- `git cat-file -p` allows you to read from the database, `-p` makes the output pretty, `-t` by the way, returns the object’s type (e.g. blob, tree)
		- Git’s database stores compressed objects, compressed with zlib


- **Exercise**
- [Cheat sheet](https://github.com/emilyxxie/gits_guts_commands)
- `git hash-object -w bio.md`
- `git cat-file -p 9d6b6928c57e27ddd64bcad64b1a53623c9867b2`
- Git doesn’t store diffs, for each version of a file, it installs an entire copy of the file (initially) but… [follow up later on this]

- **Trees**
	- A complete snapshot of your directory
	- To create a tree… Need an index first (`git update-index --add`, a low-level `git add`), index lives in `.git/index`
	- `git ls-files —stage` shows the index
	- `git write-tree`
	- Note, trees can reference other trees (sub-directories)

- **Exercise**: Make a tree!
```
git write-tree
0baa49142494d6bb979bcd36572662bdd62f2160
git cat-file -p 0baa49142494d6bb979bcd36572662bdd62f2160
100644 blob 9d6b6928c57e27ddd64bcad64b1a53623c9867b2	bio.md
040000 tree d35e12dfe16923b05e99fbf49c31e91c18eb1db5	subdir
git cat-file -p d35e12dfe16923b05e99fbf49c31e91c18eb1db5
100644 blob 8ab01e46b848c561cf37000562915c4ae4d116ba	barbaz.md
100644 blob 5ddc4a0635b7e92187567282868679136da1ec1f	foobar.md
```

- **Commit objects**
	- `git commit-tree` (`echo “first commit” | git commit-tree $SHA -p $PARENT_SHA`)
	- We’ve done a `git commit`! Up until now, **we have not committed anything**, nuttin’!

- **Exercise**: Commit an object!

```
echo "First commit" | git commit-tree 0baa49142494d6bb979bcd36572662bdd62f2160
cat >> foobar.md
git update-index --add foobar.md
git write-tree
echo "Second commit" | git commit-tree 4fa2797f288b553d0ed8cddb59b3719f817cdabe -p f6e6ec6a7806b894ccce06c57a6568798b11ab60
git cat-file -p ea99086abafac64f6598a3053d80c64a24fc3f04
tree 4fa2797f288b553d0ed8cddb59b3719f817cdabe
parent f6e6ec6a7806b894ccce06c57a6568798b11ab60
author Steve Winton <stevewinton@gmail.com> 1467069112 -0700
committer Steve Winton <stevewinton@gmail.com> 1467069112 -0700

Second commit
```

- :tada: We’ve now performed all the low-level plumbing commands for `git add`, `git commit`
- **Git is a both a DAG and a Merkle tree (Merkle DAG)**
	- Merkle also used with Bitcoin

- **Git references**
- We have blobs, trees, commits as our low-level objects in our Git objects database
- How do we keep track of what commit we want to work with?
	- Branches, but what *is* a branch?
	- How does Git know what goes with a branch?
	- Branches are just pointers, that reside in `.git/refs/heads`
- `git update-ref` can be used to create a branch
	- `git update-ref refs/heads/master $SHA`
	- Just a file, containing the SHA the branch points to :open_mouth:
- What about `.git/HEAD`?
	- Just a pointer to current branch
	- Detached head is when HEAD points to a commit, not to a branch
  - Any commits made on detached HEAD will not belong to a branch, and will eventually get pruned by Git
  - To recover: Checkout a branch

- **Exercise**: References
```
 git update-ref refs/heads/master ea99086abafac64f6598a3053d80c64a24fc3f04
 cat .git/refs/heads/master
 git checkout -b my-feature-is-a-feature
 ls -a .git/refs/heads/
 cat .git/refs/heads/my-feature-is-a-feature
 cat bio.md
 cat >> bio.md
 git st
 git add bio.md
 git commit
 cat .git/refs/heads/my-feature-is-a-feature
```

- **Packfiles**
	- `git gc` garbage collects
	- `git count-objects`, returns total no. of lose objects, should significantly shrink after `git gc`
	- `git verify-pack`

## Resources
- [Pro Git](https://git-scm.com/book/en/v2) Scott Chacon & Ben Straub
- [Git from the Inside Out](https://maryrosecook.com/blog/post/git-from-the-inside-out) Mary Rose Cook
- [Git from the Bottom Up](https://jwiegley.github.io/git-from-the-bottom-up/) John Wiegley
- [Advanced Git: Graphs, Hashes, and Compression, Oh My.](https://youtu.be/ig5E8CcdM9g) Matthew McCullough
- [Unpacking Git Packfiles](https://codewords.recurse.com/issues/three/unpacking-git-packfiles) Aditya Mukerjee
- [Visualizing Git’s Merkle DAG with D3.js](https://tylercipriani.com/2016/03/21/Visualizing-Git-Merkle-DAG-with-D3.js.html) Tyler Cipriani

## Slides?
- This was recorded at Git Merge, recording available… :soon:?

___
## Metadata
```

Mon Jun 27 15:05:30 PDT 2016
```

