# Live Gecko Reftest Analyzer

A tool for looking at failed reftests live. 

For instance, say you run a try build, and get the following in the reftest analyzer:

```
!   file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/551463-1.html == file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/551463-1-ref.html
!   file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/586683-1.html == file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/586683-1-ref.html
!   file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/614272-1.svg == file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/614272-1-ref.svg
!   file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/615121-2.html != http://localhost:59831/1505412836519/163/bugs/615121-2-notref.html
!   file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/621918-1.svg == file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/621918-1-ref.svg
!   file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/633344-1.html == file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/633344-1-ref.html
!   file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/641770-1.html == file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/641770-1-ref.html
!   file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/641856-1.html == file:///builds/worker/workspace/build/tests/reftest/tests/layout/reftests/bugs/641856-1-ref.html
```

Just copy-paste that text into this tool, and it will bring up live instances of all the tests in iframes to check what they're doing in your local build (or nightly install). You can also use it to check what chrome/safari/edge do on the same inputs.

Each test also has a "source" button to quickly view the source of the tests, to see what they're trying to do.

This isn't great for finding small differences such as slight offsets or aliasing, but is good for quickly categorizing tests and catching big obvious things.



# Basic Usage

1. copy `analyzer.html` to the root of your gecko directory
2. run `python3 -m http.server` in that same directory (this should produce something like (`Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...`)
3. go to `http://localhost:8000/analyzer.html` (port may vary depending on previous step)
4. paste text into input and hit submit!



# Missing Features

* Work directly off of a reftest URL
* Show reftest image results for extra comparison
* Properly format/highlight source
* Source diffs?
