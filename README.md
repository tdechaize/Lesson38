# Lesson38
Lesson38 OpenGL (from NeHe)

Vous trouverez dans le sommaire ci-dessous les explications vous permettant de regénérer cette appliczation illustrant la possibilité d'utiliser uen fichier 
de ressources pour référencer plusieurs bitmap qu'il est ensuite possible d'animer par un mapping en OpenGL (issu du site NeHe).
Le résultat est encore une fois bluffant, car il s'agit d'animer des papillons qui semblent voleter en tombant de façon très élégante. 
Il me semble que la vitesse de la chute des papillons est proportionnelle à la taille de l'image ainsi restituée. 
Ce qui rend cette animation très poétique ... pas mal.

Un "bug" subsiste : il semblerait que le chargement des images bitmap ne fonctionne pas correctement avec le compilateur Open Watcom C/C++.
En fait, ce bug existe sur TOUTES les lecons OpenGL issues de NeHe avec ce compilateur, cer l'icône "OpenGL" n'est jamais chargée correctement 
lors de la création des applications par "CreateWindowEx". A investiguer !

## Table of contents

- [Introduction](<Introduction.md>)
  - [Accueil](<Accueil.md>)
  - [Quoi de neuf](<Quoideneuf.md>)
- [Comment démarrer une génération ?](<Commentdemarrerunegeneration.md>)
  - [Exigences du système](<Exigencesdusysteme.md>)
  - [Lancement d'une génération CB ou CMAKE](<LancementdunegenerationCBouCMAKE.md>)

Voici un résumé succinct ds possibilités d'usage de cette application :

## OpenGL Tutorial #38.

Project Name: Jeff Molofee's OpenGL Tutorial

Project Description : Resource File Tutorial

Authors Name: Jeff Molofee (aka NeHe)

Authors Web Site: nehe.gamedev.net

COPYRIGHT AND DISCLAIMER: (c)2000 Jeff Molofee

	If you plan to put this program on your web page or a cdrom of
	any sort, let me know via email, I'm curious to see where
	it ends up :)

        If you use the code for your own projects please give me credit,
        or mention my web site somewhere in your program or it's docs.

 Modified smoothly by Thierry DECHAIZE

Paradigm : obtain one source (only one !) compatible for multiple free C Compilers
    and provide for all users an development environment on Windows (64 bits compatible),
    the great Code::Blocks manager (version 20.3), and don't use glaux.lib or glaux.dll.

	a) Mingw 32 bits, version officielle gcc 9.2.0 (old !) : downloadable on http://sourceforge.net/projects/mingw/ (official) 
	b) Mingw 64 bits included in new IDE Red Panda Dev-Cpp, version gcc 10.3.0 : donwloadable on http://sourceforge.net/projects/dev-cpp-2020/
	c) Mingw 64 bits included in package Code::Blocks (version 20.03), version gcc 8.1.0 (very old !) : downloadable on http://sourceforge.net/projects/codeblocks/files/Binaries/20.03/Windows/
	d) Mingw 32 and 64 bits packagés, version gcc 11.2.0 : downloadable on  https://winlibs.com/ (and CLANG included in, 32 and 64 bits), two kits :
			- winlibs-i686-posix-dwarf-gcc-12.2.0-llvm-14.0.6-mingw-w64ucrt-10.0.0-r2.7z (32 bits)
			- winlibs-x86_64-posix-seh-gcc-12.2.0-llvm-14.0.6-mingw-w64ucrt-10.0.0-r2.7z (64 bits)
	e) Cygwin64, 32 et 64 bits, version gcc 11.3.0 : downloadable on http://www.cygwin.com/install.html (tool for install : setup-x86_64.exe)
	f) TDM GCC, 32 et 64 bits, version 10.3.0 : downloadable on http://sourceforge.net/projects/TDM-GCC
	g) MSYS2 environnement MINGW32 and MINGW64, 32 et 64 bits, version de 2022 (msys2-x86_64-20220603.exe), version gcc 12.2.0 : downloadable on https://repo.msys2.org/distrib/x86_64/msys2-x86_64-20220603.exe
	h) Visual Studio 2022, 32 et 64 bits, community edition for free : downloadable on https://visualstudio.microsoft.com/fr/thank-you-downloading-visual-studio/?sku=Community&rel=17
	i) Borland C/C++ 32 bits, version 5.5 : downloadable on https://developerinsider.co/download-and-install-borland-c-compiler-on-windows-10/
	j) Digital Mars Compiler C/C++ 32 bits version 8.57 : downloadable on http://www.digitalmars.com (the more old compiler, the more bugged, dead branch !)
	k) OpenWatcom C/C++ 32 et 64 bits, version 2.0 : downloadable on http://openwatcom.mirror.fr/ (only 32 bits version run correctly !)
	l) Lcc and Lcc64, 32 et 64 bits: downloadable http://www.cs.virginia.edu/~lcc-win32/
	m) PELLES C (only C) , 32 et 64 bits, version 11.0 : downloadable on http://www.smorgasbordet.com/pellesc/
	o) CLANG, adossé aux environnements MINGW64 et MINGW32, version 14.0.6 (version gcc 12.0.0) : downloadable on https://winlibs.com/ 
	p) CLANG, adossé aux environnements Visual Studio 2022 (+ kits Microsoft), version 15.0.1 : downloadable on https://releases.llvm.org/download.html
	q) CLANG de la version MSYS2, adossé aux environnements MINGW64 et MINGW32, version 15.0.0 (version gcc 12.2.0) : downloadable on https://repo.msys2.org/distrib/x86_64/msys2-x86_64-20220118.exe
	r) CLANG de la version CYGWIN, adossé aux environnements MINGW64 et MINGW32, version 8.0.0 (very old !) (version gcc 11.3.0) : downloadable http://www.cygwin.com/install.html (tool for install or update : setup-x86_64.exe)

  Add resource file end resource header for restitute version + icon OpenGL.ico for fun
  because versionning is important, same for freeware :-) !
