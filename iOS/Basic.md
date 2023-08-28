# some iOS basic
## 1. the diff between `load` & `init`
- `load` & `init` have same load order : father -> son
- but `load` will have another : father -> son -> category
- son's `load` won't cover father's but init will do
- `load` will run befor main , `init` only run when main start
- `init` use objc_msgSend, but `load` use the memeory address `(*load_method)(cls, SEL_load)`

## 
