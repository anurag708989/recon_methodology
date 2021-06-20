# Recon_methodology 
recon from my perspective and  combining different methodlogies of security reasearchers such as jason haddix , nahamsec and more


Increasing the target region:

## Part 1 find subdomains of target from different tools || google dorks  

### google dorks:

site: *.hackerone.com
site: *.*.hackerone.com

### sublis3r
sublist3r -d domain-name

### dnsrecon :

dnsrecon -d hackerone.com -D ~/wordlists/subdomains.txt -t brt


### Part 2 How to organise work for bug bounty 

software for organizing the work: xmind

<a href="https://github.com/anurag708989/recon_methodology/blob/main/jasonHaddix_PentestingTemplate.xmind">JASON HADIX TEMPLATE</a>
