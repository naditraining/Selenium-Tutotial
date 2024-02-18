## Why Maven

  Here are some reasons why Maven is commonly used for Java projects and other software development:
  
  Dependency Management: Maven simplifies the process of managing project dependencies.
  It allows you to specify the libraries and frameworks your project depends on, and it automatically downloads and includes them in your project's build.
  
  Project Structure: Maven follows a standard project structure, making it easier for developers to understand and navigate the codebase. 
  This standardization helps maintain consistency across different projects.
  
  Build Lifecycle: Maven defines a standard build lifecycle with common phases such as compile, test, package, install, and deploy. 
  Developers can execute these phases to build, test, and package their projects without having to manually configure each step.
  
  Plugin Architecture: Maven has a rich plugin architecture, allowing developers to extend its functionality easily. 
  There are plugins for various tasks, such as generating documentation, code analysis, and deployment.
  
  Central Repository: Maven central repository is a centralized repository where Maven can automatically download dependencies. 
  This helps in reducing the effort required to manage external libraries.
  
  Convention over Configuration: Maven promotes convention over configuration, meaning that it makes certain assumptions about project structure and configuration. 
  This reduces the amount of configuration developers need to write, making the build process more straightforward.
  
  Reproducibility: Maven builds are designed to be reproducible on different environments. 
  This ensures that the build process is consistent across development, testing, and production environments.
  
  Integration with IDEs: Maven integrates well with popular integrated development environments (IDEs) such as Eclipse and IntelliJ IDEA, making it easier for developers to work with Maven projects in their preferred development environment.

## Maven life cycle

  These are the different functions in Maven for a development project. Testing team can use test to run the tests.
  
  validate:
  Validates the project configuration.
  
  compile:
  Compiles the source code of the project.
  
  test:
  Runs tests using a suitable unit testing framework. The testing phase is important for ensuring the quality of the code.
  
  package:
  Takes the compiled code and packages it into a distributable format, such as a JAR, WAR, or EAR file.
  
  verify:
  Runs checks on the packaged artifact to ensure it meets certain quality criteria.
  
  install:
  Installs the packaged artifact into the local Maven repository, making it available for other projects on the same machine.
  
  deploy:
  Copies the final package to the remote repository for sharing with other developers or projects.


## how to install maven
### MAC OS
    brew update
    brew install maven
    mvn -v

### Windows 
    download the latest binary zip archive from https://maven.apache.org/download.cgi
    extract the contents of the zip archive to a directory C:\Program Files\Apache\mave
    Configure Environment Variables M2_HOME and MAVEN_HOME
    Variable Name: M2_HOME
    Variable Value: Path to your Maven installation (e.g., C:\Program Files\Apache\maven
    in the system variables, edit the 'Path' variable and add the below path of bin folder - C:\Program Files\Apache\maven\bin
    verify in command prompt using the command  mvn -v

    
    
    
    


  
