

# Kernel tree


Mainline kernel
First of all: don't use that github link (it's just a mirror). The actual repositories are located at kernel.org. You probably want to use Linus Torvalds' tree, which is torvalds/linux.git.

It's called mainline kernel, which means this tree is the one where actual development of next kernel version is happening. Although it has only master branch, you can checkout to any kernel version using tags. This command will show you all version tags:

$ git tag
You can checkout to desired tag like that:

$ git checkout v4.0
There is no need in a bunch of branches for mainline kernel, as development process in this tree never stops, and once new version is released, there won't be any back-porting to that version (inside mainline tree). So Linus sticks to tags (instead of branches) in this case.

Stable kernel
There is also linux-stable tree. "Stable" means that after release, some bug fixes would be back-ported to it. In this tree you should look for branches (rather than tags):

$ git branch -a
You can see branches like:

linux-4.9.y
where y suffix is just a placeholder for a bugfix version (because naming scheme is linux-4.x.y). Whenever you see y suffix -- it's a stable kernel branch. Some of those branches are LTS kernels (read this for details).

In this case branches are needed because developers have to backport some bug fixes into released versions. So just tags are not enough here.

Next kernel
It also should be mentioned that there is linux-next tree. Here is the description from kernel process documentation:

Before updates from subsystem trees are merged into the mainline 4.x tree, they need to be integration-tested. For this purpose, a special testing repository exists into which virtually all subsystem trees are pulled on an almost daily basis:

https://git.kernel.org/?p=linux/kernel/git/next/linux-next.git

This way, the -next kernel gives a summary outlook onto what will be expected to go into the mainline kernel at the next merge period. Adventurous testers are very welcome to runtime-test the -next kernel.

Maintainer trees
Back to the trees. Actually there are many of them, they are called maintainers trees. You can see all of them here.

You need to understand merging policy: only Linus can actually merge code to the mainline tree. You can see a lot of merge commits from him in git log. So if you want your patch to be applied to mainline kernel, you need to send it to kernel mailing lists for review first. See Documentation/SubmittingPatches. Once your patch is reviewed and acknowledged by corresponding subsystem maintainer, he will apply it to his own tree. From there this patch will be merged to mainline kernel during next merge window. Linux kernel development model is described here.


- https://stackoverflow.com/a/30268416/4387991
- https://www.kernel.org/category/faq.html


About the kernel naming.

The Linux main branch is separated with stable branch.

The main kernel tree has only one branch, master.

All other maintained parts are in linux-stable tree.

- https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git/

We mirrored that tree locally at `git@code:pica8/linux.git`

Most of time we sync from a fast mirror nearby `https://mirrors.tuna.tsinghua.edu.cn/help/linux-stable.git/`

The `.y` suffix is convention for a stable branch, coming from the main.x.y naming with `.y` for bugfix version.


v3.16.7 had been the last 3.16 stable release from official maintainer Greg KH.

But the Canonical Kernel Team(-ckt) then had been providing maintenance after that as 3.16.y-ckt branch, for 2 more years.

- https://lkml.org/lkml/2014/10/30/649

Until latest 3.16.y-ckt:
- http://kernel.ubuntu.com/git/ubuntu/linux.git/log/?h=linux-3.16.y

Also:
- https://git.launchpad.net/~canonical-kernel/linux/+git/linux-stable-ckt/log/?h=linux-3.16.y

As Extended Stable:
- https://wiki.ubuntu.com/Kernel/Dev/ExtendedStable

Ben Hutchings, official Debian Kernel maintainer,
- https://salsa.debian.org/kernel-team/linux

Provides extra maintenance till 2020.
- https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git/log/?h=linux-3.16.y



For example, official 3.16 stable kernel is 3.16.56, with the meltdown fixes.

    remotes/origin/linux-3.16.y   a413cc78bc64 Linux 3.16.56


See also
- http://kroah.com/log/blog/2018/02/05/linux-kernel-release-model/

