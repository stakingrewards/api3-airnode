# How to use StakingRewards on Web3

> [Airnode](https://api3.org/airnode) API Documentation

This API is for testing purposes and playing with staking data.

**Home Page:** https://www.stakingrewards.com

**Web2 Docs:** https://api-beta.stakingrewards.com/docs

## Call this Airnode API

Read the [Airnode developer documentation](https://docs.api3.org/d/call-an-airnode) to learn how to call Airnode APIs. You'll need the **Provider ID** to call any endpoint in this API.

**Provider ID:** 0xd3eaae7d0a8b62f8dc005059cea60a3914c9b860d00e7c152922b195bb4bbad7

**Provider XPub:** xpub661MyMwAqRbcFXHrXTqWUDjBHzYsYqe56D1XKhStwh6bohK6P5m97L9hZw94J1DTpdR24ui7YYmmKZpHdyidYEoGQNYsbR7FGouhP3ZBmcq

[Reserved Parameters](https://docs.api3.org/r/reserved-parameters) are used to control Airnode behavior and are available for all endpoints.

## Available on Networks:

> Find more information on each chain [Here](https://ethereum.org/en/developers/docs/networks/).

| Chain   | Airnode RRP Contract                       |
| ------- | ------------------------------------------ |
| Rinkeby | 0xF9C39ec11055508BddA0Bc2a0234aBbbC09a3DeC |

# Endpoints

1. [/assets/overview/{slug}](#0x85ba5e034c548434047f0e890719c7efb46b98f59b36c4f13abfdc2bed896e74)
2. [/assets/providers/{slug}](#0x9b98b312b16191125fc86f9115806aa7fc1383a37834f4d0ba20e151fb27c1b6)
3. [/assets/reward-options/{slug}](#0x9c5bcd4952b9491fe8966f033299b0281c25d47d26219a621081977ee1ce7d17)
4. [/list/assets](#0x8ba90e0f3310145497f7a4a89384295b8aecda43b0dd1755b7b5bb72d43abb85)
5. [/list/providers](#0x0eb6e8bf9e6c01756b5f40f2347fb8cc7d01be2e91c8a9b328ec5c51fefe23a8)

---

## /assets/overview/{slug} <a name="0x85ba5e034c548434047f0e890719c7efb46b98f59b36c4f13abfdc2bed896e74"></a>

The Staking Assets endpoint serves the most recent reward rates, reward changes, adjusted rewards, score, consensus types, tokens staked and total staked %. The reward changes are calculated in percent.

You'll need the **Endpoint ID** to call this endpoint.

**Endpoint ID:** 0x85ba5e034c548434047f0e890719c7efb46b98f59b36c4f13abfdc2bed896e74

[Request Parameters](https://docs.api3.org/pre-alpha/protocols/request-response/request.html#request-parameters)

```solidity
slug
```

[Response](https://docs.api3.org/pre-alpha/airnode/specifications/reserved-parameters.html#path)

```json
{
  "adjReward": 1.2555555555555555,
  "algorithmType": "Proof of Stake",
  "averageValidatorFee": 0.1511111111111111,
  "engagedBalance": 960000000.406406,
  "inflation": 5.666666666666667,
  "marketcap": 1500000000,
  "price": 1.666666666666667,
  "reward": 7.666666666666667,
  "reward24hChange": 0.6888888888888889,
  "reward30dChange": -1.7111111111111112,
  "score": 85.46666666666668,
  "stakedValue": 1600000000.6767676,
  "totalStaked": 79.37373737373737,
  "volume24h": 92000000
}
```

---

## /assets/providers/{slug} <a name="0x9b98b312b16191125fc86f9115806aa7fc1383a37834f4d0ba20e151fb27c1b6"></a>

The Staking Providers endpoint serves a list of all staking providers for an asset with their commission and reward rates for staking, hosting and lending services. Verified Staking Providers serve the most accurate data. All reward rates are already deducted by the individual fee.

You'll need the **Endpoint ID** to call this endpoint.

**Endpoint ID:** 0x9b98b312b16191125fc86f9115806aa7fc1383a37834f4d0ba20e151fb27c1b6

[Request Parameters](https://docs.api3.org/pre-alpha/protocols/request-response/request.html#request-parameters)

```solidity
slug
```

[Response](https://docs.api3.org/pre-alpha/airnode/specifications/reserved-parameters.html#path)

```json
{
  "name": "Name",
  "providers": [
    {
      "hosting": [
        {
          "address": "0x123",
          "fee": 20.5,
          "feeType": "per month"
        }
      ],
      "isVerified": true,
      "lending": [
        {
          "address": "0x123",
          "custodial": true,
          "reward": 12.46666666666668
        }
      ],
      "name": "Provider",
      "staking": [
        {
          "address": "0x123",
          "balance": 5778663.788888889,
          "custodial": true,
          "fee": 5.5,
          "proportion": 2.466666666666668,
          "reward": 12.46666666666668,
          "status": "active",
          "users": 125
        }
      ],
      "website": "https://provider.com"
    }
  ],
  "slug": "name",
  "symbol": "NA"
}
```

---

## /assets/reward-options/{slug} <a name="0x9c5bcd4952b9491fe8966f033299b0281c25d47d26219a621081977ee1ce7d17"></a>

The Reward Options endpoint serves all reward options for an asset including reward rates, compoundes reward rates, adjusted reward rates, lock-up times, staking requirements and default reward frequency. If the default provider fee is given, the reward is already deducted by that.

You'll need the **Endpoint ID** to call this endpoint.

**Endpoint ID:** 0x9c5bcd4952b9491fe8966f033299b0281c25d47d26219a621081977ee1ce7d17

[Request Parameters](https://docs.api3.org/pre-alpha/protocols/request-response/request.html#request-parameters)

```solidity
slug
```

[Response](https://docs.api3.org/pre-alpha/airnode/specifications/reserved-parameters.html#path)

```json
{
  "name": "Name",
  "rewardOptions": [
    {
      "adjReward": 1.2555555555555555,
      "compoundedAdjReward": 1.7555555555555555,
      "compoundedReward": 15.46666666666668,
      "defaultProviderFee": 0.1,
      "frequency": 150003.07207207207,
      "lockUpTime": 86400,
      "name": "Name",
      "recommendedMinimum": 1000,
      "requiredMinimum": 1000,
      "reward": 12.46666666666668
    }
  ],
  "slug": "name",
  "symbol": "NA"
}
```

---

## /list/assets <a name="0x8ba90e0f3310145497f7a4a89384295b8aecda43b0dd1755b7b5bb72d43abb85"></a>

The Assets endpoint serves a list of all assets listed on Staking Rewards.

You'll need the **Endpoint ID** to call this endpoint.

**Endpoint ID:** 0x8ba90e0f3310145497f7a4a89384295b8aecda43b0dd1755b7b5bb72d43abb85

[Request Parameters](https://docs.api3.org/pre-alpha/protocols/request-response/request.html#request-parameters)

```solidity
None
```

[Response](https://docs.api3.org/pre-alpha/airnode/specifications/reserved-parameters.html#path)

```json
[
  {
    "name": "Name",
    "slug": "name",
    "symbol": "NA"
  }
]
```

---

## /list/providers <a name="0x0eb6e8bf9e6c01756b5f40f2347fb8cc7d01be2e91c8a9b328ec5c51fefe23a8"></a>

The Providers endpoint serves a list of all providers listed on Staking Rewards.

You'll need the **Endpoint ID** to call this endpoint.

**Endpoint ID:** 0x0eb6e8bf9e6c01756b5f40f2347fb8cc7d01be2e91c8a9b328ec5c51fefe23a8

[Request Parameters](https://docs.api3.org/pre-alpha/protocols/request-response/request.html#request-parameters)

```solidity
None
```

[Response](https://docs.api3.org/pre-alpha/airnode/specifications/reserved-parameters.html#path)

```json
[
  {
    "name": "Name",
    "slug": "name"
  }
]
```

---
