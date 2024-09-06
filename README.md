# Git pre-commit hook for Puppet Parsing

This pre-commit hook assumes you have:

> puppet-lint<br>
> metadata-json-lint<br>
> Ruby<br>
> YAMLLinr
> and a Puppet agent on the system in which you wish to use it.<br>

### Installation

Place the pre_commit hook into a project's .git/hooks directory.  When you issue a commt statement, the pre-commit hook will be fired against your code and will process:

	Puppet Parser validation via the "puppet parser validate" command.
	Puppet-lint validation via the "puppet-lint <filename>.pp" command
	Metadata.json-lint validation of the metadata.json file if it exists.
	Ruby erb template validation via Ruby command validation.

...before allowing a commit to your local staging area.

You may also place the pre_commit hook itself in your system's Git "templates" directory.  This will automatically copy the pre_commit hook to any new project each time you run "git init" into the appropriate hooks directory.

###Advanced
Git allows you to also customize your templates directory when using `git init`.  To use this feature, perform the following steps:

1. mkdir -p /path/to/templates/hooks
2. git config --global init.templatedir '/path/to/templates'
3. cp pre-commit /path/to/templates/hooks
4. cp <any other hooks> /path/to/templates/hooks

Now, each time you execute a `git init` on the system, Git will copy in the pre-commit hook (and anything else you've placed into the templates/hooks location) into your project in the <project>/.git/hooks directory

***For this hook to work properly, you have to have the following installed:***

	puppet-lint
	metadata-json-lint
	yamllint
	ruby
	Puppet Agent for your platform installed

### Credits

This hook is a compliation of multiple people's assistance and work, and I do not have everyone's information, only that of those mentioned inside the hook itself.  Please do feel free to contribute as much as you like.

Contributors:

**Original authors:**<br>
Ronny Roethof<br>
Mattias Geniar

Jerald Sheets (me) added metadata-json-lint and ruby testing
Isaac Hall added Yamllint support

### License
This hook is under GPLv2 license.  Use it how you wish. Please distribute my info with it.  Please pay it forward.