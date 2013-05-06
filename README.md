ansible-library-extra
=====================

Extra modules for ansible. Home for modules that are not accepted upstream.


Modules
=======

  * dpkg_reconfigure: reconfigure a Debian package

_A number of questions has to be answered (depending on the package).
Use 'DEBIAN_FRONTED=editor dpkg-reconfigure $pkg' for finding them._


    # Set default locale to fr_FR.UTF-8, and generate en_US.UTF-8 as well:
    dpkg_reconfigure:
       pkg: locales
       answers:
           locales/default_environment_locale: fr_FR.UTF-8
           locales/locales_to_be_generated: en_US.UTF-8 UTF-8, fr_FR.UTF-8 UTF-8
    
    # Reconfigure roundcube, using configuration answers stored in a file:
    dpkg_reconfigure: pkg=roundcube answers='$FILE(/path/dpkg-reconfigure/roundcube)'
