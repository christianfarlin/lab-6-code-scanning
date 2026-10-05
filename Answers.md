# Answers to Part 3

Add your answers to the questions in Part 3, Step 2 below.

## Vulnerability Remediation:

### Vulnerability 1: Pillow

**1. Which package or library are you addressing?**

Pillow 9.4.0. The Trivy and Docker Scout scans identified a CRITICAL severity vulnerability affecting this version of the Pillow library.

**2. Which CVE is linked to this vulnerability?**

CVE-2023-50447. Pillow versions prior to 10.2.0 are vulnerable to arbitrary code execution through the `environment` parameter of `PIL.ImageMath.eval()`. An attacker who can influence this parameter may be able to cause the application to execute arbitrary code (GitHub, 2024).

**3. What remediation steps do you suggest?**

Upgrade Pillow from version 9.4.0 to version 10.2.0 or later. Version 10.2.0 is identified as the first patched version for CVE-2023-50447 (GitHub, 2024).

**References**

GitHub. (2024). *Arbitrary code execution in Pillow (CVE-2023-50447).* GitHub Advisory Database. https://github.com/advisories/GHSA-3f63-hfp8-52jq


### Vulnerability 2: PyJWT

**1. Which package or library are you addressing?**

PyJWT 2.4.0. The Trivy and Docker Scout scans identified a CRITICAL severity vulnerability affecting the PyJWT library.

**2. Which CVE is linked to this vulnerability?**

CVE-2026-102268. Under configurations that permit both HMAC and asymmetric algorithms, specially formatted PEM public keys may bypass PyJWT's asymmetric-key detection. This can allow a public key to be treated as an HMAC secret and potentially enable an attacker to forge valid JWTs (GitHub, 2026).

**3. What remediation steps do you suggest?**

Upgrade PyJWT to version 2.14.0 or later, since version 2.14.0 contains the fix for this vulnerability. Applications should also avoid allowing both symmetric and asymmetric JWT algorithms when this configuration is unnecessary (GitHub, 2026).

**References**

GitHub. (2026). *PyJWT: Asymmetric-PEM detection bypass: Whitespace/line-ending-mutated public keys skip the HS/asymmetric confusion guard (CVE-2026-102268).* GitHub Advisory Database. https://github.com/advisories/GHSA-ffc3-869f-jxw9


### Vulnerability 3: PyYAML

**1. Which package or library are you addressing?**

PyYAML 5.1. The Trivy and Docker Scout scans identified a CRITICAL severity vulnerability affecting this version of the PyYAML library.

**2. Which CVE is linked to this vulnerability?**

CVE-2019-20477. PyYAML versions 5.1 through 5.1.2 contain insufficient restrictions in the `load` and `load_all` functions due to a class-deserialization issue, which can result in unsafe deserialization of untrusted data (GitHub, 2021).

**3. What remediation steps do you suggest?**

Upgrade PyYAML from version 5.1 to version 5.2 or later, since version 5.2 contains the patch for this vulnerability. When processing untrusted YAML, applications should also use `SafeLoader` or `safe_load` rather than unsafe loading mechanisms (GitHub, 2021; PyYAML, n.d.).

**References**

GitHub. (2021). *Deserialization of untrusted data in PyYAML (CVE-2019-20477).* GitHub Advisory Database. https://github.com/advisories/GHSA-3pqx-4fqf-j49f

PyYAML. (n.d.). *PyYAML yaml.load(input) deprecation.* GitHub. https://github.com/yaml/pyyaml/wiki/PyYAML-yaml.load%28input%29-Deprecation


### Vulnerability 4: PyYAML

**1. Which package or library are you addressing?**

PyYAML 5.1. The Trivy and Docker Scout scans identified another CRITICAL severity vulnerability affecting this version of the PyYAML library.

**2. Which CVE is linked to this vulnerability?**

CVE-2020-14343. PyYAML versions prior to 5.4 can permit arbitrary code execution when untrusted YAML is processed using `full_load` or `FullLoader`. An attacker can exploit the `python/object/new` constructor to execute arbitrary code (GitHub, 2021).

**3. What remediation steps do you suggest?**

Upgrade PyYAML from version 5.1 to version 5.4 or later, since version 5.4 patches this vulnerability. Applications processing untrusted YAML should also use `SafeLoader` or `safe_load` rather than `FullLoader` (GitHub, 2021; PyYAML, n.d.).

**References**

GitHub. (2021). *Improper input validation in PyYAML (CVE-2020-14343).* GitHub Advisory Database. https://github.com/advisories/GHSA-8q59-q68h-6hv4

PyYAML. (n.d.). *PyYAML yaml.load(input) deprecation.* GitHub. https://github.com/yaml/pyyaml/wiki/PyYAML-yaml.load%28input%29-Deprecation


### Vulnerability 5: PyYAML

**1. Which package or library are you addressing?**

PyYAML 5.1. The Trivy and Docker Scout scans identified another CRITICAL severity vulnerability affecting this version of the PyYAML library.

**2. Which CVE is linked to this vulnerability?**

CVE-2020-1747. PyYAML versions prior to 5.3.1 can allow arbitrary code execution when an application processes untrusted YAML using `full_load` or `FullLoader`. An attacker can exploit the `python/object/new` constructor to execute arbitrary code on the affected system (GitHub, 2021).

**3. What remediation steps do you suggest?**

Upgrade PyYAML from version 5.1 to version 5.3.1 or later. Applications processing untrusted YAML should additionally use `SafeLoader` or `safe_load` to restrict potentially dangerous YAML constructs (GitHub, 2021; PyYAML, n.d.).

**References**

GitHub. (2021). *Improper input validation in PyYAML (CVE-2020-1747).* GitHub Advisory Database. https://github.com/advisories/GHSA-6757-jp84-gxfx

PyYAML. (n.d.). *PyYAML yaml.load(input) deprecation.* GitHub. https://github.com/yaml/pyyaml/wiki/PyYAML-yaml.load%28input%29-Deprecation