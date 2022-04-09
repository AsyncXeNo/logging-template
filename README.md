# Description
Colored logging in python. Just put this folder in your project and import the get_logger function from custom_logging.py.

# Customization
To add a new logger, go to logging.conf and do the following
1. Add **file_handler_loggername** under handlers, replacing **loggername** with any name you like.
```
[handlers]
keys=file_handler_root,file_handler_new_logger
```
2. Create a new heading like \[logger_loggername].
3. Under the new heading, define the **level**, **handlers**, **qualname** and **propogate** options like shown below
```
[logger_new_logger]
level=DEBUG
handlers=file_new_logger
qualname=new_logger
propagate=1
```
4. Create another new heading called \[handler_file_handler_new_logger], replacing **new_logger** with your logger's name.
5. Under the new heading define the following stuff
```
[handler_file_handler_new_logger]
class=FileHandler
level=DEBUG
formatter=complex_formatter
args=('logs/new_logger.log', 'w+')
```
6. You're good to go

# Requirements
1. Python