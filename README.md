# directory-project

This is a docker-based app that provides a REST API allowing the client to build a directory structure and save files within it. Done as a personal project / creative exercise to learn some technologies that are new to me.

## Contents

 1. App Summary
 2. Code Highlights

## 1. App Summary

The directory-project is the name for 4 services and a common java library which together provide an application deployable with docker

**directory-service** : provides REST api for directory operations, uses solr backend  
**user-service** :  supports distributed authentication model by storing the session token in a redis cache, allowing other services to verify incoming requests efficiently  
**project-sdk** : library containing common utilities  
**Solr**  : used to persist directory data  
**Redis** : used in distributed authentication model  

This app also utilises a project repository for storing common artefacts, another repo for deploying with docker and docker-compose, and GitHub actions to perform tests and analyse code quality with Sonar.  

## 2. Code Highlights

Custom authentication filter [here](https://github.com/bcollins92/user-service/blob/main/src/main/java/com/bc92/userservice/authn/CustomUsernamePasswordAuthenticationFilter.java)  
REST API for files [here](https://github.com/bcollins92/directory-service/blob/main/src/main/java/com/bc92/directoryservice/restapi/FileController.java) and service layer [here](https://github.com/bcollins92/directory-service/blob/main/src/main/java/com/bc92/directoryservice/service/FileService.java)  
REST API for folders [here](https://github.com/bcollins92/directory-service/blob/main/src/main/java/com/bc92/directoryservice/restapi/FolderController.java) and service layer [here](https://github.com/bcollins92/directory-service/blob/main/src/main/java/com/bc92/directoryservice/service/DirectoryService.java)  
Rich domain model for directory structure [here](https://github.com/bcollins92/directory-service/blob/main/src/main/java/com/bc92/directoryservice/model/Directory.java)  
