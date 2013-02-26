dvid-test-data
==============

Test image volume configuration file and images for [DVID](http://github.com/janelia-flyem/dvid).

Once dvid is built, you can do the following to test image addition to DVID:

	% dvid init dir=/path/to/new/db config=/dvid-test-data/config.json
	   # Note the hexidecimal "Root node UUID" printed by "init" commmand, e.g., 78a0...
	% dvid serve dir=/path/to/new/db &   # Or run in separate shell to see server-side messages
        % dvid grayscale8 server-add 0,0,0 /dvid-test-data/data/250-cube/grayscale8/*.png uuid=78a0

The "grayscale8 server-add" command will add to the datastore all the PNG images in the 
250-cube/grayscale8 directory. Note that the path to the PNG images *must* be absolute and
the server must have access to that path.
