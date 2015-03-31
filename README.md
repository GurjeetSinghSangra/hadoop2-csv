[![Build Status](https://snap-ci.com/ashwanthkumar/hadoop2-csv/branch/master/build_image)](https://snap-ci.com/ashwanthkumar/hadoop2-csv/branch/master)

# hadoop2-csv

Input format for hadoop able to read multiline CSVs

Run BasicTest.java to see it working. Check src/test/resource/test.csv to see a multiline demofile.

The key returned is the file position where the line starts and the value is a List with the column values

Zip files are supported.

More ideas to improve this are welcome.

## Example:
If we read this CSV (note that line 2 is multiline):

	Joe Demo,"2 Demo Street,
	Demoville,
	Australia. 2615",joe@someaddress.com
	Jim Sample,"3 Sample Street, Sampleville, Australia. 2615",jim@sample.com
	Jack Example,"1 Example Street, Exampleville, Australia.
	2615",jack@example.com


The output is as follows:

	==> TestMapper
	==> key=0
	==> val[0] = Joe Demo
	==> val[1] = 2 Demo Street, 
	Demoville, 
	Australia. 261
	==> val[2] = joe@someaddress.com
	
	==> TestMapper
	==> key=73
	==> val[0] = Jim Sample
	==> val[1] = 
	==> val[2] = jim@sample.com

	==> TestMapper
	==> key=10
	==> val[0] = Jack Example
	==> val[1] = 1 Example Street, Exampleville, Australia. 261
	==> val[2] = jack@example.com

## License
https://www.apache.org/licenses/LICENSE-2.0.html

## Credits
Personal fork of [CSVInputFormat](https://github.com/mvallebr/CSVInputFormat), but built against hadoop2. Please report the issues to the original fork.
