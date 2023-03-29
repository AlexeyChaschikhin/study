
Last login: Fri Jan 13 07:32:59 2023 from 192.168.100.165
alexey@vm3ubn22serv:~$ cd 
alexey@vm3ubn22serv:~$ cd 01_Git_Local/
alexey@vm3ubn22serv:~/01_Git_Local$ ll
total 24
drwxrwxr-x 5 alexey alexey 4096 Jan 13 07:34 ./
drwxr-x--- 8 alexey alexey 4096 Jan 13 13:11 ../
drwxrwxr-x 8 alexey alexey 4096 Jan 13 07:34 .git/
-rw-rw-r-- 1 alexey alexey   17 Jan 11 08:32 .gitignore
drwxrwxr-x 2 alexey alexey 4096 Jan 11 09:07 master/
drwxrwxr-x 2 alexey alexey 4096 Jan 11 08:33 temp/
##alexey@vm3ubn22serv:~/01_Git_Local$ git branch 
  dev
  features/do_one
  hotfix/we_gonna_die
* master
alexey@vm3ubn22serv:~/01_Git_Local$ 
alexey@vm3ubn22serv:~/01_Git_Local$ 
alexey@vm3ubn22serv:~/01_Git_Local$ 
alexey@vm3ubn22serv:~/01_Git_Local$ git log --oneline 
bf8e459 (HEAD -> master) Master_2nd_commit
b1bb685 Master_1st_commit
#alexey@vm3ubn22serv:~/01_Git_Local$ git checkout dev 
Switched to branch 'dev'
#alexey@vm3ubn22serv:~/01_Git_Local$ git log --oneline 
08460a6 (HEAD -> dev) dev_2nd_commit
8e566a3 dev_1st_commit
bf8e459 (master) Master_2nd_commit
b1bb685 Master_1st_commit
#alexey@vm3ubn22serv:~/01_Git_Local$ git checkout features/do_one 
Switched to branch 'features/do_one'
alexey@vm3ubn22serv:~/01_Git_Local$ git log --oneline 
ea780d7 (HEAD -> features/do_one) Merge branch 'dev' into features/do_one
e75516a features_1st_additional commit
08460a6 (dev) dev_2nd_commit
8e566a3 dev_1st_commit
bf8e459 (master) Master_2nd_commit
b1bb685 Master_1st_commit
#alexey@vm3ubn22serv:~/01_Git_Local$ git checkout master 
Switched to branch 'master'
#alexey@vm3ubn22serv:~/01_Git_Local$ git rebase dev 
Successfully rebased and updated refs/heads/master.
alexey@vm3ubn22serv:~/01_Git_Local$ git log --oneline 
08460a6 (HEAD -> master, dev) dev_2nd_commit
8e566a3 dev_1st_commit
bf8e459 Master_2nd_commit
b1bb685 Master_1st_commit
#alexey@vm3ubn22serv:~/01_Git_Local$ git rebase features/do_one 
Successfully rebased and updated refs/heads/master.
alexey@vm3ubn22serv:~/01_Git_Local$ git log --oneline 
ea780d7 (HEAD -> master, features/do_one) Merge branch 'dev' into features/do_one
e75516a features_1st_additional commit
08460a6 (dev) dev_2nd_commit
8e566a3 dev_1st_commit
bf8e459 Master_2nd_commit
b1bb685 Master_1st_commit
alexey@vm3ubn22serv:~/01_Git_Local$ git log --oneline
ea780d7 (HEAD -> master, features/do_one) Merge branch 'dev' into features/do_one
e75516a features_1st_additional commit
08460a6 (dev) dev_2nd_commit
8e566a3 dev_1st_commit
bf8e459 Master_2nd_commit
b1bb685 Master_1st_commit
alexey@vm3ubn22serv:~/01_Git_Local$ git branch
  dev
  features/do_one
  hotfix/we_gonna_die
* master
#alexey@vm3ubn22serv:~/01_Git_Local$ git checkout hotfix/we_gonna_die 
Switched to branch 'hotfix/we_gonna_die'
alexey@vm3ubn22serv:~/01_Git_Local$ git log --oneline 
cd92a04 (HEAD -> hotfix/we_gonna_die) hotfix_1st_additional_commit
bf8e459 Master_2nd_commit
b1bb685 Master_1st_commit
#alexey@vm3ubn22serv:~/01_Git_Local$ git checkout master 
Switched to branch 'master'
#alexey@vm3ubn22serv:~/01_Git_Local$ git cherry-pick hotfix/we_gonna_die cd92a04
[master d15f449] hotfix_1st_additional_commit
 Date: Wed Jan 11 13:35:11 2023 +0000
 1 file changed, 1 insertion(+)
 create mode 100644 hotfix_we_gonna_die/hotfix_1st_commit.txt
alexey@vm3ubn22serv:~/01_Git_Local$ git log --oneline 
d15f449 (HEAD -> master) hotfix_1st_additional_commit
ea780d7 (features/do_one) Merge branch 'dev' into features/do_one
e75516a features_1st_additional commit
08460a6 (dev) dev_2nd_commit
8e566a3 dev_1st_commit
bf8e459 Master_2nd_commit
b1bb685 Master_1st_commit
#alexey@vm3ubn22serv:~/01_Git_Local$ git checkout dev 
Switched to branch 'dev'
alexey@vm3ubn22serv:~/01_Git_Local$ git log --oneline 
08460a6 (HEAD -> dev) dev_2nd_commit
8e566a3 dev_1st_commit
bf8e459 Master_2nd_commit
b1bb685 Master_1st_commit
#alexey@vm3ubn22serv:~/01_Git_Local$ git cherry-pick hotfix/we_gonna_die cd92a04
[dev 07293ba] hotfix_1st_additional_commit
 Date: Wed Jan 11 13:35:11 2023 +0000
 1 file changed, 1 insertion(+)
 create mode 100644 hotfix_we_gonna_die/hotfix_1st_commit.txt
#alexey@vm3ubn22serv:~/01_Git_Local$ git log --oneline 
07293ba (HEAD -> dev) hotfix_1st_additional_commit
08460a6 dev_2nd_commit
8e566a3 dev_1st_commit
bf8e459 Master_2nd_commit
b1bb685 Master_1st_commit
#alexey@vm3ubn22serv:~/01_Git_Local$ git checkout features/do_one 
Switched to branch 'features/do_one'
#alexey@vm3ubn22serv:~/01_Git_Local$ git cherry-pick hotfix/we_gonna_die cd92a04
[features/do_one e65ccde] hotfix_1st_additional_commit
 Date: Wed Jan 11 13:35:11 2023 +0000
 1 file changed, 1 insertion(+)
 create mode 100644 hotfix_we_gonna_die/hotfix_1st_commit.txt
#alexey@vm3ubn22serv:~/01_Git_Local$ git log --oneline 
e65ccde (HEAD -> features/do_one) hotfix_1st_additional_commit
ea780d7 Merge branch 'dev' into features/do_one
e75516a features_1st_additional commit
08460a6 dev_2nd_commit
8e566a3 dev_1st_commit
bf8e459 Master_2nd_commit
b1bb685 Master_1st_commit
#alexey@vm3ubn22serv:~/01_Git_Local$ git checkout master 
Switched to branch 'master'
alexey@vm3ubn22serv:~/01_Git_Local$ git log --oneline 
d15f449 (HEAD -> master) hotfix_1st_additional_commit
ea780d7 Merge branch 'dev' into features/do_one
e75516a features_1st_additional commit
08460a6 dev_2nd_commit
8e566a3 dev_1st_commit
bf8e459 Master_2nd_commit
b1bb685 Master_1st_commit
#alexey@vm3ubn22serv:~/01_Git_Local$ git checkout hotfix/we_gonna_die 
Switched to branch 'hotfix/we_gonna_die'
alexey@vm3ubn22serv:~/01_Git_Local$ git log --oneline 
cd92a04 (HEAD -> hotfix/we_gonna_die) hotfix_1st_additional_commit
bf8e459 Master_2nd_commit
b1bb685 Master_1st_commit

