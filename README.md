# Vagrant Homestad Mac OS
***Setup Vagrant box on Mac OS***

**Ref: https://gist.github.com/idecardo/deec25b8fa54976edb496d7ce7d320a7**

1. Download Vagrant_2.2.9 (https://releases.hashicorp.com/vagrant/)
1. Download vagrant-box-9.5.1 (https://app.vagrantup.com/laravel/boxes/homestead)


* Clone Homestead through 
    * *``git clone https://github.com/laravel/homestead.git ~/Homestead``*
* Now we have to Install Vagrant Box Manually  
  * *``vagrant box add laravel/homestead [PATH_TO_BOX]``*
  * This will install vagrant box in system
* Next step is to rename folder   
  * *``cd .vagrant.d/boxes/laravel-VAGRANTSLASH-homestead``*
    <code><pre>
        *``touch metadata_url``*
        *``echo -n 'https://app.vagrantup.com/laravel/boxes/homestead' > metadata_url``*
        *``mv 0 9.5.1``*
    </pre></code>
* If you have issue and when **vagrant up** it start downloading vagrant box do this to fix it
    * *``nano ~/Homestead/scripts/homestead.rb``*
    * On line 22 ; change 
      * *'>= 11.0' to '>=10.0'* this will according to the vagrant box you download mine was 9.5
  
  
## Download and Add Composer
* *``php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"``*
* *``php -r "if (hash_file('sha384', 'composer-setup.php') === '756890a4488ce9024fc62c56153228907f1545c228516cbf63f885e036d37e9a59d27d63f46af1d4d07ee0f76181c7d3') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"``*
* *``php composer-setup.php``*
* *``php -r "unlink('composer-setup.php');"``*
* *``mv composer.phar /usr/local/bin/composer``*