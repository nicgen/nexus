# Implementation Plan - Configuring Jenkins for Nexus

## Goal Description
Resume the configuration of Jenkins for Nexus by resolving port conflicts, starting the Nexus service, and configuring Jenkins credentials to enable artifact publishing.

## User Review Required
> [!WARNING]
> **Pipeline Failed**: The recent build failed with "wrapper script does not seem to be touching the log file".
> **Likely Causes**: Resource exhaustion (RAM) due to parallel Maven builds, or missing `mvn` tool configuration.

## Proposed Changes

### Jenkins Configuration
#### [MODIFY] [buy-02/Jenkinsfile](file:///home/nic/dev/java/nexus/buy-02/Jenkinsfile)
- **Deployment**: Pass `-Dnexus.url=http://nexus:8081` to `mvn deploy` to override the default URL.

### Maven Configuration
#### [MODIFY] [buy-02/services/*/pom.xml](file:///home/nic/dev/java/nexus/buy-02/services/)
- **Properties**: Add `<nexus.url>http://nexus.local.hello-there.net</nexus.url>` default property.
- **DistributionManagement**: Use `${nexus.url}` in repository URLs.


## Verification Plan

### Automated Tests
- **Retry Pipeline**: Run the pipeline again.
- **Success Criteria**: 
    - `Test Backend` stage passes (sequentially or parallel).
    - `Publish Artifacts` stage attempts connection to Nexus.

### Manual Verification
- **Console Logs**: Review logs for `mvn -version` output (if added) or successful test execution.
