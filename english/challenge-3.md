---
description: 'Mina Hardware Survey. (1,000 bonus pts)'
---

# Challenge \#3

### Technical characteristics

The Mina team would like to know more about the hardware you intend to use for the upcoming Mina testnet 3.3 release. The information you provide will help us make improvements in future releases.

Fill out the form at [this link](https://forms.gle/Qft3VquQ5Nobgetb7).

The form has a CPU Platform item. To find out what platform you have, use the instructions below and fill in the answer in the form.

### On Linux:

Install GCC:

```text
sudo apt install build-essential curl -y
sudo apt-get install manpages-dev
```

```text
gcc -march=native -Q --help=target | sed -ne 's/^  -march=\W*\(.*\)$/\1/p'
```

In return, you will receive:

{% code title="\#EXAMPLE OF ANSWER" %}
```text
broadwell or knl...
```
{% endcode %}

![](../.gitbook/assets/image%20%285%29.png)

### On Windows:

1. Install Windows Subsystem for Linux. 
2. Then follow the instructions for Linux described above.

### On Mac OSX:

1. Open terminal 
2. Enter the command:

```text
sysctl -n machdep.cpu.brand_string
```

In return, you will receive:

{% code title="\#EXAMPLE OF ANSWER" %}
```text
Intel(R) Core(TM) i5-8257U CPU @ 1.40GHz
```
{% endcode %}

