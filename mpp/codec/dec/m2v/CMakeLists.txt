# vim: syntax=cmake
include_directories(.)

# m2v decoder api
set(M2VD_API
	../../inc/m2vd_api.h  
  )
set(M2VD_COMMON
  )
	
# m2v decoder header	
set(M2VD_HDR
	m2vd_parser.h
	m2vd_codec.h
	m2vd_com.h
  ) 
	
# m2v decoder source
set(M2VD_SRC
	m2vd_api.c
	m2vd_parser.c
) 

			
add_library(codec_m2vd STATIC
				${M2VD_API}
				${M2VD_COMMON}
				${M2VD_HDR} 
				${M2VD_SRC} 
			)	
target_link_libraries(codec_m2vd
                      mpp_base
                      )
set_target_properties(codec_m2vd PROPERTIES FOLDER "mpp/codec")

