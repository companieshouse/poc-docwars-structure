# POC-docwars-structure
A proof of concept for centralized Companies House technical documentation created from the docWars meetings

template documentation can be found [here](https://tdt-documentation.london.cloudapps.digital/#technical-documentation-template)

## Getting started

### Install Ruby
You can install Ruby to any location on your local machine.

You can install Ruby in multiple ways, for example using Ruby Version Manager (RVM) or rbenv. These instructions assume you are using RVM.

1. Run the following in the command line to install the ruby version manager:
```
\curl -sSL https://get.rvm.io | bash -s stable --ruby
```
2. Check the Ruby downloads page for the latest version of Ruby.

3. Run `rvm install ruby-x.x.x` to install the latest version of Ruby.

### Install Middleman
You can install Middleman to any location on your local machine.

Run the following in the command line to install Middleman:
```
gem install middleman
```

## Preview

Whilst writing documentation we can run a middleman server to preview how the
published version will look in the browser. After saving a change the preview in
the browser will automatically refresh.

The preview is only available on our own computer. Others won't be able to
access it if they are given the link.

Type the following to start the server:

```
bundle exec middleman server
```

If all goes well something like the following output will be displayed:

```
== The Middleman is loading
== LiveReload accepting connections from ws://192.168.0.8:35729
== View your site at "http://Laptop.local:4567", "http://192.168.0.8:4567"
== Inspect your site configuration at "http://Laptop.local:4567/__middleman", "http://192.168.0.8:4567/__middleman"
```

You should now be able to view a live preview at http://localhost:4567.

## More information

*This is internal to companies house*

- Join the `#fix_docs_in_small_steps` slack channel for more information
- Checkout our [confluence page](https://companieshouse.atlassian.net/wiki/spaces/DEV/pages/1729003595/Fix+our+Docs+Overview)




