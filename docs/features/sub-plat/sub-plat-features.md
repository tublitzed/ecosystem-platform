---
id: sub-plat-features
title: Subscription Features
sidebar_label: Subscription Features
---

## If you want to become a subscription product

Ask in `#subscription-platform` on slack

## How subscriptions work

Subscriptions are just metadata that attach to an user's Firefox Account. Once a user has subscribed to your product, their FxA profile reflects their subscribed state and your product can respond accordingly.

Importantly, subscriptions are not locked to any one FxA-attached product by default, so if a user is subscribed to Firefox Foo, Firefox Bar can optionally see the subscription metadata as well. In this way, we can create subscription bundles that can span multiple different products or services.

If a user cancels their subscription, this metadata goes away and your product can go back to treating them as a non-subscribed user.

### Payment methods & geography

The Subscription Platform currently supports payments with major US credit cards.

Importantly, the Subscription Platform does not implement any geo-restrictions. Instead, we rely on Stripe to reject non-US credit cards. This means that if you're building a lead page to market a subscription product, you will be responsible for geo-restricting access to the Subscription Platform.

### Billing intervals

The Subscription Platform supports billing intervals of one-month, six months, and one year. Subscriptions auto-renew and do not expire until a user cancels them.

### Tiers & upgradable subscriptions

The Subscription Platform supports upgradable subscriptions between tiers of a product. This is a streamlined way to organize a set of subscription products that are related. For example, you might wish to sell a subscription to Firefox Private Network Proxy for $2.99 a month with an optional upgrade to unlock the Firefox Private Network VPN for $4.99 a month.

Rather than making a user go through an entire payments Flow, Sub Plat allows upgrades with a single click. Users are charged a pro-rated amount for the the upgrade for their current billing cycle and in subsequent billing cycles they will be charged the full amount of their new subscription.

### Coming soon

Our [Jira board][Jira board] is the best place to see work that's in progress.

[team page]: /ecosystem-platform/docs/process/integration-with-subscription-platform
[jira board]: https://jira.mozilla.com/secure/RapidBoard.jspa?rapidView=360&projectKey=FXA&view=detail&quickFilter=1923#