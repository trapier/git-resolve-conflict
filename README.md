> Resolve merge conflict in one file, using given strategy (--ours, --theirs, --union)

**TL;DR** we need to use [git-merge-file](https://git-scm.com/docs/git-merge-file) but its API is not easy. Hence I wrote a wrapper `./git-resolve-conflict.sh` around it (I used temp files instead of process substitution to make it msys/mingw-friendly). 
    me@mymachine /d/gh/merge-file-ours-poc (merge_master_to_develop +|MERGING)
    $ git diff --cached
    diff --git a/added-in-master.txt b/added-in-master.txt
    new file mode 100644
    index 0000000..9cef8af
    --- /dev/null
    +++ b/added-in-master.txt
    @@ -0,0 +1 @@
    +added in master
    diff --git a/package.json b/package.json
    index 75c469b..03f513b 100644
    --- a/package.json
    +++ b/package.json
    @@ -6,6 +6,10 @@
       "scripts": {
         "test": "echo \"Error: no test specified\" && exit 1"
       },
    +  "dependencies": {
    +    "foobar": "1.0.0",
    +    "quux": "2.0.0"
    +  },
       "author": "",
       "license": "ISC"
     }

            modified:   package.json