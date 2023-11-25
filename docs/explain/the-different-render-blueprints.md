# Explain: the different Render blueprints

## Context

If you look at the [Render blueprints tab](https://dashboard.render.com/blueprints), you'll see two styles of
blueprints:

- `deployment-*` (like `deployment-prod`)
- `repo-*` (like `repo-be-app`)

At first glance, it isn't obvious why we have so many blueprints and when to adjust one or the other.

### Different blueprints for different SDLCs

The different blueprints is to support different sdlc pipelines for different components. The `deployment` blueprint is
a typical release manifest. All of our production runtimes are declared in a single place and peer-reviewed with the
proper scrutiny. Additionally, we don't need to modify many different places to release **or rollback**.

For the repo-specific blueprints, we similarly want to keep code changes and nonprod deployments in a single merge.
Consider a situation where you want to add a new feature to your app that requires new external dependencies (like a
database). When you merge to your repo, you don't want to take down dev, so you would modify your source code and
blueprint in the same changeset.

Finally, render does support the ability to do `preview environments`. In other words, a branch of your repo could
generate a super scaled down version of this app deployment, but this depends on having configured render.yml which we
wouldn't want to support in the production manifest.

You might be wondering if we could use the github triggered autodeployment feature as well. With the repo-aligned
blueprints this is possible. However, we avoid it for 2 reasons:

- we like building our own images and being able to pull them for local development and debugging
- we want to save on pipeline time to keep ourselves on the free tier for as long as possible