# fullstack-dev-setup

gulp-nodemon doesn't monitor filechanges when e.g. Sublime Text already has many files open.

See https://github.com/remy/nodemon/issues/214 post by eyce9000

eyce9000 commented on Apr 1, 2014

I just had this issue and it was a problem of too many files open on the system. 
(Sublime Text loves to open lots of files if you let it)

Potential fix:

https://discourse.roots.io/t/gulp-watch-error-on-ubuntu-14-04-solved/3453/2

Post by: ajithrn

the reason for the error is there is a limit in the system for how many files can be watched by a user, using the following command in a terminal window we can simply increase the limit ..

echo fs.inotify.max_user_watches=582222 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
