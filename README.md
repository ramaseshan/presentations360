Presentations 360

A better way to manage and build web presentations.

## Set up :

1. Install python-pip 
2. sudo pip install virtualenv
3. cd ~/Documents
4. virtualenv presentations
5. cd presentations && source bin/activate
6. git clone https://gitlab.com/lhs/presentations360.git
7. cd presentations360
8. pip install -r requirements.txt
9. cd src
10. pelican -o ../ (Doing this because the index.html and other html files will come in the root directory.)
11. cd ../
12. firefox index.html 
