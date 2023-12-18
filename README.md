# bug_zed-typescript-detection

## Instructions

1. `tail -f ~/Library/Logs/Zed/Zed.log` to capture logs
2. `cd` into wherever you clone'd this repo
3. `zed` to open the clone'd repo in Zed
4. Open `example-subdir/index.ts` file
5. Zed logs should say: `Using Typescript version (user-setting) 5.3.3 from path \"/Users/exampleuser/bug_zed-typescript-detection/node_modules/typescript/lib/tsserver.js\"`
6. Close Zed
7. `zed example-subdir/` to open the sub directory in Zed
8. Open `example-subdir/index.ts` file
9. Zed logs should say: `Using Typescript version (user-setting) 4.9.5 from path \"/Users/exampleuser/bug_zed-typescript-detection/example-subdir/node_modules/typescript/lib/tsserver.js\"`
10. Conclusion: Zed is searching the TypeScript version to use closest to the "root/project" directory rather than the closest version to the file being opened.
11. Expected: Zed should use the TypeScript version closest to the file being opened.
