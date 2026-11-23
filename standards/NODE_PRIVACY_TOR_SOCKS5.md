# Optional Node Privacy — Tor, SOCKS5 Proxies and VPNs

> **Community operator guide — 23 November 2026.** For TAO Revival/TaoX, XNUVA, Europa (ERA), Zeus (ZUS) and Hopium (HOPE). **Source-code capability is NOT evidence of a tested private or anonymous node.**
>
> **Reliability first, release second.** This is optional networking guidance, NOT a change to consensus, wallet balances, signing, mining algorithms or monetary rules. Never experiment on an irreplaceable wallet or live production service without a tested backup and rollback.

## What this does and does not protect

A properly configured Tor SOCKS5 proxy can mask the public IP address of the node operator **from the remote blockchain peers reached through that proxy**. This does **not** make blockchain transactions anonymous, conceal public addresses or balances, protect a compromised machine, hide the fact that Tor may be in use from the local network provider, or guarantee that another program on the same computer uses Tor. A plain SOCKS5 proxy or VPN is not the same privacy system as Tor.

The node's P2P proxy setting typically applies to **blockchain peer networking**, not to the wallet's browser, explorer, updater, mining software, game treasury, RPC services or other applications. Never expose RPC credentials or ports publicly. Use local RPC access only unless separately secured by an expert.

**Important:** Bitcoin-derived `onlynet=onion` ordinarily restricts **automatic outbound peers**, not necessarily manually configured peers or inbound connections. A missing peer set is a connectivity failure, not proof of privacy. Network isolation and independent leak testing are essential before making anonymity claims.

## 1. Choose an operating mode

| Mode | Meaning | When to consider it |
|---|---|---|
| Conventional P2P (default) | Direct internet connections; remote peers may see your IP | Normal operation when privacy routing is not required |
| Tor SOCKS5 to ordinary peers | Outbound P2P traffic goes to the local Tor proxy; ordinary internet peers may be reached through Tor exits | First **isolated experiment** for older clients where v3 onion support is uncertain |
| Tor onion peers only | Outbound peer selection restricted to onion addresses | Only after confirming the client supports **Tor v3 onion addresses** and compatible peers actually exist |
| Tor inbound onion service | Peers can connect to your node using an onion address without disclosing its home IP | More advanced: needs working Tor v3 service, local listening and explicit port/control permissions |
| Another SOCKS5 proxy | A single proxy operator routes your P2P traffic | IP masking from peers, but that proxy provider can observe connection metadata and may log traffic |
| VPN with firewall/kill switch | The VPN may tunnel operating-system traffic for the node | Depends on provider, routing, DNS, split tunnelling, disconnect handling and kill-switch configuration |

**Do not run a Tor SOCKS5 listener on a public interface** (for example 0.0.0.0:9050). Keep it bound to loopback and protect the host firewall.

## 2. Set up a separate Tor service on Ubuntu/Debian

These are examples, **not instructions to run any coin as root**.

1. Back up the existing coin configuration and wallets. Identify the correct daemon, its command-line `-help` options, its current data directory, and the actual configuration file in use. Do not guess a `.conf` filename or edit the wrong network's data.
2. Install the official distribution Tor package and keep it updated:

   ```bash
   sudo apt update
   sudo apt install tor
   ```

3. Start the Tor **service** using your distribution's normal service manager. Some Debian/Ubuntu systems use the `tor@default` instance, whereas others use `tor`. Check the available unit and active listener rather than assuming a unit name:

   ```bash
   systemctl list-units 'tor*' --all
   sudo systemctl start tor
   ss -ltn | grep ':9050'
   ```

   If the last command reports no local listener, inspect your Tor service and `SocksPort` configuration before doing anything with the cryptocurrency. Port **9050 is a common default**, not a universal guarantee. Tor Browser may use another port and is **not** a substitute for verifying a dedicated Tor daemon.

4. Optionally test the Tor SOCKS listener through a request with **remote hostname resolution** (requires `curl`):

   ```bash
   curl --socks5-hostname 127.0.0.1:9050 -fsS https://check.torproject.org/api/ip
   ```

   The test should identify a Tor exit rather than your home internet address. **This verifies the curl test path, not the cryptocurrency node's own P2P connections.**

## 3. Starter configuration: outbound P2P through a SOCKS5 proxy

Only if the **exact installed coin/client build** supports the corresponding settings, add to its existing config file or pass equivalent CLI flags:

```ini
# Example for isolated testing, not an anonymity certification
proxy=127.0.0.1:9050
listen=0
```

- The proxy at 127.0.0.1:9050 must be running on **the same host/network namespace as the coin process**. In Docker or a remote server, 127.0.0.1 is **not** your laptop's Tor service.
- `listen=0` disables incoming P2P listening, including ordinary incoming onion services. A correctly configured Tor-backed inbound node is possible on some modern clients but needs its **own** tested setup.
- For older clients, `proxy` plus `listen=0` is a safer *starting experiment* than assuming a modern `.onion` peer network exists. Tor exit traffic is not itself end-to-end P2P encryption.
- Confirm coin support for the setting in `-help`, the exact binary/source revision and operational logs; different legacy versions may behave differently.

### Optional: onion-only automatic outbound peers (modern, **not yet coin-qualified**)

Test this only on an **isolated compatible modern build** after verifying current Tor v3 support and a source of genuine v3 peers:

```ini
proxy=127.0.0.1:9050
onlynet=onion
listen=0
```

If a coin only recognises obsolete Tor v2 addresses, **do not use or advertise this as a working Tor-only node**. Tor v2 onion services are no longer supported. Modern P2P address relay may need additional compatibility work. Tor-only mode can produce **zero peers**, especially in small networks. No consensus rule, seed list or normal public node settings should be altered to force a result.

**Warning:** `onlynet=onion` does not necessarily block manually configured clearnet `connect`/`addnode` targets or other software traffic; inspect the installed version's precise semantics. Do not claim fail-closed operation without explicit network testing.

## 4. Which of our coins supports what?

| Coin | Source options observed (23 Nov 2026) | User-facing qualification status |
|---|---|---|
| **XNUVA** | Modern networking code exposes `-proxy`, `-onion`, `-onlynet`, `-listenonion`, `-proxyrandomize`, and Tor control options | **Unverified on live Tor.** Presence of code is not proof of v3 connectivity or IP-leak safety. |
| **TAO Revival (current maintained legacy client)** | Historical `-proxy`, SOCKS settings, `-tor`, and network restriction options | **Unverified.** Older `-tor` syntax is not the same as modern `-onion`; avoid promising v3 onion-service support. |
| **TaoX experimental modernisation** | Modern Bitcoin Core-derived overlay contains `-proxy`, `-onion`, `-onlynet`, `-listenonion`, `-proxyrandomize` and Tor control configuration | **Experimental — DO NOT deploy as a live replacement.** Modern Tor code is present; network and release qualification remain open. |
| **Europa (ERA)** | Maintained source contains SOCKS5 `-proxy`, `-onion`, `-onlynet`, and onion listening options | **Unverified** for modern Tor v3 and proxy-only fail-closed networking. |
| **Zeus (ZUS)** | Maintained source advertises `-proxy`, `-onion`, `-onlynet`, and onion listening options | **Unverified** for modern Tor v3; PoW/PoS staking and node availability must be considered separately. |
| **Hopium (HOPE)** | Maintained source advertises `-proxy`, `-onion`, `-onlynet`, and onion listening options | **Unverified** for modern Tor v3; staking and node availability need separate validation. |

**Source review:** [XNUVA init](https://github.com/Xnuva-Blockchain-Project/Xnuva/blob/main/src/init.cpp), [TAO current init](https://github.com/Xnuva-Blockchain-Project/Tao/blob/main/src/init.cpp), [TaoX experimental init](https://github.com/Xnuva-Blockchain-Project/Tao/blob/modernisation/taox-consolidated-full-source/migration/modern-tao-draft/src/init.cpp), [Europa init](https://github.com/Xnuva-Blockchain-Project/Europa/blob/main/src/init.cpp), [Zeus init](https://github.com/Xnuva-Blockchain-Project/Zeus/blob/main/src/init.cpp), [Hopium init](https://github.com/Xnuva-Blockchain-Project/Hopium/blob/hope-repair-final-20260904/src/init.cpp).

## 5. Verify privacy and reliability before relying on it

1. **Backup and baseline:** note client revision/commit, binary hash, original config, network, peer count and blockchain tip. Keep any private wallet data out of shared reports.
2. **Proxy presence:** check the Tor service is actually listening on the expected loopback port. A successful `curl` test is only a first check.
3. **Coin-specific P2P:** launch an **isolated test node** and inspect its `debug.log` or supported `getpeerinfo`/`getnetworkinfo` RPC output. Commands vary between coins. Observe that it finds and maintains peers, reaches the expected blockchain tip and never crosses to a different chain.
4. **Network leak check:** independently inspect outbound sockets, DNS requests and firewall/packet-capture traffic from the coin process. Verify that P2P traffic never connects directly to public peer IPs, including during startup, manual peer configuration, restarts and network loss. Other services on the host may legitimately use direct connections: attribute connections to the **coin process**.
5. **Failure test:** stop Tor *on the isolated machine*, and verify that the node does not silently bypass the proxy to connect directly. Record whether it disconnects, stops syncing, falls back or errors. Restart Tor and verify recovery.
6. **Wallet/miner/staker check:** ensure that running through Tor does not change consensus, wallet balances, block reward accounting or any applicable PoS staking behaviour. Privacy routing may reduce connectivity and affect block propagation.
7. **Sustained test and independent review:** verify stable P2P sync and connectivity over time, record test evidence privately where logs contain IP addresses, and publish redacted evidence only.

**Result labels:** `SOURCE PRESENT` / `ISOLATED TEST PASS` / `LIVE VERIFIED` / `BLOCKED` / `NOT TESTED`. No coin inherits another coin's PASS. Do **not** say “anonymous” merely because `proxy=` exists.

## 6. Troubleshooting

| Symptom | Possible cause / safe first response |
|---|---|
| No peers | Tor service missing, wrong local port, no reachable peers, unsupported Tor v3, DNS/seed behaviour, `onlynet=onion` too restrictive. Check without changing production chain data. |
| Tor connects but node stalls | Proxy configuration and P2P handshake may differ by client/version. Inspect safe logs and version-specific `-help`; never assume the firewall is leak-proof. |
| Wallet/node appears to disclose public IP | **Stop privacy claims immediately**; check direct inbound listening, manually configured peer routes, DNS, port forwarding, other network interfaces and separate programs. |
| Node stops when Tor stops | That can be correct fail-closed behaviour; do not silently fall back to clearnet if hiding the IP is the purpose. |
| Outbound peers work but nobody can connect inbound | `listen=0` intentionally disables incoming P2P. An inbound Tor v3 onion node requires a distinct, qualified setup. |
| Staking/mining becomes unreliable | Proxy delays or loss of peers may affect operations. Use conventional networking until this exact coin's Tor design and fail/recovery paths have passed tests. |

### Using a different SOCKS5 proxy or VPN

A SOCKS5 provider is **not** equivalent to Tor: it may know your real IP, destinations and timestamps. Verify DNS handling, authentication, provider trust, routing and disconnect behaviour; do not put wallet keys or RPC credentials into proxy settings.

A VPN normally works at a different layer and may protect the whole node's network route rather than just application P2P connections. Check IPv4/IPv6/DNS routes, split tunnelling, port forwarding and the provider's **kill switch**. Neither a VPN nor a proxy makes public-chain transfers private.

## 7. Advanced inbound onion nodes — not yet a user-tested recipe

An inbound **Tor v3** service can let others connect to a node without advertising its household IP. Implementation usually requires a working Tor service, onion v3 support in the coin, a local P2P listener, properly configured Tor ControlPort authentication or a manual `HiddenService` mapping, and accessible v3 peers. Do **not** expose wallet RPC or wallet data as an onion service. We will publish coin-specific inbound instructions **only after** an independent node successfully joins, restarts and reconnects to that coin over Tor v3.

## Official background reading

- [Tor Project: Onion service setup](https://community.torproject.org/onion-services/setup/)
- [Tor Project: Tor vs other proxy services](https://support.torproject.org/about-tor/introduction/tor-vs-other-proxies/)
- [Tor Project: SOCKS extensions](https://spec.torproject.org/socks-extensions)
- [Bitcoin Core's Tor documentation](https://github.com/bitcoin/bitcoin/blob/master/doc/tor.md) — useful engineering background, **not** proof that each fork behaves identically.

## Evidence and stewardship

This is a **living community operations guide**. Please report coin name, exact version/source SHA, operating system, mode chosen, redacted errors and reproduction steps using the relevant GitHub repository's issues or pull requests. Remove public IP addresses, private credentials, wallet seeds and secret keys. Maintain verified per-coin instructions separately when tests prove differences.

> **Golden Standard:** Protect the operator's privacy without harming peer connectivity, historical blockchain validity, wallet funds or decentralisation. Source code is evidence of capability, not evidence of successful private operation.
