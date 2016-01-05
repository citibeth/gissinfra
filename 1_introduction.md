#Introduction

##Purpose
Discuss tools and software that could help our work at GISS.
   - We have **common problems** but not yet **common solutions**
   - Needs not unique to GISS, but shared with:
       - Earth science community
       - Scientists in general
       - General "data science"
   - Much is available now, open source!
   - GISS community effort required to be useful.
       - Choose best-of-breed packages for specific needs.
       - Demonstrate how they can be used at GISS.
       - Develop some GISS-specific components.
       - Share knowledge, hand-holding for others at GISS.

## Software Trends since 1990's
* Open Source, Larger Communities
   - More available software, higher quality.
   - Finding the *right* software is harder.
   - Integration skills as valuable as programming.
   - Growing dependency management problem.
* Bigger, Faster Computers
   - Python practical for many problems.
   - Datasets bigger than ever.
   - Software bigger than ever (with more dependencies).
* Centralization of large-scale computing
   - Deal with remote supercomputers.
   - More available resources for large-scale analysis.
* Climate Modeling Explosion
   - No longer a cottage industry
   - Increasingly sophisticated Earth Systems:
      - Radiation
      - Atmosphere
      - Ocean
      - Aerosols and Chemistry
      - Carbon Cycle
      - Plants
      - Ice Sheets
      - ...
* Larger, more complex code
  - More interfaces
  - More languages
  - More "glue"
  - More programmers
  - More users with varied needs
    - More flexibility required
    

###Example: ModelE
* Year 2000:
   - 33,000 Lines of Code
   - Single language (Fortran)
   - No dependencies
* Year 2004: MPI Introduced
   - 131,285 Lines of Code
   - Single Language (Fortran)
   - One Dependency
     - MPI: C required
* Year 2009: C Introduced
   - 343,000 Lines of Code
   - Two Languages:
     - Fortran + C
* Year 2010: New I/O Introduced
   - 390,000 Lines of Code
   - Two Languages (Fortran)
   - Two Dependencies
     - NetCDF, MPI: C required
* Year 2015: NetCDF4
   - 415,000 Lines of Code
   - Two Languages (Fortran + C)
   - Multiple Depenencies:
     - MPI, zlib, Szip, HDF5, netCDF, netCDF-Fortran
     - NetCDF evolved...
* The Future: Here Come the Models!
   - Link with models, don't build your own:
     - Ice, Carbon, Plants
     - ESMF Too!
   - Multiple Languages (Fortran, C, C++, ??)
   - More stuff needed for analysis (Python, R, etc)
   - Dozens of Dependencies

## Lessons from the Trends
 * We can build off others' work to improve our efficiency
  - Just have to user their stuff!
 * Integration is as important as programming from scratch
   - Finding/assembling software is a valuable skill!
 * Dependency management and software builds must be solved
    - Avoiding dependencies will no longer work
