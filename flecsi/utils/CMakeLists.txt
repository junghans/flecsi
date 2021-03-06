#~----------------------------------------------------------------------------~#
#  @@@@@@@@  @@           @@@@@@   @@@@@@@@ @@
# /@@/////  /@@          @@////@@ @@////// /@@
# /@@       /@@  @@@@@  @@    // /@@       /@@
# /@@@@@@@  /@@ @@///@@/@@       /@@@@@@@@@/@@
# /@@////   /@@/@@@@@@@/@@       ////////@@/@@
# /@@       /@@/@@//// //@@    @@       /@@/@@
# /@@       @@@//@@@@@@ //@@@@@@  @@@@@@@@ /@@
# //       ///  //////   //////  ////////  // 
# 
# Copyright (c) 2016 Los Alamos National Laboratory, LLC
# All rights reserved
#~----------------------------------------------------------------------------~#

set(utils_HEADERS
  bitfield.h
  check_sig.h
  check_types.h
  common.h
  const_string.h
  dimensioned_array.h
  doxygen_main.h
  dummy.h
  factory.h
  hash.h
  id.h
  index_space.h
  iterator.h
  static_for.h     detail/static_for.h
  static_list.h
  tuple_for_each.h detail/tuple_for_each.h
  tuple_visit.h    detail/tuple_visit.h
  tuple_zip.h      detail/tuple_zip.h
  zip.h            detail/zip.h
  PARENT_SCOPE)

if (ENABLE_STATIC_CONTAINER)
set(utils_HEADERS 
   ${utils_HEADERS} 
   static_container/type_list.h
   static_container/meta_counter.h
   static_container/meta_list.h
   static_container/static_for.h
   PARENT_SCOPE)
endif (ENABLE_STATIC_CONTAINER)

set(utils_SOURCES
  dummy.cc
  PARENT_SCOPE)

cinch_add_unit(bitfield
  SOURCES test/bitfield.cc)
  
cinch_add_unit(check_sig
  SOURCES test/check_sig.cc)

cinch_add_unit(const_string
  SOURCES test/const_string.cc)

cinch_add_unit(factory
  SOURCES test/factory.cc)

cinch_add_unit(zip
  SOURCES test/zip.cc)

cinch_add_unit(static_for
  SOURCES test/static_for.cc)

#cinch_add_unit(static_list
#  SOURCES test/static_list.cc)

cinch_add_unit(tuple_for_each
  SOURCES test/tuple_for_each.cc)

cinch_add_unit(tuple_visit
  SOURCES test/tuple_visit.cc)

cinch_add_unit(tuple_zip
  SOURCES test/tuple_zip.cc)

if (ENABLE_STATIC_CONTAINER)
cinch_add_unit(meta_container
  SOURCES test/meta_container.cc)
endif (ENABLE_STATIC_CONTAINER)
#~---------------------------------------------------------------------------~-#
# Formatting options
# vim: set tabstop=2 shiftwidth=2 expandtab :
#~---------------------------------------------------------------------------~-#
