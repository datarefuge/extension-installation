The original task was to write a test suite to confirm that newly installed extensions were not
breaking the ckan instance. What we did was to get the built-in test suite running
see http://docs.ckan.org/en/ckan-2.6.0/contributing/test.html

This probably does NOT satisfy the original requirement - since extensions are modular
running the ckan test suite only tests the core code. Having said that, you can run the tests
by doing

run-tests-easy output-file.txt

They currently take about 25 minutes to run and use nohup so you can log out.

In spite of not living up to the requirement, a few useful things have come out of this:

1) a possible problem with our set
up (see https://github.com/ckan/ckan/issues/3465)
2) if we do modify the ckan core, we have a functioning test suite
3) MOST IMPORTANTLY, we have a test-core.ini file and database tables
which enable us to run an extension's own tests.
4) Loads of ckan knowledge gained!

Here's what's in this repo:

ckan-testing-setup.txt
	- how we set up our ckan instance to run the ckan test suite
install-extensions.txt
	- general outline of how to install extensions and test ckan
ckan-tests-bin
	- scripts for testing and utility scripts
version.txt
	- versions and locations of ckan and extensions configured in /etc/ckan/default/production.ini
