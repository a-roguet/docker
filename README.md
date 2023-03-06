### Set up R in docker for WSLH-EHD wastewater genomic surveillance

Download docker_r_dashboard repository
```git clone https://github.com/a-roguet/docker_r_dashboard/```

Go to the repository
```cd docker_r_dashboard```

Build the r docker (dashboard)
```docker build r -t r/dashboard:lastest```


Verify it works by running. If the R console is displayed on your terminal, you are golden. 
```docker run -ti r/dashboard:lastest R```

