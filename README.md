# measurementor
measurementor helps you visualize data from your development cycle to help you be a better team.  This code is
used as an example data collection system in the book [Agile Metrics In Action](http://manning.com/davis2/).

# Getting Started
First note the [vagrant file](https://www.vagrantup.com/).  That will call the [puppet](http://puppetlabs.com/) manifest
that will install everything you need to get going.  In a nutshell it installs:
- [Elasticsearch](http://www.elasticsearch.org/) : used for indexing data for searching
- [Kibana](http://www.elasticsearch.org/guide/en/kibana/current/) : used for displaying pretty dashboards
- [MongoDB](http://www.mongodb.org/) : used to back the [Grails](https://grails.org/) based application
- [GVM](http://gvmtool.net/) : used to install Groovy and Grails
- [Groovy](http://groovy.codehaus.org/) : because Groovy is fun
- [Grals](https://grails.org/) : to run the data collector

Once you run:

    vagrant up

everything will get installed and you should have a box up and running.  Check elasticsearch and kibana
by navigating to the following URLs in your web browser of choice:

- local elasticsearch: [http://localhost:9200](http://localhost:9200)
- local kibana: [http://localhost:5601](http://localhost:5601)

To get the measurementor grails app running inside the vagrant box:
- Update the shared directory in your Vagrantfile on line 49.  This will share the source code on your local box with the appropriate directory on the Vagrant box.  Specifically, replace [DIRECTORY WHERE YOU DOWNLOADED THE CODE] with the path on your dev machine where you downloaded this code.
- Measurementor has a number of configurable settings including the URLs and credentials of the source systems and system defaults.  Update the application.properties (measurementor.properties) to configure your source systems.
- Get your vagrant box up and running and use the following commands to get it up and running

    vagrant up
    vagrant ssh
    cd /measurementor
    grails run-app -Dgrails.server.port.http=8070

NOTE: by default Grails uses port 8080 which is used by many other things, so I changed it to 8070.


# In Progress...
This is still a bit of a work in progress but feel free to let me know if there's anything that could be better.
- Still tweaking the vagrant/puppet setup
- When Grails 3 comes out I need to update the app to take advantage of the new goodness
- Need to install the data collector and start it up when everything else starts up

thanks!

