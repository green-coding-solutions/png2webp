# png2webp
A little service that converts png/jpg to webp or avif

It is quite simple actually. You either give the script `png2webp.sh` a directory or a git link. If you give it a git repo it will clone it and do the optimization in there. If you give it a directory it will obviously change everything in there.

The script takes two parameters that are optional:
- `-q int`: Which is the quality webp should use. Defaults to 80
- `-d`: This will delete all unused files. This should be fairly save to use and should be the default but I don't want to delete per default.
- `-c`: This will check if there are the strings `.png` or `.jpg` somewhere in the code. This is because quite often image names are dynamically created in code and we will currently not match these.

IMPORTANT! Please always make backup of your files. This script does not make backups it assumes you are working on git and all your files are secured! If this is not the case PLEASE make a copy of the directory before calling the script. IT WILL EDIT FILES!!!

Also please always test the result. Like everything this script is not perfect

## Install

```
git clone https://github.com/green-coding-solutions/png2webp.git
cd png2webp
chmod a+x png2webp.sh
```

## Docker

You can also use the script as a docker container.

```
docker build -t png2webp .
docker run --rm png2webp https://github.com/green-coding-solutions/website.git
```