# AUTOGENERATED COPYRIGHT HEADER START
# Copyright (C) 2023 Michael Fabian 'Xaymar' Dirks <info@xaymar.com>
# AUTOGENERATED COPYRIGHT HEADER END

cmake_minimum_required(VERSION 3.26)
project("Upscaling")
list(APPEND CMAKE_MESSAGE_INDENT "[${PROJECT_NAME}] ")

streamfx_add_component("Upscaling"
	RESOLVER streamfx_upscaling_resolver
)
streamfx_add_component_dependency("NVIDIA" OPTIONAL)

function(streamfx_upscaling_resolver)
	# Providers
	#- NVIDIA
	streamfx_enabled_component("NVIDIA" T_CHECK)
	if(T_CHECK)
		target_compile_definitions(${COMPONENT_TARGET} PRIVATE
			ENABLE_NVIDIA
		)
	endif()
endfunction()
