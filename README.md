# vc — browser video codec support

A single static page (`index.html`) that shows which video codecs the current browser supports through three APIs, one per tab: **WebRTC** (`RTCRtpSender`/`RTCRtpReceiver.getCapabilities`), **MSE** (`MediaSource.isTypeSupported`) and **WebCodecs** (`VideoDecoder`/`VideoEncoder.isConfigSupported`). Codec parameters are decoded into readable form, e.g. H.264 `profile-level-id=640c1f` or `avc1.640C1F` becomes `Constrained High / 3.1`, alongside H.265, VP9 and AV1 profile/level/bit depth.

Live demo: https://witaly-iwanow.github.io/vc/

No build step or dependencies: open `index.html` in a browser. WebCodecs requires a secure context, so serve it over HTTPS or from `localhost` (e.g. `python3 -m http.server`) if that tab reports it as unavailable.
