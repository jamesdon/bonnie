This App is intended to make collecting and parsing out Bonnie++ results a snap.  Splunk relies heavily on this output to determine if your storage meets minimum requirements.  

Changes to Splunk:
This App does not install any new indexes, however I would recommend putting this data in its own index for data separation.  This App only relies on a sourcetype=bonnie associated with the data.  Make sure that the index you place it in is searched by default.

How to configure and use this App:
All of this information is conveniently embedded in the "Bonnie++ Resources" dashboard in this App.

Why is it important?:

1) You need to run custom Bonnie++ commands for every Splunk environment.
- This App builds that command for you!

2) Below is the cryptic output from the Splunk recommended Bonnie++ commands to test your hardware.
- This App extract all possible fields, even if they are not being used quite yet.

----------------------------------------------------------------------------------------------------------------------------
Using uid:0, gid:0.
Writing intelligently...done
Rewriting...done
Reading intelligently...done
start 'em...done...done...done...done...done...
Create files in sequential order...done.
Stat files in sequential order...done.
Delete files in sequential order...done.
Create files in random order...done.
Stat files in random order...done.
Delete files in random order...done.
Version  1.96       ------Sequential Output------ --Sequential Input- --Random-
Concurrency   1     -Per Chr- --Block-- -Rewrite- -Per Chr- --Block-- --Seeks--
Machine        Size K/sec %CP K/sec %CP K/sec %CP K/sec %CP K/sec %CP  /sec %CP
servername01  160G           39912   3 29398   4           79075   4 207.2  34
Latency                       12226ms   61883ms               349ms    3643ms
Version  1.96       ------Sequential Create------ --------Random Create--------
servername01       -Create-- --Read--- -Delete-- -Create-- --Read--- -Delete--
              files  /sec %CP  /sec %CP  /sec %CP  /sec %CP  /sec %CP  /sec %CP
                 50   170   2 42859  17   288   1   225   3  3525   9   345   1
Latency               234ms   22897us     145ms     296ms     897us   84789us
1.96,1.96,servername01,1,1450900351,160G,,,,39912,3,29398,4,,,79075,4,207.2,34,50,,,,,170,2,42859,17,288,1,225,3,3525,9,345,1,,12226ms,61883ms,,349ms,3643ms,234ms,22897us,145ms,296ms,897us,84789us
----------------------------------------------------------------------------------------------------------------------------

Field mappings:
Using the last comma separated values line in the output, the field mappings are as follows:

version1
version2
server
concurrency
undef
size
undef0
seq_output_per_char_k_per_sec
seq_output_per_char_percent_CP
seq_output_block_k_per_sec
seq_output_block_percent_CP
seq_output_rewrite_k_per_sec
seq_output_rewrite_percent_CP
seq_input_per_char_k_per_sec
seq_input_per_char_percent_CP
seq_input_block_k_per_sec
seq_input_block_percent_CP
random_seeks_k_per_sec
random_seeks_percent_CP
files
undef1
undef2
undef3
undef4
seq_create_create_k_per_sec
seq_create_create_percent_CP
seq_create_read_k_per_sec
seq_create_read_percent_CP
seq_create_delete_k_per_sec
seq_create_delete_percent_CP
random_create_create_k_per_sec
random_create_create_percent_CP
random_create_read_k_per_sec
random_create_read_percent_CP
random_create_delete_k_per_sec
random_create_delete_percent_CP
seq_output_per_char_latency
seq_output_block_latency
seq_output_rewrite_latency
seq_input_per_char_latency
seq_input_block_latency
random_seeks_latency
seq_create_create_latency
seq_create_read_latency
seq_create_delete_latency
random_create_create_latency
random_create_read_latency
random_create_delete_latency

Contact and Support:
Please provide feedback and/or enhancement requests to jim@splunk.com.  I will respond within three business days or sooner to address any issues that are reported.  

Application development is hosted on github - https://github.com/jamesdon/chargeback, if you would like to join in on the fun!


Contributing Authors:
James Donn
