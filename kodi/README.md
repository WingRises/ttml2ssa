Usually Kodi allow very little customization of subtitles (SRT format),
you can mainly only change the color, that's all.

However Kodi also supports subtitles in SSA/ASS format, which are more
customizable, for example you can add a shadow, set an outline color...
It's also possible to place the subtitles on the top of the screen.

Ttml2ssa is a library that can convert TTML/XML/DFXP/VTT/SRT subtitles used
by Netflix, HBO, Disney+, Prime Video and other stream services to SRT,
SSA/ASS and VTT format. It also provides a configuration dialog where the user
can select the font size, colors, shadow and many other things.

This is the idea: you create an addon to provide support for a streaming
service in Kodi. Your addon downloads the subtitles (TTML, VTT, any supported
format) and calls the ttml2ssa library to convert the subtitles to SSA/ASS.
Subtitles will look nicer than the regular SRT format. Moreover the subtitles
will be displayed on top of the screen when necessary (just like the official
apps of Netflix, Disney+ and others do). The user will use the configuration
dialog provided by ttml2ssa. This configuration will be shared by all addons
that use the ttml2ssa library.

In the case you don't want to use the SSA/ASS format, ttml2ssa can also
convert to SRT.

Ttml2ssa can also perform some cosmetic changes so the subtitles look with
the same style among different services.

Example code:

```
from ttml2ssa import Ttml2SsaAddon
....

ttml = Ttml2SsaAddon()
ttml.parse_subtitle_file(input_file)
ttml.write2file('output.ssa')
```

There's available a repo with modified versions of the Netflix, Amazon, Disney+ and
hbogoeu (only Nordic/Spain) addons with support for ttml2ssa:
https://github.com/Paco8/kodi-repo

More info:
https://github.com/Paco8/ttml2ssa