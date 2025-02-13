# kernel-listnewyesconfig

When building a new kernel, most of the time we are only interested in new 
things that the kernel devs decided to enable by default. Unfortunately the 
makefile offers no such option. The best we officialy get is 
"make listnewconfig", which will list every single new configuration added to 
the kernel based on the old config you provide. That means you will have to 
spend hours answering "no" to new drivers that you will never use.

In order to avoid that, this patch adds a new mode called

**listnewyesconfig**

As the name implies, it works just like the stock `listnewconfig` target does, 
but instead of showing all new configuations, only new configurations that would
default to "yes" will be shown. Then you can decided if you want to add them or not, 
without having to worry about missing an important config because you were
pressing RETURN like crazy trying to say "no" to a bunch of new drivers
will won't ever need
