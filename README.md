# UCSDUnfoldingMaps
UCSD Unfolding Maps Java/Maven

A modified version of the official UCSD provided zip on Coursera. The source is unchanged, 
however the project has been 'Maven-fied'! - so there is an additional pom.xml file. 

The intention is to make this available as a cross-platform, IDE independant distribution (as the UCSD provided one
on Coursera is Eclipse based and lots of people seem to be having issues with dependencies). Further those wishing to
learn about developing in Java will generally benefit from learning about Dependancy Management tooling like Maven.

You need to install maven (version 2 or 3) and import the project into your IDE of choice (Eclipse/Intellij/etc/etc)

Maven will now handle all the dependency management for you.

There is one caveat! Unfoldingmaps.org do not as yet have a maven artfiact of the jars available. Therefore, you must
install the following jars from the /externaljars folder into your local maven repository:

- Unfolding.jar (unfoldingMaps version 0.9.6)
- json4processing (unfoldingMaps version 0.9.6)

MD5 hash values for the files in /externaljars folder: 

MD5 (Unfolding.jar) = adf9454823d1b656027deccca027e960
MD5 (Unfolding_for_processing_0.9.6.zip) = 5c0d5bdeb1c61535e7fa624bc79388ea
MD5 (json4processing.jar) = 3f097ab4458261482518ffa2229ca857

you can alternatively download and extract from the unfoldingmaps.org site directly:

https://github.com/tillnagel/unfolding/releases/download/v0.9.6/Unfolding_for_processing_0.9.6.zip

then extract the zip and use the above two named jars from the ./library folder.

The maven command line to install into your local repo is: (assuming your jars are in the current working directory/folder)

mvn install:install-file -Dfile=./Unfolding.jar -DgroupId=org.unfoldingmaps -DartifactId=unfolding -Dversion=0.9.6 -Dpackaging=jar
mvn install:install-file -Dfile=./json4processing.jar -DgroupId=org.unfoldingmaps -DartifactId=json4processing -Dversion=0.9.6 -Dpackaging=jar

Please note, you will need to be familiar, or become familiar with Maven. The same goes for your flavour of IDE.

POLITE NOTICE: DO NOT post issues that are not DIRECTLY related to the Maven POM or mavenised folder structure here,
that is all that is being managed. Any other issues need to be posted back on the MOOC @Coursera. I hope you understand ;)

If anyone wants to add other DM files from other tools, eg Ivy, Gradle, etc, Im happy to add them!

ENJOY!
