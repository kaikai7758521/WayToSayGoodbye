# some iOS basic
## the diff between `load` & `init`
- `load` & `init` have same load order : father -> son
- but `load` will have another : father -> son -> category
- son's `load` won't cover father's but init will do
- `load` will run befor main , `init` only run when main start
- `init` use objc_msgSend, but `load` use the memeory address `(*load_method)(cls, SEL_load)`

## the category in iOS
categroy usually use in follow ways:
1. make private method for class
2. reduce size of class file
3. make frame work method visiable

category feature:
1. decide in runtime : for same name method , it will work by order(only the first be found will work)
2. you can add method for system api (by hook: method switch)

category usage:
1. can add instance medthod
2. can add class method
3. can add property
4. can add protocol

category will be compiled into a struct
```objc
struct category_t {
    
    const char *name;                           // name
    classref_t cls;                             // its owner
    struct method_list_t *instanceMethods;      // list of instance method
    struct method_list_t *classMethods;         // list of class method
    struct protocol_list_t *protocols;          // list of protocol
    struct property_list_t *instanceProperties; // list of property
    
}
```

## 

