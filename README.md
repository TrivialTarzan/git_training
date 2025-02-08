# git_training

Git setup highlights

You can download git here: http://git-scm.com/downloads

Install Git with default settings.

Generating a pair of ssh keys:

     ssh-keygen -t rsa –C “vitali_shulha@epam.com"

The public key (id_rsa) should be sent to the owner of the repository in order to obtain work rights. Or upload to profile settings in bitbucket / github / gitlab.

Username and email settings:

     git config --global user.name “Vitali Shulha“

     git config --global user.email “vitali_Shulha@epam.com"
