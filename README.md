# madlib_vagrant_box
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
