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

# Task: Audit Evidence for Buy-02
- [x] Collect Evidence <!-- id: 7 -->
    - [x] **Git History**: Capture merge log <!-- id: 8 -->
    - [x] **Database**: Capture product snapshot from MongoDB <!-- id: 9 -->
    - [x] **SonarQube**: Capture dashboard screenshot (User or Browser) <!-- id: 10 -->
    - [x] **Jenkins**: Capture pipeline success screenshot (User or Browser) <!-- id: 11 -->
    - [x] **Shopping Cart**: Capture persistence screenshot (User or Browser) <!-- id: 12 -->
- [x] Update `AUDIT_ANSWERS.md` with evidence <!-- id: 13 -->

# Task: Audit Evidence for Nexus
- [x] Collect Evidence <!-- id: 14 -->
    - [x] **Reuse Evidence**: Copy Jenkins/Nexus screenshots from buy-02 <!-- id: 15 -->
    - [x] **Nexus Security**: Capture Real/Security settings (User to provide) <!-- id: 16 -->
    - [x] **Nexus Browse**: Capture artifact versions (User to provide) <!-- id: 17 -->
- [x] Update `AUDIT_GUIDE.md` with evidence <!-- id: 18 -->
    - [x] Add GitHub file links <!-- id: 19 -->
    - [x] Create/Update `README.md` for Setup/Config/Usage <!-- id: 20 -->
    - [x] Link `README.md` in `AUDIT_GUIDE.md` <!-- id: 21 -->
