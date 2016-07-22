# Useful_Formula_Repo

This repository will have useful formulas that have come into my knowledge base.
Timeconv() is used to take inconsistent times and convert them to a standard format
Times will either be 24-hour HHMM ("1330") or 12-hour strings with AM/PM ("01:30:00 PM")
Functions returns format of 24-hour HH:MM:SS ("13:30:00")
```{r}
timeconv <- function(x) {
        if (nchar(x) == 4) {
                paste(substr(x,1,2), substr(x,3,4), "00", sep=":")
        } else {
                timeadd <- 1
                if (substr(x,nchar(x)-1,nchar(x)) == "PM") timeadd <- 12
                paste0(
                        formatC(as.integer(substr(x,1,2)) + timeadd, width=2, format="d", flag="0"),
                        substr(x,3,nchar(x)-3))
        }
}
```
