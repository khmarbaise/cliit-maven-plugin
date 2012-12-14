Maven CLI Integration Test Plugin (cliit-maven-plugin).
=======================================================

Status
------
- First thoughts about this.

TODOs
-----
- Everything.

- copy a bat/cmd/sh script to an appropriate location.
- Copy the created archive (which contains the app which should be tested) to
  a particular location and unpack it.
  - Result of build which uses maven-assembly-plugin in relationship with maven-appassembler-plugin.

Questions
---------

* How to do the setup?
  - Put everything into pre folder. => execute everything there or copy to execute (may be both cases?)

  - run the application (Command: xyz) + arguments ?

  - verify phase to check the results
    => result for this integration test case: sucessful or failed.

  - run the post execution phase to clean up things or whatever ?


location of CLI integration tests:

	src/itcli/
	   +-- test1
	         +-- (sub folders if needed)
	         +-- supplemental files
	         +-- setup.(sh,bat,groovy)
	         +-- execute.(sh,bat,groovy)
	         +-- verify.(sh,bat,groovy)
	    +-- test2
	         +-- (sub folders if needed)
	         +-- supplemental files
	         +-- setup.(sh,bat,groovy)
	         +-- execute.(sh,bat,groovy)
	         +-- verify.(sh,bat,groovy)


preBuildHookScript (setup.(bsh,groovy)):
postBuildHookScript (verify.(bsh,groovy));


tests will be cloned to target folder:

	target/cliit/
	        +--- test1
	               +-- (sub folders if needed)
	               +-- supplemental files
	               +-- execute.(sh, groovy) is filtered 
	               +-- execution.log
	        +--- test2
	               +-- (sub folders if needed)
	               +-- supplemental files
	               +-- execute.(sh, groovy) is filtered 
	               +-- execution.log

