# POC-docwars-structure
A proof of concept for centralized Companies House technical documentation created from the docWars meetings

template documentation can be found [here](https://tdt-documentation.london.cloudapps.digital/#technical-documentation-template)

## Getting started
### Install node.js
node.js is required
### Install Ruby
You can install Ruby to any location on your local machine.

You can install Ruby in multiple ways, for example using Ruby Version Manager (RVM) or rbenv. 

However, these instructions assume you are using chruby instead of RVM or rbenv.

To install chruby and ruby-install run the following:
```
brew install chruby ruby-install
```    
Add this to bash_profile 

"source /usr/local/share/chruby/chruby.sh"

Install ruby you will need to specify which version (in this example I installed ruby-2.7.2)
```
ruby-install ruby 2.7.2
```    
If you get openssl errors during the install then find where your openssl is install and use the with-openssl-dir attribute. 
```
ruby-install ruby 2.7.2 —- --with-openssl-dir=/usr/local/Cellar/openssl@1.1/1.1.1d/
 ```   
Switch to the newly installed version of ruby by running the following
```
chruby ruby-2.7.2
```
To ensure you have all the relevant dependencies run the following
```
gem install bundler
```
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

Navigate to the root directory of this project and then type the following to start the server:

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




