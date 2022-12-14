# proCAST

Streamlit project forked for debugging purposes.

## Issues

Currently this streamlit application does not run properly when using the `archive` subpage.
It neither runs on streamlit cloud nor in the standard `python:3.9-slim` local docker container.

The problem is probably around the `eccodes` library:

```log
Warning: ecCodes 2.21.0 or higher is recommended. You are running version 2.20.0
```

The required version or later is not available within the `debian/bullseye/stable` repository.
The `eccodes` library is used by the `cfgrib` library, which is used by the `xarray` library.

It only runs on the local docker container with a custom `westonsteimel/python:3.9-slim-bookworm` image.
Still the application throws a lot of errors when loading the files from the `data` folder in `HDF5` format.

Perhaps these problems can be solved by using a different and more common file format for the data files.
