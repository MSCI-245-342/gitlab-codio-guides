#### Resolving conflicts

If you run `git merge main` and there are conflicts, you'll get a message from git telling you which files are in conflict and that "Automatic merge failed; fix conflicts and then commit the result."

To see the files that need work, do `git status`.

Then open each of these files.  You will see one or more sections like:

```
<<<<<<< HEAD
This is code you wrote in your branch.
=======
This is code that is on the main branch.
>>>>>>> main
```

From `<<<<<<< HEAD` to `=======` is what you have in your working branch.  The part from `=======` to `>>>>>>> main` is from the main branch.  It has the changes that you just pulled in.

You need to decide what the file should really look like.  Either take your version, or the new version, or go and talk with your team to decide what to do.  

Fix up the file to be correct.  (You will also remove the `<<<<<<< HEAD` and `=======` and `>>>>>>> main` text, for they should not be in the file if you've made it be correct working code.)

Once you've made your changes, `git add` the fixed file, and then `git commit` the file.  You will have resolved the conflicts and finished the merge.
