# homelab-ansible

Some commands that I'm finding handy 
To make the modified bootable ISO image 
`sudo livefs-edit ./ubuntu-22.04.3-live-server-amd64.iso ubuntu-22.04.3-live-server.moded-netload.iso --cp /tmp/grub.cfg new/iso/boot/grub/grub.cfg`

This is of course after I modified /tmp/grub to allow for it to pull the cloud-init from this repo.    

To Write it 
`sudo dd bs=4M if=./ubuntu-22.04.3-live-server.moded.iso of=/dev/sdh conv=fdatasync status=progress`

And I went ahead and made that call to bomb.localdomain:3003 and I'm just using the python webserver 
`python3 -m http.server 3003`


## Goal... why do I do this to myself 
I'd like to be able to provision new "servers" and by server I men laptops in an automated fashion. 

I think the ultimate goal would be to have them spin up and start working a config right away.  
by having them go to a web server for their cloud-init data I can have 1 iso image configure multiple servers but all differently. 

Step one, modified iso image which is pulling in the cloud-init / auto install data from github.  So you boot off it, and walk away

Currently this is done through a public repo,  I need to play with it some more to see if I can get this done through a private repo
  - alternatively I could bake the init and autoinstall stuff into the iso image but I think I want to keep those independent for now.  
