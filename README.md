# Description
Colored logging in python. Just put this folder in your project and import the get_logger function from custom_logging.py.

# Customization
To add a new logger, go to logging.conf and do the following
1. Add the name of the new logger under the \[loggers] heading in **keys**.
2. Add **file_handler_loggername** under handlers, replacing **loggername** with any name you like.
```
[handlers]
keys=file_handler_root,file_handler_new_logger
```
3. Create a new heading like \[logger_loggername].
4. Under the new heading, define the **level**, **handlers**, **qualname** and **propogate** options like shown below
```
[logger_new_logger]
level=DEBUG
handlers=file_new_logger
qualname=new_logger
propagate=1
```
5. Create another new heading called \[handler_file_handler_new_logger], replacing **new_logger** with your logger's name.
6. Under the new heading define the following stuff
```
[handler_file_handler_new_logger]
class=FileHandler
level=DEBUG
formatter=complex_formatter
args=('logs/new_logger.log', 'w+')
```
7. You're good to go

# Requirements
1. Python