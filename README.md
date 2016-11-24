# Vagrant with docker provider on Mac OS

           
# Steps to setup:
  1. Create a new folder as your working directory for vagrant. Make sure you have all priviledges accessing to this directory.
       - $ chmod 755 (The Path of this folder) 
  2. Clone all the files in this directory.
  3. Terminal
  4. Run:
       - $ vagrant up --provision --no-parallel
  5. You will see "Thank you for using nginx.", meaning it has been successfully setup.
  6. Check the status of docker containers you just created:
       - $ vagrant global-status
  7. Directly SSH into Host VM by $ vagrant ssh 
    - Look up the docker container:
       - $ docker ps 
    - Enter the specific docker container:
    
       - $ docker exec -it (Container's ID) /bin/bash
  8. Directly SSH into the docker container by 
       - $ vagrant ssh (VM's ID)
       
         Note that (VM's ID) is shown in $ vagrant global-status

  
Note that SQL is not actually installed since I have not decided which SQL I will use. Thus it is just a normal sript validating the connection between two containers. And Vagrant itself should have supported the ansible provisioning directly without shell provisioning. However, the latest version of ansible contains some bugs that cause Vagrantfile cannot check the existance of ansible installed in containers.
