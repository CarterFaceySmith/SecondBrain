RWX means read, write and execute, permissions diplayed in the command line interface will be in this form.

We can change permissions with the chmod command:
- chmod u=rw file.txt = changes the permissions of user to read and write
- chmod u+r(or x or w) filename can also be used to add a permission, vice versa with subtract sign
- when doing this you can use a= for 'all'
- you can leave the permissions field (rwx) empty to give no permissions at all

See also:
-[[UNIX]]