# Rosetta_ddG_monomer High Resolution Protocol
## 1. Pre-minimisation
### Input file: 1pga.pdb 
*/path/to/minimize_with_cst.static.linuxgccrelease -in:file:s 1pga.pdb -in:file:fullatom -ignore_unrecognized_res -fa_max_dis 9.0 -database /path/to/rosetta/main/database/ -ddg::harmonic_ca_tether 0.5 -ddg::constraint_weight 1.0 -ddg::out_pdb_prefix min_cst_0.5 -ddg::sc_min_only false > mincst1pga.log*
### Output file: min_cst_0.5.1pga_0001.pdb | mincst1pga.log

## 2. Constraint file: 
### Input file: mincst1pga.log
#### Open to /Rosetta/main/source/src/apps/public/ddg/convert_to_cst_file.sh
#### change 
grep ^c-alpha $1 | awk '{print "AtomPair CA "$6" CA "$8" HARMONIC "$10" "$13}' to 	grep ^apps.public.ddg.minimize_with_cst: $1 | awk '{print "AtomPair CA "$7" CA "$9" HARMONIC "$11" "$14}'
