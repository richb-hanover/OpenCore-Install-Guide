# Contributing to OpenCore Install Guide

OpenCore is software that allows non-Mac hardware to run macOS. If you would like to learn to install macOS on your computer, [read the OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/).

This repository holds the source pages for that documentation. Want to help support the Guide? Well there are several ways you can help!

* [Contributing via Issues](#contributing-via-issues)
* [Contributing via PRs](#contributing-via-prs)
* [Contributing via Translations](#contributing-via-translations)

**Note**: This is a community run guide which is not officially endorsed by Acidanthera. Please do not bug Acidanthera with issues about this Guide.

**Note**: We seriously appreciate offers of financial support but we're not set up to accept funds. We make this documentation to teach, not for the money. If you have some money left over we highly recommend donating it to a charity. [Crohn's and Colitis Canada](https://crohnsandcolitis.donorportal.ca/Donation/DonationDetails.aspx?L=en-CA&G=159&F=1097&T=GENER) is one we recommend if you don't have one in mind.

## Contributing via Issues

Use the [Bugtracker](https://github.com/dortania/bugtracker) to contribute problems you have found. Our rules are pretty simple:

* Only report problems with the OpenCore Install Guide itself. **Do not submit personal Hackintosh issues.** They will be ignored because the Bugtracker is not a place to discuss installation issues.
* If you are writing about a typo or asking for clarification, please indicate the URL of the page where you found it, otherwise it will be ignored. (We don't enjoy a scavenger hunt looking for these issues.)

## Contributing via PRs

Please use standard Github PRs. Some guidelines when contributing via PRs:

* Use your brain (please).
* Proofread your submissions.
* Pull Requests can be denied if we feel they do not fit or have inaccurate information. We will generally tell you why it is rejected though or ask for revisions.
  * We would also appreciate sources for any bigger commits to make it easier on us to verify the info you provide is valid
* Images must be hosted locally in the repo under the `../images/` folder
* Your PR must be spell-checked and run through a markdown lint and have all issues fixed. (See **Developing and Testing...** below.)
* We avoid using "non-Acidanthera" tools. Generally we want to avoid use of third-party tools  - though if it's impossible otherwise, then you can link it. These tools are explicitly banned:
    * UniBeast, MultiBeast and KextBeast
      * We outline the reasons here: [Tonymacx86-stance](https://github.com/khronokernel/Tonymcx86-stance)
    * TransMac
      * Know for creating borked USB drives
    * Niresh Installers
      * We'd like to avoid piracy with the guides

### Developing and Testing Your Edits

The OpenCore Install Guide has a set of tools for previewing the site as you edit it, and for testing the documents to ensure they are properly formatted before submitting a PR. Steps to install the tools:

* [Fork this repo](https://github.com/dortania/OpenCore-Install-Guide/fork/)
* Install the required tools:
  * [Node.js](https://nodejs.org/)
  * `npm install`  to install all the required plugins
* Preview the site:
  * `npm run dev` View your version of the documentation at [http://localhost:8080/OpenCore-Install-Guide/](http://localhost:8080/OpenCore-Install-Guide/)
* Make your changes and save the files. Web pages update automatically.
* Before creating a PR, check linting and spelling:
  * `npm test` (runs both tests on all files)
  * `npm run lint` and `npm run spellcheck` (to run them individually)
  * `npm run fix-lint` (Attempts to fix lint issues automatically)
* Create a "distribution" by sending all the HTML files to the `.vuepress/dist` directory with `npm run build` 

### Tips

Some tools that make contributing a bit easier:

* [Typora](https://typora.io) for real time markdown rendering. (Win/Lin/Mac)
* [SublimeText](https://www.sublimetext.com/) for easy and powerful mass find/replace. (Win/Lin/Mac)
* ~~[TextMate](https://macromates.com) for easy and powerful mass find/replace.~~ (Site seems to be off the air...)
* [Github Desktop](https://desktop.github.com) for more user friendly GUI. (Win/Mac)

## Contributing via Translations

While Dortania's guide are primarily English based, we know there's plenty of other languages in the world and that not everyone is fluent in English. If you want to help translate our guides into different languages, we're more than happy to support you.

Main things to keep in mind:

* Translations must be a dedicated fork and won't be merged into Dortania's guide
* Forks must indicate they're translations of Dortania and are not official
* Forks must also comply with our [License](LICENSE.md)

If the above are met, you're free to host your translation without issue! Dortania's sites are built with [VuePress](https://vuepress.vuejs.org) using [Travis-CI](https://travis-ci.org) and finally hosted on [Github Pages](https://pages.github.com), so there is no cost to hosting your own translation.

If you have any questions or concerns with either translations or hosting, feel free to reach out on our [Bugtracker](https://github.com/dortania/bugtracker).

Current known translations:

* [InyextcionES](https://github.com/InyextcionES/OpenCore-Install-Guide)(Spanish)
* [macOS86](https://macos86.gitbook.io/guida-opencore/)(Italian)
* [Technopat](https://www.technopat.net/sosyal/konu/opencore-ile-macos-kurulum-rehberi.963661/)(Turkish)

And note that these translations are subject to authors preferences, translation changes and human errors. Please keep this in mind when reading as they're no longer official Dortania guides.

