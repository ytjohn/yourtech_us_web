---
ID: 26
post_title: LaView DVR access from zoneminder/vlc
author: ytjohn
post_date: 2017-04-30 21:42:52
post_excerpt: ""
layout: post
permalink: https://new.yourtech.us/?p=26
published: false
---
Finally connected my DVR to the network. It's an LaView lv-d0404bs (4-ch dvr). I searched all over and couldn't find an rtsp url for this model. Finally, I did what I should have done, and opened the source of the web page.

I found this bit of code:     ` var url = "rtsp://" + ip + ":" + port + "/H264?ch="+channelnum+"&subtype=" + _type;`

Which translates to:

`rtsp://[IP]:554//H264?ch=[CAMERA]&subtype=1`

I am not sure what the difference in sub-types is. Valid values are 0 & 1, and they seem to have the same resolution. Sub-type 0 seems to scale to fill the window, whereas 1 starts off at a 4:3 aspect ratio.

<img src="https://lh4.googleusercontent.com/-ae7Ji-npt38/VPxOI3oAkiI/AAAAAAAAXnY/tCtOITKq2hs/w852-h474/Screen%2BShot%2B2015-03-08%2Bat%2B9.25.33%2BAM.png"  style="max-width:80%;" height="237" width="426"
 alt="Camera03 Driveway">