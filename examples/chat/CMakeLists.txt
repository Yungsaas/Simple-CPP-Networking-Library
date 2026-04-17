cmake_minimum_required(VERSION 3.20)

add_executable(chat_server server_main.cpp)
target_link_libraries(chat_server PRIVATE simplenet)

add_executable(chat_client client_main.cpp)
target_link_libraries(chat_client PRIVATE simplenet)
