---
description: 'Provide time to produce blocks using the New Pickles SNARK (1,000 pts)'
---

# Challenge \#1

### Opening Coda logs

```text
sudo docker logs --follow coda
```

We are looking for lines with`Producing block in 0 slots` and `Generated transition $state_hash was accepted into transition frontier` and take a screenshot as in the picture below. Next, we count the time from the production of a block to the generation of a new one. In my case, it is 4 minutes 57 seconds.

Save the screenshot and time before generating a new block, and also copy the contents of the logs to a text file. We need this to fill out the form.

![](../.gitbook/assets/image%20%282%29.png)

