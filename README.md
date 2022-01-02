# My Website
An attempt at making my website, which should be deployed [here](https://keivan-shah.github.io). I am making use of [Hugo](https://gohugo.io/) with the theme [Hello Friend NG](https://github.com/rhazdon/hugo-theme-hello-friend-ng) and hosting with help of [Github Pages](https://pages.github.com/).

While I have not decided what I want to do with this Blog/Website. I do love exploring random topic that interest me and I want to share some of them with the world. I also want to start posting once every month eventually? (Currently posting once a year). I maintain a list of topic I might post on [here](TODO.md), let me know if you have some interesting topics to there.

If you are cloning this repo, you will need to make a lot of changes. Also this repo has a lot of my personal info, so I would suggest creating your own repo from scratch while looking at this repo as reference.
For starters, I suggest looking at [Hugo's QuickStart Guide](https://gohugo.io/getting-started/quick-start/), [this theme repo](https://github.com/rhazdon/hugo-theme-hello-friend-ng), [my config file](config.toml) and [GA workflow file](.github/workflows/main.yml).

## Development

```bash
# Clone this repo

# Install the submodules first time to fetch the theme
git submodule update --init --recursive
# git submodule update --recursive --remote # To update the submodules

# Fetch hugo(extended) binary from "https://github.com/gohugoio/hugo/releases"
<path_to_binary>/hugo server # Local demo of the website

# Now, make what ever changes needed, Maybe add a new post?
# Once done, commit changes to the repo, GA will automatically deploy the changes
```

## Deployment

The website has been configured to be deployed with the help of [Github Actions](https://docs.github.com/en/actions). Whenever a commit is made to the repo, the static website is re-generated and then deployed to this repo: [github.com/keivan-shah.github.io](https://github.com/keivan-shah/keivan-shah.github.io) which is then visible to everyone [here](https://keivan-shah.github.io), thanks to Github Pages.

## Acknowledgements

Thanks a lot to these projects for making this quite easy to do:
- [gohugoio/hugo](https://github.com/gohugoio/hugo)
- [Hello Friend NG](https://github.com/rhazdon/hugo-theme-hello-friend-ng)
- [peaceiris/actions-hugo](https://github.com/peaceiris/actions-hugo)
- [peaceiris/actions-gh-pages](https://github.com/peaceiris/actions-gh-pages)
