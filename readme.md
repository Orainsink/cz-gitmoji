# cz-gitmoji-customize

> Commitizen adapter formatting commit messages using emojis.

**cz-gitmoji-customize** allows you to easily use emojis in your commits using [commitizen].

```sh
? Select the type of change you are committing: (Use arrow keys)
❯ feature   :sparkles:  New features.
  fix       :bug:  Fix a bug.
  docs      :pencil:  Write docs.
  refactor  :art:  Improve structure / format of the code.
  chore     🔩  A chore change
```

## Install

**Globally**

```bash
npm install --global cz-gitmoji-customize

# set as default adapter for your projects
echo '{ "path": "cz-gitmoji-customize" }' > ~/.czrc
```

**Locally**

```bash
npm install --save-dev cz-gitmoji-customize
```

Add this to your `package.json`:

```json
"config": {
  "commitizen": {
    "path": "cz-gitmoji-customize"
  }
}
```

## Usage

```sh
$ git cz
```

## Customization

By default `cz-gitmoji-customize` comes ready to run out of the box. Uses may vary, so there are a few configuration options to allow fine tuning for project needs.

### How to

Configuring `cz-gitmoji-customize` can be handled in the users home directory (`~/.czrc`) for changes to impact all projects or on a per project basis (`package.json`). Simply add the config property as shown below to the existing object in either of the locations with your settings for override.

```json
{
  "config": {
    "cz-gitmoji-customize": {}
  }
}
```

### Configuration Options

#### Types

By default `cz-gitmoji-customize` comes preconfigured with the [Gitmoji](https://gitmoji.carloscuesta.me/) types.

An [Inquirer.js] choices array:

```json
{
  "config": {
    "cz-gitmoji-contomize": {
      "types": [
        {
          "emoji": "🌟",
          "code": ":star2:",
          "description": "A new feature",
          "name": "feature"
        }
      ]
    }
  }
}
```

#### Scopes

An [Inquirer.js] choices array:

```json
{
  "config": {
    "cz-gitmoji-customize": {
      "scopes": ["home", "accounts", "ci"]
    }
  }
}
```

#### Symbol

A boolean value that allows for an using a unicode value rather than the default of [Gitmoji](https://gitmoji.carloscuesta.me/) markup in a commit message. The default for symbol is false.

```json
{
  "config": {
    "cz-gitmoji-customize": {
      "symbol": true
    }
  }
}
```

#### Skip Questions

An array of questions you want to skip:

```json
{
  "config": {
    "cz-gitmoji-customize": {
      "skipQuestions": ["scope", "issues"]
    }
  }
}
```

You can skip the following questions: `scope`, `body`, and `issues`. The `type` and `subject` questions are mandatory.


#### Customize Questions

An object that contains overrides of the original questions:

```json
{
  "config": {
    "cz-gitmoji-customize": {
      "questions": {
        "body": "This will be displayed instead of original text"
      }
    }
  }
}
```

## Examples

- https://github.com/Falieson/TRAM

## License

MIT © [Nicolas Gryman](http://ngryman.sh)

[commitizen]: https://github.com/commitizen/cz-cli
[inquirer.js]: https://github.com/SBoudrias/Inquirer.js/
[cz-emoji]: https://github.com/ngryman/cz-emoji
