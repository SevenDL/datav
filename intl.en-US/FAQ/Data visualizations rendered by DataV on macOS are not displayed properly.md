# Data visualizations rendered by DataV on macOS are not displayed properly {#concept_qqc_wrk_q2b .concept}

## Symptoms {#section_um5_2wk_q2b .section}

Data visualizations do not display properly if the following conditions apply:

-   You are using a full-HD Retina display.
-   You have updated the latest version of Google Chrome on macOS.
-   You use DataV to edit projects that use a map widget.

## Cause {#section_gjj_pwk_q2b .section}

This firmware issue occurs because the latest macOS version of Google Chrome \(version: 66.0.3359.31\) has a [bug](https://bugs.chromium.org/p/chromium/issues/detail?id=822417&q=canvas%20Composite%20performance&colspec=ID%20Pri%20M%20Stars%20ReleaseBlock%20Component%20Status%20Owner%20Summary%20OS%20Modified). Due to this bug, frame rates as slow as 8 FPS and display lag may occur in many cases, and CPU consumption increases to full capacity while rendering projects on a canvas.

## Solution {#section_rwf_rwk_q2b .section}

This issue has been reported to the Google Chrome development team. A new version is expected to be released soon that will rectify this firmware issue. To continue using DataV properly, we recommend that you consider the following workarounds:

-   Use Google Chrome 57 or a later version \(excluding the latest version\) for macOS.
-   Use another web browser such as Safari on macOS, or temporarily switch to using Chrome or another browser on Windows.

