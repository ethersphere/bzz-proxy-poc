# bzz-proxy-poc

**This repo is now archived as we have implemented this functionality as part of https://github.com/ethersphere/gateway-proxy/**

Proof-of-concept proxy service for serving web content from Swarm with subdomains.

# Usage

## Installation

```
npm install
```

## Running

```
npm start
```

## Setting up DNS

You may need to set up DNS with wildcard submdomain support.

## Environment variables

- `PROXY_TARGET`: the target host (default: http://localhost:1633)
- `PROXY_PORT`: the port to serve requests (default: 8633)

## Utilities

Because the maximum length of a subdomain can be 63 characters, we need to convert Swarm hashes to CIDs.

There are command line utilities to convert a hash to CID:

```
% node hash2cid.js 3bde66cca4bcbc3c49f21b55446dc437fb2d71a1948528d181e743050a51e66d
{
  cid: 'bafybwib33ztmzjf4xq6et4q3kvcg3rbx7mwxdimuquundaphimcquupgnu',
  version: 1,
  codec: 'dag-pb',
  multihash: Uint8Array(34) [
     27,  32,  59, 222, 102, 204, 164, 188,
    188,  60,  73, 242,  27,  85,  68, 109,
    196,  55, 251,  45, 113, 161, 148, 133,
     40, 209, 129, 231,  67,   5,  10,  81,
    230, 109
  ],
  multibaseName: 'base32'
}
```

And CID to hash:

```
% node cid2hash.js bafybwib33ztmzjf4xq6et4q3kvcg3rbx7mwxdimuquundaphimcquupgnu
3bde66cca4bcbc3c49f21b55446dc437fb2d71a1948528d181e743050a51e66d
```
