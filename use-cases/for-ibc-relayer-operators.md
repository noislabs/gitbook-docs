---
description: >-
  Relayers transfer packets from a chain to another via IBC. They will ship the
  randomness from Nois chain to the consumer chains
---

# 🌉 For IBC relayer operators

{% hint style="info" %}
In this tutorial we are using the ts-relayer by confio as a relayer software.\
However, feel free to use other relayer software like Hermes and if you want to contribute to the docs by providing the steps for setting up such different software let us know on discord
{% endhint %}

{% hint style="warning" %}
We are not doing token transfer ICS 20 yet. The relayers we are currently operating on the wasm ports and they are relaying randomness data not tokens
{% endhint %}

### Setting up ts-relayer

\
Install docker from this [link](https://docs.docker.com/engine/install/ubuntu/)

#### &#x20;elgafar-1 => nois relay

```shell
export MNEMONIC='<YOUR_MNEMONICS_HERE>'
export CHAIN_ID=elgafar-1

#Check #deployment discord channel for this value
export NOIS_PROXY=<NOIS_PROXY_ADDR_ON_CONSUMER_CHAIN>
#example:
#export NOIS_PROXY=juno162vdumcg626zxumvuh9u6vxcakr3rrn804dxfex8qfxnhrldl68ss0lrdn

docker run -d -e "MNEMONIC=$MNEMONIC" \
            noislabs/nois-relayer:$CHAIN_ID-$NOIS_PROXY-prd
```

#### euphoria-2 => nois relay

```shell
export MNEMONIC='<YOUR_MNEMONICS_HERE>'
export CHAIN_ID=euphoria-2

#Check #deployment discord channel for this value
export NOIS_PROXY=<NOIS_PROXY_ADDR_ON_CONSUMER_CHAIN>
#example:
#export NOIS_PROXY=juno162vdumcg626zxumvuh9u6vxcakr3rrn804dxfex8qfxnhrldl68ss0lrdn

docker run -d -e "MNEMONIC=$MNEMONIC" \
            noislabs/nois-relayer:$CHAIN_ID-$NOIS_PROXY-prd
```

#### uni-6 => nois-testnet-003 relay

```shell
export MNEMONIC='<YOUR_MNEMONICS_HERE>'
export CHAIN_ID=uni-6

#Check #deployment discord channel for this value
export NOIS_PROXY=<NOIS_PROXY_ADDR_ON_CONSUMER_CHAIN>
#example:
#export NOIS_PROXY=juno162vdumcg626zxumvuh9u6vxcakr3rrn804dxfex8qfxnhrldl68ss0lrdn

docker run -d -e "MNEMONIC=$MNEMONIC" \
            noislabs/nois-relayer:$CHAIN_ID-$NOIS_PROXY-prd
```

#### &#x20;juno-1 => nois-testnet-003 relay

[https://ibc.nois.network/connections/connection-28/channels/wasm.nois1s9ly26evj8ehurptws5d6dm4a9g2z0htcqvlvn95kc30eucl4s5sd8hkgp:channel-20](https://ibc.nois.network/connections/connection-28/channels/wasm.nois1s9ly26evj8ehurptws5d6dm4a9g2z0htcqvlvn95kc30eucl4s5sd8hkgp:channel-20)

```shell
export MNEMONIC='<YOUR_MNEMONICS_HERE>'
export CHAIN_ID=juno-1

#Check #deployment discord channel for this value
export NOIS_PROXY=<NOIS_PROXY_ADDR_ON_CONSUMER_CHAIN>
#example:
#export NOIS_PROXY=juno162vdumcg626zxumvuh9u6vxcakr3rrn804dxfex8qfxnhrldl68ss0lrdn

docker run -d -e "MNEMONIC=$MNEMONIC" \
            noislabs/nois-relayer:$CHAIN_ID-$NOIS_PROXY-prd
```
