# Atomic

API Evangelist profile of [Atomic](https://atomic.financial/) — the connected-banking infrastructure for income, payroll, and merchant data.

Atomic's user-permissioned APIs link consumers to thousands of payroll providers, gig platforms, employers, and merchants, then read or update that data in real time. Core use cases include direct-deposit switching, paycheck-linked income and employment verification, tax-document retrieval, and card-on-file / subscription management.

## APIs

| API | Description | Documentation |
|---|---|---|
| Atomic Deposit API | Direct-deposit switching across thousands of payroll providers. | [Docs](https://docs.atomicfi.com/reference/transact-sdk) |
| Atomic Verify API | Instant income and employment verification. | [Docs](https://docs.atomicfi.com/reference/transact-sdk) |
| Atomic PayLink API | Card-on-file updating and subscription management across merchants. | [Docs](https://docs.atomicfi.com/reference/transact-sdk) |
| Atomic Tax API | W-2 / 1099 document retrieval and refund-advance enablement. | [Docs](https://docs.atomicfi.com/reference/transact-sdk) |
| Atomic Authentication API | StandardAuth, TrueAuth, and CoAuth for permissioned third-party access. | [Docs](https://docs.atomicfi.com/reference/api) |
| Atomic Webhooks API | CloudEvents-formatted task, company, and continuous-access events. | [Docs](https://docs.atomicfi.com/reference/webhooks) |
| Atomic Transact SDK | Web, iOS, Android, React Native, Flutter, and Capacitor client SDKs. | [Docs](https://docs.atomicfi.com/reference/transact-sdk) |

## Authentication

The REST API at `https://api.atomicfi.com` (sandbox: `https://sandbox-api.atomicfi.com`) supports two authentication modes:

- **API key / secret** via `x-api-key` and `x-api-secret` headers for server-to-server calls.
- **Access token** via `x-public-token` for Transact SDK initialization.

## SDKs

All Transact SDKs live under the [atomicfi GitHub organization](https://github.com/atomicfi):

- [atomic-transact-javascript](https://github.com/atomicfi/atomic-transact-javascript)
- [atomic-transact-ios](https://github.com/atomicfi/atomic-transact-ios)
- [atomic-transact-android-public](https://github.com/atomicfi/atomic-transact-android-public)
- [atomic-transact-react-native](https://github.com/atomicfi/atomic-transact-react-native)
- [atomic-transact-flutter](https://github.com/atomicfi/atomic-transact-flutter)
- [atomic-transact-capacitor](https://github.com/atomicfi/atomic-transact-capacitor)
- [helium](https://github.com/atomicfi/helium) — starter project for building a custom UI on Atomic's API.

## Resources

- Website: <https://atomic.financial/>
- Documentation: <https://docs.atomicfi.com/>
- API Reference: <https://docs.atomicfi.com/reference/api>
- Console / SignUp: <https://console.atomicfi.com/>
- GitHub: <https://github.com/atomicfi>
- LinkedIn: <https://www.linkedin.com/company/atomic-fi/>
- YouTube: <https://www.youtube.com/@atomic.financial>
- Blog: <https://atomic.financial/insights/>
- Help Center: <https://atomic.financial/help-center/>

## Maintainer

This profile is maintained by [Kin Lane](https://apievangelist.com), API Evangelist.
