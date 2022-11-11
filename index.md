# What is Linux About?

**Linux is a kernel**, low-level code that forms the base layer of an operating system. Usually when people talk about “using Linux,” they’re talking about using some Linux-based operating system like Ubuntu, Fedora, Arch, Endless OS, Pop!_OS, elementary OS, etc.

These Linux-based operating systems run one of several **desktop environments** which make up what is typically thought of as the OS’s user experience like GNOME, KDE Plasma, XFCE, etc. or their own version of a desktop environment.

Sometimes the people and organizations behind these desktop environments are also working to build a cohesive **ecosystem** of apps and tools that use a common set of design patterns and other shared approaches.

The people designing and developing these operating systems, desktop environments, and ecosystems frequently work together under the **FreeDesktop** umbrella; a collection of specifications and defacto implementations to ensure that software made “for Linux” generally works across any of these layers.

However, the people working on different parts of the greater ecosystem don't always agree! That's part of the beauty of “Linux;” its diversity and choice. That said, let's dive into specifics:

# Is Linux about…

{% for page in site.pages %}
{% if page.title and page.url != "/" and page.url != "/404.html" %}
…[{{ page.url | replace: "/", "" | replace: "-", " " }}]({{ page.url }})?
{% endif %}
{% endfor %}
