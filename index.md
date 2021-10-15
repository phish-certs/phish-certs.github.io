# Certificate classification features
Features extracted from certificates

## Certificate features
| # | Type | Description | 
|---|------|-------------|
|    1          |          cat.        | Validation level of the certificate                                                                                    |
|    2          |          bool          | If the certificate by the Apple root store                                                                           |
|    3          |          bool          | If the certificate by the Mozilla NSS root store                                                                     |
|    4          |          bool          | If the certificate by the Microsoft root store                                                                       |
|    5          |          bool          | If the subject has a country (C) field                                                                               |
|    6          |          bool          | If the subject has a state (S) field                                                                                 |
|    7          |          bool          | If the subject has a locality (L) field                                                                              |
|    9          |          bool          | If the subject has a common name (CN) field                                                                          |
|    10          |         bool          | If the subject only consists of a common name                                                                        |
|    11          |         int           | Number of fields in subject RDN                                                                                      |
|    12          |         int           | Length of the subject                                                                                                |
|    13          |         int           | Validity period of the certificate                                                                                   |
|    14          |         int           | Number of policy identifiers embedded in certificate                                                                 |
|    15          |         bool          | If the certificate has an OSCP (Online Certificate Status Protocol) link                                             |
|    16          |         bool          | If the certificate has an CDP (CRL Distribution Point) link                                                          |
|    17          |         int           | The number of Subject Alternative Names (SANs)                                                                       |
|    18          |         int           | The unique number of TLDs of SANs                                                                                    |
|    19          |         cat.        | The public key algorithm                                                                                               |
|    20          |         int           | The public key size                                                                                                  |
|    21          |         int           | The key usage                                                                                                        |
|    22          |         int           | The version of the certificate                                                                                       |
|    23          |         cat.        | The signature algorithm                                                                                                |
|    24          |         int           | The length of the serial number                                                                                      |
|    25          |         bool          | If the certificate has expired                                                                                       |
|    26          |         bool          | If the issuer is empty                                                                                               |
|    27          |         bool          | If the issuer has a common name (CN) field                                                                           |
|    28          |         bool          | If the subject is empty                                                                                              |
|    29          |         bool          | If the certificate has any extensions                                                                                |
|    30          |         bool          | If the serial numbers conforms to requirements                                                                       |
|    31          |         bool          | If the *NotBefore* timestamp is *higher* the *NotAfter*
|    32          |         int           | Length of the Longest Common Subsequence (LCS) of all SANs                                                           |
|    33          |         float         | Length of the Longest Common Subsequence (LCS) of all SANs, normalized                                               |
|    34          |         bool          | If the certificate contains a SAN with a CDN pattern                                                                 |
|    35-36      |         bool          | Existence and critical status of authority info access extension                                                     |
|    37-38      |         bool          | Existence and critical status of certificate policies extension                                                      |
|    39-40      |         bool          | Existence and critical status of basic constraints extension                                                         |
|    41-42      |         bool          | Existence and critical status of CRL distribution point extension                                                    |
|    43-44      |         bool          | Existence and critical status of subject alternative name extension                                                  |
|    45-46      |         bool          | Existence and critical status of extended key usage extension                                                        |
|    47-48      |         bool          | Existence and critical status of authority key identifier extension                                                  |
|    49-50      |         bool          | Existence and critical status of signed certifiate timestamp extension                                               |
|    51-52      |         bool          | Existence and critical status of inhibit any policy extension                                                        |
|    53-54      |         bool          | Existence and critical status of policy contraints extension                                                         |
|    55-56      |         bool          | Existence and critical status of name constraints extension                                                          |
|    57-58      |         bool          | Existence and critical status of issuer alternative name extension                                                   |

## Domain features

|# | Type| Description |
|----|-----|------|
| 59                  | int           | domain length                                                                                                                       |
| 60                  | bool          | If the domain has seven or more labels                                                                                              |
| 61                  | bool          | If the domain is under a suspicious TLD                                                                                             |
| 62                  | bool          | If the domain contains a suspicious keyword                                                                                         |
| 63                  | int           | Shannon entropy of the domain                                                                                                       |
| 64                  | int           | Number of dashes (`-') in domain                                                                                                    |
| 65                  | int           | Number of tokens in domain (i.e., split domain on periods ('.') and dashes ('-'))                                                   |
| 66                  | int           | Number of parts of the domain (i.e., split domain on period ('.'))                                                                  |
| 67                  | int           | Number of parts of the domain (i.e., split domain on period ('.'))                                                                  |
| 68                  | int           | Number of labels of the subdomain part of the domain                                                                                |
| 69                  | bool          | If one of the tokens in the domain is a TLD                                                                                         |
| 70                  | bool          | If the domain contains "https"                                                                                                      |
| 71                  | float         | Fraction of domain that is a special character                                                                                      |
| 72                  | bool          | If the domain is an IP address                                                                                                      |
| 73                  | bool          | If the domain is an International Domain Name (IDN)                                                                                 |
| 74                  | float         | Fraction of the domain that is a vowel                                                                                              |
| 75                  | float         | Fraction of the domain that is a digit                                                                                              |
| 76                  | bool          | If the domain contains "www."                                                                                                       |
| 77                  | bool          | If the domain contains a subdomain label of digits only                                                                             |
| 78                  | bool          | The mean length of the subdomain labels of the domain                                                                               |
| 79                  | bool          | If the domain contains digits                                                                                                       |
| 80                  | bool          | If the domain is under a valid TLD (according to [IANA](https://data.iana.org/TLD/tlds-alpha-by-domain.txt))           |
| 81                  | bool          | If the domain contains at least one single-character subdomain                                                                      |
| 82                  | float         | Character diversity (ratio unique letters in domain)                                                                                |
| 83                  | int           | Alphabet size (Number of unique letters in domain)                                                                                  |
| 84                  | float         | Fraction of the domain that is an underscore                                                                                        |
| 85                  | int           | The Tranco rank of the domain                                                                                                       |
| 86                  | bool          | If the domain is a wildcard domain (i.e., starts with a start ('*'))                                                                |
| 87-93              | int           | \{stdev, mean, min, max, median, bottom quartile, top quartile\} of the count of 1-grams in the domain                 |
| 84-100             | int           | \{stdev, mean, min, max, median, bottom quartile, top quartile\} of the count of 2-grams in the domain                 |
| 101-107            | int           | \{stdev, mean, min, max, median, bottom quartile, top quartile\} of the count of 3-grams in the domain                 |