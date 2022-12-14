## Install Changesets

```shell
pnpm add -Dw @changesets/cli
pnpm changeset init
```

## update version

### first, add changeset

```shell
pnpm changeset
```

then, you'll see the changeset's cli for updating version.

```shell
pnpm changeset version
```

set the selected package's version, update `CHANGELOG.md`.

```shell
pnpm install
```

update the lockfile and rebuild packages.

### generate version tag

If you don't wanna publish it (like me 😭) You might run additional command for generating version tag.

It is possible to input the command line below.

```shell
pnpm changeset tag
```


---

# [Questions in the official docs](https://github.com/changesets/changesets/blob/main/docs/common-questions.md)


## Changesets are automatically generated

Changesets are generated by the `yarn changeset` or `npx changeset` command. As long as you are following a changeset release flow, you shouldn't have any problems.

## Each changeset is its own file

We use random human readable names by default for these files to avoid collisions when generating them, but there's no harm that will come from renaming them.

## Changesets are automatically removed

When `changeset version` or equivalent command is run, all the changeset folders are removed. This is so we only ever use a changeset once. This makes this a very bad place to store any other information.

## Changesets are markdown files with YAML front matter

The two parts of the file are for different purposes. You should feel free to edit both parts as much as you want.

- The markdown text is a summary of the changes that will be prepended to your changelog when you next run your version command.
- The YAML front matter describes what should be versioned by the version command

## I want to edit the summary or package bump types - is it safe to do that?

Editing the summary or package bump types is completely safe. You can even write changesets without the command if you want.

## Can I manually delete changesets?

You can, but you should be aware this will remove the intent to release communicated by the changeset, and should be done with caution.

---