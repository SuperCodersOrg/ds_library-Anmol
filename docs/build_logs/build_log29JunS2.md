- Date: 29 June 2026 (Session 2)
Duration: 2 HOurs 45 mins

Goal():
Integrating the command parser with redis lite and start implementation of cli 

What I did():
I tried adding the command parser in the redislite by adding one more function in the redislite that is 
```std::execute``` which directly runs the comand parser in the redilite .cpp only.

During adding the execute and testing wheter it works or not i faced some erros which are listed below

Error 1:

Redis.hpp:28:42: error: 'Command' does not name a type
     std::string RedisLite::execute(const Command& command)
                                          ^~~~~~~
This error says that the command is not recognized that meand it has not been clearly declared.

Error 2:

Redis.hpp:28:17: error: extra qualification 'RedisLite::' on member 'execute' [-fpermissive]
     std::string RedisLite::execute(const Command& command)
                 ^~~~~~~~~
I have added the redislite extra during the decalration of the member which is wrong due to which this error occured.

Error3:
Redis.hpp:28:58: error: expected ';' at end of member declaration
     std::string RedisLite::execute(const Command& command)
                                                          ^
This happend because in this line when added redislite it made the compiler confused.

Error4:

testi.cpp: In function 'int main()':
testi.cpp:21:43: error: no matching function for call to 'RedisLite::execute(Command&)'
         std::cout << redis.execute(command) << std::endl;
                                           ^
In file included from testi.cpp:3:0:
Redis.hpp:28:17: note: candidate: std::__cxx11::string RedisLite::execute(const int&)
     std::string RedisLite::execute(const Command& command)
                 ^~~~~~~~~
Redis.hpp:28:17: note:   no known conversion for argument 1 from 'Command' to 'const int&'

ecause Command wasn't recognized (Error 1). The parser got confused, so the declaration became invalid and the diagnostic ends up showing an incorrect parameter type



Error5;
PS D:\CQ> g++ testi.cpp Redislite.cpp CommandParser.cpp -o redis
In file included from CommandParser.hpp:4:0,
                 from testi.cpp:4:
command.hpp:4:12: error: multiple definition of 'enum class CommandType'
 enum class CommandType
            ^~~~~~~~~~~
In file included from Redis.hpp:3:0,
                 from testi.cpp:3:
command.hpp:4:12: note: previous definition here
 enum class CommandType
            ^~~~~~~~~~~
In file included from CommandParser.hpp:4:0,
                 from testi.cpp:4:
command.hpp:16:8: error: redefinition of 'struct Command'
 struct Command
        ^~~~~~~
In file included from Redis.hpp:3:0,
                 from testi.cpp:3:
command.hpp:16:8: error: previous definition of 'struct Command'
 struct Command
        ^~~~~~~

This error says that the command.hpp has been included multiple times due to which compiler is compiling it more than once. 
It was added in redislite.hpp and also it is included in the commandparser.hpp also.
What i did was added the ```#prgma once``` in the command.hpp which helps the compiler to understand that the file should run only once in the compilation even it is included multiple times.
