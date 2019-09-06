# Using Dell Boomi Atom on Mac OS

The Dell Boomi Atom can be installed on Window, Linux, Docker, PCF or Kubernetes (see [link]: https://github.com/anthonyrabiaza/BoomiKubernetes/	"Kubernetes") and also on an Apple computer.

**Please note that this is not supported and the steps are provided only for information**



These are the steps required:

1. Install Oracle JDK 8 from Oracle website. After the installation, the default location (depending on the version) will be /Library/Java/JavaVirtualMachines/jdk1.8.0_*version*.jdk . 

   For instance  /Library/Java/JavaVirtualMachines/jdk1.8.0_221.jdk 

2. Install the Atom by downloading the Linux-64bits version and getting a token

```
$ chmod u+x atom_install64.sh 
$ ./atom_install64.sh
(...)
Please read the following important information before continuing.

The following will be installed when you choose to continue:

Atom - MacBookPro55
Installation Directory -
/Applications/Boomi_AtomSphere/Atom/Atom_MacBookPro55
Program Group - Boomi AtomSphere\Atom - MacBookPro55

[Enter]

Retrieving Build Number
Extracting files...

Downloading JRE Files
Unpacking JRE Files
Downloading Atom Files
Retrieving Container ID
Retrieving account keystore.
Retrieving account trustore.
Configuring Atom.
The Atom has been installed on your computer.
Atom Name: MacBookPro55
Preferred JVM: /Applications/Boomi_AtomSphere/Atom/Atom_MacBookPro55/jre
Finishing installation...

```

3. Update pref_jre.cfg with the path of the freshly installed JDK/JRE

```
$ vi /Applications/Boomi_AtomSphere/Atom/Atom_MacBookPro55/.install4j/pref_jre.cfg

/Library/Java/JavaVirtualMachines/jdk1.8.0_221.jdk/Contents/Home/jre
```
4. Backup unpack200

```
cp /Applications/Boomi_AtomSphere/Atom/Atom_MacBookPro55/jre/bin/unpack200 /Applications/Boomi_AtomSphere/Atom/Atom_MacBookPro55/jre/bin/unpack200.bak
```
5. Copy unpack200 from the freshly installed JDK/JRE
```
cp /Library/Java/JavaVirtualMachines/jdk1.8.0_221.jdk/Contents/Home/jre/bin/unpack200 /Applications/Boomi_AtomSphere/Atom/Atom_MacBookPro55/jre/bin/unpack200 
```
6. Run the Atom

```
$ ./atom start
Preparing JRE ...
Starting atom
```

7. Connect to AtomSphere and validate that the Atom is RUNNING (blue icon)