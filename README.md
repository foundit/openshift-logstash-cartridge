## OpenShift Logstash Cartridge

This is a simple cartridge for making Logstash easily available in your applications.


## Environment Variables

These environment variables are used when configuring Logstash:

 * **`OPENSHIFT_LOGSTASH_ES_HOST`**: URL of the Elasticsearch cluster to log to. Required.
 * **`OPENSHIFT_LOGSTASH_ES_USERNAME`**: Username to connect as. Optional.
 * **`OPENSHIFT_LOGSTASH_ES_PASSWORD`**: Password to connect with. Optional.


## Installation

First, configure the application with the appropriate environment variables. Then, add the cartridge to your application:

    # Configure environment
    $ rhc set-env --app my-app --env "OPENSHIFT_LOGSTASH_ES_HOST=abc123-us-east-1.foundcluster.com"
    $ rhc set-env --app my-app --env "OPENSHIFT_LOGSTASH_ES_USERNAME=readwrite"
    $ rhc set-env --app my-app --env "OPENSHIFT_LOGSTASH_ES_PASSWORD=secret"

    # Add cartridge
    $ rhc cartridge add -a your-app-name https://cartreflect-claytondev.rhcloud.com/github/foundit/openshift-logstash-cartridge

If you want better control of your Logstash configuration, for this repository, customize [conf/logstash.conf.erb] and specify your repository in the last step.


## License

Released under the [Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).