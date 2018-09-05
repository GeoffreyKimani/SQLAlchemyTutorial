# SQLAlchemyTutorial
This is a small project to familiarize beginners with using SQLAlchemy ORM with Flask and postgresql

First you will need to have python, flask, postgresql, and SQLAlchemy extension for flask installed.

After writing the piece of code above, follow the steps below to run it:
  1.  Activate your virtual environment for the application. If you are new, check out this guide --> 
       
       https://docs.python-guide.org/dev/virtualenvs/
        
  2.  Move to the folder where this project has been saved and open the interactive python shell.
        
        e.g. cd Desktop/folder_with_project 
             
             then type python in the terminal to open the shell.
  
  3.  We will need to do a few imports;
  
        3.1 import db object, i.e. from file_with_the_code import db
            we have imported the db, but we don't have the initial database, so let's create it by running this -->
            db.create_all()
            
        3.2 import table created i.e from file_with_the_code import User
        
  4.  We are now ready to work with the database, so let's add some data to it.
      In SQLAlchemy, we use sessions to make changes/ commits to a database.
      
      Let's create the objects we shall put in the database;

          root = User(username='root', email='root@example.com') 

          admin = User(username='admin', email='admin@example.com') 

          guest = User(username='guest', email='guest@example.com') 

          worker = User(username='worker', email='worker@example.com') 
      
      
      Since we now have our objects, let's add them to the session;

          db.session.add(root)

          db.session.add(admin)

          db.session.add(guest)

          db.session.add(worker)
      
      
      Let's commit this session to the database
      

          db.session.commit()
      
      
      Now our database has been populated, but let's confirm this by making a query to the database;
      
      
          User.query.all()
      
      
      This should return all the objects that have been created above,
      
          i.e. [<User 'root'>, <User 'admin'>, <User 'guest'>, <User 'worker'>]
          
     Try it out! its as simple...

      
