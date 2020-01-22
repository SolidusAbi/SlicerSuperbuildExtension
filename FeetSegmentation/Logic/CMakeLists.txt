project(vtkSlicer${MODULE_NAME}ModuleLogic)

set(KIT ${PROJECT_NAME})

set(${KIT}_EXPORT_DIRECTIVE "VTK_SLICER_${MODULE_NAME_UPPER}_MODULE_LOGIC_EXPORT")

set(${KIT}_INCLUDE_DIRECTORIES
  ${TORCH_INCLUDE_DIRS}
  ${PCL_INCLUDE_DIRS}
)

set(${KIT}_SRCS
  vtkSlicer${MODULE_NAME}Logic.cxx
  vtkSlicer${MODULE_NAME}Logic.h
  ${MODULE_NAME}.cxx
  ${MODULE_NAME}.h
  ${MODULE_NAME}Dataset.h
  ${MODULE_NAME}Dataset.cxx
  vtk${MODULE_NAME}Dataset.h
  vtk${MODULE_NAME}Dataset.cxx
  Utils.h
  Utils.cxx
)

set(${KIT}_TARGET_LIBRARIES
  ${TORCH_LIBRARIES}
  ${PCL_LIBRARIES}
  ${ITK_LIBRARIES}
  ${VTK_LIBRARIES}
)

#-----------------------------------------------------------------------------
SlicerMacroBuildModuleLogic(
  NAME ${KIT}
  EXPORT_DIRECTIVE ${${KIT}_EXPORT_DIRECTIVE}
  INCLUDE_DIRECTORIES ${${KIT}_INCLUDE_DIRECTORIES}
  SRCS ${${KIT}_SRCS}
  TARGET_LIBRARIES ${${KIT}_TARGET_LIBRARIES}
  )