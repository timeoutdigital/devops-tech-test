my website
==========

A neat website

Setup and Deployment
--------------------

* Have Python 2 set up
* Install Ansible 2.0+ with `pip install ansible`
* Install the AWS CLI with `pip install awscli`
* Have your credentials set up for an AWS account for which you have full
  access to CloudFormation and S3. You can configure using
  [these instructions][aws_configure]
* Run `ansible-playbook deploy.yml`. A message is printed at the end with the
  URL of the website on S3's domain.

This website only needs an S3 bucket with minimal storage so should cost only
a few cents a year to run, and will easily fit inside the AWS Free Tier.

How to Complete
---------------

Spend an hour in total to do these three tasks. You can do them in any order
you feel comfortable with, however they are intended to be in roughly
complexity order. We're also looking at some relatively new S3 features so it's
expected you don't know everything. Don't worry if you can't produce code - if
you get halfway from reading the documentation, just write an explanation about
what you would have done.

Please make all changes as commits to a clone of this git repo, and *do not*
put it on a GitHub fork or make a pull request, as that would show your answers
to other candidates. Instead please submit your changes as a patch file
generated with `git format-patch origin/master --stdout > my-name.patch` and
email it back to us.

Questions
---------

1. For SEO purposes, the `animal` folder was recently renamed to `animals`. As
   a result, links on third party sites leading to e.g. `/animal/dog.html` are
   now broken. We should add an S3 [routing rule][routing_rule] to redirect
   these links to the [cloudformation resource][cf_bucket].

2. Currently the site isn't available at its own domain or with HTTPS. Suggest
   how this could be done - just write an answer below, no need to change code.

3. We don't currently have any stats on visitors to the website, and would like
   some indication. It looks like S3 itself could track the number of requests
   on CloudWatch using the new [Request Metrics][request_metrics] feature.
   Change the Ansible playbook so that it [turns on Request Metrics][turn_on]
   for the bucket (it's not supported by CloudFormation at the moment).

Answers
-------

1. (Make your changes in other files, or if you can't finish, explain here how
   far you got)

2. ...

3. (Make your changes in other files, or if you can't finish, explain here how
   far you got)

[aws_configure]: https://boto3.readthedocs.io/en/latest/guide/configuration.html
[routing_rule]: https://docs.aws.amazon.com/AmazonS3/latest/dev/HowDoIWebsiteConfiguration.html#configure-bucket-as-website-routing-rule-syntax
[cf_bucket]: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-s3-bucket.html
[request_metrics]: https://docs.aws.amazon.com/AmazonS3/latest/dev/cloudwatch-monitoring.html
[turn_on]: https://docs.aws.amazon.com/AmazonS3/latest/dev/metrics-configurations.html
