# Remarkable 2

## Using Modifications

This likely requires us to downgrade the firmware to match the latest [toltec version](https://toltec-dev.org/).

I've tested Toltec on version 3.10x and some applications worked, with majority not working.
Toltec only officially supports "builds between 2.6.1.71 and 2.15.1.1189", hence the reason we are required to downgrade the firmware to use additional applications.

- From testing, the repository itself works, the only application which does not function properly is `rm2fb-client`, which requires a lot of manual intervention to work properly. 
Again, not officially supported.

We can do this with [codexctl](https://github.com/Jayy001/codexctl) by using the command:

 ``codexctl --auth PASSWORD install toltec``

Afterwords, we can install [toltec](https://toltec-dev.org/):

```
# 4/1/2024
# Check the official site to ensure the hash is updated

wget http://toltec-dev.org/bootstrap
echo "37f6cc2a0c87dfe9b895c01a546315e9e43d87b9dc04e39b28e2c76ea87b1f7c  bootstrap" | sha256sum -c && bash bootstrap
```

## Installing Packages
[Stable Repo](https://toltec-dev.org/stable/) | [Testing Repo](https://toltec-dev.org/testing/)

We can switch to the beta branch by running:

``toltecctl switch-branch testing``

We should update packages:

``opkg update && opkg upgrade``

We can install the [linux-stracciatella](https://github.com/Etn40ff/linux-remarkable) kernel via

``opkg install linux-stracciatella kernelctl``

then using `kernelctl` to select the proper kernel.

To launch applications we need to install a launcher of your choosing.

``opkg install remux``

