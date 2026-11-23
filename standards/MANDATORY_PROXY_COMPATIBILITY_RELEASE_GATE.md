# Mandatory Proxy Compatibility and Privacy Qualification

**Status:** Golden Standard release-gate policy, adopted 23 November 2026. **Evidence status:** not independently qualified for any of the five modernised coin binaries.

**Principle: Reliability first, release second.**

Applies to every future modernisation release of **TAO Revival/TaoX, XNUVA, Europa (ERA), Zeus (ZUS), and Hopium (HOPE)**. This is an engineering/testing rule, not a production configuration change, mainnet hard fork, cryptocurrency privacy promise, or approval of any current experimental release.

## 1. Mandatory contract for modernised node releases

A newly modernised public node **MUST** retain usable, optional SOCKS5 outbound P2P proxy support. The exact release-candidate binary, rather than merely its source-code help text, must demonstrate:

1. The documented proxy setting is parsed correctly, applied to intended outbound P2P connections and rejected with clear errors when invalid.
2. A functioning proxy reaches a real, independently controlled compatible blockchain peer; authentic headers and blocks sync and validation remains correct.
3. An unreachable proxy causes an observable connection failure **without silently bypassing the proxy to make direct P2P connections**. Test this in an isolated environment with attributable socket and DNS monitoring.
4. Manual peers, seed discovery, IPv4, IPv6, hostnames, proxy authentication, restart and recovery follow the **documented** routing policy. The option onlynet=onion ordinarily limits automatic outbound peer choice; it is **not** a system-wide leak firewall.
5. Default direct P2P operation remains available and working when no proxy is requested. Privacy routing remains **opt-in**.
6. Mining, staking where applicable, wallet access, coinbase maturity, balances, historical consensus, monetary policy, block propagation, RPC safety and treasury integration are not accidentally changed by proxy configuration.
7. Independent checks and redacted evidence document the true privacy boundary. A P2P proxy setting does **not** proxy every application, wallet browser, game service, miner, RPC connection or operating-system request.

**Release consequence:** Any failed or unevidenced requirement above is **OPEN / HOLD** for a modernised node release. **Source-code present** is an observation, not a pass.

## 2. Onion-specific features are separately gated

A client may claim to support **Tor v3 onion outbound peers** only after a genuine v3-addressed peer successfully exchanges a blockchain handshake, headers, blocks and transactions, with no direct-route leakage. If it advertises an **inbound onion node**, test Tor v3 service creation or configuration, local listener mapping, independent inbound connection, safe credentials and restart recovery. Tor v2 onion services are obsolete.

A modernisation release can qualify for the **mandatory general SOCKS5** requirement while marking **Tor v3 outbound and/or inbound onion features UNAVAILABLE**; it must not advertise untested features as working.

A VPN and an ordinary single-hop SOCKS5 proxy are not synonymous with Tor anonymity. Public blockchain transactions remain publicly analysable.

## 3. Per-coin release evidence worksheet

**Use these statuses:** V = reviewed independent verification, P = reproducible checkpoint-reported result awaiting independent review, O = untested/open, B = failed/blocked, N/A = justified only for a genuinely optional feature. Tests below are **O until separately evidenced for each coin**.

| ID | Required test | Acceptance |
|---|---|---|
| PX-01 | Record coin, branch, exact source SHA, binary SHA-256, OS and network identity | V |
| PX-02 | Prove actual daemon accepts valid SOCKS5 config and rejects malformed values | V |
| PX-03 | With proxy disabled, connect and synchronise with an independent conventional peer | V |
| PX-04 | With proxy enabled, controlled SOCKS5 server records the correct P2P handshake | V |
| PX-05 | Validate actual peer header/block sync and network tip via SOCKS5 | V |
| PX-06 | Verify configured manual peers, DNS seed, IPv4/IPv6 and hostname handling | V |
| PX-07 | Check remote DNS resolution where claimed; monitor for unintended local DNS requests | V |
| PX-08 | Attribute outbound sockets and packets to the coin process; show no bypass in enforced proxy mode | V |
| PX-09 | Stop/block proxy **in an isolated test environment**; no silent direct P2P fallback | V |
| PX-10 | Restart proxy; test reconnect, continued synchronisation and peer churn | V |
| PX-11 | Restart/reindex/rescan where relevant; verify proxy settings persist safely | V |
| PX-12 | Test explicit connect/addnode options and discovery behaviour under proxy configuration | V |
| PX-13 | Demonstrate new transaction and block propagation over proxied P2P peers | V |
| PX-14 | Reconfirm wallet recovery, balances, maturity and spendability | V |
| PX-15 | Reconfirm miner rewards and any PoS stake broadcast/rewards where applicable | V or independently justified N/A |
| PX-16 | Test failed SOCKS negotiation, unreachable target, timeout, malformed response and resource limits | V |
| PX-17 | Verify no inadvertent RPC exposure, Tor control leakage or publicly shared credentials | V |
| PX-18 | Complete monitored 24–48-hour proxy-mode stability with independent peers | V |
| PX-19 | If **Tor v3 outbound** is advertised, demonstrate valid v3 peer connectivity and no v2-only assumption | V or feature not advertised |
| PX-20 | If **Tor v3 inbound** is advertised, prove functioning v3 service and an independent inbound peer | V or feature not advertised |
| PX-21 | Verify published settings match the exact release binary and include caveats/rollback | V |
| PX-22 | Independent review and sign-off; reconcile with main G0–G8 release gates | V |

**Scope discipline:** A passing curl Tor check, an option shown by help output, or a synthetic SOCKS connection alone does not prove real coin P2P operation. Do not copy a passing test from TaoX to ERA, XNUVA, ZUS or HOPE.

## 4. Recommended test design

Test on disposable, isolated nodes with separate data directories and throwaway keys; **never** stop Tor, change the firewall, swap daemon binaries, manipulate balances or interrupt the working production networks merely to qualify this policy.

Run a candidate node through a controlled local SOCKS5/Tor service to an independently operated peer; monitor sockets, DNS and peer logs. Repeat with Tor/proxy shut down, restored, and across restarts. Validate chain identity, propagation and miner/staker accounting as applicable. Keep private keys, RPC credentials and personal IP addresses out of published evidence.

Sample configuration for an isolated outbound-only test **after confirming the exact client accepts these flags**:

```ini
proxy=127.0.0.1:9050
listen=0
```

The proxy must actually listen on that address **from the node's network namespace**. This example is not proof of privacy. Do not rely on onlynet=onion unless compatible modern onion peers and version-specific behaviour are verified.

## 5. Source survey — NOT an execution test

| Client | Source-level finding | Proxy qualification |
|---|---|---|
| XNUVA main | Modern networking advertises proxy, onion, onlynet, Tor control and stream-isolation options | O |
| TAO Revival legacy | Historical SOCKS and tor proxy options | O |
| TaoX experimental modernisation | Bitcoin Core-derived modern overlay advertises SOCKS5, onion and Tor controller options | O |
| ERA | Maintained source includes SOCKS5 and onion options | O |
| ZUS | Maintained source includes SOCKS5 and onion options; separately preserve **PoW and PoS** | O |
| HOPE | Maintained source includes SOCKS5 and onion options; preserve applicable staking and coinbase behaviour | O |

Inspected public source: [XNUVA](https://github.com/Xnuva-Blockchain-Project/Xnuva/blob/main/src/init.cpp), [TAO Revival](https://github.com/Xnuva-Blockchain-Project/Tao/blob/main/src/init.cpp), [TaoX overlay](https://github.com/Xnuva-Blockchain-Project/Tao/blob/modernisation/taox-consolidated-full-source/migration/modern-tao-draft/src/init.cpp), [ERA](https://github.com/Xnuva-Blockchain-Project/Europa/blob/main/src/init.cpp), [ZUS](https://github.com/Xnuva-Blockchain-Project/Zeus/blob/main/src/init.cpp), [HOPE](https://github.com/Xnuva-Blockchain-Project/Hopium/blob/hope-repair-final-20260904/src/init.cpp).

See [Optional Node Privacy — Tor, SOCKS5 and VPNs](NODE_PRIVACY_TOR_SOCKS5.md) for public installation examples and cautions.

## 6. Required evidence record

Each coin's review must record: commit and binary hash; network and test mode; independent peer; proxy version and endpoint; per-test PX status; P2P handshakes and validated block hashes; socket/DNS observations; deliberate proxy failure and recovery; wallet/miner/staker results; monitoring duration; redacted supporting logs; and reviewer/sign-off.

**Standing rule: Proxy capability must be demonstrated on the released binary. No direct-P2P fallback when strict proxy use is configured. No anonymity claims without independent leak testing. No release without evidence.**
