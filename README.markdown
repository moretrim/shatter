[![shatter](./title.png)](https://github.com/moretrim/shatter)

# Shatter

Build status:
[![travis-master][travis-master-image]](https://travis-ci.com/moretrim/shatter/branches)

[travis-master-image]: https://travis-ci.com/moretrim/shatter.svg?branch=master

Description
-----------

Shatter your Victoria II world at any time you want, in any mod.

Shattering means breaking all extant vassal–overlord relationships, and having every country release
as many independent countries as possible. This can be done on 1 January 1836 or at any later point.
Do it once or repeatedly through a campaign, it’s all up to you.

Installation
------------

Grab the [0.1.0 release].

[0.1.0 release]: https://github.com/moretrim/shatter/releases/tag/v0.1.0

Install this as you would any other mod. When installed properly, the `shatter.mod` file and the
`shatter` directory should live side-by-side. In the Victoria 2 launcher you should see an entry for
the mod:

![launcher](./launcher.jpg)

Make sure that the mod is selected in the launcher (as pictured above) so that it will be loaded by
the game.

This mod has been designed so that load order should not matter.

Usage
-----

Once a game has been started you can verify that <cite>Shatter</cite> has been loaded correctly by
looking at the decision screen. It should include the following decision somewhere:

![decision](./decision.jpg)

You can be playing any country for this to be available. Activate the decision at any time to be
presented with the following choice, before anything is performed:

![event](./event.jpg)

The event gives you four options:

- shatter the world, breaking free all vassal countries & releasing as many countries as possible by
  trying to follow normal gameplay rules
- utterly shatter the world, breaking free all vassal countries & releasing even special case
  countries (typically, countries that are only meant to appear through events and/or in unusual
  circumstances)
- do nothing (in case you activated the decision by accident)
- do nothing, and dismiss the decision for the country you are currently playing (you will not be
  able to shatter the world again as that country)

If you do decide to shatter the world, the game may turn unresponsive for a short period of time.
Please be patient, there is a lot of processing to be done.

Countries that release others will see their cores revoked on their former lands. Your country will
not be given preferential treatment and will be undergoing the full shattering process as well.

Once the world has been shattered you will be offered the choice to dismiss the <cite>Shatter</cite>
decision for the country you are currently playing. This is convenient if e.g. you only intended to
shatter the world once at the start.

Limitations & Known Issues
--------------------------

The mod does not do anything beyond freeing vassals and releasing countries. In particular, freshly
released countries will only control cores of their former master. (This is the same as hitting
'Release' in the diplomatic interface while playing as the latter.) As a result the final borders
may not quite be what you expect.

Since shattering is always performed in the same order behind the scenes, the process always
produces the same result (given starting countries and cores on the map **and** which country
initiates the shattering). This is a bit unfortunate as in general several different results are
possible (see previous paragraph) and this could be improved on with a little bit of randomisation.
Unfortunately random results are harder to achieve in Victoria II mods than you might think.

Compatibility
-------------

This mod should be compatible with Victoria II with its two expansions. It should also be compatible
with any mod, as long as the following holds:

- event IDs `634736xxx` are available

Image Licence
-------------

The image as well as its variants that can be found in the mod proper are licenced under a [Creative
Commons Attribution-ShareAlike 4.0 International License][CC BY-SA 4.0]. They are derivative works
of <cite>[Point of Impact]</cite> by [Bill Harrison], itself available under the terms of the
[Creative Commons Attribution 2.0 Generic License][CC BY 2.0].

[Point of Impact]: https://www.flickr.com/photos/29053754@N08/6074633858
[Bill Harrison]: https://www.flickr.com/photos/bill_harrison/
[CC BY-SA 4.0]: https://creativecommons.org/licenses/by-sa/4.0
[CC BY 2.0]: https://creativecommons.org/licenses/by/2.0

Release History
---------------

### 0.1.0

[The original release.][v0.1.0]

[v0.1.0]: https://github.com/moretrim/shatter/tree/v0.1.0
