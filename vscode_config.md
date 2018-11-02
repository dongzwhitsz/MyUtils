 ## launch.jason:
 
    {
        // Use IntelliSense to learn about possible attributes.
        // Hover to view descriptions of existing attributes.
        // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
        "version": "0.2.0",
        "configurations": [
        // java环境配置
            {
                "type": "java",
                "name": "CodeLens (Launch) - hellojava",
                "request": "launch",
                "cwd": "${workspaceFolder}",
                "console": "internalConsole",
                "stopOnEntry": false,
                "mainClass": "hellojava",
                "args": ""
            },
         // python环境配置
            {
                "name": "Python: Terminal (integrated)",
                "type": "python",
                "request": "launch",
                "program": "${file}",
                "console": "integratedTerminal"
            },
        // c++配置
            {
                "name": "(gdb) Launch",
                "type": "cppdbg",
                "request": "launch",
                "program": "${workspaceRoot}\\${fileBasenameNoExtension}.exe",
                "args": [],
                "stopAtEntry": false,
                "cwd": "${workspaceRoot}",
                "environment": [],
                "externalConsole": false,
                "MIMode": "gdb",
                "miDebuggerPath": "F:\\compilers\\mingw64\\bin\\gdb.exe",
                "preLaunchTask": "F:\\compilers\\mingw64\\bin\\g++.exe",
                "setupCommands": [
                    {
                        "description": "Enable pretty-printing for gdb",
                        "text": "-enable-pretty-printing",
                        "ignoreFailures": true
                    }
                ]
            }
        ]
    }
    
    
## tasks.json

    {
        "version": "2.0.0",
        "command": "F:\\compilers\\mingw64\\bin\\g++.exe",
        "args": ["${file}","-o","${workspaceRoot}\\${fileBasenameNoExtension}.exe"],
        "problemMatcher": {
            "owner": "cpp",
            "fileLocation": ["relative", "${workspaceRoot}"],
            "pattern": {
                "regexp": "^(.*):(\\d+):(\\d+):\\s+(warning|error):\\s+(.*)$",
                "file": 1,
                "line": 2,
                "column": 3,
                "severity": 4,
                "message": 5
            }
        }
    }
