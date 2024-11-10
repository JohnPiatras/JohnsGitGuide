# Reverting a Commit

Mistakes are inevitable. So lets make one and see what we can do.

Lets add another line to staging_test.txt so it now looks like:
```
This text was added before staging the file.
This text was added after staging the file.
Yet another sentence.
Babylon 5's a big pile 'o shit!
```

We'll then `git add staging_text.txt` and then `git commit -m 'Commit a mistake'`.
