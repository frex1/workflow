# CI/CD Workflow Demo

A minimal repository demonstrating a GitHub Actions workflow for running Python code on multiple versions.

---

## Features

- **GitHub Actions Pipeline:**  
  Runs on each push, across Python 3.6, 3.7, and 3.8 (matrix).
- **Checks Setup & Python Versions:**  
  Demonstrates repository checkout, Python installation, listing contents, and job/environment echo.
- **Python Test Script:**  
  Contains a simple `helloworld.py` with version-dependent behavior for demonstration.

---

## How it Works

### CI/CD Workflow

- **Workflow Definition:** [.github/workflows/test_hello.yml](https://github.com/frex1/workflow/blob/main/.github/workflows/test_hello.yml)
- **Steps:**
  1. Echo environment and repository info.
  2. Checkout repo code.
  3. List repository contents.
  4. Set up Python (3.6, 3.7, 3.8 via matrix).
  5. Run the demonstration Python script.

### Python Demo Code

```python
import sys

def main():
    print("Hello World! From Python: " + str(sys.version_info))
    if sys.version_info >= (3, 6) and sys.version_info < (3, 7):
        # let's make this script fail for Python 3.6
        raise Exception('Python version 3.6.x is unsupported!')

if __name__ == "__main__":
    main()
```

---

## Usage

- Modify `test_hello.yml` for your own workflows.
- Replace or expand `helloworld.py` to test other logic.

---

## License

MIT

---

## Author

[@frex1](https://github.com/frex1)

---

## Issues

Open issues or feature requests at: https://github.com/frex1/workflow/issues