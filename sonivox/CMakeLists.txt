add_definitions(
  -DUNIFIED_DEBUG_MESSAGES
  -DEAS_WT_SYNTH 
#_IMELODY_PARSER 
#_RTTTL_PARSER 
#_OTA_PARSER 
#_XMF_PARSER 
  -DNUM_OUTPUT_CHANNELS=2 
  -D_SAMPLE_RATE_22050 
  -DMAX_SYNTH_VOICES=64 
  -D_8_BIT_SAMPLES 
  -D_FILTER_ENABLED 
  -DDLS_SYNTHESIZER 
  -D_REVERB_ENABLED 
  -D_CHORUS_ENABLED
)

set( SOURCES
  host_src/eas_config.c 
  host_src/eas_hostmm.c 
#host_src/eas_main.c 
  host_src/eas_report.c 
  host_src/eas_wave.c 
  lib_src/eas_chorus.c 
  lib_src/eas_chorusdata.c 
  lib_src/eas_data.c 
  lib_src/eas_dlssynth.c 
  lib_src/eas_flog.c 
#lib_src/eas_ima_tables.c 
#lib_src/eas_imaadpcm.c 
#lib_src/eas_imelody.c 
#lib_src/eas_imelodydata.c 
  lib_src/eas_math.c 
  lib_src/eas_mdls.c 
  lib_src/eas_midi.c 
  lib_src/eas_mididata.c 
  lib_src/eas_mixbuf.c 
  lib_src/eas_mixer.c 
#lib_src/eas_ota.c 
#lib_src/eas_otadata.c 
  lib_src/eas_pan.c 
  lib_src/eas_pcm.c 
  lib_src/eas_pcmdata.c 
  lib_src/eas_public.c 
  lib_src/eas_reverb.c 
  lib_src/eas_reverbdata.c 
#lib_src/eas_rtttl.c 
#lib_src/eas_rtttldata.c 
  lib_src/eas_smf.c 
  lib_src/eas_smfdata.c 
  lib_src/eas_tcdata.c 
  lib_src/eas_tonecontrol.c 
  lib_src/eas_voicemgt.c 
#lib_src/eas_wavefile.c 
#lib_src/eas_wavefiledata.c 
  lib_src/eas_wtengine.c 
  lib_src/eas_wtsynth.c 
#lib_src/eas_xmf.c 
#lib_src/eas_xmfdata.c 
  lib_src/jet.c 
  lib_src/wt_22khz.c 
)

add_library( sonivox STATIC ${SOURCES} )

target_include_directories( sonivox 
  PUBLIC host_src
  PRIVATE lib_src
)

set_target_properties( sonivox PROPERTIES 
  POSITION_INDEPENDENT_CODE true
  VERSION 3.6.10 
)

