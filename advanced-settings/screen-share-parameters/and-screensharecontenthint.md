---
description: >-
  =motion prioritizes screen-share frame rate; =detail prioritizes screen-share
  resolution
---

# \&screensharecontenthint

Sender-Side Option! ([`&push`](../../source-settings/push.md))

## Aliases

* `&sscontenthint`
* `&screensharecontenttype`
* `&sscontent`
* `&sshint`

## Options

Example: `&screensharecontenthint=detail`

| Value    | Description                                                 |
| -------- | ----------------------------------------------------------- |
| `detail` | will prioritize **screen-share resolution** over frame rate |
| `motion` | will prioritize **screen-share frame rate** over resolution |

#### Additional value options

Depending on browser and version, there may be additional values you can pass, such as `text`. Please see the following link for possible options that your browser may offer:

[https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/contentHint](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/contentHint)



## Details

`&screensharecontenthint` can customize how you want VDO.Ninja to balance screen-share resolution vs screen-share frame rate, specifically when bitrate or CPU is insufficient to offer both at the same time.

The two options are `detail` or `motion`. Screen-shares generally tend towards `detail` by default, and camera sources are tend towards `motion` by default. `detail` will try to prioritize resolution over frame rate, so the frame rate may drop a lot used. `motion` will try to maximize frame rate, but may drop the resolution a lot. There's no way to force both on as there's no magic bullet if your CPU or network cannot keep up.



For more information on how to lock or maximize the resolution of a video feed, please see the following guide:

{% content-ref url="../../guides/how-do-i-lock-the-resolution.md" %}
[how-do-i-lock-the-resolution.md](../../guides/how-do-i-lock-the-resolution.md)
{% endcontent-ref %}

There is [`&contenthint`](../video-parameters/and-contenthint.md) if you want the parameter to affect all kinds of video sources. You can also use both, `&screensharecontenthint` will override [`&contenthint`](../video-parameters/and-contenthint.md) for just screen-shares if set also.

{% hint style="info" %}
If using [`&codec=vp9`](../view-parameters/codec.md) on the viewer side, the frame rate may drop as low as even 5-fps.
{% endhint %}

{% hint style="warning" %}
This parameter has been tested on Chrome, but other browsers may vary in behavior. Safari seems to just ignore things, for example.
{% endhint %}

## Related

{% content-ref url="../video-parameters/and-contenthint.md" %}
[and-contenthint.md](../video-parameters/and-contenthint.md)
{% endcontent-ref %}