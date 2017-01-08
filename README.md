# Stroop_effect


> stroop=read.csv('stroop.csv')
> str(stroop)
> stroop%>%mutate(subject = 1:nrow(dat))
> library(dplyr)
> a<-stroop%>%mutate(subject = 1:nrow(stroop))
> tidy.dat <- gather(a, congruency, time, -subject)
> tidy.dat
>tidy.dat %>%
    group_by(congruency) %>%
    summarise(mean(time), median(time), sd(time), var(time))
>library(ggplot2)
>b <- ggplot(tidy.dat, aes(y = time, x = congruency, fill = congruency))
>b + geom_boxplot()
>h <- ggplot(tidy.dat, aes(x = time, fill = congruency))
>h + geom_histogram()
> t.test(x=a$Congruent, y=a$Incongruent, alternative = "two.sided", mu = 0, paired = TRUE, conf.level = 0.95)
