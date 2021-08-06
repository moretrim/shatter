[![shatter](media/title.png)](https://github.com/moretrim/shatter)

Shatter
-------

Build status:
[![Github Workflow][github-workflow-badge]][github-workflow-dashboard]

[github-workflow-badge]:
    https://github.com/moretrim/shatter/actions/workflows/ci-on-push.yaml/badge.svg
[github-workflow-dashboard]:
    https://github.com/moretrim/shatter/actions/workflows/ci-on-push.yaml
    "Github Workflows"

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

<figure>

![launcher](media/launcher.jpg)

  <figcaption>

  Example launcher picture featuring the older 0.1.0 version

  </figcaption>
</figure>

Make sure that the mod is selected in the launcher (as pictured above) so that it will be loaded by
the game.

This mod has been designed so that load order should not matter.

Usage
-----

Once a game has been started you can verify that *Shatter* has been loaded correctly by looking at
the decision screen. It should include the following decision somewhere:

![decision](media/decision.jpg)

You can be playing any country for this to be available. Activate the decision at any time to be
presented with **Parameter events** that allow you to pick the right kind of shattering for your
purposes:

1.  * **History-based release**: set up new countries by relying on their historical data for
      picking techs, inventions, and government type. Appropriate for shattering precisely on or
      shortly after a bookmark e.g. 1 January 1836, but can result in large tech deficits otherwise.
      Some countries that are set up to appear at a later point may have their historical data tuned
      for that date, resulting in oddities.
    * **Parent-based release**: set up new countries by relying on their parent country for picking
      techs, inventions, and government type. Convenient for shattering on a later date, with the
      drawback of sometimes imposing an inappropriate government type. This has largely the same
      effects as releasing a country through the *Release Nations* tab of the *Politics* screen
      except that shattering will only ever produce independent countries, never puppets.

1.  * **Releasable countries only**: stick to countries that are allowed to be released through the
      *Release Nations* tab of the Politics screen. Special cases (usually: revolt tags, some
      cultural unions) will not appear on the map.
    * **Allow unreleasable countries**: try to release everything, consequences be damned.

1.  * **Enable core revokation**: countries lose cores on the countries they release. This mimics
    the behaviour of releasing a country through the *Release Nations* tab of the *Politics* screen.
    * **Disable core revokation**: countries keep cores on countries they release. This tends to
      benefit large countries.

Each parameter is picked on a per-activation basis, or can alternatively be saved to be re-used for
all subsequent shatterings for this campaign. Saved parameters are stored on a per-country basis,
and can be reset through the decision (without actually shattering anything).

Once all parameters have been picked, or if all parameters were already saved, you will be presented
with the following choice before anything is performed:

![event](media/event.jpg)

The event gives you five options:

- shatter the world, breaking free all vassal countries & releasing as many countries as possible by
  trying to follow normal gameplay rules
- shatter your country only (though released countries may still retrieve their cores from other
  countries)
- do nothing (in case you activated the decision by accident)
- reset the saved parameters for the country you are currently playing, without shattering anything
- do nothing, and dismiss the decision for the country you are currently playing (you will not be
  able to shatter the world again as that country)

If you do decide to shatter the world, the game may turn unresponsive for a short period of time.
Please be patient, there is a lot of processing to be done.

Countries that release others will see their cores revoked on their former lands. Your country will
not be given preferential treatment and will be undergoing the full shattering process as well.

Once the world has been shattered you will be offered the choice to dismiss the *Shatter* decision
for the country you are currently playing. This is convenient if e.g. you only intended to shatter
the world once at the start.

Shattering in detail
--------------------

The shattering process is best explained as a set of rules:

* countries are released in generations: for a given shattering the initial countries constitute
  generation 1 and they release the countries that will constitute generation 2
* the process repeats until shattering is complete: generation 2 will release generation 3 and so on
* capital priority rule: existing countries attempt to release non-existing countries of which they
  hold the capital before they do other countries (this is a global order)
* non-union priority rule: existing countries attempt to release non-cultural unions before they do
  unions (this is also a global order)
* core recovery order: countries from a given generation recover their cores from all countries of
  preceding generations (but never from their own)
* *no full overlap* rule: a country will not release another that has cores all it, nor will it turn
  over its entire territory during core recovery
* unciv priority rule: civilised countries do *not* recover cores held by non-Westernised country

The *no full overlap* rule prevents non-existing cultural unions from subverting the overall
process. Consider for instance most 1836 maps which feature many German countries (some tiny) and no
united Germany yet. Without the rule and because German cores usually fully overlap these countries,
the map would easily end up with a very solid Germany—quite the opposite of shattering.

The same logic applies to non-union countries that fully overlap another as well, which usually act
as a “variant” government or quasi-cultural union. A good example of this is Bolivian cores fully
overlapping Peru-Bolivia on 1836 maps based e.g. on the New Nations Mod.

The unciv priority rule is to avoid creating colonial provinces.

Limitations & Known Issues
--------------------------

Since shattering is always performed in the same order behind the scenes, the process always
produces the same result (given starting countries and cores on the map **and** which country
initiates the shattering). The shattering rules are designed to mitigate this as best as possible.
Unfortunately random results are harder to achieve in Victoria II mods than you might think.

A side-effect of the design is that shattering is *very* process intensive.

Compatibility
-------------

This mod has only been tested with Victoria II with its two expansions. It should be compatible with
any mod, as long as the following holds:

- event IDs `634736xxx` are available

Image Licence
-------------

The image as well as its variants that can be found in the mod proper are licenced under a [Creative
Commons Attribution-ShareAlike 4.0 International License][CC BY-SA 4.0]. They are derivative works
of *[Point of Impact]* by [Bill Harrison], itself available under the terms of the [Creative Commons
Attribution 2.0 Generic License][CC BY 2.0].

[Point of Impact]: https://www.flickr.com/photos/29053754@N08/6074633858
[Bill Harrison]: https://www.flickr.com/photos/bill_harrison/
[CC BY-SA 4.0]: https://creativecommons.org/licenses/by-sa/4.0
[CC BY 2.0]: https://creativecommons.org/licenses/by/2.0

Release History
---------------

### 1.0.0-dev (in development)

- implement shatter parameters, to customise shattering behaviour
- prevent AI countries from picking event outcomes reserved to players (i.e. dismissing the
  *Shatter* decision)
- implement capital priority rule for improved consistency and final borders
- implement core recovery for improved final borders
- add and document a couple other shatter rules

### 0.1.0

[The original release.][v0.1.0]

[v0.1.0]: https://github.com/moretrim/shatter/tree/v0.1.0
