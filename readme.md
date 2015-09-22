## Spacewalk Common Channel Extra Configurations
spacewalk-common-channel is a tool to quickly add Channels and Repositories to a Spacewalk Server. By default only free channels are available with the RPM package but you can add your own configuration (like this one)


### SLES 
The configuration files for SLES11 are used to communicate with the NCC of Novell. You have to substitute the %%USER%% and %%PASS%% placeholder with an valid account (systemid)

### Red Hat

#### RHEL 7
To use the Channels you need the entitlement certificate of a subscribed RHEL7 Server.

```
This can also be reached by logging into https://access.redhat.com -> Subscription -> Manage: Subscriber Inventory: Systems -> Register a system.
Needed information: FQDN of the Server, System Type, Architecture, Number of Sockets, RH Version
```

After you added the system it will be visible in the Inventory. Select the new server and download the entitlement certificate. You will also need the CA of the RedHat CDN which comes with the subscription manager client (look in the rhsm.conf)

Both Keys must be uploaded to the Spacewalk Kickstart Section, GPG and SSL Keys -> New Key (SSL). After running the spacewalk-common-channels script add the CA and the entitlement information to the Repository in the Spacewalk GUI (Channels -> Manage Software Channels -> Manage Repositories)


