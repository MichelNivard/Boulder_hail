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


we need to upload the whole resources subfolder from the boulder workshop hail folder, it might take a while.

Alternatively you can save the folder to google drive, and access your google drive directly from colab with this button:

[![image](https://github.com/MichelNivard/Boulder_hail/assets/11858442/0cde157c-4cd1-4103-8d1d-fcabcbac613a)


Then the fiels will be under drive/MyDrive/ressources/bla.mt so you will need to adjust any paths from:

```
mt = hl.read_matrix_table('resources/hgdp-tgp-rare-variants.mt')
mt = hl.variant_qc(mt)
call_rate_cdf = mt.aggregate_rows(hl.agg.approx_cdf(mt.variant_qc.call_rate))
call_rate_cdf
```

to something like this, the exact path depends on where you save each file:


```
mt = hl.read_matrix_table('drive/myDrive/resources/hgdp-tgp-rare-variants.mt')
mt = hl.variant_qc(mt)
call_rate_cdf = mt.aggregate_rows(hl.agg.approx_cdf(mt.variant_qc.call_rate))
call_rate_cdf
```
