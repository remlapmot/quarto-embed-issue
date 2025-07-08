# Repo demonstrating a small possible bug in quarto render when used repeatedly with a document containing an embed shortcode

To restore the virtual environment .venv, install uv and run

```sh
uv sync
```

Then activate the virtual environment, etc

```sh
source .venv/bin/activate
```

To generate the incorrect tutorial-solutions.html document run

```sh
# Incorrect second render
rm -rf .quarto/embed
quarto render --profile questions
quarto render --profile questions
```

To generate the correct tutorial-solutions.html document run

```sh
# Correct second render
rm -rf .quarto/embed
quarto render --profile questions
rm -rf .quarto/embed
quarto render --profile questions
```
