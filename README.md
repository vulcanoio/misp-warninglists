# misp-warninglist

misp-warninglists are lists of well-known indicators that can be associated to potential false positives, errors or mistakes.

[![Build Status](https://travis-ci.org/MISP/misp-warninglists.svg?branch=master)](https://travis-ci.org/MISP/misp-warninglists)

The warning lists are integrated in MISP to display an info/warning box at the event and attribute level if such indicators
are available in one of the list. The list can be globally enabled or disabled in MISP following the practices of the organization.

# lists

- [lists/alexa](lists/alexa) - Top 1000 websites from Alexa
- [lists/empty-hashes](lists/empty-hashes) - hash values of empty files
- [lists/google](lists/google) - known domains and hostnames from Google
- [lists/ipv6-linklocal](ipv6-linklocal) - IPv6 link local prefix
- [lists/microsoft](lists/microsoft) - known microsoft domains
- [lists/multicast](lists/multicast) - known IPv4 multicast CIDR blocks
- [lists/public-dns-v4](lists/public-dns-v4) - IPv4 addresses and reverse of public DNS resolver
- [lists/public-dns-v6](lists/public-dns-v6) - IPv6 addresses and reverse of public DNS resolver
- [lists/rfc1918](lists/rfc1918) - RFC 1918 network subnets
- [lists/rfc3849](lists/rfc3849) - RFC 3849 - Documentation prefix for ipv6
- [lists/rfc5735](lists/rfc5735) - RFC 5735 CIDR blocks - Special Use IPv4 Addresses
- [lists/second-level-tlds](lists/second-level-tlds) - Mozilla list of second level top-level domains
- [lists/tlds](lists/tlds) - top-level domains

# Format of a warning list

~~~~json
{
  "name": "List of known public DNS resolvers",
  "version": 1,
  "description": "Event contains one or more public DNS resolvers as attribute with an IDS flag set",
  "matching_attributes": [
    "ip-src",
    "ip-dst"
  ],
  "list": [
    "8.8.8.8",
    "8.8.4.4",
    "208.67.222.222",
    "208.67.220.220",
    "195.46.39.39",
    "195.46.39.40"
  ]
}
~~~~

If matching_attributes are not set, the list is matched against any type of attributes.

# License

MISP warning-lists are licensed under [CC0 1.0 Universal (CC0 1.0)](https://creativecommons.org/publicdomain/zero/1.0/) -  Public Domain Dedication. If a specific author of a taxonomy wants to license it under a different license, a pull request can be requested.
