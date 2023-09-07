# Explainer: Extending Storage Access API (SAA) to non-cookie storage

## Introduction

To prevent certain types of cross-site tracking, storage and communication APIs in third party contexts are being partitioned or deprecated (read more about [storage partitioning](https://developer.chrome.com/en/docs/privacy-sandbox/storage-partitioning/) and [cookie deprecation efforts](https://developer.chrome.com/docs/privacy-sandbox/third-party-cookie-phase-out/) in Chrome and [Firefox](https://developer.mozilla.org/en-US/docs/Web/Privacy/State_Partitioning)). This breaks use cases that depend on cookie and non-cookie storage and communication surfaces in cross-site contexts. Several solutions (like Chrome’s [Privacy Sandbox](https://developer.chrome.com/docs/privacy-sandbox/overview/)) have been proposed to address use cases that rely on third-party cookies, including the [Storage Access API](https://github.com/privacycg/storage-access) (shipping with multi-browser support), which facilitates limited access to third-party cookies in specific scenarios to mitigate user-facing breakage. This explainer proposes to extend that same mechanism to non-cookie storage/communication mediums.