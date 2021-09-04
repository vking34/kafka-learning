# Kafka Security

## Authentication

- __SASL__: SASL (Simple Authentication Security Layer) is a framework that provides developers of applications and shared libraries with mechanisms for authentication, data integrity-checking, and encryption.
    - __SASL using JAAS__
    - __SASL/GSSAPI (Kerberos)__
    - __SASL/OAUTHBEARER__
    - __SASL/PLAIN__
    - __SASL/SCRAM__
    - __Delegation Tokens (SASL/SSL)__
    - __LDAP__

- __mTLS__: With mTLS (mutual TLS) authentication–also known as “two-way authentication”–both Kafka clients and servers use TLS certificates to verify each other’s identities to ensure that traffic is secure and trusted in both directions.

- __HTTP Basic Auth__: You can use HTTP Basic Authentication to authenticate with the Admin REST APIs using a username and password pair, which are presented to the REST Proxy server using the Authorization HTTP header.

## Authorization

- __ACLs__
    - Kafka ships with a pluggable, out-of-the-box Authorizer implementation that uses ZooKeeper™ to store all the ACLs.

## References

- https://docs.confluent.io/platform/current/kafka/overview-authentication-methods.html