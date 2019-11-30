

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



