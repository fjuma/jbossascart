# OpenShift AeroGear Unified Push Cartridge

Provides the AeroGear Unified Push Server running on top of JBoss Application Server on OpenShift.

## Template Repository Layout

    .openshift/        Location for OpenShift specific files
      action_hooks/    See the Action Hooks documentation [1]
      markers/         See the Markers section [2]

\[1\] [Action Hooks documentation](https://github.com/openshift/origin-server/blob/master/node/README.writing_applications.md#action-hooks)
\[2\] [Markers](#markers)


## Environment Variables

The `jbossas` cartridge provides several environment variables to reference for ease
of use:

    OPENSHIFT_JBOSSAS_IP                         The IP address used to bind JBossAS
    OPENSHIFT_JBOSSAS_HTTP_PORT                  The JBossAS listening port
    OPENSHIFT_JBOSSAS_CLUSTER_PORT               TODO
    OPENSHIFT_JBOSSAS_MESSAGING_PORT             TODO
    OPENSHIFT_JBOSSAS_MESSAGING_THROUGHPUT_PORT  TODO
    OPENSHIFT_JBOSSAS_REMOTING_PORT              TODO

For more information about environment variables, consult the
[OpenShift Application Author Guide](https://github.com/openshift/origin-server/blob/master/node/README.writing_applications.md).

## Markers

Adding marker files to `.openshift/markers` will have the following effects:

    enable_jpda          Will enable the JPDA socket based transport on the java virtual
                         machine running the JBoss AS 7 application server. This enables
                         you to remotely debug code running inside the JBoss AS 7
                         application server.

    java7                Will run JBossAS with Java7 if present. If no marker is present
                         then the baseline Java version will be used (currently Java6)
