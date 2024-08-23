Below given code is for creating custom logger for project.

Step : Go to project source code directory > logger folder >  "\__init__.py" and then copy and paste below code. Custom logging message and logs folder & file structure can be modified as required . 

```python
import os
import logging
from datetime import datetime

filename=f"{datetime.now().strftime('%d_%m_%Y_%H_%M_%S')}.log"

logs_path=os.path.join(os.getcwd(),"logs")
os.makedirs(logs_path,exist_ok=True)

log_file_path=os.path.join(logs_path,filename)

logging.basicConfig(
    filename=log_file_path,
    level=logging.INFO,
    format="[%(asctime)s] | module : %(name)s | %(levelname)s , log line number %(lineno)s - %(message)s"
)


```