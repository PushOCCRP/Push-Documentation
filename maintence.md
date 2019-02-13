---
title: Maintaining Push
description: Instructions and tips for maintaining a Push installation.
permalink: maintence.html
---

Upgrading
====

Backend
----
Upgrading the backend is usually pretty straight forward. From the root directory of the backend run ```sudo bash maintence-scripts/upgrade.sh```

If anything breaks you can try rebuilding the images as well ```sudo bash maintence-scripts/upgrade.sh -r```

**TODO** Add instructions for remote upgrade

