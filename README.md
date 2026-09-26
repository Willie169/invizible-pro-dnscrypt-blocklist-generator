DNSCrypt blocklist generator for [InviZible Pro: Tor & Firewall, DNSCrypt & I2P](https://github.com/Gedsh/InviZible) (`pan.alexander.tordnscrypt.stable`, [F-Droid](https://f-droid.org/packages/pan.alexander.tordnscrypt.stable)) in order to solve [issue#404](https://github.com/Gedsh/InviZible/issues/404), licensed under [ISC License](LICENSE.txt)

- [domains-blocklist.conf](domains-blocklist.conf): The blocklists to be unified. You can fork this repo and adjust this file to fit your need. Remember to re-generate the blocklist after changing this using GitHub Action (recommended) or by running the Python script manually.
- [generate-domains-blocklist.py](generate-domains-blocklist.py): [generate-domains-blocklist.py](https://raw.githubusercontent.com/DNSCrypt/dnscrypt-proxy/refs/heads/master/utils/generate-domains-blocklist/generate-domains-blocklist.py) from [dnscrypt-proxy](https://github.com/DNSCrypt/dnscrypt-proxy). To generate the blocklist, execute
  ```
  python3 generate-domains-blocklist.py -o blocklist.txt -a domains-allowlist.txt
  ```
- [blocklist.txt](blocklist.txt): The blocklist to be used in InviZible Pro. To use it, open InviZible Pro, go to DNSCrypt Settings, click Blacklist under Pattern-based blocking (blacklist), click ADD REMOTE LIST or REPLACE REMOTE LIST, paste `https://raw.githubusercontent.com/Willie169/invizible-pro-dnscrypt-blocklist-generator/refs/heads/main/blocklist.txt`, and click OK. Remember to change `Willie169` to your GitHub user name when applying that in your fork.
- [domains-allowlist.txt](domains-allowlist.txt): My allow list of domains to be excluded from the blocklist.
- [dnscrypt-blocklist-generator.yml](.github/workflows/dnscrypt-blocklist-generator.yml): GitHub Action to generate [blocklist.txt](blocklist.txt) every 6 hours. Remember to enable GitHub Action and go to Settings > Actions > General > Workflow permissions, select Read and write permissions, and Save in your fork to use it.

