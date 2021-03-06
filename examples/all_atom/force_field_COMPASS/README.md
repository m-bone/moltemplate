This directory contains some examples of all-atom simulations using the COMPASS force field.

### WARNING

This software is experimental and the force-fields and equilbration protocols have not been tested carefully by me.  There is no gaurantee that simulations prepared using moltemplate will reproduce the behavior of other MD codes.

If you notice a problem with these examples, please report it. Peer-review is the only way to improve this software (or any software).

(jewett.aij @ gmail.com)

### Limitations

The moltemplate implementation of COMPASS currently relies on the same incomplete force-field file that "msi2lmp" uses ("compass_published.frc").  Unfortunately this means that many force field parameters and some atom types (such as sp2-carbons) have not (yet) been publicly released and are not available.

### Suggestions
Currently I recommend that users should run the "cleanup_moltemplate.sh" script after running "moltemplate.sh system.lt".  Then manually check that  the "system.in.settings" and "system.in.charges" files which remain make sense.  Specifically, you must check that the angle_coeff, dihedral_coeff, bond_coeff commands are not full of zeros (in places where they should not be zero.  This is another consequence of the fact that the .FRC files I mentioned above are incomplete.)  It's a good idea to also check that the charges in the "system.in.charges" file seem reasonable (ie. not all zeros).  (There is a list of warnings at the end of the "compass_published.lt" file.  You can check to see if any of the bonds in your system are covered by these warnings.)  Later on hopefully I'll add some automated way to warn users when these problems arise, but now you should check for them manually.
