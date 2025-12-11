# Preview for Mastodon Taiwanese translations

Last update: 2025-12-11.

Since Mastodon only activates a locale after it's sufficiently translated, it's a little hard to put the translated strings into context without making a local version that enables the language. This is an attempt to automate that.

Upstream `main` sits in the `main` branch. I plan to manually periodically update it then rebase this minimal branch on top of it.

## Making a preview build

This is adopted from the [main DEVELOPMENT.md](https://github.com/mastodon/mastodon/blob/main/docs/DEVELOPMENT.md).

- Visit https://codespaces.new/kisaragi-hiu/mastodon?quickstart=1&devcontainer_path=.devcontainer%2Fcodespaces%2Fdevcontainer.json which creates a new codespace
  - Confirm the options
  - Wait for the environment to build (takes a few minutes)
- When the editor is ready, run `bin/dev` in the terminal to start the instance
- Wait for the editor to show an *Open in Browser* prompt and click it. This will open the front-facing page of the instance in your browser
- Go to the `Ports` tab, find the "stream" item, right click and change its *Port visibility* to *Public*

Now you have access to a development instance. Stop the command in the codespace to spin it down.

Because the preferences are only available after log in, you have to log in to a user. The development instance provides a default admin user, which can be used to log in.

- The username is `admin@<domain>`, where domain is the domain that your browser connected to. For instance, `super-space-winner-5ggxj99w5x9f74r-3000.app.github.dev`. This is different for every codespace.
- The password is `mastodonadmin`.

## Bike shedding

The language code is `nan`. It would be better if it's `nan-TW`, but `nan` is what Crowdin already syncs translations to, frustratingly. It would be even better if it's `ftg`, but that's pending [ISO 639-3 Change Request 2021-044](https://iso639-3.sil.org/request/2021-044).

I use "Taiwanese (Hokkien)" and "台語（閩南語）" in `languages_helper.rb` [like has been done in Pleroma](https://git.pleroma.social/pleroma/pleroma-fe/-/merge_requests/1841#note_101496).
