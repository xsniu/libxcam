lib_LTLIBRARIES = libxcam_isp.la

XCAMISP_CXXFLAGS = \
    $(XCAM_CXXFLAGS)            \
    $(IA_IMAGING_CFLAGS)        \
    -I$(top_srcdir)/xcore       \
    -I$(top_srcdir)/modules/isp \
    $(NULL)

XCAMISP_LIBS = \
    $(IA_IMAGING_LIBS)                    \
    $(top_builddir)/xcore/libxcam_core.la \
    $(NULL)

if USE_LOCAL_ATOMISP
XCAMISP_CXXFLAGS += \
    -I$(top_srcdir)/ext/atomisp \
    $(NULL)
endif

if HAVE_LIBDRM
XCAMISP_CXXFLAGS += $(LIBDRM_CFLAGS)
XCAMISP_LIBS += \
    -ldrm_intel    \
    $(LIBDRM_LIBS) \
    $(NULL)
endif

xcam_isp_sources = \
    aiq3a_utils.cpp                       \
    atomisp_device.cpp                    \
    isp_poll_thread.cpp                   \
    isp_image_processor.cpp               \
    isp_controller.cpp                    \
    isp_config_translator.cpp             \
    x3a_isp_config.cpp                    \
    sensor_descriptor.cpp                 \
    iq/x3a_analyze_tuner.cpp              \
    iq/x3a_ciq_tuning_handler.cpp         \
    iq/x3a_ciq_tnr_tuning_handler.cpp     \
    iq/x3a_ciq_bnr_ee_tuning_handler.cpp  \
    iq/x3a_ciq_wavelet_tuning_handler.cpp \
    x3a_statistics_queue.cpp              \
    aiq_handler.cpp                       \
    hybrid_analyzer.cpp                   \
    hybrid_analyzer_loader.cpp            \
    x3a_analyzer_aiq.cpp                  \
    libtbd.c                              \
    xcam_cpf_reader.c                     \
    $(NULL)

libxcam_isp_la_SOURCES = \
    $(xcam_isp_sources) \
    $(NULL)

libxcam_isp_la_CXXFLAGS = \
    $(XCAMISP_CXXFLAGS) \
    $(NULL)

libxcam_isp_la_CFLAGS = $(libxcam_isp_la_CXXFLAGS)

libxcam_isp_la_LIBADD = \
    $(XCAMISP_LIBS) \
    $(NULL)

libxcam_isp_la_LDFLAGS = \
    $(XCAM_LT_LDFLAGS) \
    $(NULL)

libxcam_isp_la_LIBTOOLFLAGS = --tag=disable-static
