# EzPrint Privacy Policy

**Product:** EzPrint — v2.0.4 Experimental  
**Intended audience:** Authorized SPXExpress personnel  
**Effective date:** 17 November 2026  
**Privacy contact:** Nguyễn Khắc Tấn, Staff – Đà Lạt 02 Hub  
**Email:** khactan.nguyen@spxexpress.com

## 1. Purpose and scope

EzPrint is an internal experimental Chrome extension for a narrow operational purpose: looking up Pickup Task (PT) records and SPX shipment records in the SPX FMS Portal, displaying order status and tracking history, consolidating valid SPX shipment numbers, and generating AWB labels for printing through the configured WMS Print Agent.

The extension is intended for authorized internal use. It is not a general browsing monitor and does not provide unrelated browsing, advertising, analytics, or profiling features.

## 2. Information handled

Depending on the operation performed by the user, EzPrint handles:

- **Identifiers supplied by the user:** Pickup Task IDs (PT) and SPX Tracking Numbers entered or pasted into the extension.
- **Shipment and FMS website content:** task details, shipment IDs, order status codes and names, ETA values, Sortcodes, pickup-point names, station or Hub identifiers/names, and tracking-event messages and timestamps returned by SPX FMS.
- **Personal information that may appear in FMS event records:** operator display names and work email addresses included in tracking-event responses. EzPrint displays these as part of the shipment history; it does not use them for advertising, profiling, or unrelated purposes.
- **Temporary label-access information:** SPX FMS may return a short-lived, shipment-specific label URL containing a `token_str` parameter. EzPrint holds this URL in runtime memory during preview/printing and forwards it in the print request to the configured WMS Print Agent. The extension does not intentionally save the token-bearing URL in persistent Chrome storage.
- **Local preferences and operational state:** copy count, station type, station ID, the user's explicit-use notice acceptance record, and the FMS status-name catalog cache.

EzPrint does not request the Chrome `cookies` permission, inspect or extract cookie values, read passwords, or persist the user's SPX login credentials or session-cookie values. FMS API requests use the browser's existing signed-in SPX FMS session; Chrome automatically attaches the applicable session credentials to requests because the extension uses authenticated requests to `spx.shopee.vn`.

EzPrint does not collect device GPS coordinates, microphone or camera data, browsing history, general website activity, keystrokes, or clipboard contents. The Copy feature writes the selected SPX numbers to the clipboard only after the user activates it; it does not read clipboard contents.

## 3. How information is used

Information is used only to provide the extension's shipment lookup and AWB-printing purpose:

1. PT and SPX identifiers are used to request the corresponding task, shipment, order-status, and tracking information from SPX FMS.
2. Shipment status, tracking events, ETA, Sortcode, and operational station information are displayed so the user can review the shipment before printing.
3. Selected shipment identifiers and FMS-generated label information are used to request AWB labels and submit the labels to the configured print service.
4. Local preferences and cached status catalogs are retained to restore the user's workflow and reduce repeated requests.

EzPrint does not sell user data, use it for targeted advertising, build advertising profiles, determine creditworthiness, or use it for purposes unrelated to shipment lookup and AWB printing.

## 4. Storage and retention

- **Chrome local storage (`chrome.storage.local`):** stores the entered PT/SPX input, task/order state needed to restore the workflow, FMS status-catalog cache, print preferences, and the explicit-use notice acceptance record. These values remain in the user's Chrome profile until cleared by the user, removed by the extension's clear/reset function where applicable, or deleted when the extension's stored data is cleared/uninstalled.
- **Chrome session storage (`chrome.storage.session`):** temporarily transfers the selected print rows and related status information from the Side Panel to the separate print window. The extension attempts to remove this session entry when the print window closes. Session storage is also cleared by Chrome when the extension browser session ends or the extension is reloaded.
- **Runtime memory:** short-lived label URLs and their `token_str` values are held in memory for label preview/printing and are not intentionally written to persistent extension storage.

The extension does not operate its own cloud database for these records. SPX FMS and the WMS Print Agent may process or retain information under their own applicable systems, policies, and operational controls.

## 5. Sharing and recipients

EzPrint sends information only to services required for the stated functionality:

### SPX FMS Portal

Requests are sent to `https://spx.shopee.vn/` to retrieve PT details, shipment lists, status catalogs, tracking information, shipment confirmation/Sortcode information, and AWB label URLs. These requests use the user's existing signed-in FMS session. Shipment identifiers and related request data are sent to SPX FMS so that FMS can return the requested operational records and labels.

### Configured WMS Print Agent

For printing, EzPrint sends a print request to `https://printproxy.wms.shopeemobile.com:21317/api/print`. The request includes print settings and the short-lived FMS-generated label URL in the `file_path` field so that the print service can retrieve and process the label. This request omits browser credentials and does not send the browser's SPX session cookies.

EzPrint does not send shipment or user data to advertising networks, data brokers, unrelated analytics providers, or other unrelated third parties. The above transfers are limited to what is needed to retrieve shipment information and produce the requested AWB print job.

## 6. Security

Requests to the SPX FMS and WMS Print Agent endpoints use HTTPS. EzPrint does not store the user's SPX password or extract/persist the browser's session-cookie values. Short-lived label URLs are handled as sensitive information and are kept in runtime memory for the print operation rather than intentionally saved in persistent extension storage.

Users should protect their signed-in FMS account and use EzPrint only on trusted devices and authorized SPXExpress environments.

## 7. User choices

- The extension requires the user to accept its in-product use notice before Side Panel FMS API requests are enabled.
- Users decide which PT/SPX identifiers to enter and which shipment rows to preview or print.
- Users may clear the task input and task data using the extension's clear/reset controls.
- Users may remove the extension or clear its Chrome extension data to remove locally stored extension information. Chrome session storage is temporary and is cleared at the end of the browser session or when the extension is reloaded.

## 8. Limited Use

EzPrint's access to and use of information is limited to providing the disclosed single purpose of PT/SPX shipment lookup, status and tracking display, and AWB label printing. Information is not sold or transferred for advertising, creditworthiness, or unrelated purposes. Transfers to SPX FMS and the configured WMS Print Agent occur only as necessary to perform the user's requested lookup and print operations.

## 9. Changes to this policy

If EzPrint's data practices change, this policy and the in-product disclosure will be updated before the changed practices are introduced. The effective date at the top of this page will also be revised.

## 10. Contact

For privacy questions, data-handling inquiries, or support relating to EzPrint, contact:

**Nguyễn Khắc Tấn**  
Staff – Đà Lạt 02 Hub  
**Email:** khactan.nguyen@spxexpress.com
