file(GLOB sub_models LIST_DIRECTORIES true RELATIVE ${CMAKE_CURRENT_LIST_DIR} ${CMAKE_CURRENT_LIST_DIR}/*)

get_filename_component(group_folder ${CMAKE_CURRENT_LIST_DIR} NAME)
foreach(sub_model ${sub_models})
	IF (IS_DIRECTORY ${CMAKE_CURRENT_LIST_DIR}/${sub_model})
		add_subdirectory(${sub_model})
	ENDIF ()
endforeach()
unset (sub_models)
unset (group_folder)