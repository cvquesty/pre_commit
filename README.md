##Git pre-commit hook for Puppet Parsing

This pre-commit hook assumes you have 

puppet-lint
metadata-json-lint
Ruby

and a Puppet agent on the system in which you wish to use it.

##Installation

Place the pre_commit hook into a project's .git/hooks directory.  When you issue a commt statement, the pre-commit hook will be fired against your code and will process:

	Puppet Parser validation via the "puppet parser validate" command.
	Puppet-lint validation via the "puppet-lint <filename>.pp" command
	Metadata.json-lint validation of the metadata.json file if it exists.
	Ruby erb template validation via Ruby command validation.

...before allowing a commit to your local staging area.

You may also place the pre_commit hook itself in your system's Git "templates" directory.  This will automatically copy the pre_commit hook to any new project each time you run "git init" into the appropriate hooks directory.

***For this hook to work properly, you have to have the following installed:***

puppet-lint<br>
metadata-json-lint<br>
ruby<br>

##Credits

This hook is a compliation of multiple people's assistance and work, and I do not have everyone's information, only that of those mentioned inside the hook itself.  Please do feel free to contribute as much as you like.

##License
This hook is under GPLv2 license.  Use it how you wish. Please distribute my info with it.  Please pay it forward.
