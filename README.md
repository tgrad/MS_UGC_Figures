## Load Author Week Level data
```{stata, include=TRUE}
use "~/Dropbox/Gogol/Stata/input/replication_author_week.dta", clear
```

## Figure 3a
```{stata, include=TRUE}
reghdfe art_auth ib3052.week c.holiday_week if author_type==5&(week<3062)&(week>3044), absorb(author_id) cluster(author_id)
coefplot, baselevels omitted drop(holiday_week _cons) vertical yline(0) xline(9) levels(99)  coeflabels(3043.week="-10" 3044.week="-9" 3045.week="-8" 3046.week="-7" 3047.week="-6" 3048.week="-5" 3049.week="-4" 3050.week="-3" 3051.week="-2" 3052.week="-1" 3053.week="0" 3054.week="1" 3055.week="2" 3056.week="3" 3057.week="4" 3058.week="5" 3059.week="6" 3060.week="7" 3061.week="8" 3062.week="9" 3063.week="10")  ytitle("Citizen Journalist Content") xtitle("Number of Weeks Before and After") title("Impact of Platform Change on Content")
graph export "/Users/tomgrad/Dropbox/CitizenJournalists/Replication files/Figures/Fig3a.png", as(png) name("Graph") replace
```
![Figure 3a](/Fig3a.png)

## Figure 3b
```{stata, include=TRUE}
reghdfe art_auth ib3052.week c.holiday_week if author_type==5&(week<3062)&(week>3044)&pre_tot_suc>141, absorb(author_id) cluster(author_id)
coefplot, baselevels omitted drop(holiday_week _cons) vertical yline(0) xline(9) levels(99)  coeflabels(3043.week="-10" 3044.week="-9" 3045.week="-8" 3046.week="-7" 3047.week="-6" 3048.week="-5" 3049.week="-4" 3050.week="-3" 3051.week="-2" 3052.week="-1" 3053.week="0" 3054.week="1" 3055.week="2" 3056.week="3" 3057.week="4" 3058.week="5" 3059.week="6" 3060.week="7" 3061.week="8" 3062.week="9" 3063.week="10")  ytitle("Citizen Journalist Content") xtitle("Number of Weeks Before and After") title("Impact of Platform Change on Content")
graph export "/Users/tomgrad/Dropbox/CitizenJournalists/Replication files/Figures/Fig3b.png", as(png) name("Graph") replace

```
![Figure 3b](/Fig3b.png)

