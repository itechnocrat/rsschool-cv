# rsschool-cv

## IVAN PROKOFYEV

Russia, Moscow

**email**: <ivan.prokofyev@gmail.com>  
**Discord**: `itechnocrat#3013`

Out of curiosity, I study various technologies.  
I love learning and discovering new things!

TECHNICAL SUMMARY:

<pre>
HARDWARE:  
    Ethernet (10, 100, 1000), Wi-Fi: routers, switches, access points; Intel x86 computers and all peripheral equipment.
    WAGO PLC, EIB/KNX equipment, Z-Wave equipment.
    AVR MCU: ATmega, ESP, STM, RasperryPi.

OPERATION SYSTEM:
    Linux: Ubuntu, Ubuntu Server and Arch, MS Windows, MikroTik RouterOS.

SOFTWARE:
    Apache, MySQL, Oracle VM VirtualBox, Vagrant, Docker, Git, CMS/CMF: WordPress, Drupal; LVM2, SSH, SMB, FTP-servers, NFS, programmable RAID, Firewall (netfilter + iptables), VPN:WireGuard; WarCoDeSys v2, Arduino, PlatformIO.

LANGUAGES:
    Some experience: Shell, Pascal, Assembler (Intel x86), С, С++, PHP, Java, Python, SQL, Lisp, Haskell, JS.
                     IEC 61131-3 Programming Languages.
OTHERS:
    LibreOffice, Inkscape, GIMP, Open Source Gantt Chart Software for Linux: GanttProject, ProjectLibre; Trello (Canban), Evernote, CAD systems.

SKILLS:
    10-finger blind typing on layouts "Dvorak for programmers" и "Russian Typewriter".
</pre>

SOME OF MY PROJECT:

```c++
#include <Bounce2.h>
/* Arduino */
/* https://github.com/itechnocrat/i8to4/blob/master/i8to4.ino */

int input[] = {0,1,2,3,8,9,10,11};
int output[] = {4,5,6,7};
int j;
bool first_entry;
bool value_input;
Bounce *ptr_debouncer[8];

void setup() {

  for(int j=0; j<4; j++){
    pinMode(output[j], OUTPUT);
  }

  for(int j=0; j<8; j++){
    pinMode(input[j], INPUT_PULLUP);
  }

  for(int j=0; j<8; j++){
    ptr_debouncer[j] = new  Bounce();
    (*ptr_debouncer[j]).attach(input[j]);
    (*ptr_debouncer[j]).interval(10);
  }

  first_entry = true;

  j = 0;
}

void loop() {

  if( (*ptr_debouncer[j]).update() || first_entry ) {
    value_input = (*ptr_debouncer[j]).read();
    if ( j < 4 ) {
      if ( !value_input ) {
        digitalWrite( output[j], !digitalRead( output[j] ) );
      }
    }
      if ( j > 3 ) {
        digitalWrite( output[j-4], !value_input );
    }
  }
  
  if ( j < 7 ) j ++;
  else {
    j = 0;
    if (first_entry) {
      first_entry = false;
    }
  }

}
```

<pre>
EDUCATION:
    Military School

COURSES:
    2014 - "Z-Wave.Me Introduction", certificate from RUSSIA traning center rus.z-wave.me
    2017 - "KNX Basic Course", JUNG traning center, certificate from "www.knx.org"

FOREIGN LANGUAGES:
Before A1 English, reading technical documentanion
Native Russian
</pre>
