---
title: "Request banner ad with XML"
permalink: ver_3.2.0_4_banner_xml.html
sidebar: mps_side_bar
---
The second way to display banner ad is to add its view to your view hierarchy. To do this just add MpsBannerAdView to your xml layout file in a way like this:

```xml
<com.nbcuni.mps.MPSBannerAdView
   		android:id="@+id/mps_ad"
		android:layout_width="match_parent"
		android:layout_height="wrap_content"/>
```

Instantiate an object of this view in a way of your app using standard *findViewById*, *butterknife*, *databinding* or anything else. For example:

```java
MPSBannerAdView mpsAdView = findViewById(R.id.mps_ad);
```

After you have an object of the view just add the following code to load an ad into the banner view:

```java
mpsAdView.displayBannerAd("testbox", page, new MPSBannerAdListener() {
    @Override
    public void onAdLoaded(@NonNull MPSBannerAdView bannerAdView) {
        super.onAdLoaded(bannerAdView);
    }
});
```

Also you can pass additional ad targeting as third parameter to `displayBannerAd` function:

```java
Map<String, String> additionalTargeting = new HashMap<>();
additionalTargeting.put("key", "value");
mpsBannerAdView.displayBannerAd("testbox", page, additionalTargeting, new MPSBannerAdListener() {
    @Override
    public void onAdLoaded(@NonNull MPSBannerAdView bannerAdView) {
        super.onAdLoaded(bannerAdView);
    }
});
```

## Result

This image shows the displayed banner ad.

{% include image.html file="android/banner_xml.png" caption="Banner Loaded Via XML" %}
