###############################################################################
# GTest setup
###############################################################################

macro(ecl_geometry_add_gtest TESTNAME)
  ament_add_gtest(ecl_test_${TESTNAME} ${TESTNAME}.cpp)
  if(TARGET ecl_test_${TESTNAME})
    target_link_libraries(
      ecl_test_${TESTNAME}
        ${PROJECT_NAME}
        ecl_config::ecl_config
        ecl_containers::ecl_containers
        ecl_exceptions::ecl_exceptions
        ecl_formatters::ecl_formatters
        ecl_linear_algebra::ecl_linear_algebra
        ecl_math::ecl_math
        ecl_mpl::ecl_mpl
        ecl_type_traits::ecl_type_traits
    )
  endif()
endmacro(ecl_geometry_add_gtest)

###############################################################################
# GTests
###############################################################################

ecl_geometry_add_gtest(angles)
ecl_geometry_add_gtest(cartesian_points)
ecl_geometry_add_gtest(cubic_splines)
ecl_geometry_add_gtest(homogeneous_points)
ecl_geometry_add_gtest(linear_segment)
ecl_geometry_add_gtest(polynomials)
ecl_geometry_add_gtest(legacy_pose2d)
ecl_geometry_add_gtest(legacy_pose3d)
ecl_geometry_add_gtest(smooth_linear_splines)
ecl_geometry_add_gtest(tension_function)
ecl_geometry_add_gtest(tension_splines)
ecl_geometry_add_gtest(odometry_helper)
