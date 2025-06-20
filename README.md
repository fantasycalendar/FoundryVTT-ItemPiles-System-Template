# What is this?

[Item Piles](https://github.com/fantasycalendar/FoundryVTT-ItemPiles) has gone system agnostic, which means every game system is not supported by Item Piles directly, but will need a module or direct system support.

Follow the guide below (provided mostly by [this Foundry module template](https://github.com/League-of-Foundry-Developers/FoundryVTT-Module-Template)), and you will be able to create releases for your system.

# Module.js setup

You must edit the `module.js` to be configured according to your system.

Please see read this page (specifically the `Adding system support` header) to learn more:

https://fantasycomputer.works/FoundryVTT-ItemPiles/#/contributing-to-item-piles?id=adding-system-support

# Module JSON setup

You must change your `module.json` to have the right setup;

- You must fill in the `id` with your module name, which is the same as the one you create on Foundry's website, specifically the module management page
- You must change the last 5 keys by replacing `[your repository URL here]` with the URL to the repository you just created
- You should change the `title` to reflect which system you are supporting
- You should change the `description` to reflect which system you are supporting
- You should fill in the `authors` section with your online handle, optionally any website URL or discord handle
- You may want to add an additional `relationships.requires` entry for your system 


# How to use this Template to create a versioned Release

1. Open your repository's releases page.

![Where to click to open repository releases.](https://user-images.githubusercontent.com/7644614/93409301-9fd25080-f864-11ea-9e0c-bdd09e4418e4.png)

2. Click "Draft a new release"

![Draft a new release button.](https://user-images.githubusercontent.com/7644614/93409364-c1333c80-f864-11ea-89f1-abfcb18a8d9f.png)

3. Fill out the release version as the tag name.

If you want to add details at this stage you can, or you can always come back later and edit them.

![Release Creation Form](https://user-images.githubusercontent.com/7644614/93409543-225b1000-f865-11ea-9a19-f1906a724421.png)

4. Hit submit.

5. Wait a few minutes.

A Github Action will run to populate the `module.json` and `module.zip` with the correct urls that you can then use to distribute this release. You can check on its status in the "Actions" tab.

![Actions Tab](https://user-images.githubusercontent.com/7644614/93409820-c1800780-f865-11ea-8c6b-c3792e35e0c8.png)

6. Grab the module.json url from the release's details page.

![image](https://user-images.githubusercontent.com/7644614/93409960-10c63800-f866-11ea-83f6-270cc5d10b71.png)

This `module.json` will only ever point at this release's `module.zip`, making it useful for sharing a specific version for compatibility purposes.

7. You can use the url `https://github.com/<user>/<repo>/releases/latest/download/module.json` to refer to the manifest.

This is the url you want to use to install the module typically, as it will get updated automatically.

# How to List Your Releases on Package Admin

To request a package listing for your first release, go to the [Package Submission Form](https://foundryvtt.com/packages/submit) (accessible via a link at the bottom of the "[Systems and Modules](https://foundryvtt.com/packages/)" page on the Foundry website).

Fill in the form. "Package Name" must match the name in the module manifest.  Package Title will be the display name for the package.  Package URL should be your repo URL.
![image](https://user-images.githubusercontent.com/36359784/120664263-b49e5500-c482-11eb-9126-af7006389903.png)


One of the Foundry staff will typically get back to you with an approval or any further questions within a few days, and give you access to the package admin pages.

Once you have access to the [module admin page](https://foundryvtt.com/community/wasp/packages), you can release a new version by going into the page for your module, scrolling to the bottom, and filling in a new Package Version.

When listing a new version, Version should be the version number you set above, and the Manifest URL should be the manifest __for that specific version__ - **do not use /latest/ here.**

I repeat:

### DO NOT USE THE /LATEST/ LINK FROM YOUR MODULE JSON


It is very important that you use the specific release manifest url, and not the `/latest` url here. For more details about why this is important and how Foundry Installs/Updates packages, read [this wiki article](https://foundryvtt.wiki/en/development/guides/releases-and-history).

Clicking "Save" in the bottom right will save the new version, which means that anyone installing your module from within Foundry will get that version, and a post will be generated in the #release-announcements channel on the official Foundry VTT Discord.