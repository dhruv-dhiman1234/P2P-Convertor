# P2P-Convertor

🚀 Features

- Function-to-Function Conversion  
  Convert individual functions or code blocks from Pandas to Polars and vice versa using AI and AST-based logic.

- Auto-Detection  
  convert(code, backend="polars") figures out the source library, maps idioms, and rewrites accordingly.

- Benchmarking & Analysis  
  Compare execution time and memory usage between original and converted versions.

- Explainable Diffs  
  View side-by-side diffs with human-readable comments explaining each transformation.

- Safety Checks  
  Warn about potential data-loss or unsupported patterns; ensure round-trip integrity when possible.

- CLI & Python API  
  Use via simple CLI commands or integrate into your Python scripts.

---

⚙️ Installation

pip install ptop-ai

Or clone and install from source:

git clone https://github.com/yourusername/ptop-ai.git  
cd ptop-ai  
pip install -e .

---

🔧 Usage

Python API:

from ptop_ai import convert

pandas_code = '''
def analyze(df):
    df = df[df["age"] > 30]
    df["score"] = df["score"] * 1.2
    return df.groupby("dept").mean()
'''

result = convert(pandas_code, backend="polars", benchmark=True)
print(result.code)
print(result.benchmark)

CLI:

ptop-ai convert --input script.py --to polars --benchmark

Converts script.py to Polars, prints converted code, and shows performance metrics.

---

📦 Project Structure

ptop-ai/  
├── ptop_ai/  
│   ├── __init__.py  
│   ├── converter.py      # Core logic (AST + AI)  
│   ├── benchmark.py      # Timing & memory profiling  
│   ├── cli.py            # CLI entry points  
│   └── utils.py          # Helpers & patterns  
├── tests/                # pytest-based tests  
├── pyproject.toml        # Packaging  
└── README.md  

---

📈 Roadmap

1. MVP: Basic AST-based Pandas → Polars conversion for common functions.  
2. Benchmark Module: Time & memory comparison reports.  
3. AI Integration: LLM-powered fallback for unsupported patterns.  
4. Round-Trip Checker: Validate Pandas→Polars→Pandas equivalence.  
5. Plugins: Allow community to register custom handlers.

---

🤝 Contributing

1. Fork the repo and create a branch for your feature/fix.  
2. Write tests under tests/ covering new behavior.  
3. Submit a Pull Request with a clear description.  
4. Be patient and humble; we’ll review together.

---

🛡 License

This project is released under the MIT License.
