cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_VERBOSE_MAKEFILE on)

add_library(sqlite3 STATIC sqlite3.c)

target_link_libraries(sqlite3 dl log atomic)

target_compile_options(sqlite3 PRIVATE -DNDEBUG=1
                                        -DHAVE_USLEEP=1
                                        -DSQLITE_HAVE_ISNAN
                                        -DSQLITE_DEFAULT_JOURNAL_SIZE_LIMIT=1048576
                                        -DSQLITE_THREADSAFE=2
                                        -DSQLITE_TEMP_STORE=3
                                        -DSQLITE_POWERSAFE_OVERWRITE=1
                                        -DSQLITE_DEFAULT_FILE_FORMAT=4
                                        -DSQLITE_DEFAULT_AUTOVACUUM=1
                                        -DSQLITE_ENABLE_MEMORY_MANAGEMENT=1
                                        -DSQLITE_ENABLE_FTS3
                                        -DSQLITE_ENABLE_FTS3_PARENTHESIS
                                        -DSQLITE_ENABLE_FTS4
                                        -DSQLITE_ENABLE_FTS4_PARENTHESIS
                                        -DSQLITE_ENABLE_FTS5
                                        -DSQLITE_ENABLE_FTS5_PARENTHESIS
                                        -DSQLITE_ENABLE_JSON1
                                        -DSQLITE_ENABLE_RTREE=1
                                        -DSQLITE_UNTESTABLE
                                        -DSQLITE_OMIT_COMPILEOPTION_DIAGS
                                        -DSQLITE_DEFAULT_FILE_PERMISSIONS=0600
                                        -DSQLITE_DEFAULT_MEMSTATUS=0
                                        -DSQLITE_MAX_EXPR_DEPTH=0
                                        -DSQLITE_USE_ALLOCA
                                        -DSQLITE_ENABLE_BATCH_ATOMIC_WRITE
                                        -O3)

add_library(android_spatialite SHARED android_database_SQLiteCommon.cpp
    android_database_SQLiteConnection.cpp
    android_database_SQLiteFunction.cpp
    android_database_SQLiteGlobal.cpp
    android_database_SQLiteDebug.cpp
    android_database_CursorWindow.cpp
    CursorWindow.cpp
    JNIHelp.cpp
    JNIString.cpp)

target_link_libraries(android_spatialite sqlite3 libspatialite log)

target_include_directories(sqlite3 PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>)

