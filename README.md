# 025deg_jra55_iaf
Standard configuration for 0.25 degree [ACCESS-OM2](https://github.com/COSIMA/access-om2) experiment (ACCESS-OM2-025) with JRA55-do interannual forcing (IAF).

# Changes to accomodate WMT framework:
- replace .exe in config.yaml with new .exe files from [ryan/master-updated](https://github.com/rmholmes/MOM5/tree/ryan/master-updated) (only mom, not yatm or cice)
```
exe: /short/public/access-om2/bin/yatm_b6caeab.exe
exe: /short/e14/mv7494/access-om2/bin/fms_ACCESS-OM_1c1f23e_libaccessom2_b6caeab.x
exe: /short/public/access-om2/bin/cice_auscom_1440x1080_480p_47650cc_libaccessom2_b6caeab.exe
```
- update ocean/diag_table with WMT diagnostics
- update ocean/input.nml to include
```
&ocean_density_nml
     neutral_density_theta = .true.
     neutral_density_potrho = .false.
     nrho_face_bin = .true.
     potrho_min=1028.0
     potrho_max=1038.0
     layer_nk=74
     neutralrho_min=34.0
     neutralrho_max=-3.0
     eos_linear=.false.
     eos_preteos10=.true.
```