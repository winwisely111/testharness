# testharness

This is a Test harness for core that can then be reused for the many apps.

Many of these aspects are not in the main client but some are in there,
but are mixed up and "spread" into the code base making the code highly coupled,
and hence preventing us to build more applications.


Architecturally its important to strive for abstractions to enable builds apps on top.
IOC  (Inversion of Control ), Dependency injection & Factory Patterns help sometimes so be aware of this.

Here is one example: https://github.com/jonsamwell/flutter_simple_dependency_injection



This has core things that all our apps need:

- i18n internationalisation

- Printing

- Responsive Master Details Layout

- Deep Linking and routing

- Help & Docs

- Nav & Settings

It also has tooling around many of these cross cutting things.

## I18n

The gsheet tool in the bootstrap repo is able to download the translations for all languages and convert them to JSON.

- We need to incorporate that with the Standard Flutter Arb file format and tooling.

- LTR / RTL support

- Settings - Select language

## Printing

See the Plugins repo for the dart plugin (https://github.com/DavBfr/dart_pdf) that supports PDF output and Printing support

It recently works for Web and Mobile and partially for Desktop ( not go-flutter desktop like we use)

## Responsive Master Details Layout

We need to support all screen sizes and orientations.

A common approach to this is to use the Master Detail Pattern.

There is an example here: https://github.com/roughike/adaptive-master-detail-layouts

It lacks:

- Back button
	- There must always be a back button and at the moment there is not.

## Deep Linking and routing

This is obvious.

Needs to work on Web, Desktop and Mobile.

## Help & Docs

This just needs to be a Markdown driven GUI.

The folders of the Markdown determines the Navigation of the GUI. One to One.

The markdown can be assets or pulled from a Server.

## Nav & Settings

We prefer the Google Chrome Duet pattern, in which all Nav buttons are at the bottom of the Screen,
so that its easy to reach from a Mobile.

[demo]: chrome-duet.png "Screenshot of Chrome Duet"
![](https://github.com/winwisely99/testharness/blob/master/chrome-duet.gif)

