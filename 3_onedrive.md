##1.同步选项位置##
win11 22557后 在:右键菜单(未同步文件夹)
                explorer右上方,已同步
##2.mkdir 硬/软/符号链接##
>https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/create-symbolic-links

>(?)https://blog.alphatr.com/windows-mklink.html

>https://blogs.windows.com/windowsdeveloper/2016/12/02/symlinks-windows-10/
>>How to use Symlinks

Symlinks are created either using the mklink command or the CreateSymbolicLink API

mklink

There is no change in how to call mklink.  For users who have Developer Mode enabled, the mklink command will now successfully create a symlink if the user is not running as an administrator.
CreateSymbolicLink

To enable the new behavior when using the CreateSymbolicLink API, there is an additional dwFlags option you will need to set:
Value	Meaning
SYMBOLIC_LINK_FLAG_ALLOW_UNPRIVILEGED_CREATE

0x2	Specify this flag to allow creation of symbolic links when the process is not elevated
Example Use

In the example below:

A subfolder folder called “animals” containing three files (cat.txt, dog.txt, and fish.txt)
(green) The mklink command is executed to create a symlink called “pet.txt” pointing at the “animalsdog.txt” file
(blue) When the contents of the current folder are listed, the symlink can be seen (yellow)
(purple) When contents of pet.txt are queried, the content of the referenced file (“dog.txt”) is displayed