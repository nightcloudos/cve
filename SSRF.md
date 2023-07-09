The SSRF vulnerability exists in dedeCMS v5.7.109

official website:https://www.dedecms.com/

version:5.7.109

Access the dnslog via the rssurl parameter

![WPS图片(1)](https://github.com/nightcloudos/cve/assets/76925342/de611780-21fd-40d1-af19-e34a3e112973)

The Dnslog command is displayed successfully
![WPS图片(2)](https://github.com/nightcloudos/cve/assets/76925342/f953e92d-e531-4f26-8c74-b1f1d160ddea)

Follow the GetRssLinks() function in the co do.php file

![WPS图片(3)](https://github.com/nightcloudos/cve/assets/76925342/b5bf6db5-633e-4572-aa50-cd716cffeb5d)

Follow up with the OpenUrl() function

![WPS图片(4)](https://github.com/nightcloudos/cve/assets/76925342/ad0aad84-a9e4-4a50-80d8-46780b33103f)

Finding the parse_url() function in the PrivateInit() function is the key to ultimately triggering ssrf

![WPS图片(5)](https://github.com/nightcloudos/cve/assets/76925342/45ec69f9-c1c2-4eb8-be3e-b89c41732f4d)
