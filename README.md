# RFIDEncoderOSX
RFIDEncoder framework for OSX, includes Converter.

TPM - 3/3/19

Refactored EPCEncoder into RFIDEncoder and included all the sub encoders (EPCEncoder, TCINEncoder, and TIAIEncoder), as well as the converter, in the umbrella header.

- EPCEncoder - encodes UPCs in GS1 compliant EPC encodings
- TCINEncoder - encodes retail TCINs in non GS1 compliant RFID tags for Target internal use only
- TIAIEncoder - encodes non retail TIAIs in non GS1 compliant RFID tags for Target internal use only

To include these, you now need to use the following construct:

    #import <RFIDEncoder/EPCEncoder.h>
    #import <RFIDEncoder/TCINEncoder.h>
    #import <RFIDEncoder/TIAIEncoder.h>
    #import <RFIDEncoder/Converter.h>

Or for them all:

    #import <RFIDEncoder.h>


IMPORTANT NOTE: When you add this framework to another project, make sure you include it in one of the following:
- Project Target --> General --> Embedded Binaries
- Build Phases --> Embed Frameworks


TPM - 3/2/19

### PROJECT SETUP NOTES

I created this as a clean Cocoa Framework for OSX using the latest version of XCode and the default OSX framework project template.  This framework is only used for GeniTag on the MacOS.

IMPORTANT NOTE: all the .m and .h files in this project are identical to RFIDEncoderiOS, and should be kept in
sync.  This project is only to build the framework for the OSX architecture.

The framework is in the build subdirectory.  This version also builds the framework with every build, so the
post run scripts are a little different than the tutorial linked above and you don't have to do anything different.
