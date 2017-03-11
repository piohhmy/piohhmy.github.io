---
layout: post
title:  "Serverless Python"
date:   2017-03-11 12:05:14 -0800
tags: dev serverless python aws
---

I recently switched over my python based microclimate weather app [Weather Hunt][weatherhunt] from running in Heroku to AWS Lambda. Heroku changed their pricing structure a while back that made it so a 24/7 running hobby app costs $7/mo.  Amazon's Lambda serverless offering on the other hand offers 1 million requests a month for free!\*.  Because I'm cheap, that $7 savings got me all excited.  I also fully concur with the post on how [Serverless is the PaaS I always wanted][paas].

While the AWS Console has a nice GUI for configuring Lambda and API Gateway I prefer to keep all infrastructure and setup as code. The open source [Serverless Framework][serverless] solves these problems.  This post is how to get an isolated python virtualenv configured with the Serverless Framework for programatic deployments of AWS Lambda functions.

\* *Note: There is also a GB-sec limit. As long as the lambda is configured with default memory and each request doesn't span more than a couple seconds it is more than sufficient to run 1M invocations/mo for free.*

### Create the virtualenv
At the time of writing, AWS Lambda only supports python 2.7 :cry:. Let's create a virtualenv using python 2.7 using [virtualenvwrapper][virtualenvwrapper] for an isolated project sandbox

```
pip install virtualenvwrapper
mkvirtualenv -p python2.7 hobbyproject
```

With the virtualenv created we can now enter the sandbox at any time via:

```
workon hobby-project
```

And exit via:

```
deactivate
```

### Install Serverless via nodeenv
The Serverless Framework is built via javascript so we'll need to install node via NPM.  Because Serverless is used as a command line tool it is going to want to be installed with the `-g` (global) option when installing via npm.  Because we want an isolated project sandbox with all our dependencies local we can use [nodeenv][nodeenv] to add a node environment to our existing python virtualenv.

```
pip install nodeenv
nodeenv --python-virtualenv --node=4.3.2

```
Now whenever we switch to our python virtualenv we have an isolated node environment for running the serverless framework.  

```
npm install -g serverless
```

### Bootstrap Serverless
With the serverless CLI now available in our virtualenv we can bootstrap all the configuration for our Python based Lambda project.
```
serverless create --template aws-python --path hobbyproject
```

### Bundle Python Packages into Lambda
By default any `pip install` will end up in the virtualenv folder.  This is fine for dev dependencies like test runners, code coverage, linters, etc.  However, any dependencies that the lambda function depends on during runtime will need to be packaged up with the lambda at deploy time.  The [serverless-python-requirements][sls-python-req] plugin will handle the bundling automatically so they are available in PYTHONPATH when running in Lambda.

```
npm install serverless-python-requirements
```  

And add the plugin to `serverless.yml`

```
plugins:
  - serverless-python-requirements
```

For the bundling to work, the dependencies just needs to be defined in requirements.txt.  

```
pip install package && pip freeze > requirements.txt
```

### Deploy the service!

```
serverless deploy
```

We now have an isolated python/node environment for testing and deploying python Lambdas.  Cheers!


[weatherhunt]: http://weatherhunt.com/
[serverless]: https://serverless.com/
[virtualenvwrapper]: https://virtualenvwrapper.readthedocs.io/en/latest/
[nodeenv]: https://github.com/ekalinin/nodeenv
[sls-python-req]: https://github.com/UnitedIncome/serverless-python-requirements
[paas]: https://medium.com/capital-one-developers/serverless-is-the-paas-i-always-wanted-9e9c7d925539#.lq3z118bt
