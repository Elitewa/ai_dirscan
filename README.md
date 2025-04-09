# AI DirScan - 智能目录扫描与漏洞分析工具

🔗 **项目地址**: [https://github.com/Elitewa/ai_dirscan](https://github.com/Elitewa/ai_dirscan)

## 📖 项目简介

AI DirScan 是基于 **MCP协议** 的新一代智能安全扫描工具，创新性地将传统目录爆破工具 dirsearch 与大型语言模型（LLM）相结合，实现：

✨ **核心功能**  
✅ 自动化目录扫描与状态码分析  
✅ 智能结果解析与漏洞关联分析  
✅ 主流大模型兼容支持（需自行配置API）  

🚀 **技术亮点**  
- 采用 **FastMCP** 框架实现高并发处理
- 支持 200/403/500 等状态码智能过滤
- 全流程扫描日志追溯机制

🤩 目前项目还在逐步完善中，后续会增加更多的功能，如果有更好的建议欢迎指出

## 🛠️ 快速开始

### 环境要求
- Python 3.10+
- UV 虚拟环境工具
- 支持的大模型API密钥

### 安装步骤
```bash
# 克隆仓库
git clone https://github.com/Elitewa/ai_dirscan.git
cd ai_dirscan

# 创建虚拟环境
uv venv .venv

# 激活环境
（macOS/Linux）
source .venv/bin/activate
（Windows）
.venv\Scripts\activate.bat

# 安装依赖
uv pip install -e .
cd dirsearch
uv pip install -r requirements.txt
uv pip install setuptools
# 对接客户端
    "scan_dir": {
      "command": "uv",
      "args": [
        "--directory",
        "your_path/ai_dirscan/",
        "run",
        "main.py"
      ]
    }
```

### 提示词优化

```
你是一个帮公司扫描网站目录路径的专家，我们为你提供了一个叫做 scan_dir 的mcp服务，你可以调用这个服务，传入用户提供的url参数，然后scan_dir会返回形如以下格式的参数
        {
            "status": 200,
            "data": {
                "file_path": str(output_file),
                "valid_paths": valid_paths,
                "total_found": len(valid_paths)
            },
            "message": "扫描完成"
        }
其中"valid_paths"部分便是扫描得到的路径，你需要把这些路径可能产生的危害和利用方法以及修复方案还有该目录，以标准漏洞报表的表格的形式返回给用户，并且返回扫描结果保存的路径file_path
```

