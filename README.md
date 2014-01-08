HubDrop.io Development
======================

Welcome to hubdrop/development. This repo will serve to assist developers and 
host issue tracking.

Issues
------
Issues are tracked on GitHub, in the "development" repository.

Submit and track issues with HubDrop.io here: https://github.com/hubdrop/issues/issues

Developing HubDrop
------------------

Developing hubdrop requires Git & Vagrant.  

To install Vagrant, head to [VagrantUp.com](http://www.vagrantup.com/downloads).

To install Git, head to [GitSCM.com](http://www.gitscm.com).

1. Clone the `hubdrop/vagrant` repo.

    ```
    $ git clone git@github.com:hubdrop/vagrant.git 
    $ cd vagrant
    ```
2. Run the `init.sh` script to prepare your system. 
    ```
    $ ./init.sh
    ```
    This does a few things:
  1. Clones the `hubdrop/cookbook` and `hubdrop/app` repos.
  2. Copies attributes.json.example to attributes.json.
  3. Adds the hostname and IP to your local /etc/hosts file for hubdrop.local.

3. Launch your VM.
  You can ssh into the VM easily.
    ```
    $ vagrant up
    $ vagrant ssh
    ```
4. [Open hubdrop.local](http://hubdrop.local)
  You should see the homepage for hubdrop!

5. Edit `app` and `cookbooks` source code.
  These folders are shared to the Vagrant virtual machine.

  Most code changes in `app` will be visible immediately. You might have to clear the symfony cache:
    ```
    $ sudo console cache:clear
    ```
  To apply changes to `cookbooks`, you must run `vagrant reload`.
  
