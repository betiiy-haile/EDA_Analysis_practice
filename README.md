name: Run unittests

on:
  push:
    branches:
      - main

jobs:
  unittests:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install -r requirements.txt

      - name: Run unittests
        run: |
          pip install pytest
          pytest -v