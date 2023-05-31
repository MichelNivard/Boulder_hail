# Boulder_hail
These are the boulder hail practicals, with a "Open in colab" link. click the notebooks above, click "Open in Colab".


you will need to make some (MINIMAL!) adjust emts. first uyou need to install hail, this is done by addin a code cell, or additin to the first code cell, where you also find the code:

```
import os
os.environ['PYSPARK_SUBMIT_ARGS'] = '--driver-memory 6G pyspark-shell'

import hail as hl
hl.init()
```

Adjust this to:

```
import os
os.environ['PYSPARK_SUBMIT_ARGS'] = '--driver-memory 6G pyspark-shell'

pip install hail

import hail as hl
hl.init()
```

Okay thats one big adjustment done! this is required in each and every notebook, sorry!

So now we need to upload files to google colab, this is a screenshot of where the upload button is:

[![image](https://github.com/MichelNivard/Boulder_hail/assets/11858442/fecbced1-844a-4c7d-985a-b1b00796c135)
