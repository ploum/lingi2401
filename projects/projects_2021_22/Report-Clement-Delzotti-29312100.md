# Open Source contribution report

* *Author:* Clément Delzotti
* *NOMA:* 29312100
* *Year:* 2021-2022
* *Selected project:* [Cilium](https://github.com/cilium/cilium)
* *License* : Apache 2.0

## Finding a project

Knowing that the eBPF technology had peaked my interest, I was looking for a project using it. I was thinking that maybe I could even keep this project for the *Open Source project* course. After a bit of research I realized that there isn't so much project using eBPF, but *Cilium* had the advantage to have loads of *good-first-issues*, therefore I chose it for this contribution.

## What is Cilium ?

Cilium is a project leveraging eBPF to enhance Kubernetes networking. Allowing secured exchanges between pods and nodes, load balancing, better visibility on what is happening on the network layer, etc. It is written mainly in Go, using the homemade [Go Library for eBPF](https://github.com/cilium/ebpf).

## Compiling the project

This is where the fun started. I'm running a Manjaro Linux distribution on my desktop computer and an Arch Linux distribution on my laptop, and none could actually build Cilium. After a lot of unsuccessful research to find a solution, I decided to try it on Ubuntu as it is probably the most common distribution. It actually fixed my problem, even if it took me less than 10 minutes to run into an outdated package that stopped me from building Cilium. I just had to install it by hand and I could finally compile the project !

## Contacting the community

This part was actually quite easy, I found a GitHub issue with the "*good-first-issue*" label and asked if I could do it. They accepted.

## Contributing

The contribution consisted on adjusting bad castings in C that generated lots of warnings. Once I did it, and made my pull request, GitHub indicated that a test was failing. As I had no idea what this test was, I sent a message on their Slack Server asking for help. Some kind stranger explained to me that some of their tests where messed up, he simply re-run it and it passed successfully. Still, it wouldn't be enough as I apparently didn't respect the coding conventions, and therefore I had to make a second commit to fix it.

## Merge situation

Still pending, people are busy on the weekend (Contribution has been made on 26th November)