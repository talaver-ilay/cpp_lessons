cmake_minimum_required(VERSION 3.3) # Проверка версии CMake.
									# Если версия установленой программы
# 									# старее указаной, произайдёт аварийный выход.
set(CMAKE_CXX_STANDARD 23)

project(class)			# Название проекта

set(SOURCE_EXE class.cpp)		# Установка переменной со списком исходников для исполняемого файла
                                   
set(SOURCE_LIB dog.cpp)			# Тоже самое, но для библиотеки
                                    
add_library(dog STATIC ${SOURCE_LIB})	# Создание статической библиотеки с именем foo
                                    
add_executable(class ${SOURCE_EXE})	# Создает исполняемый файл с именем main
                                    
target_link_libraries(class dog)		# Линковка программы с библиотекой
