Maven CLI Integration Test Plugin (cliit-maven-plugin).
=======================================================

location of CLI integration tests:

	src/cliit/
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

