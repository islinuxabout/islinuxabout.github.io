---
author: Cassidy James Blaede
author-link: https://cassidyjames.com
redirect_from:
  - /theming
  - /theme
---

# [Is Linux About]({{ site.baseurl }}/) Themes?

## No.

Linux is a kernel, and has nothing to do with themes. While some desktop environments and underlying technologies of Linux-based desktop OSes may expose some sort of theming capability, it's equally valid if a Linux-based desktop offers no theming at all.

- [FreeDesktop.org](https://freedesktop.org) specifications try to ensure different desktops' _basic features_ are inter-compatible, but does not address visual style.

  - There are specs for _icon_ and _sound_ themes, but even these are both incomplete and outdated.

- [KDE Plasma][https://kde.org/plasma-desktop] officially supports themes, color schemes, accent colors, and FreeDesktop-compatible icon themes, as applied to both Plasma itself and apps using the Qt and GTK toolkits.

- Several app developers are calling for Linux distributions and downstreams to [stop theming their apps](https://stopthemingmy.app/).

- [elementary OS](https://elementary.io) does not support user themes, and consequently supports unique [branding and in-app theming](https://medium.com/elementaryos/developer-tips-branding-your-app-a57cb44d31d3) capabilities.

- [GNOME](https://gnome.org) offers no official support for themes.

  - [LibAdwaita](https://gnome.pages.gitlab.gnome.org/libadwaita/), the implementation of the [GNOME Human Interface Guidelines and design patterns](https://developer.gnome.org/hig/), does not support user or vendor theming. As such, it enables powerful and easy per-app [custom styling](https://developer.gnome.org/hig/guidelines/ui-styling.html#custom-styling).

  - There are [efforts to improve vendor styling](https://discourse.gnome.org/t/gtk-adwaita-and-vendor-styles/1641) with downstream distributors, but that may look more like setting an accent color than a whole separate theme.
