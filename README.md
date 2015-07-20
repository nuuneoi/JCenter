# JCenter
build scripts to upload artifacts to jcenter.

From In The Cheese Factory [blog post](http://inthecheesefactory.com/blog/how-to-upload-library-to-jcenter-maven-central-as-dependency/en)

# Prerequisites
Read the blog post linked above first. You need to have following properties, how to get that is described in the post.

# Personal or ownership information
- `bintrayUser` (A Bintray user name)
- `bintrayApiKey` (Bintray API key)
- `bintrayGpgPassword` (A GPG signing mechanism, and it's passphrase)
- `DEVELOPER_EMAIL` (developer email)

# Library information
- `GROUP`(Group id of your library)
- `POM_ARTIFACT_ID` (POM Artifact Id-better to keep it in lowercase)
- `POM_NAME`
- `POM_DESCRIPTION`
- `POM_URL`
- `POM_DEVELOPER_ID`
- `POM_DEVELOPER_NAME`
- `DEVELOPER_EMAIL`
- `POM_SCM_URL`

# Where should I keep these properties?
If you put these information in gradle.properties this script can read it easily.

The best place to put Personal or ownership information in system's build.gradle file, so that it does not go with source control.
For windows it's located at
C:\Users\{UserName}\.gradle\gradle.properties

For Library information it's better to create gradle.properties in your library module and put all the information there.

# Is there any example?
Yes, See [android external file writer repository](https://github.com/PrashamTrivedi/AndroidExternalFileWriter) 

# Everything is set, what should I do to upload a file in bintray.
Just open a command prompt, cd to your library directory and run
`..\gradlew clean build bintrayUpload`
