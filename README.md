# bloglite

Running the Tornado Blog example app
====================================
This demo is a simple blogging engine that uses MySQL to store posts and
Google Accounts for author authentication. Since it depends on MySQL, you
need to set up MySQL and the database schema for the demo to run.

If you have `docker` and `docker-compose` installed, the demo and all
its prerequisites can be installed with `docker-compose up`.

1. Install prerequisites and build tornado

   See http://www.tornadoweb.org/ for installation instructions. If you can
   run the "helloworld" example application, your environment is set up
   correctly.

2. Install Python prerequisites

   Install the packages bcrypt, and markdown (e.g. using pip or
   easy_install). Note that these packages currently only work on Python 2.
   Tornado supports Python 3, but this blog demo does not.

   You may install libffi-dev in Ubuntu by:
   sudo apt-get install libffi-dev

   or in Redhat-based OS by:
   yum install libffi-devel

3. Create the tables in your new database.

   You can use the provided schema.sql file by running this command:
   sqlite3 blog < schema.sql

   You can run the above command again later if you want to delete the
   contents of the blog and start over after testing.

4. Run the blog example

   With the default user, password, and database you can just run:
   ./blog.py

   If you've changed anything, you can alter the default MySQL settings
   with arguments on the command line, e.g.:
   ./blog.py --database=foodblog.db

5. Visit your new blog

   Open http://localhost:8888/ in your web browser.

   Currently the first user to connect will automatically be given the
   ability to create and edit posts.

   Once you've created one blog post, subsequent users will not be
   prompted to sign in.
