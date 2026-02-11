# Task: Resuming Jenkins Configuration for Nexus

- [x] Verify Nexus and Docker Registry are running <!-- id: 0 -->
- [x] Verify Nexus Configuration <!-- id: 1 -->
- [x] Configure Jenkins <!-- id: 2 -->
- [x] Debug Pipeline Failure <!-- id: 3 -->
    - [x] Investigate "wrapper script" error (Fixed by sequential builds)
    - [x] Fix `settings.xml` mirror (Fixed "Connection refused" for downloads)
    - [x] Fix `pom.xml` distributionManagement (Fixing "Connection refused" for deployment)
        - [x] Update `pom.xml` files with `${nexus.url}` property
        - [x] Update `Jenkinsfile` to pass `-Dnexus.url=http://nexus:8081`
- [x] Test Pipeline <!-- id: 4 -->
- [x] Create Audit Guide <!-- id: 5 -->
- [x] Cleanup Unused Branches <!-- id: 6 -->
