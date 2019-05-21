The results in the file `skyserver_results.fits`
correspond to the query

```
-- This query does a table JOIN between the imaging (PhotoObj) and spectra
-- (SpecObj) tables and includes the necessary columns in the SELECT to upload
-- the results to the SAS (Science Archive Server) for FITS file retrieval.
SELECT 
   p.objid,p.ra,p.dec,p.u,p.g,p.r,p.i,p.z,
   s.class, s.z as redshift
FROM PhotoObj AS p
   JOIN SpecObj AS s ON s.bestobjid = p.objid
WHERE 
   p.r BETWEEN 0 AND 17.0
   AND s.class = "GALAXY"

```

on Data Release 15.