# odbvm(1)

`odbvm` is a very stupid version manager for OrientDB.

Few people will feel the need for a version manager for a database, but I happen
to be one of them :) (if you're wondering, it's cause I developed and maintain
[MarcoPolo][marco-polo], an OrientDB driver for Elixir).

## Installation

Clone the repo and add the directory to your `$PATH`:

```
$ git clone https://github.com/whatyouhide/odbvm SOME_DIR
$ export PATH="SOME_DIR:$PATH"
```

You'll have three new executables:

* `odbvm` - used to choose versions to use and list installed versions
* `orientdb-console` - used to launch an OrientDB console for the current version
* `orientdb-server` - used to launch an OrientDB server for the current version

To update, just `git pull` inside the directory you cloned this project in.

## Usage

(`odbvm --help` to the rescue)

Basically, you choose an OrientDB version to use with `odbvm use VERSION` and
then use `orientdb-console` and `orientdb-server`.

For now, you have to manually download OrientDB versions and manually move them
to the installations directory:

```bash
$ cd /tmp
$ wget "http://orientdb.com/download.php?email=unknown@unknown.com&file=orientdb-community-2.1.4.tar.gz&os=mac"
$ mv orientdb-community-2.1.4 ~/.odbvm/installations
```

Now, you can list all your installations:

```bash
$ odbvm list
orientdb-community-2.1.4
```

and choose an installation to use:

```bash
$ odbvm use 2.1.4
Using version: 2.1.4
```

As you can see, you specify only the version number when choosing the version
(ignoring the `orientdb-community-` part).

### Overriding the version

You can override the OrientDB version that `orientdb-console` and
`orientdb-server` use at any time by running them with the `$ORIENTDB_VERSION`
environment variable set:

```bash
$ ORIENTDB_VERSION="2.1.2" orientdb-console
```

## Contributing

Just open issues, there are probably a thousand bugs in here :).

## License

MIT &copy; 2015 Andrea Leopardi

[marco-polo]: https://github.com/MyMedsAndMe/marco_polo
