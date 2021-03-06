# OpenID Connect for Identity Assurance Authority Claim for Japanese gBizID

## Backgrounds

The Japanese Digital Agency is providing identity system for legal entities called 'gBizID'(until mid of 2021, the Ministry of Economy and Trade provided its service, but the service was transferred to the Digital Agency on fall 2021). Currently it is mainly focuses on KYC for legal entities on G2B(Government to Business) application such as apply for a grant, but the Digital Agency is now planning to enlarge its focus to B2B scenarios.

## Types of account

The gBizID provides three types of account as below.
| account type | description | identity assurance level |
| ---- | ---- | ---- |
| gBizID prime | Account the represent the legal entity. Mainly issued to the representative of the legal entity. | IAL2 |
| gBizID member | Child-account of gBizID prime. Only gBizID prime account can issue the member account. | IAL2 |
| gBizID entry | Whoever can apply and get an entry account via gBizID portal. | IAL1 |

Note 1) the identity assurance level definition is based on NIST SP800-63A.  
Note 2) gBizID portal. [https://gbiz-id.go.jp/top/](https://gbiz-id.go.jp/top/)

## Use-cases for each account type

### gBizID prime

Currently, the issuance of a gBizID Prime account requires identity proofing through presenting a certified copy of the commercial register, which is issued by referring to a record in the corporate database held by the Ministry of Justice. In the near future, the Digital Agency and the Ministry of Justice will start providing commercial registry data through API and the gBizID will be able to use the API on identity proofing process.

| use-case                                                                                            | claims to be issued                                           | identity evidence which was used on account registration      | sample request | sample response                               |
| --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | -------------- | --------------------------------------------- |
| The president of the company provide verified claims using gBizID prime account to a relying party. | claims of the president, verified claims of the legal entity. | a certified copy of the commercial register                   |                | [here](./authority_claim_meti_prime_api.json) |
| The president of the company provide verified claims using gBizID prime account to a relying party. | claims of the president, verified claims of the legal entity. | the record which get from the companies database through APIs |                | [here](./authority_claim_meti_prime_api.json) |

### gBizID member

gBizID member account is a child account issued by gBizID prime. The gBizID platfoem does not require any identity proofing for gBizID member accounts, and gBizID prime is responsible for all account issuance.

| use-case                                                                                                                        | claims to be issued                                           | identity evidence which was used on account registration                                     | sample request | sample response                                |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------- | ---------------------------------------------- |
| Corporate finance department personnel issue verified claims to a relying party on behalf of the company.                       | claims of the personnel, verified claims of the legal entity. | no evidence of the personnel itself, only granted by the representative of the legal entity. |                | [here](./authority_claim_meti_member.json)     |
| External accountants present verified claims to a relying party such as application system for grants on behalf of the company. | claims of the personnel, verified claims of the legal entity. | no evidence of the personnel itself, only granted by the representative of the legal entity. |                | [here](./authority_claim_meti_delegation.json) |

### gBizID entry

G Biz ID entry accounts are self-issued accounts that anyone is able to be issued, and is not required any identity proofing.

| use-case                                                                                                              | claims to be issued      | identity evidence which was used on account registration | sample request | sample response                           |
| --------------------------------------------------------------------------------------------------------------------- | ------------------------ | -------------------------------------------------------- | -------------- | ----------------------------------------- |
| Individuals provide claims to a relying party such as application system for grants before starting his/her business. | claims of the personnel. | no evidence of the personnel itself.                     |                | [here](./authority_claim_meti_entry.json) |

## Other resoueces

- [comparison between the gBizID schema and the Authority Claim](./gbizid_schema_and_ida.md)
