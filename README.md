# KDE service menus for video file converting

KDE service menus for video file converting to the common video formats
MP4 or WebM. The encoding specifications are chosen for wide compatibility and
good tradeoff between encoding speed and size.

The conversion is done using FFmpeg. If available, hardware encoding with VAAPI
will be used.

## Prerequisites

* [KDE](https://www.kde.org/)
* [FFmpeg](https://www.ffmpeg.org/)
* [BC](https://www.gnu.org/software/bc/)

## Installation (Plasma 5)

Install the requirements (Arch Linux):

    sudo pacman -S ffmpeg qt5-tools bc

For hardware encoding support on Intel CPU:

    sudo pacman -S intel-media-driver libva-intel-driver libva-utils

To install system wide:

    sudo cp ServiceMenus/* /usr/share/kservices5/ServiceMenus/
    sudo cp bin/videoconvert-kdialog /usr/local/bin/

Per user installation:

    cp ServiceMenus/* ~/.local/share/kservices5/ServiceMenus/
    cp bin/videoconvert-kdialog ~/.local/bin

In that case the directory `~/.local/bin` has to be be placed in the search path
environment variable `$PATH`.
E.g. for a Fish shell you can simply call `fish_add_path ~/.local/bin`.

Finally you need to restart your plasma session or call:

    kbuildsycoca5

## Uninstall

System wide installation:

    sudo rm /usr/share/kservices5/ServiceMenus/videoconvert.desktop.desktop
    sudo rm /usr/local/bin/videoconvert-kdialog

Per user installation:

    rm ~/.local/share/kservices5/ServiceMenus/videoconvert.desktop.desktop
    rm ~/./local/bin/videoconvert-kdialog

## Contributing

Pull requests are welcome. For major changes, please open an issue first to
discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[GPL-3.0+](https://www.gnu.org/licenses/gpl-3.0.de.html)
