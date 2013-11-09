Some notes on Django Logging
----------------------------

I find next Django logging points difficult to grasp through documentation: 

* You should define a new logger with the name of your project or app. Later you can discriminate by module defininig new specific loggers by my advice is define always a top level logger
* To get the logging message you have to set a level >= the level of the logger. For instance if you defined your logger level to INFO, logger.debug() messages will NOT be send to it
