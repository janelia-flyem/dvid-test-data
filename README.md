dvid-test-data
==============

Test image volume configuration file and images for [DVID](http://github.com/janelia-flyem/dvid).

Once dvid is built, you can do the following to test image addition to DVID:

	% dvid init dir=/path/to/new/db config=/dvid-test-data/config.json
	   # Note the hexadecimal "Root node UUID" printed by "init" commmand, e.g., 78a0...
	% dvid serve dir=/path/to/new/db &   # Or run in separate shell to see server-side messages
        % dvid grayscale8 server-add 0,0,0 /dvid-test-data/grayscale8/*.png uuid=78a0

The "grayscale8 server-add" command will add to the datastore all the PNG images in the 
/dvid-test-data/grayscale8 directory. Note that the path to the PNG images *must* be absolute and
the server must have access to that path.  Also note that the "uuid=78a0" argument doesn't have
to have the full hexadecimal UUID; it only needs a sufficient number of characters to uniquely
identify the UUID already in the DVID datastore.
