** Note: This is a work in progress. Nothing works as of now. Do check
   back sometime later. If you are wondering why there is an elaborate
   (kind of) README and no code, I am trying out Readme driven
   development **

MicroJournal
============

Microjournal is a simple, lightweight jornal backed by Git. On its own,
it does not do much. Instead of doing all the heavy lifting on it's own,
it uses your default editor to add entries and uses Git to safe keep the
entries. It does not do any kind of post processing on the entries. The
expectation is that one would write the entries in plain text, but then
you can use whatever format you want.

Installation
------------

1. Clone the MicroJournal repo
```shell
git clone https://github.com/sdqali/microjournal.git
```
2. Once you have cloned the repo add the bin directory to your
$PATH. This can be done by adding
```shell
export PATH=$PATH:<microjournal-repo-dir>/bin
```
to the end of the init file of your shell (`~/.bashrc`, `~/.zshrc`)

Settng up a journal
-------------------

1. Run
```shell
mkdir foobar
```
```shell
cd foobar
```
```shell
microjournal init git@github.com:sdqali/foobar.git
```
This will create the following directory structure

<pre>
foobar
  |- entries
  |   |- 2012
  |       |- 06
  |           |- 23.txt
  |- config.yml
  |- .git
</pre>

In addition, it will add `git@github.com:sdqli/foobar.git` as a remote for the Git
repo created.

Adding entries
--------------

1. Run
```shell
microjournal jot
```
This will open the journal entry for today in your default editor (read
from $EDITOR). MicroJournal will automatically add todays date and
current date in to the entry.

Safekeeping
-----------

As mentioned above, MicroJournal does not do any magic of its own and
hence Safekeeping just means a git push. To do this, run
```shell
microjournal safekeep
```

This would commit all the entries in the entries/ directroy along with
with the config.yml file, and push to the remote.
