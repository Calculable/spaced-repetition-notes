# Rebase vs. Merge vs. Squash
🍹

##  Merge
![][image-1]

##  Rebase

- Gibt eine schönere History
- Oft bevorzugt
- Kann heikel sein wenn mehrere Leute auf einem Branch arbeiten: Durch das Rebasing wird die Commit History des Branches geändert auf dem ich arbeite.

> Therefore, it's recommended to use git rebase only for cleaning up local, private branches before merging them into the main codebase. For public branches, it's safer to use git merge to combine changes.


![][image-2]


##  Squash
Squash ist wie Rebase aber man fasst die Commits zu einem einzigen zusammen.

![][image-3]


##  Zusammenfassung
- Unterschied zwischen Merge, Rebase und Squash
- Wann muss man bei Rebase vorsichtig sein?

[image-1]:	assets/Bildschirmfoto%202023-09-22%20um%2007.47.12.png
[image-2]:	assets/Bildschirmfoto%202023-09-22%20um%2007.47.15.png
[image-3]:	assets/Bildschirmfoto%202023-09-22%20um%2007.47.19.png

#learning unit# #guide