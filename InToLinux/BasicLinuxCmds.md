> ### Command Format: command [options…] [arguments…]
> ### man cmd
> ### cmd --help
> ### apropos "Text to search cmd"

## Listing Files:
-  **ls** used to list the contents of a directory.
-  The -t option will sort the files by timestamp
-  The -S option will sort the files by file size
-  more **man ls**

## Navigate through filesystem
- pwd: print working dir
- dot (.) = Current directory
- Tilt (~) = Home directory of the current user
- Hyphen (-) = Root user
- <img width="361" alt="image" src="https://user-images.githubusercontent.com/40174034/233780403-96276cf9-4f9c-4cc6-a935-8ee899584d20.png">
- cd - = to toggle between current & previous location.
- cd .. = Parent path
- cd = to go the User Home
- <img width="334" alt="image" src="https://user-images.githubusercontent.com/40174034/233781540-be38fcad-d0c1-48e6-83db-67a1d686d50f.png">


## Searching & Matching text:
- grep [OPTIONS] PATTERN [FILE]
- grep (global regular expression print): command used in searching and matching text files contained in the regular expressions.
- 

## Administrative Access:
- su OPTIONS USERNAME (The su command allows you to temporarily act as a different user by creating a new shell)
- sudo command allows a user to execute a command as another user without creating a new shell.

## Permission: (xwr 124 ugo):
- <img width="177" alt="image" src="https://user-images.githubusercontent.com/40174034/232458692-bd3a3b5a-6c33-4049-845a-d81626f76d97.png">
- <img width="340" alt="image" src="https://user-images.githubusercontent.com/40174034/233784246-fbb2af27-80d9-474e-b1b8-baabd8c038ae.png">

## Changing File Permissions: **chmod**
- chmod [<SET><ACTION><PERMISSIONS>]... FILE
- chmod really means change the modes of access.

  
## Changing File Ownership: **chown**
- chown [OPTIONS] [OWNER] FILE 
- The chown command is used to change the ownership of files and directories.
- <img width="367" alt="image" src="https://user-images.githubusercontent.com/40174034/233785079-cd651b69-1194-475d-9a63-ce45491fa155.png">


## Viewing Files: **cat** **meow lol!**
- cat [OPTIONS] [FILE] (for small files) & less [OPTIONS] [FILE] (for large files)
- The cat command will display the entire contents of the file
- head [OPTIONS] [FILE]: First 10 lines of files (More man head)
- tail [OPTIONS] [FILE]: Last 10 lines of files

## Copying//Moving/Renaming Files/Dir: 
- cp [OPTIONS] SOURCE DESTINATION
- mv old_file_name new_file_name (Rename)
- mv file full_dir_path
> Copying a file, requires execute permission in current (file location) and the read permission at destination directories.
> Moving a file requires write and execute permissions on both the origin and destination directories.
  
## Removing Files:
- rm [OPTIONS] FILE
> To delete a file within a directory, a user must have write and execute permission on a directory.
  
## Regular Expressions
- Basic regular expression characters:
- <img width="366" alt="image" src="https://user-images.githubusercontent.com/40174034/233856479-0972f75b-b5ca-4a53-96cb-e1af2b18c4ab.png">
- Extended regular expressions:
- <img width="370" alt="image" src="https://user-images.githubusercontent.com/40174034/233856581-06ca0d69-5cda-4a79-b821-f1cbb64f3a59.png">
  

## For Fun/Easter Egg:
- aptitude moo (package management tool)
- aptitude moo -v (Keep adding -v options to see how many unique responses you can get!)
- Steam Locomotive command su sl (animated Train)
