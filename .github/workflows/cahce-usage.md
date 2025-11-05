```yaml
steps:
    - name: Download code
        uses: actions/checkout@v4
    - name: Cache dependancies
        uses: actions/cache@v4
        with:
        path: ./node_modules # path to push to cache
        key: ${{runner.os}}-node-${{hashFiles('**/package-lock.json')}}
        restore-keys: |
            ${{runner.os}}-node
    - name: Install
        run: npm instsall
```
