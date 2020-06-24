# Git Hook Installation Instructions

## Git Pre-Commit Hook
These following described how to install a custom Pre-Commit hook into Git
that translates and serializes ontology files with .rdf, .owl, .ttl into an
RDF/XML file with a DTD to so that prefixes can be utilized.

The translation/serialization utilizes the RDF-ToolKit jar file to perform the translation.  Documentation on the command line switches can be found at 
https://github.com/edmcouncil/rdf-toolkit.

### Requirements
 * Java SE 1.7 or later
 * [RDF-Toolkit](https://jenkins.edmcouncil.org/job/rdf-toolkit-build/lastSuccessfulBuild/artifact/target/scala-2.12/rdf-toolkit.jar)

### Installation Steps
1. Install Java SE, if it is not already installed
2. Clone the GitHub repository
3. Copy pre-comment file in this directory to the /.git/hooks folder
4. Download the RDF-Toolkit jar files into the /.git/hooks folder
5. set JAVA_HOME in the script executed a login
	* **Windows**

		create a login.bat in your user directory that contains the definition for
		JAVA_HOME that points to the location of the installation of the Java SE
	
	* **Unix**	

		create a ~/bashrc file which contains the definition for JAVA_HOME hat points to the location of the installation of the Java SE