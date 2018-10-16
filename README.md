# Advanced_Bash_Homework

**By : Erica P da Silva Correia**

#### Description :

You have been asked to fix a website that has some error in it. You have been given access to the files on the server.

1. The folder should only be accessible by the vagrantuser.

2. Other users should not be able to enter the directory.
3. The files in the assets folder have the wrong file extension.
4. Figure out which one is correct.
5. Search the manual for a command that will help you to rename multiple files at once.
6. The four files called puppy are an old format and need to be deleted.
7. Try to delete them with a single command.
8. He says there was a file called index.html that he tried to rename but it disappeared.
9. Try to find it and fix it.
10. The files are going to be a public.
11. The owner needs full permissions but group only need to be able read to the files

**Steps**

1. sudo chown -R vagrant site
2. chmod -R 700 site
3. cd site
4. cd images
5. file - see that they're jpgs
6. man -k rename
7. lookup how to use rename
8. rename "s/txt/jpg/g" * .txt
9. rm puppy *
10. cd ..
11. ls -a
12. mv .index.html index.html
13. chmod g+r,o+rwx *


-----

#### Tech Used :
**Virtual Box, Vagrant, Bash**

-----
##### how to download :


1. go to the github page [**https://github.com/EricaDaSilvaCorreia**](https://github.com/EricaDaSilvaCorreia)
2. Click repositories and select the repository [**Development_Environment_Lab**](https://github.com/EricaDaSilvaCorreia/Development_Environment_Lab)
3. Click 'Clone or Download'
4. Choose between **Open in Desktop**, **Download ZIP**, **Clone with SSH**, **Clone with HTTPs**

-----
##### how to run :


1. Once Cloned or Downloaded, make sure you have Virtual box and Vagrant installed on your machine.
2. If you don't have Virtual Box installed, follow this link:[**Virtual Box**](https://www.virtualbox.org/wiki/Downloads)
If you don't have Vagrant installed, follow this link: [**Download Vagrant**](https://www.vagrantup.com/downloads.html)
3. Once installed, Open your terminal and check if vagrant has been downloaded.
4. In your terminal surn the command 'vagrant init' followed by the name of the machine image you want your virtual machine to have. in this case we are running **'vagrant init ubuntu/xenial64'**
5. Once that is done running, open your vagrant file in your text editor of choice and remove the commented out code you won't need.
6. In your text editor, check if the box name is correct and save. You should see something like this :

~~~

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"

end
~~~

7. In your terminal enter the command **'vagrant up'** (depending on how many times you have run this it could take between 5 minutes to an hour).
8. Once that is done, in your terminal enter the command **'vagrant ssh'** to enter the virtual machine.
9. Still in your terminal enter the command **'sudo vagrant apt-get update && apt-get upgrade'** this will check for any updates that may have been uploaded after the version was posted and immediately upgrade.
10. Following that we will install nginx **'sudo vagrant apt-get install nginx -y'**
11. Then enter **'curl http://localhost'** to check if nginx has been installed. You should see the html of the site appear.
12. Enter the command **'ifconfig'** to get the current address of your virtual machine (inet addr).
13. Go back to the vagrant file in your text editor and inside the Vagrant.configure("2") you can add a network like so :


~~~
Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"

  config.vm.network "private_network", ip:"192.168.12.120"

end
~~~

and Save the file before going back to your terminal. this sets up ip address that you can access from your browser on your normal machine. Open a browser and enter http:// (chosen ip) to check if it works.

14. Return to you terminal and enter the command **'vagrant reload'** to allow the virtual machine to run the changes to the config file.
15. Once this is done, enter the command  **'vagrant ssh'** to enter your machine.

-----


##### Challenges :

Overall, I think the main challenge I had with this homework was to trace back the steps we had taken during the day (in which the readme and the notes we wrote earlier was very helpful). I think it was a matter of taking a step back and analysing the tasks given before diving in head-first. The bash commands were super helpful as well.

-----

##### Take-Aways :

All in all I think today was very interesting. I really liked the challenge the homework presented in terms of having to change my approach to the problem and also sort of changing my way of thinking to better understand what I had to do. Once I got into it everything else just seemed to run smoothly. The bash commands were super helpful and the homework helped cement some of the ones I wasn't all too sure about so that's great.

overall I give it a 7.5/10

-----
