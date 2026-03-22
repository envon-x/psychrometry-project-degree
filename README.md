


For Latex inside Inkscape: Install TexText extension
Install texlive:
download and install inkscape:

Ensure python installed with: which python3
Ensure python command with: sudo ln -s /usr/bin/python3 /usr/bin/python

$ rm ~/.config/textext/.cache.json
cd <...>/textext-1.8.2
Install texTex with: python3 setup.py --pdflatex-executable=$(which pdflatex)

On Windows:
Ensure python command with: mklink C:\Windows\System32\python.exe C:\Python38\python.exe


APA 7 style Font for latex
Ensure install the package: 
to use:
install: 
sans serif fonts such as 12-point Aptos, 11-point Calibri, 11-point Arial, or 10-point Lucida Sans Unicode
serif fonts such as 12-point Times New Roman, 11-point Georgia, or normal (10-point) Computer Modern (the default font for LaTeX)

On main.tex
\usepackage{fontspec}
\setmainfont{Times New Roman} % O Georgia

setup available fonts:
If your system uses a DEB822 file such as /etc/apt/sources.list.d/debian.sources, add contrib to the Components: line:

sudo sed -i '/^Components:/ {/\bcontrib\b/! s/^Components: main/Components: main contrib/}' /etc/apt/sources.list.d/debian.sources
If your system still keeps the Debian mirrors in /etc/apt/sources.list, add contrib there instead:
sudo sed -i '/^deb / {/\bcontrib\b/! s/ main/ main contrib/}' /etc/apt/sources.list

sudo apt update
apt-cache policy ttf-mscorefonts-installer

4. Actualiza el caché de fuentes ￼
Para que aplicaciones como Inkscape y TexText las reconozcan de inmediato:
bash
sudo fc-cache -f -v
To use MS fonts inside Inkscape with texText
$ python3 setup.py --xelatex-executable=$(which xelatex)


¿Cómo verificar que funcionó?
fc-list | grep "Times New Roman"
Helpers pages:
https://www.codegenes.net/blog/how-to-make-python3-command-run-as-well-as-python/


MS fonts on linux:
https://linuxcapable.com/how-to-install-microsoft-fonts-on-debian-linux/


# Export .svg to .pdf
cd to the .svg  file folder content
$ inkscape -D Psychrometry_Process.svg -o Psychrometry_Process.pdf --export-latex