.FAKE : build update clean install

build : ../app/src/main/res/xml/wikimedia_licenses.xml

../app/src/main/res/xml/wikimedia_licenses.xml : licenses.php mediawiki-extensions-UploadWizard
	php licenses.php > ../app/src/main/res/xml/wikimedia_licenses.xml

mediawiki-extensions-UploadWizard : update

update :
	if [ -d mediawiki-extensions-UploadWizard ]; then (cd mediawiki-extensions-UploadWizard && git pull origin master); else git clone https://gerrit.wikimedia.org/r/mediawiki/extensions/UploadWizard mediawiki-extensions-UploadWizard; fi

clean :
	rm -rf mediawiki-extensions-UploadWizard
