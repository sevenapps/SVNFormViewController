 [![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)

# SVNFormViewController
A Form ViewController that self validates and animates errors.
<p align="center">
  <img src="/images/Setup Account.png" alt="SVNFormViewController"/>
</p>


## To use this framework
Intended to be set as a child of another ViewController.
To initialize this VC call

    init(theme:, dataSource: nibNamed:, bundleNamed:)

To validate textFields call

    validator.validate()

To be notified when all fields have been validated equate a method in the presenting class to:

    didValidateAllFields([FormFieldType: String])

Tapping Go on the return key type will attempt to validate the textFields resulting in didValidateAllFields being called if successful
When resizing this viewController make sure to resize the tableview contained within it.

## To install this framework

Add Carthage files to your .gitignore

    #Carthage
    Carthage/Build

Check your Carthage Version to make sure Carthage is installed locally:

    Carthage version

Create a CartFile to manage your dependencies:

    Touch CartFile

Open the Cartfile and add this as a dependency. (in OGDL):

    github "sevenapps/PathToRepo*" "master"

Update your project to include the framework:

    Carthage update --platform iOS

Add the framework to 'Embedded Binaries' in the Xcode Project by dragging and dropping the framework created in

    Carthage/Build/iOS/pathToFramework*.framework

Add this run Script to your xcodeproj

    /usr/local/bin/carthage copy-frameworks

Add this input file to the run script:

    $(SRCROOT)/Carthage/Build/iOS/pathToFramework*.framework

If Xcode has issues finding your framework Add

    $(SRCROOT)/Carthage/Build/iOS

To 'Framework Search Paths' in Build Settings
