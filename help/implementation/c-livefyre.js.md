---
description: The core Livefyre library used to power Livefyre on your site.
title: Livefyre.js
exl-id: 82083dc0-3b4a-467c-bad7-dbf242ab5bbd
---
# Livefyre.js {#livefyre-js}

The core Livefyre library used to power Livefyre on your site.

`Livefyre.js` is the core library that you can install on every Livefyre-enabled webpage. It defines the global `window.Livefyre` object and a single public method, `Livefyre.require`, which can be used to load other Livefyre JavaScript libraries that help with [Embedding Livefyre Apps](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md), [Integrating your authentication provider with Livefyre](/help/implementation/t-about-identity-integration/t-about-identity-integration.md) and more.

## Add to your Site {#section_cst_twg_xz}

Add the following `<script>` tag to your webpage or website template. If possible, add it to the `<head>` section of your HTML document so it loads quickly.

```
<script src="//cdn.livefyre.com/Livefyre.js"></script>
```

>[!NOTE]
>
>This script will embed a very small (~1 Kb) file called the Livefyre.js scout that will subsequently load the latest version of Livefyre.js over the protocol with which your webpage has been accessed (HTTP or HTTPS).

## Livefyre.require {#section_ipq_hwg_xz}

`Livefyre.require` is a custom JavaScript module loader like [curl.js](https://github.com/cujojs/curl) or [RequireJS](https://requirejs.org/). It can be used to load most packages published by Livefyre and presents a convenient and intuitive integration path.

Packages accessible through `Livefyre.require` are versioned using [Semantic Versioning](https://semver.org/). Packages can be required at a specific version or to a range of versions so your webpage can automatically benefit from new bugfixes features. This gives you flexibility when integrating Livefyre on your site. There are three levels of version pinning you can use with `Livefyre.require`.

* **package-name#1:** Pin to major version v1. You’ll get all new updates that maintain a backward-compatible API. Pin to a major version to receive bug fixes and minor feature enhancements for that version.
* **package-name#1.1:** Pin to minor version v1.1. You’ll get all bugfixes to this minor version. Livefyre Engineering will always bump the minor version of a package if its default behavior or functional scope changes in a way that could cause new, unexpected behavior on your webpage. Pin to a minor version if you wish to receive automated bug fixes, but no additional functionality or changes to default behavior.
* **package-name#1.1.1:** Pin to patch version v1.1.1. The behavior of this embed will never change, even if there are bugfixes. Pin to a patch version if you have extensive CSS customizations for your site that depend on a package’s markup structure that may change, or if you have other reasons to prefer that the Livefyre version you are running will not change in any way.

An example integration using `Livefyre.require` could look like this:

```
<!-- First add Livefyre.js to the page --> 
<script src="https://cdn.livefyre.com/Livefyre.js"></script> 
  
<!-- Then load up all the desired Livefyre packages and Do Stuff in the callback --> 
<script> 
Livefyre.require([ 
    'lfawesome#1', 
    'lfsuperawesome#2.1.2' 
], function (LFAwesome, LFSuperAwesome) { 
    var greatness = new LFAwesome(); 
    // etc.. 
}); 
</script>
```

## Available packages {#section_ygd_dwg_xz}

Wondering which Livefyre JavaScript packages are available through `Livefyre.require`? You can always find an up-to-date list of supported packages and their latest versions here: [packages.html](https://cdn.livefyre.com/packages.html).

## Testing pre-release Versions of Packages {#section_pgm_dpg_xz}

Sometimes you may want to test an upcoming version of a Livefyre package to make sure it will work on your website or to acceptance test a feature that is being developed at your request. In addition to including a Semantic Version range, the prerelease UAT environment can be specified.

For example, the following would require the UAT release of `fyre.conv`, the Comments, Live Blog, and Chat applications.

```
Livefyre.require(['fyre.conv#uat'], callback); 

```
