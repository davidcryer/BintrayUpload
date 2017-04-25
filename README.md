# BintrayUpload
Gradle script allowing for installation of project on maven repository and uploading artefacts to Bintray

Usage example:

Add the following to your module gradle file:

<pre>
ext {
    packagingFormat = 'aar', 'jar', etc
    groupPath = 'com.helloworld.project'
    artifactName = 'project'
    libraryName = 'Project'
    libraryDescription = 'Project description'
    gitWebsiteUrl = 'https://github.com/helloworld/Project'
    gitUrl = 'https://github.com/helloworld/Project.git'
    licenseArray = ['Apache-2.0']
    licenseName = 'Apache License, version 2.0'
    licenseUrl = 'http://www.apache.org/licenses/LICENSE-2.0'
    developerId = 'helloworld'
    developerName = 'Hello World'
    developerEmail = 'helloworld@gmail.com'
    mavenRepoName = 'maven'
    libraryVersionCode = 1
    versionTag = '0.0.1'
    versionDescription = 'Version 0.0.1'
}
</pre>

and put this at the end of the file:

<pre>
apply from: 'https://raw.githubusercontent.com/davidcryer/BintrayUpload/master/upload.gradle'
</pre>

You will also need to add these inside the buildscript dependency block in your project's gradle file:

<pre>
classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.7.3'
classpath 'com.github.dcendents:android-maven-gradle-plugin:1.5'
</pre>

To install the project to your local Maven and upload in to your maven repository on Bintray, use the following commands after cd'ing to your project's root directory:

<pre>
./gradlew install
./gradlew bintrayUpload
</pre>
