# nemo-gof

A Gulf of Finland (GoF) configuration for the NEMO ocean model.

## Background

This setup has 0.25 NM (nautical mile) or approximately 500 m horizontal resolution.

The version in this repository is a development version of the configuration that uses NEMO 4.
There are bound to be bugs and suboptimal settings. Any settings may change without prior warning.

Sevaral papers that use this configuration have been published. Those papers use earlier versions
of the configuration and mainly NEMO 3.6. Notable changes have taken place both in the settings and
inputs. Please take this into consideration when using this setup.

Some basic validation of this setup has been performed, but this setup has not yet been as thoroughly validated as previous versions.

## Getting started

The EXP00 directory has a small one day test run of the configuration.
The test run uses FMI HIRLAM atmospheric forcing and Copernicus CMEMS boundary condition.
To run, you'll need to compile NEMO 4 with seaice and NetCDF 4. You can use the SPITZ12
setup as a starting point.

Your makenemo line may look something like:
```
./makenemo -r SPITZ12 -n NEMOGOF -m yourarch add_key key_netcdf4
```

and cpp file:
```
 bld::tool::fppkeys key_mpp_mpi key_iomput key_si3 key_netcdf4
```

The NEMO version used here is the release-4.0 branch. There are no source code changes.
Repository revision 11342 has been tested.

## Authors and acknowledgements

This configuration is based on the original work by Roman Vankevich, see Vankevich et al. (2016).

Since then, it has been further developed at the Finnish Meteorological Institute (FMI) by
Antti Westerlund. See Westerlund et al. (2018, 2019) and Westerlund (2018).

If you refer to this configuration in your work, please cite at least Vankevich et al. (2016)
and Westerlund et al. (2019).

A number of other people have contributed to this work, see these papers for more information.

## Contact and contributing

This repository is maintained by Antti Westerlund.

E-mail: antti.westerlund (at) fmi.fi, twitter: [@AnttiWesterlund](https://twitter.com/AnttiWesterlund).

Contributions and improvements are most welcome. If you wish to use this configuration for your work,
please consider contacting us to discuss possible collaborations.

## Licenses and permissions

The NEMO model is licensed under the CECILL licence, so all files originating from there use that licence.

Any new files and changes specific to this configuration are licenced under the MIT License in addition
to the CECILL licence.

This study has been conducted using E.U. Copernicus Marine Service Information. See http://marine.copernicus.eu/.
The bathymetric data was obtained from the
Finnish Inventory Programme for the Underwater Marine Environment (VELMU) depth model
(Finnish Environment Institute, http://www.syke.fi/en-US/Open_information/Spatial_datasets) and the
Baltic Sea Bathymetry Database (Baltic Sea Hydrographic Commission, 2013) version 0.9.3,
downloaded from http://data.bshc.pro on 25 Aug 2014. VELMU data is licensed under the
Creative Commons BY 4.0 licence and Baltic Sea Bathymetry Database (BSBD) data is
licensed under the Creative Commons BY 3.0 licence.

FMI HIRLAM data is licensed under the CC BY 4.0 licence, see https://en.ilmatieteenlaitos.fi/open-data.

## References

Vankevich, R. E., Sofina, E. V., Eremina, T. E., Ryabchenko, V. A., Molchanov, M. S., Isaev, A. V. (2016).
Effects of lateral processes on the seasonal water stratification of the Gulf of Finland: 3-D NEMO-based model study.
Ocean Science 12 (4), 987–1001.
http://dx.doi.org/10.5194/os-12-987-2016

Westerlund A., Tuomi L., Alenius P., Miettunen E., Vankevich R. E. (2018).
Attributing mean circulation patterns to physical phenomena in the Gulf of Finland.
Oceanologia, 60 (1):16–31.
https://doi.org/10.1016/j.oceano.2017.05.003

Westerlund A. (2018).
Modelling Circulation Dynamics in the Northern Baltic Sea,
PhD thesis,
University of Helsinki.
http://urn.fi/URN:ISBN:978-952-336-055-6

Westerlund A., Tuomi L., Alenius P., Myrberg K., Miettunen E., Vankevich R. E., Hordoir R. (2019).
Circulation patterns in the Gulf of Finland from daily to seasonal timescales,
Tellus A: Dynamic Meteorology and Oceanography.
https://doi.org/10.1080/16000870.2019.1627149


