## Octotree

Browser extension (Chrome, Firefox, Opera and Safari) that displays a code tree on GitHub. Great for exploring project source code without having to download many repositories to your machine.

**Features**

- Easy-to-navigate code tree, just like in IDEs
- Fast browsing with pjax
- Support private repositories (see [instructions](#access-token))

**Features of Octotree Pro**

- Dark mode
- File search
- Change docking position
- Multiple GitHub accounts
- Support GitHub Enterprise on Chrome, Opera and Firefox
- Official Safari version (Safari doesn't support GitHub Enterprise)

Learn why we build Octotree Pro [here](HISTORY.md#v300). Subscribe to Octotree Pro on [our website](https://www.octotree.io).

![Octotree on GitHub](docs/chrome-github.png)

### Install Octotree

- Octotree: [Chrome](https://chrome.google.com/webstore/detail/octotree/bkhaagjahfmjljalopjnoealnfndnagc), [Firefox](https://addons.mozilla.org/en-US/firefox/addon/octotree/), [Opera](https://addons.opera.com/en/extensions/details/octotree/)
- Octotree Pro: [Chrome](https://chrome.google.com/webstore/detail/fjcahddnekkgihjnjnimgiggdmlgcnbc), [Firefox](https://addons.mozilla.org/en-US/firefox/addon/octotree-pro/), [Opera](https://addons.opera.com/en/extensions/details/octotree-pro/), [Safari](https://itunes.apple.com/us/app/octotree-pro/id1457450145?mt=12)

## Settings

### Access Token

Octotree uses the [GitHub API](https://developer.github.com/v3/) to retrieve repository metadata. By default, it makes unauthenticated requests to get these data. However, there are two situations when GitHub require such requests to be authenticated:

- You access a private repository
- You exceed the [API rate limit](https://developer.github.com/v3/#rate-limiting)

When that happens, Octotree will ask for your [GitHub personal access token](https://help.github.com/articles/creating-an-access-token-for-command-line-use). If you don't already have one, [create one](https://github.com/settings/tokens/new?scopes=repo&description=Octotree%20browser%20extension), then copy and paste it into the token textbox in the Settings screen. Note that the minimal scopes that should be granted are `public_repo` and `repo` (if you need access to private repositories).

**No BS Policy**: Octotree doesn't collect/share/care about your data at all. It stores the access token in your browser local storage and uses it only to communicate with GitHub API (see the code that does that [here](https://github.com/ovity/octotree/blob/559291ed9017f0c3429bc49419d001d9ea0ac510/src/adapters/github.js#L296-L313)).

**Access tokens are stored in the browser's local storage, only enter access tokens when you use a trusted computer.**

### Hotkeys

Hotkeys to pin or unpin the sidebar. You can enter multiple hotkeys by separating them with a comma.

- Supported modifiers: `⇧`, `shift`, `option`, `⌥`, `alt`, `ctrl`, `control`, `command`, and `⌘`.
- Supported special keys: `backspace`, `tab`, `clear`, `enter`, `return`, `esc`, `escape`, `space`, `up`, `down`, `left`, `right`, `home`, `end`, `pageup`, `pagedown`, `del`, `delete` and `f1` through `f19`.

Learn more at [keymaster](https://github.com/madrobby/keymaster#supported-keys).

### Others

- **Load entire tree at once**: if checked, load the entire code tree at once. For large repos where Octotree can't load it in a single request, Octotree ignores this settings and lazily-loads the repo.
- **Show in non-code pages**: if checked, show Octotree in non-code pages such as Issues and Wiki.
- **Show file-specific icons**: if checked, show different icons for different file types.
- **Show only pull request changes**: if checked, show only the change set of a pull request.

### Octotree Pro Settings

#### GitHub Enterprise

_Note: GitHub Enterprise is not supported on Safari._

After installing Octotree Pro, navigate to your GitHub Enterprise site. Right-click the Octotree Pro icon in the browser bar (see the image below) and select "Enable Octotree Pro on this domain". The page should refresh and Octotree Pro sidebar should show up. Alternatively, you can disable Octotree Pro on a domain by selecting "Disable Octotree Pro on this domain".

![GitHub Enterprise](docs/pro-ghe.png)

#### Multiple GitHub Accounts

If you have multiple GitHub accounts with access to different private repositories, you will need to let Octotree know which access token to use for which account.
This feature allows you to enter additional GitHub accounts and corresponding tokens. When you login to GitHub with an account, Octotree will use the matching token to make API requests to GitHub. If you don't login to GitHub or if the account you login is not in the account list, Octotree will use the default access token.

Go to Settings and click the + icon to add more accounts.

![Multiple GitHub accounts](docs/pro-ma.jpg)

#### Change Docking Position

You can change the location of the Octotree sidebar to either the left or right side of the screen. Click the dock icon located at the bottom of Octotree to toggle the sidebar location.

![Change docking position](docs/pro-dock.png)

#### Dark Mode

Click the dark mode icon located at the bottom of Octotree to toggle dark mode.

![Dark mode](docs/pro-dark.png)

#### File Search

Click the search icon and type in search query.
**Note:** this feature requires the "Load entire tree at once" option to be selected.

![File search](docs/pro-search.png)

## Contribution

1.  Install [node 8 or above](https://nodejs.org/en/download/)
1.  Run `npm install` to install dependencies
1.  Run `npm start` to watch code changes and build unpacked extensions
1.  Load the unpacked extensions in the `tmp` folder (check instructions of the specific browser)
1.  Please follow existing style for new code

### Credits

Octotree and Octotree Pro use the following open-source software:

- [jQuery](https://github.com/jquery/jquery)
- [jQuery UI](https://github.com/jquery/jquery-ui)
- [jstree](https://github.com/vakata/jstree)
- [file-icons](https://github.com/file-icons/atom)
- [keymaster](https://github.com/madrobby/keymaster)
- [jquery-pjax](https://github.com/defunkt/jquery-pjax)
- [github-dark](https://github.com/StylishThemes/GitHub-Dark)
