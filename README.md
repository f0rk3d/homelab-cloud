# homelab-ansible

Some commands that I'm finding handy 
To make the modified bootable ISO image 
`sudo livefs-edit ./ubuntu-22.04.3-live-server-amd64.iso ubuntu-22.04.3-live-server.moded-netload.iso --cp /tmp/grub.cfg new/iso/boot/grub/grub.cfg`

To Write it 
`sudo dd bs=4M if=./ubuntu-22.04.3-live-server.moded.iso of=/dev/sdh conv=fdatasync status=progress`

And I went ahead and made that call to bomb.localdomain:3003 and I'm just using the python webserver 
`python3 -m http.server 3003`


## Goal... why do I do this to myself 
I'd like to be able to provision new "servers" and by server I men laptops in an automated fashion. 

I think the ultimate goal would be to have them spin up and start working a config right away.  
by having them go to a web server for their cloud-init data I can have 1 iso image configure multiple servers but all differently. 