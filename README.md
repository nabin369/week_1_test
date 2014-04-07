Task:
===

* Change into the temporary directory
	* mkdir temp
	* cd temp

* Using one command, create a directory structure "my/private/files"
	* mkdir -p ./my/private/files

* Using one command, create a directory structure "my/public/files"
	* mkdir -p ./my/public/files

* Create an empty file 't-vars.env' in my/private/files
	* touch ./my/private/files/t-vars.env

* Using commad-line only add the line "List of env vars with that begin with T" to the file, make sure it ends with a newline
	* vi ./my/private/files/t-vars.env

* List all env variables that begin with "T" (hint: you'll need a regex that includes the marker of the start of the line) and append them to the end of the file
	* env | grep ^T >> ./my/private/files/t-vars.env

* export a new variable TESTING_MAKERS=working in such a way that it is still available when you open a new shell
	* echo "export TESTING_MAKERS=working" >> ~/.bash_profile

* output the count of the variable that begin with T to a new file my/public/files/t-vars.count, eg. "Overall count: 5" (hint: you'll need to use 'command substitution' in bash)
	* COUNT=`env | grep ^T | wc -l`
	* echo "Overall count:$COUNT" >> ./my/public/files/t-vars.count 

* change the permissions of the my/private/files/t-vars.env to make sure that only the owner can read and write the file
	* chmod go-r ./my/private/files/t-vars.env

* change the permissions of the my/private/files directory to make sure that only the owner can change into it
	* chmod go-r ./my/private/files 

* give read and write permissions to all users on my/public/files/t-vars.count
	* chmod a+rw ./my/public/files/t-vars.count

* create another file my/public/files/text-files-count.txt and output the number of text files in your home directory (recursively) into that file
	* touch ./my/public/files/text-files-count.txt
	* find . -name "*.txt" -print | wc -l >> ./my/public/files/text-files-count.txt

* list all env variable sorted alphabetically and show the top 3 lines
	* env | sort | head -3


