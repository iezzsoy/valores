# Valores

**Values-driven consumption, built on open protocols.**

Valores is a decentralized, open-source service built on the [Nostr](https://github.com/nostr-protocol/nostr) protocol. It catalogs companies and services in a voluntary, collaborative way and helps each person decide where to direct their money in line with their own values, beliefs, and ideas, whether to avoid (boycott) or to recommend and choose (support).

> **Status:** design-stage proposal. This document describes the vision, the premises, and the intended architecture. Items marked *(to be confirmed)* depend on verification against the official NIP specifications.

---

## Table of contents

1. [Overview](#1-overview)
2. [Sociotechnical foundations](#2-sociotechnical-foundations)
3. [Project principles](#3-project-principles)
4. [How Valores works](#4-how-valores-works)
5. [How companies are described](#5-how-companies-are-described)
6. [Values profile and privacy](#6-values-profile-and-privacy)
7. [Responsibility, contestation, and right of reply](#7-responsibility-contestation-and-right-of-reply)
8. [Locality and persistence](#8-locality-and-persistence)
9. [Modifications, corrections, and history](#9-modifications-corrections-and-history)
10. [Rewards](#10-rewards)
11. [Nostr architecture and NIPs](#11-nostr-architecture-and-nips)
12. [External data sources](#12-external-data-sources)
13. [Platforms and roadmap](#13-platforms-and-roadmap)
14. [Limitations and assumed risks](#14-limitations-and-assumed-risks)
15. [Contributing](#15-contributing)
16. [License and legal notice](#16-license-and-legal-notice)

---

## 1. Overview

Valores brings together four ideas:

- **An open, voluntary catalog** of companies and services, fed by ordinary people and anchored in verifiable public information.
- **A personal values profile**, configured and kept by the user, which determines how the catalog is filtered and presented. There is no "official list" of what is acceptable: each person views the catalog through their own criteria.
- **Positive recommendations**, not only boycotts: the service also helps people find services aligned with their values, which gives the practice continuity after attention to the topic fades.
- **Voluntary rewards**: discounts offered by businesses and tips via Lightning (zaps) for those who contribute useful information.

None of this depends on a central company. Data are signed Nostr events replicated across many relays, and the software is open so that it can be audited, copied, and adapted.

---

## 2. Sociotechnical foundations

This section sets out the premises that guide the project. They matter as much as the code: a poorly understood boycott system can promise more than it delivers, or reinforce the very problems it aims to address.

### 2.1. The service in an instrumental role

Valores is a **tool**. No application, website, or ecosystem, whether Nostr, Bitcoin, or decentralized open-source services, is capable on its own of driving change in the social fabric through boycotts. What these technologies offer is an **instrument for propagating information**: they lower the cost of getting informed, of recording what was found, and of acting in accordance with what one believes.

Keeping the project a tool, and not a movement, protects it from two errors: **(1)** exaggerated promises of transformation and **(2)** capture by any group that wishes to speak on behalf of its users.

### 2.2. Access to information is no longer the problem

The contemporary challenge is no longer obtaining information but ensuring that it is:

1. **freely preserved**, without depending on a single server or a single company that could erase it;
2. **freely disseminated**, without filters imposed by a central intermediary;
3. **carried by agents who deserve trust**, that is, agents with no interests that compromise what they claim (what is colloquially called, in Brazilian Portuguese, *não ter rabo preso*: having no compromising ties).

Valores' architecture addresses the first and second points with signed events that can be replicated across Nostr. As for the third, see [2.5](#25-agents-with-no-compromising-ties-what-the-project-affirms-and-what-it-does-not-guarantee).

### 2.3. The problem of continuity

Collective memory is short. A boycott tends to be episodic: it emerges with an event, gains attention, and once the dust settles, the practice falls into disuse. For that reason Valores:

- engages with **each user's particular universe of values**, not only with one-off campaigns;
- requests and organizes **service recommendations**, beyond simple boycotts, turning a reaction into a **values-driven consumption habit**;
- offers **voluntary rewards** that keep the practice economically attractive.

### 2.4. Money as a vehicle for values

When paying for a service, a person funds not only the establishment and its workers, as when consumer relations were more local and simple, but also:

- the **use that the corporation and the group that controls it make of part of the money**, including donations and support for causes that may not align with the values of parts of society;
- the **ideas embedded in the business's advertising**.

In a scenario in which political matters and public positioning have become tools of engagement, including through polarization, and in which corporations act as instruments of support for a variety of causes, the act of paying has also become an act of feeding ideas.

By keeping Valores a tool, the project aims to:

1. **democratize the circulation of money** and strengthen respect for communities, increasing the visibility of local and aligned businesses;
2. **not enable consumer fraud**, that is, the diversion of consumers' money through lies (misleading advertising, claims of values that are not practiced, false claims about origin or conduct), and to **bring transparency to the circulation of money also in the sphere of values, ideas, and beliefs**.

### 2.5. Agents with no compromising ties: what the project affirms and what it does not guarantee

Valores does **not guarantee** the reliability of any agent. Nostr does not verify anyone's independence, impartiality, or absence of conflicts of interest, and this project does not pretend that it does.

Valores is meant to make **the trail of every claim visible and auditable**. Each piece of information is a signed event, with an author, a date, a linked public source, and a history of contestations. A central authority is no longer the main intermediary of reliability; consequently, and systematically (through a *web of trust* and curators that each user chooses), consumption preference based on reliability becomes **a choice made by each user**.

### 2.6. Neutrality, polarization, and post-truth

Valores acknowledges the context in which it is born: a society of **free informational circulation and post-truth**, in which polarization is, to a large extent, a result of the very conditions under which information circulates. The project starts from the premise that **structures must adapt to this world**, rather than pretend it does not exist or demonize the tendencies that make it up.

This has design consequences:

- It is acknowledged that an ideology-based filtering system **can feed polarization**. This tension cannot be denied.
- The project's response is to **mitigate it through structural mechanisms**, rather than limiting itself to opinion moderation: (a) a **mandatory public source** for factual claims; (b) **open contestation** by any user, also based on public information; (c) **positive recommendations** that shift the focus from "against" to "in favor"; (d) an explicit separation between **fact with a source** and **opinion**.
- Valores' neutrality is **infrastructure neutrality**: the service does not define what is correct, does not impose an ideology, and treats all values profiles under the same rules. The filter, in turn, is **subjective by definition**, because it expresses what each person has chosen.

---

## 3. Project principles

- **No built-in bias.** The infrastructure favors no ideology. The evaluation tendency derives from the values profile the user declares.
- **Public source first.** Public information carries more weight than personal description; the latter is accepted only with a public link.
- **Voluntariness.** Cataloging, recommendations, discounts, and tips are voluntary.
- **User sovereignty.** The values profile remains under the control of whoever created it.
- **Trail transparency.** Every claim has an author, date, source, and history.
- **Open by default.** Code, data formats, and specifications are public and documented.
- **No legal advice and no accusation.** The project catalogs documented facts and opinions declared as such; it does not judge.

---

## 4. How Valores works

1. **Registering companies and services.** Anyone can propose a record, anchored to public identifiers (domain, official registry, location).
2. **Contributions.** Users add claims (facts with sources, opinions) and recommendations to a record.
3. **Values profile.** Each user configures their profile locally, for example their leanings, convictions, and priorities, and chooses trusted curators.
4. **Filtering and recommendation.** The service computes, on the user's own device or through a provider the user chooses, what appears as an alert (personal blacklist), as neutral, or as a positive recommendation.
5. **Contestation and reply.** Any claim can be contested with a public source, and the company can exercise a right of reply.
6. **Rewards.** Businesses can offer discounts to those who arrive through a recommendation, and users can send *zaps* to those who contribute.

---

## 5. How companies are described

A company's record is an **aggregation** of individual claims, not a single text editable by everyone.

**Two layers of information:**

1. **Public information** (greater weight): official registries, sanctions and compliance registers, public administrative and judicial decisions, open data, reporting from identifiable sources.
2. **Users' personal descriptions** (lesser weight): accounts, opinions, and experiences. To be accepted, a description **must be accompanied by a link to the corresponding public information**. Without a public link, the description is not recorded as a factual claim.

**Dimensions assessed.** Not only ideology is assessed. A record can receive markers of a **pragmatic** and an **ideological** nature, for example:

- Pragmatic: market concentration and dominant position, history of involvement in illicit schemes, lobbying influence over political decisions, labor practices, consumer fraud, environmental impact, and relations with local communities.
- Ideological and values-related: destination of donations and support, sponsored causes, ideas embedded in advertising, public positions of controlling owners.

**Distinction between fact and opinion.** Every contribution is marked as a **fact with a source** or as an **opinion**. The client presents the two categories differently.

---

## 6. Values profile and privacy

The values profile (ideological leanings, religious convictions, priorities) is **sensitive data**. For that reason:

- The profile is **local-first**: it stays on the device and is **not published** to Nostr.
- To sync across devices, encrypted private application data storage is used (NIP-78 with NIP-44).
- The personal *blacklist* and interest lists are derived from the profile and remain under the user's control.
- As a guideline, the project respects the data-protection legislation applicable in each jurisdiction where it operates. **As an example, in the Brazilian context**, the LGPD (*Lei Geral de Proteção de Dados*, Law No. 13,709/2018) classifies data on religious belief and political opinion as sensitive personal data (Art. 5, II), subject to stricter processing conditions (Art. 11). Other jurisdictions have comparable regimes (for instance, the GDPR in the European Union, with its special categories of data under Art. 9), and operators should check the rules that apply to them.
- Data on **natural persons** requires additional care, even when public. The guideline is to prioritize **legal entities** and **documented facts**.

---

## 7. Responsibility, contestation, and right of reply

### 7.1. Responsibility of whoever enters the information

Because Valores is open source and decentralized, there is **no central platform** that assumes authorship of the content. Responsibility is designed to fall on **whoever supplies the information**:

- Each contribution includes a **signed statement of responsibility** by the author's key, in a dedicated event linked to the contribution. The statement lives in the protocol and serves as a **proof trail** of who claimed what, and when.
- Authors may **optionally** link their key to a verifiable identity, which increases the weight of the contribution without making identification mandatory.

### 7.2. Limits of this design

It is worth being honest about what a statement of responsibility does not do:

- It **does not prevent** a third party, such as the company named, from filing a lawsuit, since no term was signed.
- It **does not remove, by contract, the position of whoever operates** a client or a *relay* that hosts and distributes content, who may be treated as a provider under local law.
- Nostr keys are **pseudonymous**; without identification, the statement has limited value.

The project must therefore **remain open to legal proceedings** and to compliance with legal orders by those who operate infrastructure, and it recommends that relay and client operators seek local legal advice.

### 7.3. Contestation

Any user can **contest** a claim by publishing a contestation event that:

- references the original contribution;
- **requires a link to public information**, just like the rule of origin;
- is displayed by the client **alongside** the contested claim.

### 7.4. Right of reply

The company named may reply. The reply's authorship is proven through **control of the domain** (for example, a record or file on the domain that links the company's key to its address). The reply is displayed alongside the record.

### 7.5. Retraction and correction

The author may retract or correct their contribution. A correction is a **new event** that references the previous one, **preserving the history**.

---

## 8. Locality and persistence

Valores has a regional dimension, inspired by services such as Bitchat and Nymchat, which use **geohash** to organize channels by location.

There are two layers:

- **Ephemeral layer (optional):** live regional conversations, using ephemeral events (kind 20000), as those services do. Relays are not required to store these events.
- **Persistent layer:** the catalog itself, in **addressable events** (the 30000-39999 kind range of NIP-01), with the `g` geohash tag. Since relays filter by exact tag value, each record publishes **several `g` tags at different precisions** (short and long prefixes of the same geohash), which allows searching by neighborhood, city, or state.

**Persistence.** Nostr does not guarantee permanence, so it depends on relays. To strengthen it, the project may provide for:

- publication to **several *relays*** (NIP-65);
- encouragement of **regional community *relays*** that keep the catalog;
- **sync between *relays*** (NIP-77, Negentropy) *(to be confirmed)* and **local copies** in clients.

---

## 9. Modifications, corrections, and history

An addressable event can only be replaced **by its own author**. For that reason a record is not a document editable by everyone, but an **aggregation**:

- **Immutable individual claims:** each piece of information is an event signed by whoever entered it.
- **Aggregated record:** computed in the client, or by a provider the user chooses (NIP-85 and NIP-90) *(to be confirmed)*, weighing public sources and trust.
- **Change by the author:** a new event that references the previous one as superseded, with the **history preserved**, which is important as proof.
- **Change by third parties:** an amendment proposal or a contestation, accepted according to each user's web of trust.
- **Deletion:** only a **request** (NIP-09); relays may ignore it. The project states this honestly: what is published on an open network may not be fully removable.

For inspiration on collaborative editing with merge proposals, NIP-54 (wikis) may be consulted *(to be confirmed)*.

---

## 10. Rewards

The rewards system is **voluntary** and has two fronts:

- **Referral discounts.** Businesses can offer discounts to users who hire a service through a Valores recommendation. Offers can be published as classified listings (NIP-99), and codes delivered through private messages (NIP-17 and NIP-59).
- **Tips via zaps.** Users can reward those who contribute useful information through zaps (NIP-57) over the Lightning Network, with a wallet connected through NIP-47.

**Separation between rewards and evaluation.** Rewards for hiring and evaluations in the same system create an incentive for bought reviews. For that reason:

- rewards and evaluations are **separate**, in distinct events with their own rules;
- anyone who receives a benefit associated with a company must make an **affiliation disclosure**, displayed alongside the contribution;
- contributions with a disclosed affiliation are presented as such and may carry reduced weight.

There is no NIP for **referral attribution** (who referred whom) or for **validating discount use**; these points require the project's own convention.

---

## 11. Nostr architecture and NIPs

Preliminary mapping. Confirm the numbers and current status in the [official specification](https://github.com/nostr-protocol/nips) before implementing.

|Function|NIPs|Notes|
|---|---|---|
|Protocol base|NIP-01, NIP-19, NIP-21, NIP-65|Events, identifiers, `nostr:` links, relay list|
|Signing|NIP-07, NIP-46|Extension and remote signer, without exposing the key|
|Authentication and spam|NIP-42, NIP-13|Relay authentication; proof of work|
|Company record|custom addressable kind (30000-39999 range)|**No existing NIP**: requires its own mini-NIP|
|External identification|NIP-73 *(to be confirmed)*|Anchor a record to a domain, URL, or geohash|
|Evaluations and comments|NIP-22, NIP-25|Comments and reactions|
|Typed markers|NIP-32|Labels for pragmatic and ideological categories|
|Reports|NIP-56|Contest false content|
|Locality|`g` tag (geohash); kind 20000 for the ephemeral layer|Persistence via addressable events|
|Private profile and lists|NIP-78, NIP-44, NIP-51|Private application data, encryption, and lists|
|Trust and curation|NIP-02, NIP-85 *(to be confirmed)*, NIP-90, NIP-89, NIP-58|Web of trust, scoring providers, DVMs, discovery, badges|
|Zaps and wallet|NIP-57, NIP-47|Lightning tips|
|Offers and discounts|NIP-99, NIP-17, NIP-59|Listings and private delivery of codes|
|Deletion|NIP-09|Request only|
|Sync|NIP-77 *(to be confirmed)*|Between relays|

**Points without a NIP.** Company records, evaluations linked to a public source, statements of responsibility, contestations, the right of reply, and referral attribution require **their own kinds and conventions**. The recommendation is to specify them in a **mini-NIP** and propose it to the community.

---

## 12. External data sources

Importing public data about companies is desirable, but it is **not a protocol matter**. Note:

- The terms of service of commercial places APIs (such as Google's) often **restrict storing and republishing** content, which conflicts with a decentralized catalog. Check the terms before importing.
- Open alternatives: **OpenStreetMap**, **Wikidata**, and open product databases such as **Open Food Facts**.
- In Brazil, for example, official public databases, such as **CNPJ open data** and the **sanctions registers of the Portal da Transparência** (CEIS and CNEP), serve well for the pragmatic aspects of evaluation.

---

## 13. Platforms and roadmap

Valores will be offered on **web, Android, and iOS**. Nostr has mature clients on all three fronts, which allows an incremental strategy:

1. **PWA first.** An installable progressive web service (PWA) lowers the initial cost and reaches every platform.
2. **Native versions later.** Android and iOS, building on existing Nostr libraries.
3. **Reuse.** Data layers and filtering rules shared across platforms.

Suggested stages:

- **Phase 0:** mini-NIP specification (records, claims, contestations, statements).
- **Phase 1:** PWA with catalog, local profile, contestation, and reading of open sources.
- **Phase 2:** locality (geohash), regional community relays, and sync.
- **Phase 3:** rewards (zaps and discounts) and scoring providers.
- **Phase 4:** native Android and iOS clients.

---

## 14. Limitations and assumed risks

- **No guarantee of agent reliability**; there is an auditable trail.
- **Persistence is not guaranteed** by the protocol; it depends on relays and copies.
- **Full deletion is not guaranteed** on an open network.
- **Legal risk** for those who operate infrastructure (relays and clients), including defamation claims, and data-protection issues (for example, under the LGPD in Brazil), especially regarding natural persons.
- **Risk of abuse**: spam, bought reviews, coordinated campaigns. Mitigations: mandatory public source, affiliation disclosure, contestation, proof of work, and web-of-trust curation.
- **Polarization**: the project acknowledges that ideology-based filters can reinforce it; structural mitigations reduce, but do not eliminate, this risk.
- **Limits of an instrument**: the service does not replace social organization, consumer education, or public policy.

---

## 15. Contributing

Contributions are welcome on several fronts: mini-NIP specification, clients (web, Android, iOS), regional relays, translation, legal review, and sociotechnical research.

*Detailed contribution instructions, code of conduct, and discussion channels: to be defined.*

---

## 16. License and legal notice

**License:** Valores is dedicated to the public domain under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) (see the [`LICENSE`](LICENSE) file). Anyone may copy, modify, distribute, and use the project, including commercially, without asking permission and without attribution.

- Where a full dedication to the public domain is not legally possible (for instance, because moral rights are inalienable in some jurisdictions, as in Brazil), CC0 acts as a fallback, granting the broadest permissive license the law allows.
- Being in the public domain also means that third parties may build closed or commercial derivatives; the project does not require them to remain open.
- CC0 does not waive any trademark or patent rights held by the author.

**Legal notice:** this project does not provide legal, financial, or any other kind of professional advice. The cataloged content is produced by users, who are responsible for their contributions. Those who operate clients or relays should seek their own legal advice in their jurisdiction.
