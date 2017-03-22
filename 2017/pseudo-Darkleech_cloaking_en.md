# pseudo-Darkleech
- Drive-by Download One of the attack campaigns
- Extremely active
  - Yesterday I observed over 20 Compromised sites
- For details, please refer to malware-traffic-analysis and articles of Unit 42
  - http://www.malware-traffic-analysis.net/2017/03/20/index2.html
  - http://researchcenter.paloaltonetworks.com/2016/12/unit42-campaign-evolution-pseudo-darkleech-2016/

---

## PDL's access control
- PDL returns 500 if it accessed more than once with the same IP
  - PDL have an access log
- Returning a normal page when accessing multiple Compromised sites with the same IP
  - Cloaking
    - What is the implementation at the back end

---

## Cloaking
### Experiment
I installed a program to access about 50 Compromised sites and accessed at regular intervals  
The access interval is 0 second, 5 seconds, 15 seconds, 30 seconds, 1 minute, 5 minutes, 10 minutes, 30 minutes, 1 hour  
Each experiment was accessed with different IP and investigation was made to see how many times the inject code could not be observed

---

### Experimental result
The results of each experiment are as follows

#### First time
##### 0 seconds
|no|access time|host|
|:--|:--|:--|
|1|2017-03-21 09:34:04|www[.]ffa[.]hr|
|2|2017-03-21 09:34:06|alkuwarih[.]com|
|3|2017-03-21 09:34:11|www[.]lingoclub[.]com|
|4|2017-03-21 09:34:14|www[.]hejazee[.]ir|
|5|2017-03-21 09:34:17|kachnul[.]org|
|6|2017-03-21 09:34:20|www[.]kremlinpalace[.]org|
|7|2017-03-21 09:34:24|www[.]asmecal[.]it|
|8|2017-03-21 09:34:25|www[.]ext-joom[.]com|
|9|2017-03-21 09:34:35|www[.]irafina[.]gr|
|10|2017-03-21 09:34:38|yubiley[.]org|
|11|2017-03-21 09:34:40|www[.]axioo[.]com|
|12|2017-03-21 09:34:42|www[.]scheduleinterpreter[.]com|
|13|2017-03-21 09:34:44|www[.]monopark[.]com[.]mx|
|14|2017-03-21 09:34:46|lenovo-fun[.]com|
|15|2017-03-21 09:34:49|loadcraft[.]net|
|16|2017-03-21 09:34:53|lapsid[.]sk|
|17|2017-03-21 09:35:02|www[.]utilisersonmac[.]com|

##### 5 seconds
|no|access time|host|
|:--|:--|:--|
|1|2017-03-21 09:44:18|www[.]ffa[.]hr|
|2|2017-03-21 09:44:25|alkuwarih[.]com|
|3|2017-03-21 09:44:35|www[.]lingoclub[.]com|
|4|2017-03-21 09:44:43|www[.]hejazee[.]ir|
|5|2017-03-21 09:44:51|kachnul[.]org|
|6|2017-03-21 09:44:59|www[.]kremlinpalace[.]org|
|7|2017-03-21 09:45:08|www[.]asmecal[.]it|
|8|2017-03-21 09:45:15|www[.]ext-joom[.]com|
|9|2017-03-21 09:45:31|www[.]irafina[.]gr|
|10|2017-03-21 09:45:38|yubiley[.]org|
|11|2017-03-21 09:45:45|www[.]axioo[.]com|
|12|2017-03-21 09:45:52|www[.]scheduleinterpreter[.]com|
|13|2017-03-21 09:46:00|www[.]monopark[.]com[.]mx|

##### 15 seconds
|no|access time|host|
|:--|:--|:--|
|1|2017-03-21 09:59:03|www[.]ffa[.]hr|
|2|2017-03-21 09:59:25|alkuwarih[.]com|
|3|2017-03-21 09:59:50|www[.]lingoclub[.]com|
|4|2017-03-21 10:00:13|www[.]hejazee[.]ir|
|5|2017-03-21 10:00:36|kachnul[.]org|
|6|2017-03-21 10:00:58|www[.]kremlinpalace[.]org|
|7|2017-03-21 10:01:23|www[.]asmecal[.]it|
|8|2017-03-21 10:01:45|www[.]ext-joom[.]com|
|9|2017-03-21 10:02:14|www[.]irafina[.]gr|
|10|2017-03-21 10:02:37|yubiley[.]org|
|11|2017-03-21 10:02:59|www[.]axioo[.]com|

##### 30 seconds
|no|access time|host|
|:--|:--|:--|
|1|2017-03-21 10:18:31|www[.]ffa[.]hr|
|2|2017-03-21 10:19:03|alkuwarih[.]com|
|3|2017-03-21 10:19:37|www[.]lingoclub[.]com|
|4|2017-03-21 10:20:10|www[.]hejazee[.]ir|
|5|2017-03-21 10:20:43|kachnul[.]org|
|6|2017-03-21 10:21:16|www[.]kremlinpalace[.]org|
|7|2017-03-21 10:21:49|www[.]asmecal[.]it|
|8|2017-03-21 10:22:21|www[.]ext-joom[.]com|
|9|2017-03-21 10:22:56|shadshow[.]ir|
|10|2017-03-21 10:23:29|www[.]irafina[.]gr|
|11|2017-03-21 10:24:02|yubiley[.]org|

##### 1 minute
|no|access time|host|
|:--|:--|:--|
|1|2017-03-21 10:35:57|www[.]ffa[.]hr|
|2|2017-03-21 10:36:59|alkuwarih[.]com|
|3|2017-03-21 10:38:03|www[.]lingoclub[.]com|
|4|2017-03-21 10:39:06|www[.]hejazee[.]ir|
|5|2017-03-21 10:40:09|kachnul[.]org|
|6|2017-03-21 10:41:12|www[.]kremlinpalace[.]org|
|7|2017-03-21 10:42:18|www[.]asmecal[.]it|
|8|2017-03-21 10:43:20|www[.]ext-joom[.]com|
|9|2017-03-21 10:44:33|yubiley[.]org|

##### 5 minutes
|no|access time|host|
|:--|:--|:--|
|1|2017-03-21 11:03:11|www[.]ffa[.]hr|
|2|2017-03-21 11:08:13|alkuwarih[.]com|
|3|2017-03-21 11:13:17|www[.]lingoclub[.]com|
|4|2017-03-21 11:18:19|www[.]hejazee[.]ir|
|5|2017-03-21 11:23:22|kachnul[.]org|
|6|2017-03-21 11:28:24|www[.]kremlinpalace[.]org|
|7|2017-03-21 11:33:28|www[.]asmecal[.]it|
|8|2017-03-21 11:38:29|www[.]ext-joom[.]com|
|9|2017-03-21 11:43:35|shadshow[.]ir|

##### 10 minutes
|no|access time|host|
|:--|:--|:--|
|1|2017-03-21 11:13:31|www[.]ffa[.]hr|
|2|2017-03-21 11:23:33|alkuwarih[.]com|
|3|2017-03-21 11:33:37|www[.]lingoclub[.]com|
|4|2017-03-21 11:43:40|www[.]hejazee[.]ir|
|5|2017-03-21 11:53:43|kachnul[.]org|
|6|2017-03-21 12:03:46|www[.]kremlinpalace[.]org|
|7|2017-03-21 12:13:50|www[.]asmecal[.]it|
|8|2017-03-21 12:23:51|www[.]ext-joom[.]com|
|9|2017-03-21 12:34:05|www[.]irafina[.]gr|

##### 30 minutes
|no|access time|host|
|:--|:--|:--|
|1|2017-03-21 09:00:28|www[.]ffa[.]hr|
|2|2017-03-21 09:30:31|alkuwarih[.]com|
|3|2017-03-21 10:00:35|www[.]lingoclub[.]com|
|4|2017-03-21 10:30:37|www[.]hejazee[.]ir|
|5|2017-03-21 11:00:40|kachnul[.]org|
|6|2017-03-21 11:30:43|www[.]kremlinpalace[.]org|
|7|2017-03-21 12:00:47|www[.]asmecal[.]it|
|8|2017-03-21 12:30:48|www[.]ext-joom[.]com|
|9|2017-03-21 13:00:59|www[.]irafina[.]gr|

##### 1 hour
|no|access time|host|
|:--|:--|:--|
|1|2017-03-21 16:19:42|www[.]ffa[.]hr|
|2|2017-03-21 17:19:44|alkuwarih[.]com|
|3|2017-03-21 18:19:49|www[.]lingoclub[.]com|
|4|2017-03-21 19:19:51|www[.]hejazee[.]ir|
|5|2017-03-21 20:19:55|kachnul[.]org|
|6|2017-03-21 21:19:58|www[.]kremlinpalace[.]org|
|7|2017-03-21 22:20:02|www[.]asmecal[.]it|
|8|2017-03-21 23:20:03|www[.]ext-joom[.]com|
|9|2017-03-22 00:20:14|www[.]irafina[.]gr|

---

#### Second time
##### 0 seconds
|no|access time|host|
|:--|:--|:--|
|1|2017-03-22 01:56:14|loadcraft[.]net|
|2|2017-03-22 01:56:23|my-teacher[.]fr|
|3|2017-03-22 01:56:25|www[.]utilisersonmac[.]com|
|4|2017-03-22 01:56:29|www[.]gwbicycles[.]com|
|5|2017-03-22 01:56:33|www[.]poliglot-16[.]com|
|6|2017-03-22 01:56:34|www[.]stanjamesaffiliates[.]com|
|7|2017-03-22 01:56:37|www[.]mediaservis[.]hr|
|8|2017-03-22 01:56:41|www[.]atfalclub[.]com|
|9|2017-03-22 01:56:43|www[.]sohofactory[.]pl|
|10|2017-03-22 01:56:47|www[.]simply-vegan[.]org|
|11|2017-03-22 01:56:49|www[.]lamarieeauxpiedsnus[.]com|
|12|2017-03-22 01:56:51|www[.]gscpsdsd[.]in|
|13|2017-03-22 01:56:53|www[.]analiticaweb[.]es|
|14|2017-03-22 01:56:55|www[.]samethattune[.]com|
|15|2017-03-22 01:57:00|www[.]selfprinting[.]es|

##### 5 seconds
|no|access time|host|
|:--|:--|:--|
|1|2017-03-22 06:29:43|loadcraft[.]net|
|2|2017-03-22 06:29:52|lapsid[.]sk|
|3|2017-03-22 06:30:05|www[.]utilisersonmac[.]com|
|4|2017-03-22 06:30:13|kedaipena[.]com|
|5|2017-03-22 06:30:21|www[.]gwbicycles[.]com|
|6|2017-03-22 06:30:29|www[.]poliglot-16[.]com|
|7|2017-03-22 06:30:36|www[.]stanjamesaffiliates[.]com|
|8|2017-03-22 06:30:43|www[.]mediaservis[.]hr|
|9|2017-03-22 06:30:52|www[.]atfalclub[.]com|
|10|2017-03-22 06:30:59|www[.]sohofactory[.]pl|
|11|2017-03-22 06:31:06|www[.]simply-vegan[.]org|
|12|2017-03-22 06:31:13|www[.]lamarieeauxpiedsnus[.]com|
|13|2017-03-22 06:31:20|www[.]gscpsdsd[.]in|
|14|2017-03-22 06:31:27|www[.]analiticaweb[.]es|
|15|2017-03-22 06:31:34|www[.]samethattune[.]com|
|16|2017-03-22 06:31:43|www[.]selfprinting[.]es|
|17|2017-03-22 06:31:57|www[.]chelagarto[.]com|

##### 15 seconds
|no|access time|host|
|:--|:--|:--|
|1|2017-03-22 04:04:05|www[.]gscpsdsd[.]in|
|2|2017-03-22 04:04:22|www[.]analiticaweb[.]es|
|3|2017-03-22 04:04:40|www[.]samethattune[.]com|
|4|2017-03-22 04:05:00|www[.]selfprinting[.]es|
|5|2017-03-22 04:05:21|www[.]chelagarto[.]com|
|6|2017-03-22 04:05:40|www[.]cosmosbank[.]com|
|7|2017-03-22 04:05:58|www[.]eurodiastasi[.]gr|
|8|2017-03-22 04:06:17|www[.]traccs[.]net|
|9|2017-03-22 04:06:34|biokurier[.]pl|
|10|2017-03-22 04:06:56|oyeintelligence[.]com|
|11|2017-03-22 04:07:19|dietwink[.]com|
|12|2017-03-22 04:07:42|www[.]wallhd4[.]com|
|13|2017-03-22 04:07:58|www[.]lovlose[.]com|
|14|2017-03-22 04:08:16|customwritingtips[.]com|
|15|2017-03-22 04:08:39|medicalhome[.]ir|
|16|2017-03-22 04:09:00|www[.]fortlauderdaledaily[.]com|

##### 30 seconds
|no|access time|host|
|:--|:--|:--|
|1|2017-03-22 06:44:55|loadcraft[.]net|
|2|2017-03-22 06:45:29|lapsid[.]sk|
|3|2017-03-22 06:46:02|my-teacher[.]fr|
|4|2017-03-22 06:46:34|www[.]utilisersonmac[.]com|
|5|2017-03-22 06:47:07|kedaipena[.]com|
|6|2017-03-22 06:47:42|www[.]gwbicycles[.]com|
|7|2017-03-22 06:48:15|www[.]poliglot-16[.]com|
|8|2017-03-22 06:48:47|www[.]stanjamesaffiliates[.]com|
|9|2017-03-22 06:49:19|www[.]mediaservis[.]hr|
|10|2017-03-22 06:49:54|www[.]atfalclub[.]com|
|11|2017-03-22 06:50:28|www[.]sohofactory[.]pl|
|12|2017-03-22 06:51:02|www[.]simply-vegan[.]org|
|13|2017-03-22 06:51:34|www[.]lamarieeauxpiedsnus[.]com|
|14|2017-03-22 06:52:06|www[.]gscpsdsd[.]in|
|15|2017-03-22 06:52:38|www[.]analiticaweb[.]es|

##### 1 minute
|no|access time|host|
|:--|:--|:--|
|1|2017-03-22 03:33:28|www[.]mediaservis[.]hr|
|2|2017-03-22 03:34:33|www[.]atfalclub[.]com|
|3|2017-03-22 03:35:35|www[.]sohofactory[.]pl|
|4|2017-03-22 03:36:37|www[.]simply-vegan[.]org|
|5|2017-03-22 03:37:38|www[.]lamarieeauxpiedsnus[.]com|
|6|2017-03-22 03:38:42|www[.]gscpsdsd[.]in|
|7|2017-03-22 03:39:43|www[.]analiticaweb[.]es|
|8|2017-03-22 03:40:45|www[.]samethattune[.]com|
|9|2017-03-22 03:41:49|www[.]selfprinting[.]es|
|10|2017-03-22 03:43:00|www[.]cosmosbank[.]com|
|11|2017-03-22 03:44:03|www[.]eurodiastasi[.]gr|
|12|2017-03-22 03:45:08|www[.]traccs[.]net|

##### 5 minutes
|no|access time|host|
|:--|:--|:--|
|1|2017-03-22 02:18:51|loadcraft[.]net|
|2|2017-03-22 02:23:57|lapsid[.]sk|
|3|2017-03-22 02:29:06|www[.]utilisersonmac[.]com|
|4|2017-03-22 02:34:08|kedaipena[.]com|
|5|2017-03-22 02:39:10|www[.]gwbicycles[.]com|
|6|2017-03-22 02:44:14|www[.]poliglot-16[.]com|
|7|2017-03-22 02:49:16|www[.]stanjamesaffiliates[.]com|
|8|2017-03-22 02:54:29|www[.]sohofactory[.]pl|
|9|2017-03-22 02:59:31|www[.]simply-vegan[.]org|
|10|2017-03-22 03:04:32|www[.]lamarieeauxpiedsnus[.]com|
|11|2017-03-22 03:09:36|www[.]gscpsdsd[.]in|
|12|2017-03-22 03:14:37|www[.]analiticaweb[.]es|
|13|2017-03-22 03:19:40|www[.]samethattune[.]com|

##### 10 minutes
|no|access time|host|
|:--|:--|:--|
|1|2017-03-22 06:19:17|www[.]gwbicycles[.]com|
|2|2017-03-22 06:29:20|www[.]poliglot-16[.]com|
|3|2017-03-22 06:39:22|www[.]stanjamesaffiliates[.]com|
|4|2017-03-22 06:49:30|www[.]atfalclub[.]com|
|5|2017-03-22 06:59:32|www[.]sohofactory[.]pl|
|6|2017-03-22 07:09:34|www[.]simply-vegan[.]org|
|7|2017-03-22 07:19:35|www[.]lamarieeauxpiedsnus[.]com|
|8|2017-03-22 07:29:39|www[.]gscpsdsd[.]in|
|9|2017-03-22 07:39:41|www[.]analiticaweb[.]es|
|10|2017-03-22 07:49:43|www[.]samethattune[.]com|
|11|2017-03-22 07:59:47|www[.]selfprinting[.]es|
|12|2017-03-22 08:09:53|www[.]chelagarto[.]com|
|13|2017-03-22 08:19:56|www[.]cosmosbank[.]com|
|14|2017-03-22 08:29:59|www[.]eurodiastasi[.]gr|

---

### Consideration
I don't know whether the information of the accessing user exists in the central server or each server, but it has certain rules
- User information is synchronized from each server every 1 minute
  - Transmission processing and synchronization processing are not performed instantaneously
    - There is a delicately time lag, but transmission and synchronization are done in around 0 seconds
- About 10 times, if you access the Compromised site with the same IP, it will be blacklisted
  - There is an error depending on which compromised site you access
    - Whether or not the processing (user's information transmission/synchronization) processing (success/failure), timing and so on are different?
- When entering the blacklist, even if you access the Compromised site you have never accessed, it returns the normal page

## Summary
- PDL shares user information between each compromised site
- About 10 times, if you access with the same IP it will go into the black list
- When you enter the blacklist, even if you visit the Compromised site, the site returns a normal page.
