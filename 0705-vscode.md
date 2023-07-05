## vscode

#### faq

vscode 编辑器引入头文件一直报错

c++ 代码正确，cmake 写的没问题，编译可以正常通过，考虑 vscode 问题

**解决**

`ctrl + shift + p` 搜索一下 json 选择 `C/C++ Edit Configurations`选项
在当前项目根目录下会创建`.vscode/c_cpp_properties.json`文件

文件内容改成大概形式

```json
{
    "configurations": [
        {
            "name": "Linux",
            "includePath": [
                "${workspaceFolder}/**",
                // "/opt/intel/openvino_2022.3.0/runtime/include"
            ],
            "defines": [],
            "compilerPath": "/usr/bin/clang-12",
            "cStandard": "c11",
            "cppStandard": "c++11",
            "intelliSenseMode": "linux-clang-x64",
            "configurationProvider": "ms-vscode.makefile-tools"
        }
    ],
    "version": 4
}
```
