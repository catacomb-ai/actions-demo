# Catacomb Github Actions Demo
> Automating publishing of catacomb projects

This demo builds and publishes the [sentiment analysis](https://github.com/catacomb-ai/examples/tree/master/sentiment_classifier) catacomb example automatically on merge into master.

## Usage

Using this repo is pretty simple! Just merge in a PR or push to master. Then go to the [actions page](https://github.com/catacomb-ai/actions-demo/actions) and wait for the build to finish. Once the build finishes, there will be a url to finalize your deploy at. Click that and youre good to go!

## Sounds cool! How do I add this to my project?

So long as your project fits the Catacomb interface, you should be just a few minutes away from building.

First, make sure you've got a system that works with Catacomb. We've got some [examples](https://github.com/catacomb-ai/examples) of what catacomb projects look like. You can check your project easily by running and starting your model locally:

```bash
$ pip install catacomb-ai
$ catacomb build
$ catacomb start
```

Now, copy [our Github Actions config](/.github/workflows/catacomb.yaml) into your repo at `.github/workflows/catacomb.yaml`. Now change the following variables under the `env` block:

- `CATABOMB_SYSTEM_NAME` - Set this to whatever you want your system to be named. This is typically the name of your repo.
- `DOCKER_USERNAME` - Set this to your docker username (or the username of whatever user you're publishing your images under)

Finally, [add in a secret](https://help.github.com/en/actions/configuring-and-managing-workflows/creating-and-storing-encrypted-secrets#creating-encrypted-secrets-for-a-repository) for your repository called `DOCKER_PASSWORD`. This should be the password for whatever user you specified under `DOCKER_USERNAME`.

Commit and push and things should start working 🤞!

If you get stuck, don't hesitate to [reach out to us](https://catacomb.ai/).

## License
MIT
