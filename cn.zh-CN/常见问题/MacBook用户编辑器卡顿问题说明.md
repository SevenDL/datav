# MacBook用户编辑器卡顿问题说明 {#concept_qqc_wrk_q2b .concept}

## 问题现象 {#section_um5_2wk_q2b .section}

使用MacBook的用户打开DataV编辑页面之后使用卡顿，CPU占用率飙升。问题发生的场景如下：

-   使用MacBook的用户，特别是Retina屏幕打开较高分辨率后。
-   使用了最新版本的Chrome浏览器。
-   使用DataV编辑包含**基础平面地图**组件的大屏项目。

## 问题原因 {#section_gjj_pwk_q2b .section}

Mac平台最新版的Chrome浏览器在Mac平台的66.0.3359.31版本更新时引入了一个bug[（关于此bug详细描述）](https://bugs.chromium.org/p/chromium/issues/detail?id=822417&q=canvas%20Composite%20performance&colspec=ID%20Pri%20M%20Stars%20ReleaseBlock%20Component%20Status%20Owner%20Summary%20OS%20Modified)，造成了以下问题：

-   在进行画布渲染时，CPU占用率从偶尔的3%～5%飙升至持续的100%，导致使用画布中组件的前端页面的帧率下跌至8fps以下，使用起来非常卡顿。
-   所有使用画布前端组件的Web产品都会受到影响。
-   问题会随着画布像素数量、画布叠加层数的增加而变的更加严重，导致这部分用户在标准的1920×1080分辨率下编辑DataV**基础平面地图**组件时非常卡顿。

## 解决方法 {#section_rwf_rwk_q2b .section}

这个Bug已经反馈给谷歌浏览器开发团队，目前尚未给出解决的时间表。在问题修复之前，建议使用MacBook版Chrome的用户通过以下方法规避该问题以免影响日常使用。

-   使用旧版本的Chrome浏览器，建议使用Chrome 57及以上版本。
-   使用其他浏览器，如Safari浏览器。
-   临时使用Windows电脑编辑。

