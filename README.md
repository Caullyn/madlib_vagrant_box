# madlib_vagrant_box

This is a simple installation of MADlib installed in PostgreSQL on a vagrant box. You can bring it up and start playing with all of the cool data science functions MADlib has to offer.

    git clone <repo_name>
    cd madlib_vagrant_box
    vagrant up
    vagrant ssh
    sudo su - postgres
    psql 
    CREATE DATABASE mad_ex;
    \c mad_ex

    CREATE EXTENSION plpythonu;
    CREATE EXTENSION madlib;

    CREATE TABLE arima_beer (time_id integer NOT NULL, value double precision NOT NULL );
    
    COPY arima_beer (time_id, value) FROM stdin WITH DELIMITER '|';
    1  | 93.2
    2  | 96.0
    3  | 95.2
    4  | 77.0
    5  | 70.9
    6  | 64.7
    7  | 70.0
    8  | 77.2
    9  | 79.5
    10 | 100.5
    11 | 100.7
    12 | 107.0
    13 | 95.9
    14 | 82.7
    15 | 83.2
    16 | 80.0
    17 | 80.4
    18 | 67.5
    19 | 75.7
    20 | 71.0
    21 | 89.2
    22 | 101.0
    23 | 105.2
    24 | 114.0
    25 | 96.2
    26 | 84.4
    27 | 91.2
    28 | 81.9
    29 | 80.5
    30 | 70.4
    31 | 74.7
    32 | 75.9
    33 | 86.2
    34 | 98.7
    35 | 100.9
    36 | 113.7
    37 | 89.7
    38 | 84.4
    39 | 87.2
    40 | 85.5
    \.
    
    select arima_train( 'arima_beer',
                            'arima_beer_output',
                            'time_id',
                            'value',
                            NULL,
                            FALSE,
                            ARRAY[1, 1, 1]
                          );
    
    SELECT madlib.arima_forecast( 'arima_beer_output',
                                  'arima_beer_forecast_output',
                                  10
                                );
    
    SELECT * FROM arima_beer_forecast_output;


