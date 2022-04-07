# Comparison between the gBizID schema and the Authority claim schema

| gBizID                 | Mandatory | Authority Claim                                        | Sample                        | Note                                                                               |
| ---------------------- | --------- | ------------------------------------------------------ | ----------------------------- | ---------------------------------------------------------------------------------- |
| sub                    | x         | sub                                                    | 1242                          | identifier of the subscriber                                                       |
| account_type           | x         | -                                                      | 1                             | account type of the METI's IdP. 1: gBizID entry, 2: gBizID prime, 3: gBizID member |
| corp_type              | x         | -                                                      | 1                             | type of the legal entity. 1: Legal entity, 2: Self-employee                        |
| parent_id              | -         | -                                                      | 1200                          | parent account identifier for gBizID member                                        |
| corporate_number       | x         | authority.applies_to.registration_number               | 27101007182XX                 | corporate number                                                                   |
| name                   | -         | authority.applies_to.organization_name                 | aaa 株式会社                  | company name in Japanese                                                           |
| en_name                | -         | authority.applies_to.organization_name                 | aaa corporation               | company name in English                                                            |
| prefecture_name        | x         | authority.applies_to.registered_address.region         | 13                            | prefecture code in JIS X 0401                                                      |
| address1               | x         | authority.applies_to.registered_address.locality       | 渋谷区                        | city name in Japanese                                                              |
| address2               | x         | authority.applies_to.registered_address.street_address | 〇〇〇丁目〇番〇号            | street address in Japanese                                                         |
| rep_last_nm            | x         | authority.applies_to.family_name                       | 山田                          | representative's family name in Japanese Kanji                                     |
| rep_first_nm           | x         | authority.applies_to.given_name                        | 太郎                          | representative's given name in Japanese Kanji                                      |
| rep_last_nm_kana       | x         | authority.applies_to.family_name                       | ヤマダ                        | representative's family name in Japanese Kana                                      |
| rep_first_nm_kana      | x         | authority.applies_to.given_name                        | タロウ                        | representative's given name in Japanese Kana                                       |
| birthday_ymd           | -         | authority.applies_to.birthdate                         | 1980-01-01                    | representative's birthdate                                                         |
| user_last_nm           | x         | family_name                                            | 山田                          | user's family name in Japanese Kanji                                               |
| user_first_nm          | x         | given_name                                             | 太郎                          | user's given name in Japanese Kanji                                                |
| user_last_nm_kana      | x         | family_name                                            | ヤマダ                        | user's family name in Japanese Kana                                                |
| user_first_nm_kana     | x         | given_name                                             | タロウ                        | user's given name in Japanese Kana                                                 |
| user_post_code         | x         | postal_code                                            | 0000000                       | user's postal code                                                                 |
| user_prefecture_name   | x         | address.region                                         | 13                            | user's prefecture code in JIS X 0401                                               |
| user_address1          | x         | address.locality                                       | 渋谷区                        | user's locality in Japanese Kanji                                                  |
| user_address2          | x         | address.street_address                                 | 〇〇〇丁目〇番〇号            | user's street address in Japanese                                                  |
| user_address3          | -         | -                                                      | 〇〇ビル                      | user's street address in detail in Japanese                                        |
| user_tel_no_contact    | -         | phone_number                                           | 1111111111                    | user's phone number                                                                |
| user_birthday_ymd      | -         | birthdate                                              | 1980-01-01                    | user's birth date                                                                  |
| mandate_info.client_id | -         | 123456                                                 | client_id for a RP to mandate |
| user_email             | x         | email                                                  | yamada.tarou@example.co.jp    | user's email                                                                       |
