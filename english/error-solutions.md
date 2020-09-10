# Error solutions

### 1. Error 132

If your node crashes with error 132, then start the node with the command below:

```text
sudo docker run \
--publish 3085:3085 \
-d \
--name coda \
codaprotocol/coda-demo:pickles-sandbox-classic
```

This could be due to old hardware on the server or home PC where you are running a node. 

Then go back to the installation section and continue from step 3:

{% page-ref page="install-sandbox-node.md" %}

