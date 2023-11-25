# How to: Release to production

Production releases on our PaaS [Render](https://dashboard.render.com/)

## Steps

1. For the components you want to upgrade, `git tag` the point in history you want to release.
    2. All release tags must start with `v` in order for our pipeline to pick it up, i.e `v1.0.2`.
3. Wait for the GitHub action to complete, for example [BE actions](https://github.com/Pax-fin/be-app/actions)
4. Navivate to the corresponding GitHub package for your image, for
   example [BE packages](https://github.com/Pax-fin/be-app/pkgs/container/be-app)
    5. Make sure your new tag is present!
6. Go to the `render-blueprints` repository and update the `image.url` value with the new tag
7. Push up your change and monitor in the dashboard