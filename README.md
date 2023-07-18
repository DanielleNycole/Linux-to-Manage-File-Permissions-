# Linux-to-Manage-File-Permissions
<h2>Description</h2>

I was tasked with reviewing and setting file and sub directory permissions within Linux for a fictional organization. This was to ensure those that are authorized to access files and directories are the only ones allowed to in order to help secure the system a little more. I examined the current file permissions and adjusted according to the requests of the organization.  <br/>

First, I reviewd the current file permissions in the project directory:  <br/>
<p align="center">
<img src="https://lh3.googleusercontent.com/pw/AIL4fc8iK_IZIOxfr_dpM77pxzCGLmpETMz7CW2I5DfAHQRT4GB4jTLNM_6TTnPo3-Lp8eTFZFKA67j_dzzdlxovhTGaq3EoQYsjBOtxfD-FZHb2fQqmRKLVGA4bprNTODJxmeIE1xP4l5J_a3vI5JknWh0=w627-h87-s-no?authuser=0" height="80%" width="80%" alt="reviewed the correct directory"/>
<br />


I then used ls -la to show all the files and subdirectories in the project directory what what the permissions were currently set to. <br/>
<p align="center"> 
<img src="https://lh3.googleusercontent.com/pw/AIL4fc8ncAI4z90TlADtKd44vCeYOxdBRpsjsoBnU0VUzEKdk6E1vd3YNQb1RGsuRr0RUICCuOtobyOGcE5BlGDeoJuj7qUOYbCgOc1Gk26vTESScvXozPntwd3apN6DouQ8T13ZrnCkv6XTiSh4EaIfqy8=w731-h215-s-no?authuser=0" height="80%" width="80%" alt="Reviewd file and directory permissions"/>
<br />

The current User Permissions were set as follows:  </br>

Project_k.txt 
  - User = read, write 
  - Group = read, write 
  - Other = read, write 

Project_m.txt
  - User =read, write  
  - Group=read 
  - Other= none 

Project_r.txt
  - User = read, write 
  - Group = read, write  
  - Other = read

Project_t.txt
  - User = read, write
  - Group = read, write
  - Other = read

.project_x.txt
  - User = ead, write
  - Group = write
  - Other = none

Drafts
  - User = read, write, execute
  - Group = execute
  - Other = none

The organization did not want “other” to have write access to any files. Which means Project_k.txt needed to be updated accordingly. I used the command chmod o-w project_k.txt to perform this task
<p align="center"> 
<img src="https://lh3.googleusercontent.com/pw/AIL4fc_9cXn3puXuyb3RbbXGwfbCpjFB2U0OTlb00ESWRPrZ9YJu_p0Zj3BjRYzj8oqz6OV7TCabbsMSp6wlzeGY05zn4mxgJj9ZMTgR_QiYWun5yKillJyRRemL4WkFMtOZ0JCjBvM9AIDa1x_RmsxkjRs=w576-h29-s-no?authuser=0" height="80%" width="80%" alt="chmod o-w"/> 
<br />
  
  <br />
<img src="https://lh3.googleusercontent.com/pw/AIL4fc8mBY6dmtQidfvoxBi-B668S3moTbHn9sbLkTzaJONz2ll-Q0W79dZLFabIMV-daNzL1Y-ZRm_C22yXAgeo6bAK_JnjtvVD7Kq96JDDh42XtiV2mdO78NkVbwtEWz3hpRHcR2OjeZZMxW_e1cq-Q0U=w652-h190-s-no?authuser=0" height="80%" width="80%" alt="Reviewd file and directory permissions 2"/>

Additionally, .project_x.txt should not have write permissions for anyone, but the user and the group should be able to read the file. I used chmod u-w,g-w,g+r .project_x.txt to remove the writer permissions from the user and the group, and add read permissions for the group. 
<p align="center"> 
<br />
<img src="https://lh3.googleusercontent.com/pw/AIL4fc_IK_jVudwWpokee_BY6b0XoTx7y4_hgxY2UONRAnYrdbnkPocZEMdX0n1jDbnGMYaonsud0tEZ2bKLuqWyJqkDF53dO6GcRDNNVji2BjMNAKyfjDu6d745IYAuWnKUh70dmkE4eUxTKzz91YN6zwuo=w663-h28-s-no?authuser=0" height="80%" width="80%" alt="chmod u-w,g-w,g+r"/>

<br />
<img src="https://lh3.googleusercontent.com/pw/AIL4fc8aLVJoJYlPBCm6BthJnzuE-pRCuxQOmeRhpDLQ6iFJzQM4yvcP9QHOjIPaFoP4PBeZm0NxQVFsOa1iWUOL-zmNWnPmjecSe7eGHyeLq6_DZKRxs8irZ40ab3V17U_j11PKRwi3P9J7ETkZTp7zndO_=w664-h208-s-no?authuser=0" height="80%" width="80%" alt="user and group should be able to read"/>

For the draft subdirectory, only researcher 2 should be allowed to access the drafts directory and its contents. 

So while logged in as researcher2, the user permissions should be set, and the group permissions removed. I used chmod g-x drafts to remove the only permission set for the group and ensure the user was the only one with permissions. 

<p align="center"> 
<br />
<img src="https://lh3.googleusercontent.com/pw/AIL4fc-tc_caswd679NR1nmWwx9QMakuxzBOuKciVSDHjJaDICKe7YDy3ejvajyZizARg9Y4j4IZCLJ77LliUmRAW82kSfUY4wXNo_uV0T7QxS8nV8Ybe1BMjaq__BMs4FOuOipWB2V-j-UFf_QK2B-0FVEv=w516-h30-s-no?authuser=0" height="80%" width="80%" alt="chmod g-x"/>

<br />
<img src="https://lh3.googleusercontent.com/pw/AIL4fc-SOpsRnaahmzlxVgmlOMm-wxlnFHd5KxbRZVFnJSfLRFufdUNyZvo4K-BfdZ45brffnAVs_2X7qlmCw-w_9ezXl3T0LA81P3YqslEEuZ8l1hB0Im7W28QOUht_8itdiKgR4yxx2MFyKb0RoKoFyBad=w719-h209-s-no?authuser=0" height="80%" width="80%" alt="only user"/>

<h2>Summary</h2>

I updated the permissions to match the authorization that was requested by the organization. By listing out the permissions set for all files, including the hidden ones, I was able to assess what permissions were currently set, and what needed to be updated to make sure only those authorized to access the files and directories could do so. 
