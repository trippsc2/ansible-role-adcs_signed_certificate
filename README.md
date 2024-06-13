<!-- BEGIN_ANSIBLE_DOCS -->

# Ansible Role: ansible-role-adcs_signed_certificate
DEPRECATED: Use trippsc2.adcs.signed_certificate instead.

## Requirements

| Platform | Versions |
| -------- | -------- |
| EL | <ul><li>8</li></ul> |
| Windows | <ul><li>2019</li><li>2022</li></ul> |

## Dependencies
| Role |
| ---- |
| trippsc2.generate_csr |

| Collection |
| ---------- |
| ansible.windows |
| community.crypto |

## Role Arguments
|Option|Description|Type|Required|Choices|Default|
|---|---|---|---|---|---|
| cert_signing_ca_hostname | The hostname of the Certificate Authority to sign the certificate. | str | yes |  |  |
| cert_signing_ca_csr_path | The path to the Certificate Signing Request (CSR) file to sign. | path | no |  | C:\Windows\temp\server.req |
| cert_signing_ca_fqdn | The Fully Qualified Domain Name (FQDN) of the Certificate Authority to sign the certificate. This variable is only used if the `cert_signing_ca_config` option is not defined. | str | no |  | {{ hostvars[cert_signing_ca_hostname].ansible_fqdn }} |
| cert_signing_ca_common_name | The Common Name (CN) of the Certificate Authority to sign the certificate. This variable is only used if the `cert_signing_ca_config` option is not defined. | str | no |  |  |
| cert_signing_ca_config | The configuration of the Certificate Authority to sign the certificate. This variable is only used if the `cert_signing_ca_fqdn` and `cert_signing_ca_common_name` options are not defined. | str | no |  | {{ cert_signing_ca_fqdn }}\{{ cert_signing_ca_common_name }} |
| cert_line_break_character | The line break character to use in the certificate. | str | no |  | \n |
| cert_certificate_owner | The owner of the certificate on Linux systems. | str | no |  | root |
| cert_certificate_group | The group of the certificate on Linux systems. | str | no |  | root |
| cert_certificate_mode | The mode of the certificate on Linux systems. | str | no |  | 0644 |


## License
MIT

## Author and Project Information
Jim Tarpley
<!-- END_ANSIBLE_DOCS -->
