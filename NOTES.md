# Fork History

Forked from Commits on Nov 19, 2019
https://github.com/dexidp/dex/tree/b1e98d8590cb7c6cca7b64c6322bd985fdb7ef04

To:
Commits on Nov 19, 2019
https://github.com/SergeAlexandre/dex/tree/b1e98d8590cb7c6cca7b64c6322bd985fdb7ef04


------------------------------------------------------
Merged with Commits on Jan 21, 2020
https://github.com/dexidp/dex/tree/8894eed8d3d1e79a1925cf1a71c1bcde8f6edfe7

To:Commits on Jan 27, 2020
https://github.com/SergeAlexandre/dex/tree/1da7cdf7c9f5c42175683483402c3a4def118adc



# Merge from original

```
cd dex
git status	# Must be on master, nothing to commit, working tree clean
git pull https://github.com/dexidp/dex.git master

# Check and fix conflict

git commit ....
git push


```


# Build on vagrant VM (test ldap)

ldap_test failed on my mac. While working on a centos7 vagrant VM.

    sudo yum -y install go openldap-servers openldap-clients

    cd ..../dex

    make clean; make

	go test ./...
	go test -v ./...
	go test github.com/dexidp/dex/connector/ldap
    
    export DEX_LDAP_TESTS=1
	go test github.com/dexidp/dex/connector/ldap

Back to mac:

    make clean; make


# LDAP modifications

Some small improvements where added to LDAP connector:

- Added a configuration variable 'EmailPrefixAttr', to select the attribute used to build the left part of an email
- Added a boolean configuration variable 'EmailOverride' to allow overriding of an existing email attribute?
- Enforce default value for IDAttr (uid) and EmailAttr (mail)

# PUSH

export REG=harbor2.bsa.broadsoftware.com
docker login -u admin $REG
docker tag dexbs $REG/library/dexbs
docker push $REG/library/dexbs


docker login -u sergealexandre
docker tag dexbs ezcplugins/dexbs
docker push ezcplugins/dexbs








