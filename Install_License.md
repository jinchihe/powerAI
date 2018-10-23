# Installing the powerAI Enterprise license on a host

1. Log in the host as root.

2. Copy the powerai-enterprise-license or powerai-enterprise-license-eval RPM from the master host where the install files were originally extracted to.

3. Install the RPM on the host by running the following command:
```
   rpm -ihv powerai-enterprise-license*.rpm
```   
4. Accept the PowerAI Enterprise license by running the following command:
```
  /opt/DL/powerai-enterprise/license/bin/accept-powerai-enterprise-license.sh
```
