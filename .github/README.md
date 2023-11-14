# ipack-registry

ipack registry is the global package index for ipack.

## Uploading

Let's say we have a package called `hello_world`. If we upload this package, there will be a entry added in the `packages` field of `he/index.json` (`he` are the first two letters of `hello_world`) that contains general metadata about the package like it's name, version and authors, as well as information used for compiling packages. Here is an example, of how that could look like for the package`hello_world`:

```json

{
	"name": "hello_world",
	"authors": [
		"John Doe <john.doe@mail.com>"
	],
	"version": "1.0.0"
}

```

There will also be a directory inside of the `he` folder called `hello_world` created, that contains a text file for each version with that versions name looking like this:

```txt

https://github.com/octocat/hello-world

```

The link will be a link to the source code of the package. Links will be determined when uploading using a field in the `project.toml`. Following like types will work (more will come later):

- Git repository
- Files, will require more information in the `project.toml` file

### Uploading to the registry directly

If you cannot upload the package to a server or git repository yourself, the code will automatically be uploaded into a folder with the versions name.

## Restrictions

Package names are restricted to the following

- Names have to be between 3 to 32 characters long
- Names can only use `a-z`, `A-Z`, `_` and `.`
- Names can only use `_` and `-` after the second character
- Cannot be the name of a module from the stdlib

We reserve the right to takedown packages/rename them if the restrictions are updated, it violates copyright law or we see need otherwise.
