# vagrantboxes


* **Vagrantfile:** base Vagrant file
* **Vagrantfile.wordpress:** Vagrant file prepared for wordpress development


####How to work

in your proyect folder
```
git clone https://github.com/enxt/vagrantboxes.git
```

if you only want a base vagrant, remove all _Vagrantfile.*_ except _Vagrantfile_

if you want any other flavour, remove all _Vagrantfile.*_ and _Vagrantfile_ except your _Vagrantfile_.**your_flavour** and rename from _Vagrantfile_.**flavour** to _Vagrantfile_

then

```
vagrant up
```

That`s all, now you can access to your VM with:
```
vagrant ssh
```
or with your favorite ssh client to: localhost port 2222



