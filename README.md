# satpy-viirs-l2
Viirs L2 Enhancements and colormap plugin for Satpy. This should allow for replication of NASA Worldview layers.
Example usage of these features is shown in the provided notebook. For more extensive documentation visit https://satpy.readthedocs.io/en/latest/reading.html#adding-a-reader-to-satpy

## Reader Python Code
All of the readers in this project use the reader python code at satpy_viirs_l2.VIIRSL2FileHandler at `satpy_viirs_l2/viirs_l2.py`, which makes some basic assumptions about the properties available.\
1. All input files are in netcdf format
2. Files have a start_time and end_time available via the file name or in at attribute
3. Files have orbit number, platform, and sensor attributes
4. Files conform with underlying assumptions made in https://satpy.readthedocs.io/en/latest/api/satpy.readers.netcdf_utils.html#satpy.readers.netcdf_utils.NetCDF4FileHandler

If these assumptions are not met you can either look at the list of satpy readers available in the main project, modify the existing reader in this project, or create your own and put it in the same folder.\n

## Reader YAML Files
All customer readers configs are stored in `/satpy_viirs_l2/etc/readers/`.\
All of these follow a consistent format with sections for metadata, file_types, and datasets. The satpy documentation is fairly complete on this and the existing files should be good examples.
