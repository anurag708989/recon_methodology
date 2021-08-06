# Recon_methodology 
recon from my perspective and  combining different methodlogies of security reasearchers such as jason haddix , nahamsec and more

### Access playlist here : <a href="https://www.youtube.com/watch?v=W8XT_KIzxBA&list=PLf3J-S0CLK3VSusI8Gn4f4ZKS16UIn720">Recon Playlist </a>

Increasing the target region:

##  1 find subdomains of target from different tools || google dorks  

### google dorks:

site: *.hackerone.com

site: *.*.hackerone.com

### sublis3r
sublist3r -d domain-name

### dnsrecon :

dnsrecon -d hackerone.com -D ~/wordlists/subdomains.txt -t brt

### subfinder

<a href="https://github.com/projectdiscovery/subfinder"> subfinder</a>


###  2 How to organise work for bug bounty 

software for organizing the work: xmind

<a href="https://github.com/anurag708989/recon_methodology/blob/main/jasonHaddix_PentestingTemplate.xmind">JASON HADIX TEMPLATE</a>

### 3 directry fuzzing or content finding  (ffuz), httprobe , byp4xx 

usefull wordlist if needed (wordlist are already in kali linux seclists but if you need more then checkout):<a href="https://github.com/anurag708989/SecLists"> USEFUL WORDLIST </a>

<a href="https://github.com/tomnomnom/httprobe">HTTPROBE</a>

```
 git clone https://github.com/tomnomnom/httprobe
```

<a href="https://github.com/ffuf/ffuf">FFUZ</a>
```
git clone https://github.com/ffuf/ffuf
```

most used ffuz command : 
```
ffuf -p 0.1 -t 1 -w ~/wordlists/content.txt -u https://www.website.com
```
ffuz command vary for different request such as requests containing parameters and cookies so 
from my opinion just brute force directries and use burp suit for another stuff but if you don't know to use burp then see the documentation from above link and hack!!!.

### Github Recon

Resources and References
Github Dorks
https://securitytrails.com/blog/github-dorks
GitROB
https://michenriksen.com/blog/gitrob-now-in-go/
News
https://nakedsecurity.sophos.com/2019/03/25/thousands-of-coders-
are-leaving-their-crown-jewels-exposed-on-github/
Github Bug Bounty
Hunting
https://gist.github.com/EdOverflow/922549f610b258f459b219a32f
92d10b
Assetnote
https://blog.assetnote.io/bug-bounty/2019/04/23/getting-access-
zendesk-gcp/

