# Little Things

## Google highlight search

We can highlight text in a page with Chrome using a special hash/anchor :

```txt
#:~:text=
```

> The hash/anchor isn't stocked in `window.location.hash` !

Example of URL :

```txt
https://website.com/page#:~:text=text%20to%20highlight%20here
```

[Example](https://github.com/Its-Just-Nans#:~:text=You%20can%20check%20my%20github%20website)

## Apache not forwarding `Authorization` header to PHP

You need to add in your `.htaccess` :

```bash
CGIPassAuth On
```

## See developer tool of the Discord client

In `"DANGEROUS_ENABLE_DEVTOOLS_ONLY_ENABLE_IF_YOU_KNOW_WHAT_YOURE_DOING": true` in `~/.config/discord/settings.json`

- [https://www.reddit.com/r/discordapp/comments/sc61n3/comment/hu4fw5x](https://www.reddit.com/r/discordapp/comments/sc61n3/comment/hu4fw5x/)

## Don't do that

![svg](./data/svg.jpg)
