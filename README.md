# Boot-logo
This project is used to change the current logo animation of our **linux OS** to our custom logo animation

here we need to install some of the tools


1.`sudo apt install plymouth`

2.`sudo apt install plymouth-themes`

3.`sudo apt install plymouth-xll`

4.`sudo apt install firmware-linux`

After running above commands lets see the default theme

`plymouth-set-default-themes`

You will see the Name of the theme

you can also see the preview of theme by
`sudo plymouth-preview`


when You clone the project you will able to see `.plymouth` and `.script` file

you also see the set of images that is nothing but the `.gif` converted into `.png`

to convert `.gif` to `.png` you have to install `ffmpeg` tool

after installing `ffmpeg` you have to write following command

`ffmpeg -i ./yourfile_name.gif ./progress-%01d.png`

now open the `.script` file and go to line number *31* 

```diff
- for (int i = 0; i < 89; i++)
+ for (int i = 0; i < number-of-png-that-Has-been-created ; i++)
```

after doing all these make sure that u have directory name `xyz` inside that u have all the files

copy the `xyz` directory to `/usr/share/plymouth/themes/`

`sudo cp -r xyz /usr/share/plymouth/themes/`

to see the all the themes 

`plymouth-set-default-theme --list`

to make `xyz` as new theme

`sudo plymouth-set-default-theme -R xyz`

to see the preview `sudo plymouth-preview`

now reboot the system you will able to see ur custom theme

