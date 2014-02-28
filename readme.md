SVN 2 Git Migration
===
This project contains the script and data files for performing complex migration from svn to git.
When I say complex I mean many svn repos to many git repos with split and merge of folders.

### Main script

the main script can be found in 
**studio/build.xml**

all repos are found according to the java property **repo.root.folder**, by default the repo.root.folder is set to the parent folder of the git repository.

### Preparing the Svn Git clone
Before launching the migration script you need to clone locally the svn repositories you need to migrate. Please follow the Atlassian tuto [here](https://www.atlassian.com/git/migration#!migration-convert).
You must create svn git clone in 

    ${repo.root.folder}/svn_git_repos
please be sure to follow the full Atlassian tuto including the clean phase

    java -Dfile.encoding=utf-8 -jar talend-svn-git-migration/svn-migration-scripts.jar clean-git --force

###Preparing the migration data

###Launching the migration
    cd talend-svn-git-migration/studio
    ant -Dremote.git.username=you_user_name -Dremote.git.password=your_password -lib ant-contrib-1.0b3.jar  -listener net.sf.antcontrib.perf.AntPerformanceListener