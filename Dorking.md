# What is dorking and why do you need it?
---
Google dorking is used to search more profecionally through the internet.  In this guide I will be showing keywords, tips and tricks that you can also use when you use searchbars in websites. 

You might be wondering why you don't get the same results when you simply write it. The reason is; when you simply write it google algorithm doesn't take it as it is.  It takes your query as what you might actually meant by that query. So when your query searched  it is different than you wrote it. By dorking, you simply say: "No don't change that, I definetely want this word inside my results.". 

Commonly this feature exist in search engines but also can be used in in website searchbars such as Github, Youtube, Twitter or even Discord.  Of course all of them doesn't include same keywords or syntax to do that, different services have their own keywords but if  you can understand the approach you can navigate your way around. 

For starters I will start with defaults you can see on google. I will also put some github dorking content. Of course inside article there won't be enough examples but I will leave some cool dorking examples on the sources section. 

#### OK there exists dorking, why do we use it?
It is actively used by experienced users to search spesific vulnerabilities all over the web. You don't have to be that experienced user, finding what you are looking for is much faster when you know how to search it. 

---
### Basics over Google Search
---
Here are some operators you should know, there is no need to limit these operators only with search engines, operators are commonly used inside website searchbars.

### Operators:

** @socialmedia query ** -> Social media search
** query -excludedword **-> Exclude words
** query +included word **-> Include words
** "query" **-> Exact match
** query1..query2 **-> Ranged search
** query1 OR query2 (query1 | query2) ** -> Search both queries seperately
** query1 AND query2 (query1 & query2) ** -> Results include both queries
** ~query ** -> Searches also for query synonyms
** partofquery ** -> ????????????

### Prefixes:

** intitle:"query" ** -> Only looks for the query word in title. If your query has two words with a space inbetween, is not searched inside the title, it  would be searched like a default query in google. If you use query with multiple words inside  ' *"* ' symbol it would look for exact match inside title.
> ``` intitle:"Welcome to ntop!"  ```
> Ntop is a program that shows current network usage. With this query attacker can gather information if  ntop service is running behind the firewall.  

** allintitle:"query" ** -> This prefix also looks for query in title. It works the same with *intitle* prefix if you use one word query. The difference between *intitle* prefix is; if there are more than one word in query, it looks for those words seperately inside the titles.
> ``` allintitle:"SyncThru Web Service"```
> This search is to find internet-connected Samsung printer control panels. 

** inurl:query ** -> With this prefix keywords are serched inside URL. It is used without space such as *inurl:query1*, if there is a second word used in search and there is space in it "*inurl:word1 word2*" word1 is searched through URL and word2 is searched in everywhere, URL or not URL. If "*inurl*" prefix is used such as "*inurl:word1 inurl:word2*" it is equivalent to "*allinurl:word1 word2*". 
> ```inurl:select_file2.php ```
>This search is for spesifically Flashden multiple file uploader shell upload vulnerability.

** allinurl:"query" ** -> Keywords given are also searched inside URL. Every parameter given after this parameter (independent from space characters and symbols) are searched inside url seperately. If exact match is needed use ' " ' characters. 
>``` allinurl:install/install.php```
> Since "/" like symbols doesn't effect results, "install" and "install.php" keywords are searched seperately inside URL.  

** filetype:"query" ** -> Specify file type you are looking for.
>```filetype:pdf "Assesement Report" nessus ```
>By this search you search through the internet for nessus vulnerability scan reports. By these reports attackers can perform attacks over systems mentioned in those reports.

** intext:"query" ** -> The query specifies the word you want to see inside page.
>```inurl:"smb.conf" intext:workgroup filetype:conf ```
> With this search attacker search samba configuration files.

** allintext:"query" ** -> Same as intext, but without quatotion marks of course. (Quatotion marks mean exact match as told before.) Multiple words are searched seperately inside website text.

** site:"query" ** -> 	Search results are limited with the domains given to this parameter.
 >```site:docs.google.com allintitle:cv OR resume OR "curriculum vitae"```
 >With this query attacker can search inside google docs for resumes to use in a phishing attack. Of course to be more spesific *countr:us* like prefixes can be added. 
 
 ** link:"query"  ** -> If a page includes link given on query, that webpage will be listed in results.
 
 ** inanchor:"query" / allinanchor:"query" ** -> Searches given keyword inside anchors. (Anchor is the result links you click after search.)
 
 ** insubject:"query" ** -> With given subject  parameters, results are limited with given query. This prefix can be useful while finding articles.  
> ``` insubject:deobfuscation filetype:pdf malware analysis ```


** before:/after: ** ->  These prefixes  are used to specify time interval.
> ```"cerberus" after:2020-04-12 malware```

** related: ** -> Lists results similar with given parameter. If you like a domain you can find similar blogs or websites with this prefix.
> ```related:fireeye.com ```

** cache: ** -> Retuns results from Google's cache. If a webpage has been deleted or changed recently you can view old version by using this parameter.

** define: ** -> Define is the prefix you can use if you are looking for definiton of a word. It provides you with explanation that Google chosed. If you are dealing with unknown definition, it is easier to learn what that definition means with this prefix.   

** stocks: **  -> This prefix is used to see stock information of given parameters. Given parameters must be ticker symbols.
>``` stocks: intc yhoo```
> As a result of this query, there will be intel and yahoos stock price related results.

**imagesize:widthxheight**-> You can search in images for images with better resolutions.

---
### Github Advanced Search
---
Github already has awesome documentation about it's advanced search rules. I highly recommend you read it. It explains much better than any external resource. 

### Operators

** >,  <, >=, <= **  -> Usage: *query prefix:n1<=n2* : (greater, less, greater than or equal, lesser than or equal)

** n..\*, \*..n , n1..n2 **  -> *" query prefix:n..\*"*,  "  *query prefix:\*..n"*, "*query prefix:n1..n2*" : (smaller than n, bigger than n, between n1 and n2)

** AND, OR, NOT(-) ** 

>``` xoxp OR xoxb ```
> This search query is used to check if there is any slackbot private tokens. 

Date time format is *YYYY-MM-DD*. You can combine date-time parameter with operators above.

>``` process injection created:>2020-01-01```
This means you are searching for process injection related results which created after January 1, 2020. 

You can use quotation marks when there is whitespace character in your query. Also use quotation marks when you want exact match in results. 

### Prefixes

**user:** -> See results related with spesific username.
**org** -> Search by organization name.
**topic: ** -> Search by topic.
**followers:** -> Search by number of followers.
**forks:**-> Search by number of forks.
**stars:** -> Find by amount of stars in a repository.
**commiter**-> Return commits of user given as parameter.
**language**-> Search query by programming language it is written.
**created:** -> By specifying date, you can search when query has been  created.
**licence:** -> Search by licence
**size:** -> Specify file size.
**pushed:** -> Usually combined with date parameter. You can search by the date-time period query was pushed into repository.
**extension: ** -> Search by file extension.
**path: ** -> Search by file path.
**mentions:**-> Return results if query is related by mentions with given parameter. 

** query type:pr** -> Search for pull requests.
** query type:issue**-> Search for issues.

**status:pending/success/failure**-> Search by pull request status of given query. 

** query in:name** -> Results are limited with query existing  in repository name.
** query in:description **-> Results are limited with query existing in project description.
** query in:title**-> Search query match in title.
** query in:body**-> Search query match in body.
** query in:comments**-> Search query match in comments.

**is:open/closed**-> Check queried open/closed issues.
**is:public/private:**-> Check if repository is public/private.

**archived:true/false**-> Show results if resulting repositories are archived or not.
**merge:true/false**-> Show merged/non-merged commits. 

**hash:<Hash>** ->  Return match for the hash.
**tree:<Hash>**-> Search for tree by given hash value.
**parent:<Hash>**-> Search for parent by given hash value.

There is much more prefixes you can find on github documentation. I only listed prefixes that non-experienced user like me might use. 
	
## Sources and Reading Recommendations

* https://support.google.com/websearch/answer/2466433?visit_id=637370847876672573-3362801961&rd=1&hl=en

* https://gist.github.com/sundowndev/283efaddbcf896ab405488330d1bbc06

* https://docs.github.com/en/free-pro-team@latest/github/searching-for-information-on-github/understanding-the-search-syntax

* https://gist.github.com/stevenswafford/393c6ec7b5375d5e8cdc

* https://www.ionos.com/digitalguide/online-marketing/search-engine-marketing/search-more-effectively-with-google-operators/

* This  is the github documentation I mentioned: https://docs.github.com/en/free-pro-team@latest/github/searching-for-information-on-github/understanding-the-search-syntax

* Even more github documentation for you: https://docs.github.com/en/free-pro-team@latest/github/searching-for-information-on-github/searching-on-github

* Dorks with explanations: http://index-of.co.uk/Google/ghdb.pdf
