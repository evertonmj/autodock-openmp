cmake_minimum_required(VERSION 3.3)
project(autodock_openmp)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES
    autodock/autom4te.cache/output.0
    autodock/autom4te.cache/output.1
    autodock/autom4te.cache/requests
    autodock/autom4te.cache/traces.0
    autodock/autom4te.cache/traces.1
    autodock/EXAMPLES/1dwd/1dwd_rec_maps/1dwd_rec.A.map
    autodock/EXAMPLES/1dwd/1dwd_rec_maps/1dwd_rec.C.map
    autodock/EXAMPLES/1dwd/1dwd_rec_maps/1dwd_rec.d.map
    autodock/EXAMPLES/1dwd/1dwd_rec_maps/1dwd_rec.e.map
    autodock/EXAMPLES/1dwd/1dwd_rec_maps/1dwd_rec.HD.map
    autodock/EXAMPLES/1dwd/1dwd_rec_maps/1dwd_rec.maps.fld
    autodock/EXAMPLES/1dwd/1dwd_rec_maps/1dwd_rec.maps.xyz
    autodock/EXAMPLES/1dwd/1dwd_rec_maps/1dwd_rec.N.map
    autodock/EXAMPLES/1dwd/1dwd_rec_maps/1dwd_rec.OA.map
    autodock/EXAMPLES/1dwd/1dwd_rec_maps/1dwd_rec.S.map
    autodock/EXAMPLES/1dwd/1dwd_rigid_maps/1dwd_rigid.A.map
    autodock/EXAMPLES/1dwd/1dwd_rigid_maps/1dwd_rigid.C.map
    autodock/EXAMPLES/1dwd/1dwd_rigid_maps/1dwd_rigid.d.map
    autodock/EXAMPLES/1dwd/1dwd_rigid_maps/1dwd_rigid.e.map
    autodock/EXAMPLES/1dwd/1dwd_rigid_maps/1dwd_rigid.HD.map
    autodock/EXAMPLES/1dwd/1dwd_rigid_maps/1dwd_rigid.maps.fld
    autodock/EXAMPLES/1dwd/1dwd_rigid_maps/1dwd_rigid.maps.xyz
    autodock/EXAMPLES/1dwd/1dwd_rigid_maps/1dwd_rigid.N.map
    autodock/EXAMPLES/1dwd/1dwd_rigid_maps/1dwd_rigid.NA.map
    autodock/EXAMPLES/1dwd/1dwd_rigid_maps/1dwd_rigid.OA.map
    autodock/EXAMPLES/1dwd/1dwd_rigid_maps/1dwd_rigid.S.map
    autodock/EXAMPLES/1dwd/dock_flexlig/1dwd_1dwd.dlg
    autodock/EXAMPLES/1dwd/dock_flexlig/1dwd_1dwd.dpf
    autodock/EXAMPLES/1dwd/dock_flexlig/1dwd_1dwd.gpf
    autodock/EXAMPLES/1dwd/dock_flexlig/1dwd_1dwd_long.dpf
    autodock/EXAMPLES/1dwd/dock_flexlig/1dwd_best.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig/1dwd_lig.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig/1dwd_rec.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig/run_examples
    autodock/EXAMPLES/1dwd/dock_flexlig_25M/1dwd_1dwd.dlg
    autodock/EXAMPLES/1dwd/dock_flexlig_25M/1dwd_1dwd.dpf
    autodock/EXAMPLES/1dwd/dock_flexlig_25M/1dwd_1dwd.gpf
    autodock/EXAMPLES/1dwd/dock_flexlig_25M/1dwd_1dwd_long.dpf
    autodock/EXAMPLES/1dwd/dock_flexlig_25M/1dwd_best.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig_25M/1dwd_lig.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig_25M/1dwd_rec.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig_25M/run_examples
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres/1dwd_flex.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres/1dwd_lig.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres/1dwd_lig_1dwd_flexres_1dwd_rigid.dlg
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres/1dwd_lig_1dwd_flexres_1dwd_rigid.dpf
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres/1dwd_lig_1dwd_flexres_1dwd_rigid_long.dpf
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres/1dwd_rec.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres/1dwd_rigid.gpf
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres/1dwd_rigid.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres/make_rigid_maps
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres/run_examples
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres_25M/1dwd_flex.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres_25M/1dwd_lig.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres_25M/1dwd_lig_1dwd_flexres_1dwd_rigid.dpf
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres_25M/1dwd_lig_1dwd_flexres_1dwd_rigid_long.dpf
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres_25M/1dwd_lig_1dwd_flexres_25M.dlg
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres_25M/1dwd_rec.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres_25M/1dwd_rigid.gpf
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres_25M/1dwd_rigid.pdbqt
    autodock/EXAMPLES/1dwd/dock_flexlig_flexres_25M/run_examples
    autodock/EXAMPLES/1dwd/dock_rigidlig/1dwd_0.pdbqt
    autodock/EXAMPLES/1dwd/dock_rigidlig/1dwd_1dwd.dpf
    autodock/EXAMPLES/1dwd/dock_rigidlig/1dwd_1dwd.gpf
    autodock/EXAMPLES/1dwd/dock_rigidlig/1dwd_1dwd_long.dpf
    autodock/EXAMPLES/1dwd/dock_rigidlig/1dwd_rec.pdbqt
    autodock/EXAMPLES/1dwd/dock_rigidlig/1dwd_rigidlig.dlg
    autodock/EXAMPLES/1dwd/dock_rigidlig/make_rec_maps
    autodock/EXAMPLES/1dwd/dock_rigidlig/run_examples
    autodock/EXAMPLES/1dwd/dock_rigidlig_25M/1dwd_0.pdbqt
    autodock/EXAMPLES/1dwd/dock_rigidlig_25M/1dwd_1dwd.dpf
    autodock/EXAMPLES/1dwd/dock_rigidlig_25M/1dwd_1dwd.gpf
    autodock/EXAMPLES/1dwd/dock_rigidlig_25M/1dwd_1dwd_long.dpf
    autodock/EXAMPLES/1dwd/dock_rigidlig_25M/1dwd_rec.pdbqt
    autodock/EXAMPLES/1dwd/dock_rigidlig_25M/1dwd_rigid_25M.dlg
    autodock/EXAMPLES/1dwd/dock_rigidlig_25M/run_examples
    autodock/EXAMPLES/1dwd/eval_lig/1dwd_1dwd.gpf
    autodock/EXAMPLES/1dwd/eval_lig/1dwd_epdb.dlg
    autodock/EXAMPLES/1dwd/eval_lig/1dwd_epdb.dpf
    autodock/EXAMPLES/1dwd/eval_lig/1dwd_epdb_best.dlg
    autodock/EXAMPLES/1dwd/eval_lig/1dwd_epdb_best.dpf
    autodock/EXAMPLES/1dwd/eval_lig/1dwd_lig.pdbqt
    autodock/EXAMPLES/1dwd/eval_lig/1dwd_rec.pdbqt
    autodock/EXAMPLES/1dwd/eval_lig/best.pdbqt
    autodock/EXAMPLES/1dwd/eval_lig/run_examples
    autodock/EXAMPLES/1dwd/local_search_lig/1dwd_1dwd.gpf
    autodock/EXAMPLES/1dwd/local_search_lig/1dwd_lig.pdbqt
    autodock/EXAMPLES/1dwd/local_search_lig/1dwd_local_only.dlg
    autodock/EXAMPLES/1dwd/local_search_lig/1dwd_local_only.dpf
    autodock/EXAMPLES/1dwd/local_search_lig/1dwd_local_only_best.dlg
    autodock/EXAMPLES/1dwd/local_search_lig/1dwd_local_only_best.dpf
    autodock/EXAMPLES/1dwd/local_search_lig/1dwd_local_only_best_long.dpf
    autodock/EXAMPLES/1dwd/local_search_lig/1dwd_local_only_long.dpf
    autodock/EXAMPLES/1dwd/local_search_lig/1dwd_rec.pdbqt
    autodock/EXAMPLES/1dwd/local_search_lig/best.pdbqt
    autodock/EXAMPLES/1dwd/local_search_lig/run_examples
    autodock/EXAMPLES/1dwd/recluster/1dwd_1dwd_1.dlg
    autodock/EXAMPLES/1dwd/recluster/1dwd_1dwd_2.dlg
    autodock/EXAMPLES/1dwd/recluster/1dwd_1dwd_3.dlg
    autodock/EXAMPLES/1dwd/recluster/1dwd_1dwd_4.dlg
    autodock/EXAMPLES/1dwd/recluster/1dwd_lig_xray.pdbqt
    autodock/EXAMPLES/1dwd/recluster/ligand.pdbqt
    autodock/EXAMPLES/1dwd/recluster/recluster.dlg
    autodock/EXAMPLES/1dwd/recluster/recluster.dpf
    autodock/EXAMPLES/1dwd/recluster/run_examples
    autodock/EXAMPLES/1dwd/simulated_annealing/1dwd_lig.pdbqt
    autodock/EXAMPLES/1dwd/simulated_annealing/1dwd_simulated_annealing.dpf
    autodock/EXAMPLES/1dwd/simulated_annealing/1dwd_simulated_annealing_long.dpf
    autodock/EXAMPLES/1dwd/simulated_annealing/best.pdbqt
    autodock/EXAMPLES/1dwd/simulated_annealing/run_examples
    autodock/EXAMPLES/1dwd/mkdist
    autodock/EXAMPLES/1dwd/run_all_examples
    autodock/EXAMPLES/1dwd/run_examples
    autodock/EXAMPLES/4hvp/4hvp_rec_maps/4hvp_rec.C.map
    autodock/EXAMPLES/4hvp/4hvp_rec_maps/4hvp_rec.d.map
    autodock/EXAMPLES/4hvp/4hvp_rec_maps/4hvp_rec.e.map
    autodock/EXAMPLES/4hvp/4hvp_rec_maps/4hvp_rec.HD.map
    autodock/EXAMPLES/4hvp/4hvp_rec_maps/4hvp_rec.maps.fld
    autodock/EXAMPLES/4hvp/4hvp_rec_maps/4hvp_rec.maps.xyz
    autodock/EXAMPLES/4hvp/4hvp_rec_maps/4hvp_rec.N.map
    autodock/EXAMPLES/4hvp/4hvp_rec_maps/4hvp_rec.OA.map
    autodock/EXAMPLES/4hvp/4hvp_rigid_maps/4hvp_rigid.C.map
    autodock/EXAMPLES/4hvp/4hvp_rigid_maps/4hvp_rigid.d.map
    autodock/EXAMPLES/4hvp/4hvp_rigid_maps/4hvp_rigid.e.map
    autodock/EXAMPLES/4hvp/4hvp_rigid_maps/4hvp_rigid.HD.map
    autodock/EXAMPLES/4hvp/4hvp_rigid_maps/4hvp_rigid.maps.fld
    autodock/EXAMPLES/4hvp/4hvp_rigid_maps/4hvp_rigid.maps.xyz
    autodock/EXAMPLES/4hvp/4hvp_rigid_maps/4hvp_rigid.N.map
    autodock/EXAMPLES/4hvp/4hvp_rigid_maps/4hvp_rigid.OA.map
    autodock/EXAMPLES/4hvp/dock_flexlig/4hvp_4hvp.dlg
    autodock/EXAMPLES/4hvp/dock_flexlig/4hvp_4hvp.dpf
    autodock/EXAMPLES/4hvp/dock_flexlig/4hvp_4hvp.gpf
    autodock/EXAMPLES/4hvp/dock_flexlig/4hvp_lig.pdbqt
    autodock/EXAMPLES/4hvp/dock_flexlig/4hvp_rec.pdbqt
    autodock/EXAMPLES/4hvp/dock_flexlig_25M/4hvp_4hvp.dpf
    autodock/EXAMPLES/4hvp/dock_flexlig_25M/4hvp_4hvp.glg
    autodock/EXAMPLES/4hvp/dock_flexlig_25M/4hvp_4hvp.gpf
    autodock/EXAMPLES/4hvp/dock_flexlig_25M/4hvp_4hvp_25M.dlg
    autodock/EXAMPLES/4hvp/dock_flexlig_25M/4hvp_lig.pdbqt
    autodock/EXAMPLES/4hvp/dock_flexlig_25M/4hvp_rec.pdbqt
    autodock/EXAMPLES/4hvp/dock_flexlig_flexres/4hvp_flex.pdbqt
    autodock/EXAMPLES/4hvp/dock_flexlig_flexres/4hvp_lig.pdbqt
    autodock/EXAMPLES/4hvp/dock_flexlig_flexres/4hvp_lig_flexres_rigid.dlg
    autodock/EXAMPLES/4hvp/dock_flexlig_flexres/4hvp_lig_flexres_rigid.dpf
    autodock/EXAMPLES/4hvp/dock_flexlig_flexres/4hvp_rigid.glg
    autodock/EXAMPLES/4hvp/dock_flexlig_flexres/4hvp_rigid.gpf
    autodock/EXAMPLES/4hvp/dock_flexlig_flexres/4hvp_rigid.pdbqt
    autodock/EXAMPLES/4hvp/dock_flexlig_flexres_25M/4hvp_flex.pdbqt
    autodock/EXAMPLES/4hvp/dock_flexlig_flexres_25M/4hvp_lig.pdbqt
    autodock/EXAMPLES/4hvp/dock_flexlig_flexres_25M/4hvp_lig_flexres_rigid.dlg
    autodock/EXAMPLES/4hvp/dock_flexlig_flexres_25M/4hvp_lig_flexres_rigid.dpf
    autodock/EXAMPLES/4hvp/dock_flexlig_flexres_25M/4hvp_rigid.gpf
    autodock/EXAMPLES/4hvp/dock_flexlig_flexres_25M/4hvp_rigid.pdbqt
    autodock/EXAMPLES/4hvp/dock_rigidlig/4hvp0_4hvp.dlg
    autodock/EXAMPLES/4hvp/dock_rigidlig/4hvp0_4hvp.dpf
    autodock/EXAMPLES/4hvp/dock_rigidlig/4hvp_0.pdbqt
    autodock/EXAMPLES/4hvp/dock_rigidlig/4hvp_4hvp.glg
    autodock/EXAMPLES/4hvp/dock_rigidlig/4hvp_4hvp.gpf
    autodock/EXAMPLES/4hvp/dock_rigidlig/4hvp_rec.pdbqt
    autodock/EXAMPLES/4hvp/dock_rigidlig_25M/4hvp0_4hvp.dlg
    autodock/EXAMPLES/4hvp/dock_rigidlig_25M/4hvp0_4hvp.dpf
    autodock/EXAMPLES/4hvp/dock_rigidlig_25M/4hvp_0.pdbqt
    autodock/EXAMPLES/4hvp/dock_rigidlig_25M/4hvp_4hvp.gpf
    autodock/EXAMPLES/4hvp/dock_rigidlig_25M/4hvp_rec.pdbqt
    autodock/EXAMPLES/4hvp/eval_lig/4hvp_4hvp.gpf
    autodock/EXAMPLES/4hvp/eval_lig/4hvp_best.pdbqt
    autodock/EXAMPLES/4hvp/eval_lig/4hvp_best_epdb.dlg
    autodock/EXAMPLES/4hvp/eval_lig/4hvp_best_epdb.dpf
    autodock/EXAMPLES/4hvp/eval_lig/4hvp_epdb.dlg
    autodock/EXAMPLES/4hvp/eval_lig/4hvp_epdb.dpf
    autodock/EXAMPLES/4hvp/eval_lig/4hvp_lig.pdbqt
    autodock/EXAMPLES/4hvp/eval_lig/4hvp_rec.pdbqt
    autodock/EXAMPLES/4hvp/local_search_lig/4hvp_4hvp.gpf
    autodock/EXAMPLES/4hvp/local_search_lig/4hvp_best.pdbqt
    autodock/EXAMPLES/4hvp/local_search_lig/4hvp_best_local_only.dlg
    autodock/EXAMPLES/4hvp/local_search_lig/4hvp_best_local_only.dpf
    autodock/EXAMPLES/4hvp/local_search_lig/4hvp_lig.pdbqt
    autodock/EXAMPLES/4hvp/local_search_lig/4hvp_local_only.dlg
    autodock/EXAMPLES/4hvp/local_search_lig/4hvp_local_only.dpf
    autodock/EXAMPLES/4hvp/local_search_lig/4hvp_rec.pdbqt
    autodock/Tests/1pgp.dpf
    autodock/Tests/1pgp.dpf.dpf
    autodock/Tests/1pgp.fpd
    autodock/Tests/1pgp.gpf
    autodock/Tests/1pgp_1_4_100.dpf
    autodock/Tests/1pgp_1_4_50.dpf
    autodock/Tests/1pgp_about_auto_ga_only.dpf
    autodock/Tests/1pgp_about_auto_gals.dpf
    autodock/Tests/1pgp_about_auto_local_only.dpf
    autodock/Tests/1pgp_about_auto_simanneal.dpf
    autodock/Tests/1pgp_about_only.dpf
    autodock/Tests/1pgp_epdb_etables.dpf
    autodock/Tests/1pgp_epdb_flexres_intelec.dpf
    autodock/Tests/1pgp_epdb_flexres_nointelec.dpf
    autodock/Tests/1pgp_flex.pdbqt
    autodock/Tests/1pgp_flexlig_pso_ls1_psw1.dpf
    autodock/Tests/1pgp_flexres.dpf
    autodock/Tests/1pgp_flexres_1_4_100.dpf
    autodock/Tests/1pgp_flexres_1_4_50.dpf
    autodock/Tests/1pgp_flexres_emptyligand.dpf
    autodock/Tests/1pgp_ga_only.dpf
    autodock/Tests/1pgp_ga_run_maxruns.dpf
    autodock/Tests/1pgp_ga_run_maxruns_analysis.dpf
    autodock/Tests/1pgp_ga_select_linear_ranking.dpf
    autodock/Tests/1pgp_ga_select_tournament.dpf
    autodock/Tests/1pgp_gals_10runs.dpf
    autodock/Tests/1pgp_gals_set_sw1.dpf
    autodock/Tests/1pgp_gals_use_defaults.dpf
    autodock/Tests/1pgp_illegal_keyword.dpf
    autodock/Tests/1pgp_illegal_outlev.dpf
    autodock/Tests/1pgp_illegal_symoutlev.dpf
    autodock/Tests/1pgp_intelec_off.dpf
    autodock/Tests/1pgp_intnbcoeffs.dpf
    autodock/Tests/1pgp_intnbpreps.dpf
    autodock/Tests/1pgp_intnbpreps_illegal_atom.dpf
    autodock/Tests/1pgp_intnbpreps_toofew.dpf
    autodock/Tests/1pgp_just_right_number_torsions.dpf
    autodock/Tests/1pgp_lig.pdbqt
    autodock/Tests/1pgp_lig2.pdbqt
    autodock/Tests/1pgp_lig_32tors.pdbqt
    autodock/Tests/1pgp_lig_33tors.pdbqt
    autodock/Tests/1pgp_ligand_types_map_mismatch.dpf
    autodock/Tests/1pgp_ligNOH.pdbqt
    autodock/Tests/1pgp_ligrand_ga_only.dpf
    autodock/Tests/1pgp_lsonly_10runs.dpf
    autodock/Tests/1pgp_map_truncated.dpf
    autodock/Tests/1pgp_mixed_adt_analysis.dpf
    autodock/Tests/1pgp_mixed_basic_analysis.dpf
    autodock/Tests/1pgp_mixed_maxruns.dpf
    autodock/Tests/1pgp_mixed_maxruns_adt_analysis.dpf
    autodock/Tests/1pgp_mixed_maxruns_analysis.dpf
    autodock/Tests/1pgp_mixed_maxruns_basic_analysis.dpf
    autodock/Tests/1pgp_multipleabouts.dpf
    autodock/Tests/1pgp_no_desolvmap.dpf
    autodock/Tests/1pgp_no_elec_desolv_maps.dpf
    autodock/Tests/1pgp_no_elecmap.dpf
    autodock/Tests/1pgp_no_extension
    autodock/Tests/1pgp_no_outlev.dpf
    autodock/Tests/1pgp_no_parameter_file.dpf
    autodock/Tests/1pgp_no_set_ga.dpf
    autodock/Tests/1pgp_no_set_psw1.dpf
    autodock/Tests/1pgp_numoutlev.dpf
    autodock/Tests/1pgp_outpopfil.dpf
    autodock/Tests/1pgp_overmaxruns.dpf
    autodock/Tests/1pgp_rec.C.map
    autodock/Tests/1pgp_rec.d.map
    autodock/Tests/1pgp_rec.e.map
    autodock/Tests/1pgp_rec.HD.map
    autodock/Tests/1pgp_rec.maps.fld
    autodock/Tests/1pgp_rec.maps.xyz
    autodock/Tests/1pgp_rec.OA.map
    autodock/Tests/1pgp_rec.OA.truncated.map
    autodock/Tests/1pgp_rec.P.map
    autodock/Tests/1pgp_rec.pdbqt
    autodock/Tests/1pgp_rec.SA.map
    autodock/Tests/1pgp_rigid.C.map
    autodock/Tests/1pgp_rigid.d.map
    autodock/Tests/1pgp_rigid.e.map
    autodock/Tests/1pgp_rigid.gpf
    autodock/Tests/1pgp_rigid.HD.map
    autodock/Tests/1pgp_rigid.maps.fld
    autodock/Tests/1pgp_rigid.maps.xyz
    autodock/Tests/1pgp_rigid.N.map
    autodock/Tests/1pgp_rigid.OA.map
    autodock/Tests/1pgp_rigid.P.map
    autodock/Tests/1pgp_rigid.pdbqt
    autodock/Tests/1pgp_rmsmode_all_heavy_atom_pairs_only.dpf
    autodock/Tests/1pgp_rmsmode_heavy_atoms_only_noH.dpf
    autodock/Tests/1pgp_rmsmode_unique_heavy_atom_pairs_only.dpf
    autodock/Tests/1pgp_seed01.dpf
    autodock/Tests/1pgp_seed37.dpf
    autodock/Tests/1pgp_seedinttime.dpf
    autodock/Tests/1pgp_simanneal_10runs.dpf
    autodock/Tests/1pgp_simanneal_small.dpf
    autodock/Tests/1pgp_simanneal_small_geometric_schedule.dpf
    autodock/Tests/1pgp_smaller.dpf
    autodock/Tests/1pgp_smooth0.dpf
    autodock/Tests/1pgp_symoutlev.dpf
    autodock/Tests/1pgp_timepid.dpf
    autodock/Tests/1pgp_too_many_ligand_types.dpf
    autodock/Tests/1pgp_too_many_torsions.dpf
    autodock/Tests/1pgp_two_ligands.dpf
    autodock/Tests/1pgp_two_mapsets.dpf
    autodock/Tests/1pgp_unbound_compute_unbound_extended.dpf
    autodock/Tests/1pgp_unbound_default.dpf
    autodock/Tests/1pgp_unbound_ignored.dpf
    autodock/Tests/1pgp_unbound_model_bound.dpf
    autodock/Tests/1pgp_unbound_model_compact.dpf
    autodock/Tests/1pgp_unbound_model_extended.dpf
    autodock/Tests/1pgp_unbound_model_illegal.dpf
    autodock/Tests/1pgp_unbound_model_value.dpf
    autodock/Tests/1pgp_unbound_set0.dpf
    autodock/Tests/1pgp_unbound_set10.dpf
    autodock/Tests/1pgp_unbound_set_illegal.dpf
    autodock/Tests/DlgParser.py
    autodock/Tests/empty.pdbqt
    autodock/Tests/hsg1_small.C.map
    autodock/Tests/hsg1_small.d.map
    autodock/Tests/hsg1_small.e.map
    autodock/Tests/hsg1_small.HD.map
    autodock/Tests/hsg1_small.maps.fld
    autodock/Tests/hsg1_small.maps.xyz
    autodock/Tests/hsg1_small.OA.map
    autodock/Tests/hsg1_small.P.map
    autodock/Tests/test_autodock4.py
    autodock/USERGUIDES/AutoDock4.0_UserGuide.doc
    autodock/USERGUIDES/AutoDock4.1_UserGuide.doc
    autodock/USERGUIDES/AutoDock4.2_UserGuide.doc
    autodock/USERGUIDES/AutoDock4.2_UserGuide.pdf
    autodock/USERGUIDES/README
    autodock/aclocal.m4
    autodock/AD4.1_bound.dat
    autodock/AD4.1_compact.dat
    autodock/AD4.1_extended.dat
    autodock/AD4_parameters.dat
    autodock/AD4_PARM99.dat
    autodock/alea.cc
    autodock/alea.h
    autodock/analysis.cc
    autodock/analysis.h
    autodock/atom_parameter_manager.cc
    autodock/atom_parameter_manager.h
    autodock/AUTHORS
    autodock/autocomm.h
    autodock/autodock3.1
    autodock/autodock4
    autodock/autodock4-alea.o
    autodock/autodock4-analysis.o
    autodock/autodock4-atom_parameter_manager.o
    autodock/autodock4-banner.o
    autodock/autodock4-bestpdb.o
    autodock/autodock4-calculateEnergies.o
    autodock/autodock4-call_glss.o
    autodock/autodock4-call_ls.o
    autodock/autodock4-center_ligand.o
    autodock/autodock4-changeState.o
    autodock/autodock4-check_header_float.o
    autodock/autodock4-check_header_int.o
    autodock/autodock4-check_header_line.o
    autodock/autodock4-clmode.o
    autodock/autodock4-cluster_analysis.o
    autodock/autodock4-cnv_state_to_coords.o
    autodock/autodock4-coliny.o
    autodock/autodock4-com.o
    autodock/autodock4-conformation_sampler.o
    autodock/autodock4-dimLibrary.o
    autodock/autodock4-distdepdiel.o
    autodock/autodock4-eintcal.o
    autodock/autodock4-eintcalPrint.o
    autodock/autodock4-eval.o
    autodock/autodock4-gencau.o
    autodock/autodock4-get_atom_type.o
    autodock/autodock4-getInitialState.o
    autodock/autodock4-getpdbcrds.o
    autodock/autodock4-getrms.o
    autodock/autodock4-gs.o
    autodock/autodock4-initautodock.o
    autodock/autodock4-input_state.o
    autodock/autodock4-intnbtable.o
    autodock/autodock4-investigate.o
    autodock/autodock4-linpack.o
    autodock/autodock4-ls.o
    autodock/autodock4-main.o
    autodock/autodock4-mapping.o
    autodock/autodock4-mingw_getrusage.o
    autodock/autodock4-minmeanmax.o
    autodock/autodock4-mkNewState.o
    autodock/autodock4-mkRandomState.o
    autodock/autodock4-mkTorTree.o
    autodock/autodock4-nbe.o
    autodock/autodock4-nonbonds.o
    autodock/autodock4-openfile.o
    autodock/autodock4-output_state.o
    autodock/autodock4-parse_dpf_line.o
    autodock/autodock4-parse_param_line.o
    autodock/autodock4-parse_PDBQT_line.o
    autodock/autodock4-parse_trj_line.o
    autodock/autodock4-parsetypes.o
    autodock/autodock4-prClusterHist.o
    autodock/autodock4-prInitialState.o
    autodock/autodock4-print_2x.o
    autodock/autodock4-print_atomic_energies.o
    autodock/autodock4-print_avsfld.o
    autodock/autodock4-print_rem.o
    autodock/autodock4-printdate.o
    autodock/autodock4-printEnergies.o
    autodock/autodock4-printhms.o
    autodock/autodock4-prTorConList.o
    autodock/autodock4-pso.o
    autodock/autodock4-qmultiply.o
    autodock/autodock4-qtransform.o
    autodock/autodock4-quicksort.o
    autodock/autodock4-ranlib.o
    autodock/autodock4-read_parameter_library.o
    autodock/autodock4-readfield.o
    autodock/autodock4-readmap.o
    autodock/autodock4-readPDBQT.o
    autodock/autodock4-rep.o
    autodock/autodock4-scauchy.o
    autodock/autodock4-setflags.o
    autodock/autodock4-simanneal.o
    autodock/autodock4-sort_enrg.o
    autodock/autodock4-stack.o
    autodock/autodock4-stateLibrary.o
    autodock/autodock4-stop.o
    autodock/autodock4-strindex.o
    autodock/autodock4-success.o
    autodock/autodock4-support.o
    autodock/autodock4-swap.o
    autodock/autodock4-threadlog.o
    autodock/autodock4-timesys.o
    autodock/autodock4-timesyshms.o
    autodock/autodock4-torNorVec.o
    autodock/autodock4-torsion.o
    autodock/autodock4-trilinterp.o
    autodock/autodock4-usage.o
    autodock/autodock4-warn_bad_file.o
    autodock/autodock4-weedbonds.o
    autodock/autodock4-writePDBQT.o
    autodock/autoglobal.h
    autodock/banner.cc
    autodock/banner.h
    autodock/bestpdb.cc
    autodock/bestpdb.h
    autodock/calculateEnergies.cc
    autodock/calculateEnergies.h
    autodock/call_cpso.cc
    autodock/call_cpso.h
    autodock/call_glss.cc
    autodock/call_glss.h
    autodock/call_gs.cc
    autodock/call_gs.h
    autodock/call_ls.cc
    autodock/call_ls.h
    autodock/center_ligand.cc
    autodock/center_ligand.h
    autodock/ChangeLog
    autodock/changeState.cc
    autodock/changeState.h
    autodock/check_header_float.cc
    autodock/check_header_float.h
    autodock/check_header_int.cc
    autodock/check_header_int.h
    autodock/check_header_line.cc
    autodock/check_header_line.h
    autodock/clmode.cc
    autodock/clmode.h
    autodock/cluster_analysis.cc
    autodock/cluster_analysis.h
    autodock/cnv_state_to_coords.cc
    autodock/cnv_state_to_coords.h
    autodock/coliny.cc
    autodock/coliny.h
    autodock/com.cc
    autodock/compile
    autodock/config.guess
    autodock/config.log
    autodock/config.status
    autodock/config.sub
    autodock/config_acro
    autodock/configure
    autodock/configure-universalDarwin
    autodock/configure.ac
    autodock/conformation_sampler.cc
    autodock/conformation_sampler.h
    autodock/constants.h
    autodock/COPYING
    autodock/default_parameters.h
    autodock/depcomp
    autodock/dimLibrary.cc
    autodock/dimLibrary.h
    autodock/distdepdiel.cc
    autodock/distdepdiel.h
    autodock/dpf_add_section_tags
    autodock/dpftoken.h
    autodock/eintcal.cc
    autodock/eintcal.h
    autodock/eintcalPrint.cc
    autodock/eintcalPrint.h
    autodock/energy.h
    autodock/eval.cc
    autodock/eval.h
    autodock/gencau.cc
    autodock/gencau.h
    autodock/get_atom_type.cc
    autodock/get_atom_type.h
    autodock/getInitialState.cc
    autodock/getInitialState.h
    autodock/getpdbcrds.cc
    autodock/getpdbcrds.h
    autodock/getrms.cc
    autodock/getrms.h
    autodock/globals.h
    autodock/grid.h
    autodock/gs.cc
    autodock/gs.h
    autodock/hybrids.h
    autodock/initautodock.cc
    autodock/initautodock.h
    autodock/input_state.cc
    autodock/input_state.h
    autodock/INSTALL
    autodock/install-sh
    autodock/intnbtable.cc
    autodock/intnbtable.h
    autodock/investigate.cc
    autodock/investigate.h
    autodock/linpack.cc
    autodock/ls.cc
    autodock/ls.h
    autodock/main.cc
    autodock/main.h
    autodock/main.h.gch
    autodock/makecheck
    autodock/Makefile
    autodock/Makefile.am
    autodock/Makefile.in
    autodock/Makefile.in.bkp
    autodock/map_declare.h
    autodock/mapping.cc
    autodock/mdist.h
    autodock/mingw_getrusage.cc
    autodock/mingw_sys_times.h
    autodock/mingw_sysconf.h
    autodock/minmeanmax.cc
    autodock/missing
    autodock/mkdistbins
    autodock/mkdisttars
    autodock/mkNewState.cc
    autodock/mkNewState.h
    autodock/mkRandomState.cc
    autodock/mkRandomState.h
    autodock/mkTorTree.cc
    autodock/mkTorTree.h
    autodock/nbe.cc
    autodock/nbe.h
    autodock/NEWS
    autodock/nonbonds.cc
    autodock/nonbonds.h
    autodock/NOTES_xml.txt
    autodock/openfile.cc
    autodock/openfile.h
    autodock/output_state.cc
    autodock/output_state.h
    autodock/paramdat2h.csh
    autodock/parameters.h
    autodock/parse_dpf_line.cc
    autodock/parse_dpf_line.h
    autodock/parse_param_line.cc
    autodock/parse_param_line.h
    autodock/parse_PDBQT_line.cc
    autodock/parse_PDBQT_line.h
    autodock/parse_trj_line.cc
    autodock/parse_trj_line.h
    autodock/parsetypes.cc
    autodock/parsetypes.h
    autodock/partokens.h
    autodock/PDBQT_tokens.h
    autodock/penmp
    autodock/prClusterHist.cc
    autodock/prClusterHist.h
    autodock/prInitialState.cc
    autodock/prInitialState.h
    autodock/print_2x.cc
    autodock/print_2x.h
    autodock/print_atomic_energies.cc
    autodock/print_atomic_energies.h
    autodock/print_avsfld.cc
    autodock/print_avsfld.h
    autodock/print_rem.cc
    autodock/print_rem.h
    autodock/printdate.cc
    autodock/printdate.h
    autodock/printEnergies.cc
    autodock/printEnergies.h
    autodock/printhms.cc
    autodock/printhms.h
    autodock/prTorConList.cc
    autodock/prTorConList.h
    autodock/pso.cc
    autodock/pso.h
    autodock/qmultiply.cc
    autodock/qmultiply.h
    autodock/qtransform.cc
    autodock/qtransform.h
    autodock/quicksort.cc
    autodock/quicksort.h
    autodock/ranlib.cc
    autodock/ranlib.h
    autodock/read_parameter_library.cc
    autodock/read_parameter_library.h
    autodock/readfield.cc
    autodock/readfield.h
    autodock/readmap.cc
    autodock/readmap.h
    autodock/README
    autodock/readPDBQT.cc
    autodock/readPDBQT.h
    autodock/RELEASENOTES
    autodock/rep.cc
    autodock/rep.h
    autodock/rep_constants.h
    autodock/scauchy.cc
    autodock/setflags.cc
    autodock/setflags.h
    autodock/simanneal.cc
    autodock/simanneal.h
    autodock/sort_enrg.cc
    autodock/sort_enrg.h
    autodock/stack.cc
    autodock/stack.h
    autodock/stateLibrary.cc
    autodock/stateLibrary.h
    autodock/stop.cc
    autodock/stop.h
    autodock/strindex.cc
    autodock/strindex.h
    autodock/structs.h
    autodock/success.cc
    autodock/success.h
    autodock/support.cc
    autodock/support.h
    autodock/swap.cc
    autodock/swap.h
    autodock/test_times.cc
    autodock/threadlog.cc
    autodock/threadlog.h
    autodock/timesys.cc
    autodock/timesys.h
    autodock/timesyshms.cc
    autodock/timesyshms.h
    autodock/torNorVec.cc
    autodock/torNorVec.h
    autodock/torsion.cc
    autodock/torsion.h
    autodock/trilinterp.cc
    autodock/trilinterp.h
    autodock/trjtokens.h
    autodock/typedefs.h
    autodock/update_copyright
    autodock/update_license_de-GNU
    autodock/usage.cc
    autodock/usage.h
    autodock/version.h
    autodock/warn_bad_file.cc
    autodock/warn_bad_file.h
    autodock/weedbonds.cc
    autodock/weedbonds.h
    autodock/writePDBQT.cc
    autodock/writePDBQT.h
    autogrid/Tests/AD4.1_bound.dat
    autogrid/Tests/hsg1.pdbqt
    autogrid/Tests/hsg1_no_receptor_types.gpf
    autogrid/Tests/hsg1_sm.gpf
    autogrid/Tests/hsg1_sm.pdbqt
    autogrid/Tests/hsg1_sm_minus_two_types.gpf
    autogrid/Tests/hsg1_sm_nbpcoeffs.gpf
    autogrid/Tests/hsg1_sm_nbpreps.gpf
    autogrid/Tests/hsg1_sm_nbpreps_illegal_atom.gpf
    autogrid/Tests/hsg1_sm_nbpreps_toofew.gpf
    autogrid/Tests/hsg1_sm_no_parameter_file.gpf
    autogrid/Tests/py_hsg1_sm.A.map
    autogrid/Tests/py_hsg1_sm.C.map
    autogrid/Tests/py_hsg1_sm.d.map
    autogrid/Tests/py_hsg1_sm.e.map
    autogrid/Tests/py_hsg1_sm.HD.map
    autogrid/Tests/py_hsg1_sm.N.map
    autogrid/Tests/py_hsg1_sm.NA.map
    autogrid/Tests/py_hsg1_sm.OA.map
    autogrid/Tests/test_autogrid4.py
    autogrid/Tests/write_python_maps.py
    autogrid/Tests/x1hpv.pdbqt
    autogrid/Tests/x1hpv_CASE0.gpf
    autogrid/Tests/x1hpv_CASE1.gpf
    autogrid/Tests/x1hpv_CASE2.gpf
    autogrid/Tests/x1hpv_CASE3.gpf
    autogrid/aclocal.m4
    autogrid/atom_parameter_manager.cpp
    autogrid/atom_parameter_manager.h
    autogrid/AUTHORS
    autogrid/autogrid.h
    autogrid/autogrid4
    autogrid/autogrid4-atom_parameter_manager.o
    autogrid/autogrid4-banner.o
    autogrid/autogrid4-calc_vina_potential.o
    autogrid/autogrid4-check_size.o
    autogrid/autogrid4-distdepdiel.o
    autogrid/autogrid4-gpfparser.o
    autogrid/autogrid4-main.o
    autogrid/autogrid4-mingw_getrusage.o
    autogrid/autogrid4-parse_param_line.o
    autogrid/autogrid4-parsetypes.o
    autogrid/autogrid4-prHMSfixed.o
    autogrid/autogrid4-printdate.o
    autogrid/autogrid4-printhms.o
    autogrid/autogrid4-read_parameter_library.o
    autogrid/autogrid4-setflags.o
    autogrid/autogrid4-stop.o
    autogrid/autogrid4-strindex.o
    autogrid/autogrid4-timesys.o
    autogrid/autogrid4-timesyshms.o
    autogrid/banner.cpp
    autogrid/calc_vina_potential.cpp
    autogrid/calc_vina_potential.h
    autogrid/check_size.cpp
    autogrid/config.guess
    autogrid/config.log
    autogrid/config.status
    autogrid/config.sub
    autogrid/configure
    autogrid/configure-universalDarwin
    autogrid/configure.ac
    autogrid/convertmap.cpp
    autogrid/copyfilesfromAD
    autogrid/COPYING
    autogrid/default_parameters.h
    autogrid/depcomp
    autogrid/distdepdiel.cpp
    autogrid/distdepdiel.h
    autogrid/gpfparser.cpp
    autogrid/gpftoken.h
    autogrid/grid.h
    autogrid/gridmap.h
    autogrid/init_gridmap.cpp
    autogrid/INSTALL
    autogrid/install-sh
    autogrid/main.cpp
    autogrid/makecheck
    autogrid/Makefile
    autogrid/Makefile.am
    autogrid/Makefile.in
    autogrid/mingw_getrusage.cpp
    autogrid/mingw_sys_times.h
    autogrid/mingw_sysconf.h
    autogrid/missing
    autogrid/parameters.h
    autogrid/parm.h
    autogrid/parse_param_line.cpp
    autogrid/parse_param_line.h
    autogrid/parsetypes.cpp
    autogrid/prHMSfixed.cpp
    autogrid/printdate.cpp
    autogrid/printdate.h
    autogrid/printhms.cpp
    autogrid/printhms.h
    autogrid/prototypes.h
    autogrid/read_parameter_library.cpp
    autogrid/read_parameter_library.h
    autogrid/README
    autogrid/setflags.cpp
    autogrid/stop.cpp
    autogrid/stop.h
    autogrid/strindex.cpp
    autogrid/times.h
    autogrid/timesys.cpp
    autogrid/timesys.h
    autogrid/timesyshms.cpp
    autogrid/timesyshms.h
    autogrid/typedefs.h
    autogrid/util.cpp
    autogrid/util.h
    README
    RELEASENOTES)

add_executable(autodock_openmp ${SOURCE_FILES})