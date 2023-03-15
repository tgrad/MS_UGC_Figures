# Load Author Week Level data
```stata
use "~/replication_author_week.dta", clear
```

## Figure 3a: All Citizens
```{stata, include=TRUE}
reghdfe art_auth ib3052.week c.holiday_week if author_type==5&(week<3062)&(week>3044), absorb(author_id) cluster(author_id)
coefplot, baselevels omitted drop(holiday_week _cons) vertical yline(0) xline(9) levels(99)  coeflabels(3043.week="-10" 3044.week="-9" 3045.week="-8" 3046.week="-7" 3047.week="-6" 3048.week="-5" 3049.week="-4" 3050.week="-3" 3051.week="-2" 3052.week="-1" 3053.week="0" 3054.week="1" 3055.week="2" 3056.week="3" 3057.week="4" 3058.week="5" 3059.week="6" 3060.week="7" 3061.week="8" 3062.week="9" 3063.week="10")  ytitle("Citizen Journalist Content") xtitle("Number of Weeks Before and After") title("Impact of Platform Change on Content")
graph export "~/Fig3a.png", as(png) name("Graph") replace
```
![Figure 3a](/Fig3a.png)



## Figure 3b: Experienced Citizens
```{stata, include=TRUE}
reghdfe art_auth ib3052.week c.holiday_week if author_type==5&(week<3062)&(week>3044)&pre_tot_suc>141, absorb(author_id) cluster(author_id)
coefplot, baselevels omitted drop(holiday_week _cons) vertical yline(0) xline(9) levels(99)  coeflabels(3043.week="-10" 3044.week="-9" 3045.week="-8" 3046.week="-7" 3047.week="-6" 3048.week="-5" 3049.week="-4" 3050.week="-3" 3051.week="-2" 3052.week="-1" 3053.week="0" 3054.week="1" 3055.week="2" 3056.week="3" 3057.week="4" 3058.week="5" 3059.week="6" 3060.week="7" 3061.week="8" 3062.week="9" 3063.week="10")  ytitle("Citizen Journalist Content") xtitle("Number of Weeks Before and After") title("Impact of Platform Change on Content")
graph export "~/Fig3b.png", as(png) name("Graph") replace

```
![Figure 3b](/Fig3b.png)



## Figure 3c: Inexperienced Citizens
```{stata, include=TRUE}
reghdfe art_auth ib3052.week c.holiday_week if author_type==5&(week<3062)&(week>3044)&pre_tot_suc<141, absorb(author_id) cluster(author_id)
coefplot, baselevels omitted drop(holiday_week _cons) vertical yline(0) xline(9) levels(99)  coeflabels(3043.week="-10" 3044.week="-9" 3045.week="-8" 3046.week="-7" 3047.week="-6" 3048.week="-5" 3049.week="-4" 3050.week="-3" 3051.week="-2" 3052.week="-1" 3053.week="0" 3054.week="1" 3055.week="2" 3056.week="3" 3057.week="4" 3058.week="5" 3059.week="6" 3060.week="7" 3061.week="8" 3062.week="9" 3063.week="10")  ytitle("Citizen Journalist Content") xtitle("Number of Weeks Before and After") title("Impact of Platform Change on Content")
graph export "~/Fig3c.png", as(png) name("Graph") replace
```
![Figure 3c](/Fig3c.png)



## Figure 4a: All Professionals
```{stata, include=TRUE}
reghdfe art_auth ib3052.week c.holiday_week if author_type==4&(week<3062)&(week>3044), absorb(author_id) cluster(author_id)
coefplot, baselevels omitted drop(holiday_week _cons) vertical yline(0) xline(9) levels(99)  coeflabels(3043.week="-10" 3044.week="-9" 3045.week="-8" 3046.week="-7" 3047.week="-6" 3048.week="-5" 3049.week="-4" 3050.week="-3" 3051.week="-2" 3052.week="-1" 3053.week="0" 3054.week="1" 3055.week="2" 3056.week="3" 3057.week="4" 3058.week="5" 3059.week="6" 3060.week="7" 3061.week="8" 3062.week="9" 3063.week="10")  ytitle("Professional Journalist Content") xtitle("Number of Weeks Before and After") title("Impact of Platform Change on Content")
graph export "~/Fig4a.png", as(png) name("Graph") replace
```
![Figure 4a](/Fig4a.png)




## Figure 4b: Experienced Professionals
```{stata, include=TRUE}
reghdfe art_auth ib3052.week c.holiday_week if author_type==4&(week<3062)&(week>3044)&pre_tot_suc>12368, absorb(author_id) cluster(author_id)
coefplot, baselevels omitted drop(holiday_week _cons) vertical yline(0) xline(9) levels(99)  coeflabels(3043.week="-10" 3044.week="-9" 3045.week="-8" 3046.week="-7" 3047.week="-6" 3048.week="-5" 3049.week="-4" 3050.week="-3" 3051.week="-2" 3052.week="-1" 3053.week="0" 3054.week="1" 3055.week="2" 3056.week="3" 3057.week="4" 3058.week="5" 3059.week="6" 3060.week="7" 3061.week="8" 3062.week="9" 3063.week="10")  ytitle("Professional Journalist Content") xtitle("Number of Weeks Before and After") title("Impact of Platform Change on Content")
graph export "~/Fig4b.png", as(png) name("Graph") replace
```
![Figure 4b](/Fig4b.png)




## Figure 4c: Inexperienced Professionals
```{stata, include=TRUE}
reghdfe art_auth ib3052.week c.holiday_week if author_type==4&(week<3062)&(week>3044)&pre_tot_suc<12368, absorb(author_id) cluster(author_id)
coefplot, baselevels omitted drop(holiday_week _cons) vertical yline(0) xline(9) levels(99)  coeflabels(3043.week="-10" 3044.week="-9" 3045.week="-8" 3046.week="-7" 3047.week="-6" 3048.week="-5" 3049.week="-4" 3050.week="-3" 3051.week="-2" 3052.week="-1" 3053.week="0" 3054.week="1" 3055.week="2" 3056.week="3" 3057.week="4" 3058.week="5" 3059.week="6" 3060.week="7" 3061.week="8" 3062.week="9" 3063.week="10")  ytitle("Professional Journalist Content") xtitle("Number of Weeks Before and After") title("Impact of Platform Change on Content")
graph export "~/Fig4b.png", as(png) name("Graph") replace
```
![Figure 4c](/Fig4c.png)



## Figure 5: All Other Journalists
```{stata, include=TRUE}
reghdfe art_auth ib3052.week c.holiday_week if main==0&(week<3062)&(week>3044), absorb(author_id) cluster(author_id)
coefplot , baselevels omitted drop(holiday_week _cons) vertical yline(0) xline(9) levels(99)  coeflabels(3043.week="-10" 3044.week="-9" 3045.week="-8" 3046.week="-7" 3047.week="-6" 3048.week="-5" 3049.week="-4" 3050.week="-3" 3051.week="-2" 3052.week="-1" 3053.week="0" 3054.week="1" 3055.week="2" 3056.week="3" 3057.week="4" 3058.week="5" 3059.week="6" 3060.week="7" 3061.week="8" 3062.week="9" 3063.week="10")  ytitle("All Other Journalists Content") xtitle("Number of Weeks Before and After") title("Impact of Platform Change on Content")
graph export "~/Fig5.png", as(png) name("Graph") replace
```
![Figure 5](/Fig5.png)



# Load Article-level Engagement Data
```{stata, include=TRUE}
use "~/replication_summary_stats_article_level.dta",clear
```
## Figure 6a: Aggregated
```{stata, include=TRUE}
reghdfe ln_clicks new_website if (week<3062)&(week>3044)&(containsdistrict==1), absorb(author_id publ_hour holiday_week) cluster(author_id)
estimates store National_News_Articles
reghdfe ln_clicks new_website  if (week<3062)&(week>3044)&(containsatleastonecountyname==1), absorb(author_id publ_hour holiday_week) cluster(author_id)
estimates store Local_News_Articles
reghdfe ln_clicks new_website  if (week<3062)&(week>3044)&(containsatleastonecountyname==1|containsdistrict==1), absorb(author_id publ_hour holiday_week) cluster(author_id)
estimates store Local_and_National_Articles
coefplot Local_and_National_Articles Local_News_Articles National_News_Articles, baselevels omitted drop(holiday_week _cons) recast(connected) ciopts(recast(rcap)) vertical yline(0) xline(9) levels(99)  coeflabels(new_website="Different Content Producers")  ytitle("Effect on Clicks")  title("Impact of Platform Change on Engagement")
graph export "~/Fig6a.png", as(png) name("Graph") replace
```
![Figure 6a](/Fig6a.png)


## Figure 6b: Disaggregated
```{stata, include=TRUE}
reghdfe ln_clicks new_website  if (week<3062)&(week>3044)&(containsatleastonecountyname==1)&author_type==4, absorb(author_id publ_hour holiday_week) cluster(author_id)
estimates store Professional_Local_Articles
reghdfe ln_clicks new_website  if (week<3062)&(week>3044)&(containsdistrict==1)&author_type==4, absorb(author_id publ_hour holiday_week) cluster(author_id)
estimates store Professional_Nat_Articles
reghdfe ln_clicks new_website  if (week<3062)&(week>3044)&(containsatleastonecountyname==1)&author_type==5, absorb(author_id publ_hour holiday_week) cluster(author_id)
estimates store Citizen_Local_Articles
reghdfe ln_clicks new_website  if (week<3062)&(week>3044)&(containsdistrict==1)&author_type==5, absorb(author_id publ_hour holiday_week) cluster(author_id)
estimates store Citizen_National_Articles
coefplot Citizen_National_Articles Citizen_Local_Articles Professional_Nat_Articles Professional_Local_Articles, baselevels omitted drop(holiday_week _cons) recast(connected) ciopts(recast(rcap)) vertical yline(0) xline(9) levels(99)  coeflabels(new_website="Different Content Producers")  ytitle("Effect on Clicks")  title("Impact of Platform Change on Engagement")
graph export "~/Fig6b.png", as(png) name("Graph") replace
```
![Figure 6b](/Fig6b.png)

