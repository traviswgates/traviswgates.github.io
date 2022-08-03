---
title: Set a Color Theme for a Specific Project or Folder in VS Code
excerpt: "Use the Workbench Color Theme property in Workspace Settings to set a per-project-directory color theme default in VS Code."
categories:
- Tips and Tricks
---

# Different Projects, Different Color Themes

Try setting the `Workbench Color Theme` property in your Workspace Settings. With this property, you can set a default color theme for each project or folder you open with VS Code, loosely coupling a theme to specific work.

1. In VS Code, open your project folder, perhaps with **File > Open Folder** or `CTRL+K, CTRL+O`. I typically invoke `code .` from the directory via my shell.
2. Navigate to the `Workspace Settings`
    - via **File > Preferences > Settings** then select the `Workspace` tab
    - via the Command Palette with `CTRL+SHIFT+P` then searching some part of `Preferences: Open Workspace Settings`
3. Select your preferred project Color Theme via the `Workbench Color Theme` property.

{% include figure.html image="/assets/images/2022-07-29/color-theme-workspace-settings.png" caption="Workbench Color Theme" %}

Alternatively, you can edit the workspace `settings.json` directly:

1. From the Command Palette (`CTRL+SHIFT+P`), select `Preferences: Open Workspace Settings (JSON)`.
2. Ensure that the `workbench.colorTheme` property is added to the `settings.json` file that is opened. **Save your changes!**

``` json
{
    "workbench.colorTheme": "Solarized Dark"
}
```

*Just remember to substitute "Solarized Dark" with the name of your preferred theme.*

# Color-Coding Different Workspaces

I recently found myself needing two work in two places at once. 

I know -- a lot of conventional wisdom discourages multi-tasking. However, it is often easier to write, say, a guide on how to do something *while* one is doing the thing. Like taking notes.

So I wanted this project, my website, open in one code window while I had a Python project open in another.

With limited screen real estate and a lot of `ALT+TAB`ing, I rapidly realized that two windows wasn't enough. Text isn't as easily distinguishable from other text as I'd like, so I thought I'd help myself out and speed up my recognition of where I'm working by changing the color theme of one of my VS Code windows.

Unfortunately, after using the Command Palette (`CTRL+SHIFT+P` by default on Windows) to open `Preferences: Color Theme` and change it, I saw during my `ALT+TAB` trial that the other window also conformed to the newly selected theme.

I didn't despair. Knowing that VS Code treats each folder it opens as its own workspace *(workbench?)*, I got to thinking: was there a configurable setting I might be able to tweak to get a per-folder or per-project color theme default?

Sure enough, the Command Palette yielded two options: `Preferences: Open Workspace Settings` and `Preferences: Open Workspace Settings (JSON)`.

I often prefer direct-views of configuration data as JSON, but a lot of the time altering the JSON directly for the first time means editing a very empty JSON object; often the defaults aren't populated, I've found.

So I opened up the Settings page as a UI and `CTRL+F`ed my way to the `Workbench: Color Theme` property, which I set to my own preference in my new project (Solarized Dark).

>There are a lot of settings that can be tweaked here, but for my needs, the base 'default' was sufficient.

Then I returned to my code project and simply selected a different color theme from the Command Palette -- changing my global or more likely user-based color theme and in the moment only affecting that project's window.

![Two Windows, Two Colors](/assets/images/2022-07-29/two-windows-two-colors.png)
