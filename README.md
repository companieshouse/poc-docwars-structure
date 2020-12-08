# POC-docwars-structure

A proof of concept for centralized Companies House technical documentation created from the docWars meetings

## How to run

1. Install Ruby with Rubygems
2. Clone Repository
3. run `bundle install`
4. run `bundle exec middleman server`
5. Browse http://localhost:4567


## More information

*This is internal to companies house*

- Join the `#fix_docs_in_small_steps` slack channel for more information
- Checkout our [confluence page](https://companieshouse.atlassian.net/wiki/spaces/DEV/pages/1729003595/Fix+our+Docs+Overview)

## Observations from POC
### Concerns
1. Storage of images (takes up space in git repo)
2. Storage of attachments (such as draw.io information for reproducibility)
3. No ability to write comments or like (likes arent widelty used in confluence)

### Aditional notes
1. Gone through the effort of copying confluence styling as close as I can. 
2. does a tool for exporting confluence pages to MD exist?
