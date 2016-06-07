# madlib_vagrant_box

This is a simple installation of MADlib installed in PostgreSQL on a vagrant box. You can bring it up and start playing with all of the cool data science functions MADlib has to offer.

    git clone <repo_name>
    cd madlib_vagrant_box
    vagrant up
    vagrant ssh
    sudo su - postgres
    psql mad_ex
    select arima_train( 'arima_beer',
                            'arima_beer_output',
                            'time_id',
                            'value',
                            NULL,
                            FALSE,
                            ARRAY[1, 1, 1]
                          );

To add MADlib on a new database instance, connect to it and run:
    

    CREATE EXTENSION plpythonu;
    CREATE EXTENSION madlib;
