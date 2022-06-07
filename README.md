# Stub file(.zip)

1. Convert .zip to base64

   ```sh
   base64 hello.zip > hello.txt
   ```

2. Add base64 content to stub response body

   ```json
    "is": {
        "statusCode": 200,
           "body": "<%- stringify(filename, 'hello.txt') %>",
        "headers": {
            "Content-Type": "application/zip",
            "Content-Disposition": "attachment;filename=\"hello.zip\""
        },
        "_mode": "binary"
    }
   ```

3. Start mountebank

   ```sh
   mb start --configfile zip.json --allowInjection
   ```
