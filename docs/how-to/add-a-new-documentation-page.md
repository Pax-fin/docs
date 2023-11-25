# How to: Add a new document

It needs to be easy to add new files.

## Steps

The instructions differ a little bit depending if the current navigation structure is good enough for you. It is
expected that we'll add new groups and possibly reorder documents as needed as the knowledge base grows.

### Add hidden files

This is the simplest approach when you just want to add a file that isn't present in the navigation bar but you can
search through hyperlinks in other documents. You'll probably use this for seldom used documents that you would only
look at in the context of another document, i.e project design documents under a project folder.

This is simplest because you can do whatever you want as long as you write markdown files under the `docs/` folder. The
file is even searchable in our search bar!

### Adding to an existing folder/group

First you need to find your folder. All documentation lives under the `docs/` folder. You can find the navigation
structure through the `mkdocs.yml`.

Second, write your markdown file. **Note**, you can take advantage of
our [material theme's](https://squidfunk.github.io/mkdocs-material/) components.

Lastly, `git commit -am 'your changes' && git push`!

### Adding a new group

First, navigate to the `mkdocs.yml` file and adjust the `nav` key as needed. Then you can
follow [add to existing folder](#adding-to-an-existing-foldergroup).