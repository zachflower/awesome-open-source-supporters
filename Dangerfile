# Ensure there is a summary for a pull request
fail 'Please provide a summary in the Pull Request description' if github.pr_body.length < 5

# Warn if PR guideline boxes are not checked.
warn 'Please check PR guidelines and check the boxes.' if github.pr_body.include? '- [ ]'

# Warn if pull request is not updated
warn 'Please update the Pull Request title to contain the company name' if github.pr_title.include? 'Update README.md'

# Check links
require 'json'
results = File.read 'ab-results-README.md-markdown-table.json'
j = JSON.parse results
if j['error']==true
  fail j['title']
  markdown j['message']
end
