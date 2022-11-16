Introduction
=========


Diarization error rate consists of ``speaker error``, ``false alarm speech``, and ``missed speech``, which may occur in overlapped parts. Sometimes, we want to evaluate the algorithm's ability to handle overlapped speeches, especially for diarization with ``OSD``(Overlapped speech detection), e.g., ``EEND`` and multi-modal diarization.

In this repo, we modified ``dscore`` to report errors in overlapped speech detection. Besides, we also make ``dscore`` to report detailed information, including ``speaker error``, ``false alarm speech``, and ``missed speech``.


Other unmentioned ilustrations can be found on the official repo [here](https://github.com/nryant/dscore).

**Usages**:
```
python score.py -r ref_rttm -s sys_rttm --collar 0.25 or 0
```

* ``ref_rttm`` --- the reference rttm from the ground truth
* ``sys_rttm`` --- the system or hypothesis rttm from the models' prediction

**Results**:
```
collar    MS        FA         SC        OVL       DER        JER
------  ------  ----------  --------  --------  ---------  ---------
(value) (value)   (value)    (value)   (value)   (value)    (value)
```

* ``MS``: missed speech
* ``FA``: false alarm speech
* ``SC``: speaker confusion or speaker error
* ``OVL``: errors in overlapped speech part
* ``DER``: Diarization error rate, the sum of ``MS``, ``FA`` and ``SC``
* ``JER``: Jaccard error rate

**Notes:** Other features may be affected and are not fullly tested.

References
=========
- https://github.com/nryant/dscore