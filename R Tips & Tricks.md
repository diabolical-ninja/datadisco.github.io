# Handy Tricks for R

## Progress Bars

Adding a progress bar to a loop is easy enough without any extra libraries required.
```R
loop_length <- 10
pb <- txtProgressBar(min = 0, max = loop_length, style = 3)
for(i in 1:loop_length){
	
	print i
	
	# Update progress bar
	setTxtProgressBar(pb, i)

}

close(pb)
```

Progress bars can also be added to apply functions with the help of a lovely packaged called [pbapply](https://jekyllrb.com/). First lets get the package:
```R
install.packages('pbapply')
```

Then it's just a simple case of loading it and changing your regular `apply` call to `pbapply`:
```R
library('pbapply')
pblapply(1:10, function(x) x+1)
```

## Common Libraries

My most common, bare minimum libraries where ever I am.

```R
install.packages('data.table',
                 'foreach',
                 'RODBC',
                 'ggplot2',
                 'h2o',
                 'doSNOW',
                 'parallel',
                 'gridExtra')
```
