---
description: Desktop environments have removed or are removing support for the legacy GtkStatusIcon (aka system tray). However, there are many new, capable, cross-desktop APIs that replace the functionality previously provided by tray icons. Here you can find a list of replacement APIs and see how well-supported they are.
author: "Daniel Foré"
author-link: https://danielfore.com
redirect_from:
  - app-indicator
  - appindicator
  - app-indicators
  - appindicators
  - indicators
  - status-icon
  - statusicon
  - status-icons
  - statusicons
  - systemtray
  - sys-tray
  - sys-trays
  - systrays
---

# [Is Linux About]({{ site.baseurl }}/) SysTray?

{% assign des = site.desktop-environments | sort: "title" %}

## No.

Desktop environments have removed or are removing support for the legacy GtkStatusIcon (aka system tray). However, there are many new, capable, cross-desktop APIs that replace the functionality previously provided by tray icons. Here you can find a list of replacement APIs and see how well-supported they are.

## I want to…

- [Convey sync status or provide actions related to cloud storage](#cloudproviders)
- [Provide quick access to my app's commonly used actions](#desktop-actions)
- [Convey progress for long-running tasks](#launcher-entry)
- [Display how many items need action (such as unread messages)](#launcher-entry)
- [Provide media player controls or now playing info](#mpris)
- [Alert the user that something has changed in my app](#notifications)
- [Inform the user that my app is accessing system functions in the background (like screen recording)](#portals)

## CloudProviders

If you want to communicate synchronization status or provide actions related to cloud storage devices, you can use the CloudProviders DBus API

<div class="overflow-x">
  <table>
    <thead>
      <tr>
        <th></th>
        {% for de in des %}
          <th>{{ de.title }}</th>
        {% endfor %}
      </tr>
    </thead>
    <tbody>
      <tr>
        <th>Status Icon</th>
        {% for de in des %}
          {% assign status = de.cloudproviders.status-icon %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
      <tr>
        <th>Actions</th>
        {% for de in des %}
          {% assign status = de.cloudproviders.actions %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
    </tbody>
  </table>
</div>

## Desktop Actions

If you want to provide quick access to common actions, you can add them to your .desktop file

<div class="overflow-x">
  <table>
    <thead>
      <tr>
        <th></th>
        {% for de in des %}
          <th>{{ de.title }}</th>
        {% endfor %}
      </tr>
    </thead>
    <tbody>
      <tr>
        <th>Actions</th>
        {% for de in des %}
          {% assign status = de.desktop-actions.actions %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
      <tr>
        <th>Icons</th>
        {% for de in des %}
          {% assign status = de.desktop-actions.icons %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
    </tbody>
  </table>
</div>

## Launcher Entry

If you want to communicate progress information for long-running background tasks or the number of items needing action in your app (such as tasks or messages) you can use the LauncherEntry DBus API

<div class="overflow-x">
  <table>
    <thead>
      <tr>
        <th></th>
        {% for de in des %}
          <th>{{ de.title }}</th>
        {% endfor %}
      </tr>
    </thead>
    <tbody>
      <tr>
        <th>Progress Bar</th>
        {% for de in des %}
          {% assign status = de.launcher-entry.progress-bar %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
      <tr>
        <th>Badge</th>
        {% for de in des %}
          {% assign status = de.launcher-entry.badge %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
    </tbody>
  </table>
</div>

## MPRIS

If you want the user to be able to access media player controls for you app, you can listen to and supply information to MPRIS

<div class="overflow-x">
  <table>
    <thead>
      <tr>
        <th></th>
        {% for de in des %}
          <th>{{ de.title }}</th>
        {% endfor %}
      </tr>
    </thead>
    <tbody>
      <tr>
        <th>Media Info</th>
        {% for de in des %}
          {% assign status = de.mpris.media-info %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
      <tr>
        <th>Player Controls</th>
        {% for de in des %}
          {% assign status = de.mpris.player-controls %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
      <tr>
        <th>Album Art</th>
        {% for de in des %}
          {% assign status = de.mpris.album-art %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
    </tbody>
  </table>
</div>

## Notifications

If you want to alert the user that something has changed in your app, you can send a notification bubble

<div class="overflow-x">
  <table>
    <thead>
      <tr>
        <th></th>
        {% for de in des %}
          <th>{{ de.title }}</th>
        {% endfor %}
      </tr>
    </thead>
    <tbody>
      <tr>
        <th>Bubbles</th>
        {% for de in des %}
          {% assign status = de.notifications.bubbles %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
      <tr>
        <th>Actions</th>
        {% for de in des %}
          {% assign status = de.notifications.actions %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
      <tr>
        <th>Notification Center</th>
        {% for de in des %}
          {% assign status = de.notifications.notification-center %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
      <tr>
        <th>Images</th>
        {% for de in des %}
          {% assign status = de.notifications.images %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
      <tr>
        <th>Replace</th>
        {% for de in des %}
          {% assign status = de.notifications.replace %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
    </tbody>
  </table>
</div>

## Portals

XDG Desktop Portals are sandbox-compatible DBus APIs for accessing system functions. Desktop environments can use these portals to request consent from users and provide an ongoing indication of portal usage.

<div class="overflow-x">
  <table>
    <thead>
      <tr>
        <th></th>
        {% for de in des %}
          <th>{{ de.title }}</th>
        {% endfor %}
      </tr>
    </thead>
    <tbody>
      <tr>
        <th>Location Consent</th>
        {% for de in des %}
          {% assign status = de.portals.location-consent %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
      <tr>
        <th>Location Indication</th>
        {% for de in des %}
          {% assign status = de.portals.location-indication %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
      <tr>
        <th>Screencast Consent</th>
        {% for de in des %}
          {% assign status = de.portals.screencast-consent %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
      <tr>
        <th>Screencast Indication</th>
        {% for de in des %}
          {% assign status = de.portals.screencast-indication %}
          {% if status == true %}
            {% assign status = "✔️" %}
          {% elsif status == false %}
            {% assign status = "✖️" %}
          {% elsif status == "planned" %}
            {% assign status = "🗋" %}
          {% elsif status == "partial" %}
            {% assign status = "◐" %}
          {% endif %}
          <td class="{{ status }}">{{ status }}</td>
        {% endfor %}
      </tr>
    </tbody>
  </table>
</div>

