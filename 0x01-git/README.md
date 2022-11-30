My first readme in this repo

## Preparing the github local repo
- To successfully be able to clone a repo without it asking for the password, clone into it using
	```
	git clone https://<personal_token_from_github>@github.com/<github_suername>/<repo_name>.git
	```
- the token is generated from your github settings at this url: https://github.com/settings/tokens
- Once done, don't forget to set the global user.name and user.email using the below commmands
	```
	git config --global user.name "Your name"
	git config --global user.email "Your email"
	```

- Finally, when pushing your changes to the online repository, it may ask you to set the origin and if it does this, it most probably will give a suggested command on how to do this. If it doesn't give a suggestion, use this guide: https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories

## Switching to a new branch
- When you need to create a copy of your current repo to do a test modification, this is where branching comes in
- We do branching like so
  ```
  # For new branches
  git checkout -b <New branch name>

  # To switch back to an existing branch
  git checkout <existing branch name>
  ```

## Merging branches
- After you've done your edits on the branch repo, you may wish to merge it back to the main repository. We do this using the merge command but before that, you need to know:
	- If you're merging changes in branch B to branch A, then you need to switch over to branch A. (Check the previous section)
	- If you want to maintain changes unique to branch B in branch A, check how to do so in the next section
	```
	# From the branch in which you want to add new changes, do:
	git merge branch_with_updates
	```

## Merge conflict resolutions
- Whe trying to merge branches, git may sometimes return an error in cases where files are new in one brach as compared to the origin or alternatively, it may return an error to say that some files have varying content
- You can check this using 
	```
	git status
	```
- For files that were new i other repositories, simply copy their whole paths as shown in the git status return message and add them like so
	```
	git add <file_1_path> <file_2_path> ... <file_n_path>
	```
- For those that claim to have differet contents ie Both modified, simply open them in your preferred code editor and delete the sectios you do not wish to have
- If you see something like >>>>> HEAD, this refers to what the current repository has. It's end is denoted by a set of ====
- The other repository's contents will be shown in the same manner above so it's just a matter of picking which section you want to remain then deleting everything else including the >>>>, <<<<< and =====

## Git ignored files
- Sometimes you may want to deliberately ignore pushing some files or those with certain extensions. The way to go about this is as below
	- Create a file called .gitignore (Include the . )
	- Keep the path to the file(s) you want excluded in a new line for each file
	- For the extensions you want to ignore eg A .pdf file, have a line with ".pdf" included
	- For files that begin with a particular name, use "filename.*"
	```
	#Command to ignore all pdf files
	*.pdf 
	```
