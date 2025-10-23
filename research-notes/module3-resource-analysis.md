### Comparison Notes Between Projects (Topic 1 vs Topic 2)

- Topic 1 is more offensive security focused, Topic 2 is defensive security focused.
-Nettacker is a full automated pentesting framework. Good example of how to organize modules, threads, and output logging. Complex but useful reference.
- BlackWidow is simpler and focused only on web app scanning + OSINT. Easier to understand for building a Python scanner.
- Topic 1 projects require more coding, logic planning, and Python troubleshooting. More technical.
- Topic 2 projects like StevenBlack/hosts are about blocking known malware domains. Simple prevention method, useful but limited.
- Nginx Bad Bot Blocker is more advanced – blocks malicious bots/traffic at web server level. Good example of perimeter defense.
- Topic 2 projects are not “tools” in the same way as Topic 1. They are more like security configurations.
- Topic 1 = scanning and finding vulnerabilities. Topic 2 = reducing attack surface and preventing ransomware.
- Nettacker shows how to structure scanner output in JSON/HTML – useful idea for my tool.
- Topic 2 repos made me think more about real defense strategies instead of just hacking.
- Topic 1 seemed more creative and customizable since I can build my own tool. Topic 2 felt more about applying existing concepts and analyzing strategies.
- Both topics connect to cybersecurity careers but from different angles: Topic 1 = penetration tester, Topic 2 = SOC analyst/blue team side.
  
### Questions from GitHub Research

- How do tools like Nettacker manage so many modules without breaking things?
- Should my vulnerability scanner use threads/multi-threading like Nettacker?
- What’s the best format to export results? JSON? HTML report?
- How do I pull CVE data into my tool automatically?
- Is BlackWidow still reliable even though it hasn’t been updated recently?
- How can I test a scanner safely without hitting real networks?
- For Topic 2: How do blocklists like StevenBlack stay updated and accurate?
- Can domain blocking really stop ransomware, or is it just a small layer of defense?
- The Nginx Bot Blocker blocks bad traffic – could this help prevent ransomware delivery?
- Why don’t companies use open-source ransomware defense tools more often?
- Can I combine both offensive and defensive knowledge in my project portfolio?
- Should I build something defensive too later to balance my skills?
