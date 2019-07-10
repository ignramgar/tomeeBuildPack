TomEE build pack
================

This is a build pack bundling Java 7, Maven and TomEE for Heroku apps.

## How to use

Create your project

    heroku create tomee-project 
    heroku config:add BUILDPACK_URL=https://github.com/Filirom1/heroku-buildpack-tomee.git
    git push heroku master

You should see in the logs :

    Counting objects: 15, done.
    Delta compression using up to 2 threads.
    Compressing objects: 100% (11/11), done.
    Writing objects: 100% (15/15), 5.02 KiB, done.
    Total 15 (delta 2), reused 0 (delta 0)

    -----> Fetching custom git buildpack... done
    -----> TomeEE app detected
    -----> Installing OpenJDK 1.7...done
    -----> Installing Maven 3.0.3...
    -----> Installing settings.xml... done
    -----> executing /app/tmp/repo.git/.cache/.maven/bin/mvn -B -Duser.home=/tmp/build_j8pc1ulwz0xo -Dmaven.repo.local=/app/tmp/repo.git/.cache/.m2/repository -s /app/tmp/repo.git/.cache/.m2/settings.xml -DskipTests=true clean install
    [INFO] Scanning for projects...
           [INFO]                                                                         
           [INFO] ------------------------------------------------------------------------
           [INFO] Building webappRunnerSample Maven Webapp 1.0-SNAPSHOT
           [INFO] ------------------------------------------------------------------------
           Downloading: ....
           [INFO] ------------------------------------------------------------------------
           [INFO] BUILD SUCCESS
           [INFO] ------------------------------------------------------------------------
           [INFO] Total time: 9.891s
           [INFO] Finished at: Fri Mar 15 18:08:38 UTC 2013
           [INFO] Final Memory: 12M/490M
           [INFO] ------------------------------------------------------------------------
    -----> Bundling TomEE version 1.5.1
    -----> Discovering process types
           Procfile declares types -> web

    -----> Compiled slug size: 85.0MB
    -----> Launching... done, v5
       http://tomee-project.herokuapp.com deployed to Heroku

Enjoy ;)

