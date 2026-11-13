# wazuh-custom-rules

![Wazuh](https://img.shields.io/badge/wazuh-4.x-005571)
![Type](https://img.shields.io/badge/type-rules%20%26%20decoders-blue)
![License](https://img.shields.io/badge/license-MIT-green)

Production-tested custom Wazuh rules and decoders for common infrastructure, covering scenarios not handled by the default ruleset.

## Install

```bash
# Rules go to local_rules.xml
cp local_rules.xml /var/ossec/etc/rules/local_rules.xml

# Decoders go to local_decoder.xml
cp local_decoder.xml /var/ossec/etc/decoders/local_decoder.xml

# Reload without restart
wazuh-reload-rules
```

> All custom rules start at `rule_id 100101` to avoid conflicts with Wazuh built-in rules (which end at 99999).

## Contents

| File | Description |
|---|---|
| `local_rules.xml` | Custom detection rules |
| `local_decoder.xml` | Custom log decoders |

## Usage notes

- Test rules before deploying: `wazuh-logtest` in the Wazuh dashboard
- Check for `if_sid` conflicts after Wazuh upgrades with `wazuh-reload-rules`
- Rule IDs 100000–109999 are reserved for local use per Wazuh documentation

## Related articles

- [Detection engineering in Wazuh: from a raw log to a tested rule](https://wazuh.blog/en/blog/wazuh-detection-engineering/)
- [Custom Wazuh decoders: syntax, regex, sibling and dynamic fields](https://wazuh.blog/en/blog/wazuh-custom-decoders/)
