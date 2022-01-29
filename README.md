# Rosetta_ddG_monomer
## 1. Pre-minimisation
### Input file: 1pga.pdb 
/path/to/minimize_with_cst.static.linuxgccrelease -in:file:s 1pga.pdb -in:file:fullatom -ignore_unrecognized_res -fa_max_dis 9.0 -database /path/to/rosetta/main/database/ -ddg::harmonic_ca_tether 0.5 -ddg::constraint_weight 1.0 -ddg::out_pdb_prefix min_cst_0.5 -ddg::sc_min_only false > mincst1pga.log
### Output file: min_cst_0.5.1pga_0001.pdb | mincst1pga.log
