# My Ansible AWS IaaC test

It takes dynamic inventory from AWS (boto Python module is to be installed), updates system packages on EC2 instances, installs some requirements, creates RDS database and it's user with specific privileges, then deploys Docker with Adminer for possibility to check DB. AWS credentials are taken from environment variables, see ec2.ini for details.

That's the whole provision.yml playbook which run could be managed via self-explanatory named tags: base, upgrade, db, docker.

IMPORTANT! RDS endpoint address should be put to group_vars if infrastructure change occur. In this case password should be changed via ansible-vault in default db role variables. The rest works (well, it highly likely should :) out of the box.

P.S. I'm not a DBA and not familiar with PostgreSQL, so SQL statements may be incorrect for the test case, althoug they don't give any errors.
