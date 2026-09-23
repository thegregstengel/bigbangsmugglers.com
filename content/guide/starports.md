---
title: "Ports & Services"
date: 2026-08-04
description: "Every port archetype, what it stocks, and which services it runs"
weight: 6
group: trade
tags: [ports]
changed_in: []
---

## The eleven services

A port runs a fixed set of services determined by its archetype. If the
service isn't there, the action isn't available.

| Service | What it does | Where |
|---|---|---|
| `trading` | Buy and sell commodities | Every port |
| `banking` | Deposit and withdraw — you must be at a teller | The three starports, Federation Ports |
| `shipyard` | Buy, sell and switch hulls; restock; limpet sweeps | The three starports |
| `repair` | Restore shields and hull | The three starports, Federation Ports |
| `upgrade` | Buy stat upgrades, drives and tech modules | Tech Ports, Pirate Haven, Merchant Exchange |
| `research` | Tech modules and intel | Research Ports |
| `supplies` | Deployables and **provisions** (turns) | The three starports, Agricultural Ports |
| `recruitment` | Security personnel and mining workers | The three starports |
| `defense` | **Defense contracts** (purchased PvP immunity) | Stardock, Merchant Exchange, Federation Ports |
| `blackmarket` | Buy and fence contraband; cloaking devices | Pirate Bases, Black Markets, Pirate Haven |
| `tavern` | Rumors and intel; **mercenary retinue hiring** | Stardock, Pirate Bases, Pirate Haven |
| `priceboard` | Galaxy-wide live price sheet | Merchant Exchange only |

The **bounty office** is not a service key: posting a bounty and redeeming
faction claims happen at the two faction **capitals** — the Stardock and the
Pirate Haven — and nowhere else.

Three things follow from all that:

- **The Pirate Haven does not sell defense contracts.** It is a full-service
  capital in every other respect. It does not sell law.
- **The Merchant Exchange has no bounty office and no black market.** It is
  deliberately clean.
- **The tavern is where mercenaries drink.** The Stardock hires the
  Federation Auxiliary, Pirate Bases and the Haven hire the Cutthroat
  Company. See [NPCs & Encounters](/guide/npcs/#the-tavern-retinue).

## The three starports

One of each per galaxy. All three are permanently uncapturable.

### The Stardock (Sector 0)

Federation capital. Million-unit pools that restock **fully every tick**, so
it is never out of anything. Anchors 125 / 150 / 625, tax **2%**.

Services: trading, banking, shipyard, tavern, repair, recruitment, defense,
supplies.

Stocks the **Federation line + neutral spine**. The Federation bounty office
lives here: player bounties are posted here, and Federation bounty claims are
redeemed here in person.

**Docks deny alignment below −300.** If you have a Federation warrant and the
credits to cover it, docking is an **arrest**: your wallet is seized up to the
bounty amount, the warrant clears, it posts publicly, and *that* action fails.
The next one works.

### The Pirate Haven

At the center of the pirate band. Pools 60k / 50k / 100k, restock 0.5,
anchors 100 / 125 / 500, **no tax at all**.

Services: trading, banking, shipyard, repair, upgrade, blackmarket,
recruitment, supplies, tavern.

Stocks the **Pirate line + neutral spine**. The Syndicate bounty office lives
here: player bounties are posted here, and Syndicate bounty claims are
redeemed here.

**Docks deny alignment above +300.** Pirate warrants arrest here on the same
terms.

### The Merchant Exchange

Middle band, placed as far from the other two as the map allows.
**Two-million-unit pools** restocking fully every tick, anchors 110 / 130 /
520, and the **lowest lawful tax in the galaxy at 0.5%**.

Services: trading, banking, shipyard, repair, upgrade, recruitment, supplies,
priceboard, defense.

Stocks the **neutral spine only**.

**No docking gate.** Open to every alignment — the one full-service port a
Scourge can walk into.

## Ordinary ports

| Archetype | Sells | Buys only | Tax | Services |
|---|---|---|---|---|
| **Federation Port** | Fuel 150, Organics 170, Equipment 750 | — | 5% (7% for Pirates) | trading, banking, repair, defense |
| **Trading Port** | Fuel 115, Organics 135, Equipment 550 | — | 2% | trading |
| **Fuel Depot** | **Fuel 90** | Organics 215, Equipment 600 | 1% | trading |
| **Agricultural Port** | **Organics 75** | Fuel 160, Equipment 850 | 4% | trading, supplies |
| **Tech Port** | **Equipment 375** | Fuel 135, Organics 155 | 3% | trading, upgrade |
| **Mining Port** | Fuel 105, Equipment 550 | **Organics 240** | 2% | trading |
| **Research Port** | **Equipment 350** | Fuel 145, Organics 185 | 5% | trading, research |
| **Pirate Base** | Fuel 100, Organics 125, Equipment 500 | — | 0% | trading, blackmarket, tavern |
| **Black Market** | Fuel 80, Organics 100, Equipment 300 | — | 0% | trading, blackmarket |

Buy-only rows are where you *sell into* — the port pays those anchors and
never stocks the goods.

Ordinary ports carry shallower pools than starports and restock at only
**0.15** per tick, so their prices move much more and recover much slower.
That is where the money is.

## Ports can be taken

Every port except the Stardock, the three starports and Federation Ports can
be **besieged and held by a corporation**. A held port skims 50% of its tax
revenue to the holding corp, charges corp members half tax, and charges
everyone else +1 percentage point.

See [Corporations](/guide/corporations-fleets/#holding-ports).

## Docking, in general

Only the two faction capitals gate docking by alignment. Everything else is
open to anyone who can get there.

Queries — looking at prices, reading the shipyard list — only ever apply the
alignment gate. **Mutations** additionally run the arrest check. So you can
window-shop at a capital that holds a warrant on you; you just can't buy
anything until the warrant is settled.
