The Open Build Service Landing page
===================================

This page is based on [Jekyll](https://github.com/mojombo/jekyll) and [Foundation](http://foundation.zurb.com/)
and is served via [Netlify](https://www.netlify.com/) to [openbuildservice.org](http://www.openbuildservice.org)

### Markdown

Pages are written in kramdown. A quick reference for the syntax can be found
[here](https://kramdown.gettalong.org/quickref.html).

### Local Preview

Run `docker-compose up` and access http://localhost:4000

### Deployments

Deployments are automated with a webhook, so whenever commits are pushed to
`master`, a new version will be published. The deployments are listed
[here](https://app.netlify.com/sites/openbuildservice/deploys).

### Add New Members to Team Page

Add the following lines at the end of the YAML front matter block:

```
- name: Example Name
  position: Frontend Developer
  email: example@suse.de
  github: examplegithub
  twitter: exampletwitter
  blog: https://examplename.com
  irc: exampleirc
  description: "Write a nice description of yourself.
  You can use **markdown** in ~~the~~ _description_.

  \nAnd add new paragraphs too."
```

You don't need to include all the fields, you can just remove the one you don't want to have.
If you use special characters you may need to surround your text by `"`.


### Updating OBS Documentation

The OBS documentation is stored in a [separate repository](https://github.com/openSUSE/obs-docu)
and is integrated into the OBS landing page via git submodules.

After doing some changes in _obs-docu_ (see how [here](https://github.com/openSUSE/obs-docu#update-documentation)) you should wait until they are
merged and then move to your local directory of _obs-landing_. Update it and run the [update_documentation.sh](update_documentation.sh) script that
you can find inside the _obs-landing_ project. This updates the documentation sub-module, compiles it into html and creates a new commit with the
changes. The new commit's message is _"Update books to current state"_.

Make sure that your working tree is clean. If it, on the contrary, shows some untracked changes in
`open-build-service-documentation`, simply run `git submodule init` and `git submodule update` manually. This will update the submodule and will clean the working tree.

Once the last _"Update books to current state"_ commit in _obs-landing_ gets merged, you'll see your changes in https://openbuildservice.org/help.

# License

The code in this repository is licensed under a [MIT license](LICENSE).

The blog's content is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License.
<img alt="CC" src="/images/icons/cc.png" width="18px"/>
<img alt="BY" src="/images/icons/by.png" width="18px"/>
