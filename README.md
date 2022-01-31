# Recon_methodology 
recon from my perspective and  combining different methodlogies of security reasearchers such as jason haddix , nahamsec and more

### Access playlist here : <a href="https://www.youtube.com/watch?v=W8XT_KIzxBA&list=PLf3J-S0CLK3VSusI8Gn4f4ZKS16UIn720">Recon Playlist </a>
### POCs playlist : <a href="https://www.youtube.com/playlist?list=PLf3J-S0CLK3WBYAILJWkjk5-PHjUinwyv">Proof of concepts playlist</a>
### New playlists: <a href="https://youtu.be/zO06tfmnhZg">AWS pentesting playlist</a>

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

### 2 Recon from google dorks see this amazing tool Bigbounty recon
<a href="https://github.com/Viralmaniar/BigBountyRecon">BIGBOUNTY RECON</A>
###  3 How to organise work for bug bounty 

software for organizing the work: xmind

<a href="https://github.com/anurag708989/recon_methodology/blob/main/jasonHaddix_PentestingTemplate.xmind">JASON HADIX TEMPLATE</a>

### 4 directry fuzzing or content finding  (ffuz), httprobe , byp4xx 

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

### <a href="https://youtu.be/Kya7bSGnJjY">Github Recon</a>

Resources and References
### 5 Github Dorks
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



### 6 Automated github recon using GitDorker
#### see original repo here : <a href="https://github.com/obheda12/GitDorker">GitDorker</a>

#### see tutorial here : <a href="https://youtu.be/zgpDx41LsL4">youtube_automated_github_recon_tutorial</a>

#### google output sheet ably : <a href="https://docs.google.com/spreadsheets/d/12wDg1ma56622LooraVT7BV9-GFEKs5G0wIzIzTuScig/edit?usp=sharing">reconSheetAbly</a>

### Steps:
1 clone the repository 
```
git clone https://github.com/obheda12/GitDorker.git
```
2. move to GitDorker diretry 

```
cd GitDorker

```
3. installation steps
```
pip3 install -r requirements.txt
```
4. use this command for more options
```
python3 GitDorker.py -h
```
5. generate personal access token 
githubAccount > settings > developer settings > personal access tokens

6. copy the tokens to a file say  github_token_for_gitdoreker.txt

7. just run command
```
python3 GitDorker.py -q <give primary query here - say tesla.com> -tf github_token_for_gitdorker.txt -d dorks_file.txt -o output.csv
```

### 7 Automated S3 bucket recon using lazys3 and s3scanner
#### lazys3 (<a href="https://github.com/nahamsec/lazys3">Nahamsec s3</a>)
##### Details:
A Ruby script to bruteforce for AWS s3 buckets using different permutations.
usage
```
ruby lazys3.rb <company>
```


### 8 Getting Starting with AWS pentesting |  s3 buckets

full youtube video: https://youtu.be/zO06tfmnhZg

chrome extension (uDomainFlag) : https://chrome.google.com/webstore/detail/udomainflag/eklbfdpploakpkdakoielobggbhemlnm?hl=en


#### using nuclei:

you can use technologies template to detect s3

for example using subfinder 

1.
```
subfinder -d target.com | httprobe -prefer-https | tee subdomain_1.txt
```

now use it in nuclei

2.

```
nuclei -l subdomain_1.txt -t path-to-template -o output-file.txt
```

#### using host command

```
host target.com
```



s3 vulnerability:
bucket listing
---> all public access

``` 
aws s3 ls s3://flaws.cloud --region us-west-2 --no-sign-request
```
---> access to aws users only
aws should be configured
command  to set configuration:
```
aws configure
```

```
aws s3 ls s3://flaws.cloud --region us-west-2 
```


tools for s3 crawl/enum : https://github.com/mxm0z/awesome-sec-s3

Bucket flaws: https://github.com/nikhil1232/Bucket-Flaws
