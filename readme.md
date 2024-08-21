Sandbox repo to try to re-create and understand various bits of information that appear when doing `git status` in the midst of a cherry-pick that has conflicts.

My current understanding:

Sitting on an old branch (old because it's a certain branched old version of the software; i.e. can't and won't just pull it up to the tip of master).
There was a commit made to master, though, that needs to be pulled into this old branch.
When cherry-picking it, there are various conflicts. When doing git status, I see two sections in the output: "Changes to be committed" and "unmerged paths". An example output is:

Changes to be committed:
	new file: foobar.c

Unmerged paths:
(use "git add/rm <file>..." as appropriate to mark resolution)
	deleted by us: trashcan.c
	added by them: newworld.c
  
I'm confused because it seems like all of these are the same thing... in a way?

foobar.c being a new file makes sense. We're on an old branch, we're cherry-picking a newer commit, there's going to be a new file added. Cool.
"added by them" sounds like another way of saying "hey we have a new file from this new commit".
And "deleted by us" seems like a roundabout way of saying "we don't have this file in our old branch, but the new commit has it", which sounds like... it's a new file.

So I want to go and try to re-create these git status messages to see if I can get a better understanding of what these messages mean, and how they differ. 
