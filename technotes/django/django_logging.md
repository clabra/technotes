Some notes on Django logging
----------------------------

I find next Django logging points difficult to grasp through documentation: 

* You should define a new logger with the name of your project or app. Later you can discriminate by module defininig new specific loggers (see propagate parameter) by my advice is define always a top level logger

With this configuration in settings.py: 

```
'loggers': {
    'django': {
        'handlers': ['stream_to_console', 'file'],
        'propagate': True,
        'level': 'DEBUG', 
    }
...
}
```

Messages sent to:  

logger = logging.getLogger('django.db.backends')

go to 'django' logger. If then you define a 'django.db.backends' and set propagate=False, these messages won't appear on 'django' loggins anymore 


* To get the logging message you have to set a level >= the level of the logger. For instance if you defined your logger level to INFO, logger.debug() messages will NOT be send to it

So, with this configuration: 

```
'django': {
    'handlers': ['stream_to_console', 'file'],
    'propagate': True,
    'level': 'DEBUG', 
},
'django.request': {
    'handlers': ['mail_admins', 'stream_to_console', 'file'],
    'level': 'ERROR',
    'propagate': False,
},
```

You can send 'ERROR' logs by mail and less critical logs to console and file
