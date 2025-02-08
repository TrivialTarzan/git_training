# git_training

Git setup highlights

You can download git here: http://git-scm.com/downloads
Install Git with default settings.

Generating a pair of ssh keys:
     ssh-keygen -t rsa –C “vitali_shulha@epam.com"

The public key (id_rsa) should be sent to the owner of the repository in order to obtain work rights. Or upload to profile settings in bitbucket / github / gitlab.
Username and email settings:

     git config --global user.name “Janusz Korwin-Mikke“

     git config --global user.email “korWIN@winwin.com"

You can add changes with this command:
     # write this if you want to add all the changed files to the commit
     git add .

     # wite this to add anly specified file
     git song.txt 

To commit write
     git commit -m "Describe the changes here"

To use the GIT GUI instead of terminal, write in GIT terminal:
     git gui&

To open a window where you'll see all the commits that were made:
     gitk&
     
                    
