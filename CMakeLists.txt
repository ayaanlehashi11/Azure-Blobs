
# Licensed under the MIT License.

cmake_minimum_required (VERSION 3.13)

if(MSVC)
  add_compile_definitions(_CRT_SECURE_NO_WARNINGS)
endif()

add_executable(azure_blob azure_blob.cpp)
target_link_libraries(azure_blob PRIVATE azure-storage-blobs get-env-helper)
create_per_service_target_build_for_sample(storage azure_blob)

add_executable(blob_listing blob_listing.cpp)
target_link_libraries(blob_listing  PRIVATE azure-storage-blobs get-env-helper)
create_per_service_target_build_for_sample(storage blob_listing)

add_executable(blob-query blob_query.cpp)
target_link_libraries(blob-query PRIVATE azure-storage-blobs get-env-helper)
create_per_service_target_build_for_sample(storage blob-query)
