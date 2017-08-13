![Streisand Logo](https://raw.githubusercontent.com/jlund/streisand/master/logo.jpg "Automate the effect")


DoStreisand
=========

This is the Dockerized Streisand for convenience.
For users:
* Step1: Choose your cloud provider and get the api access key or server ip with ssh keys;
* Step2: run `./sted ssh-keypair-name`
         Input the accesskey and keypair name when it prompts and wait for ansible to do all the boring things for you！
* Step3: Finally, use your browser to open the docs in ./docs/*.html and follow the instructions.
         If you don't have an openssh keypair in advance, then you may check the auto-generated one in ./sshkey
         Or run `ssh-keygen -t rsa -b 4096 -f ~/.ssh/id_rsa.pem -N 'passphrase'` in advance to create one in ~/.ssh;

For builders:
* Step1: Edit the Dockerfile to suit your appetites;
* Step2: run `./buildscript` to prepare your image;
* Step3: Choose your cloud provider and get the api access key;
* Step4: run `./sted ssh-keypair-name`
         Input the accesskey and keypair name when it prompts and wait for ansible to do all the boring things for you！
* Step5: Finally, use your browser to open the docs in ./docs/*.html and follow the instructions.
         If you don't have an openssh keypair in advance, then you may check the auto-generated one in ./sshkey
         Or run `ssh-keygen -t rsa -b 4096 -f ~/.ssh/id_rsa.pem -N 'passphrase'` to generate one into ~/.ssh;

[Streisand](https://github.com/jlund/streisand)
=========

**Silence censorship. Automate the [effect](https://en.wikipedia.org/wiki/Streisand_effect).**

The Internet can be a little unfair. It's way too easy for ISPs, telecoms, politicians, and corporations to block access to the sites and information that you care about. But breaking through these restrictions is *tough*. Or is it?

