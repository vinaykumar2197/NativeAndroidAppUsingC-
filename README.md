
# Hi, I'm Vinay! 👋 

  
# Native Android App ( Using C++)

Here we will learn how to connect your android activity with c++ module and get the data from c++.

# C++ Use Cases 
C++ is faster as compared to java. We can use c++ in order to secure our api keys, 
or hide encryption/decryption techniques which we are using in the application. 
That will make reverse engineering of the these components harder. 
Along with this, if you want to work on opencv, tensorflow..., you might use c++ there. 


## Native Android App ( Using C++)

*MainActivity* loads the native module through constructor. 

we have defined a method  stringFromJNI() which is going to fetch 
the value from native module. 

we are setting this value in textview field of activity. 

Make a cpp folder in app directory of your project. 

Make a CMakeLists.txt file which will contain all the necessary information 
regarding your project. This file is similar to manifest/build.gradle of android.



## Installation

native-lib.cpp code 

```bash
#include <jni.h>
#include <string>
using namespace  std;

extern "C" JNIEXPORT jstring JNICALL
Java_com_vinay_nativeandroidappusingc_MainActivity_stringFromJNI(
        JNIEnv* env,
        jobject /* this */) {
    string hello = "Hello from C++";
    return env->NewStringUTF(hello.c_str());
}
```


in above function since data type of c++ and java differs. 

string data type in c++ is lowecase string while in java it's String . 

Methods which you want to access from android code should Start with Java followed by package name and function. 

e.g. 
Suppose my mainactivity is in following directory.

java -> com -> vinay -> nativeandroidappusingc -> MainActivity -> stringFromJNI() 

so we will write our function in c++ as 

### Java_com_vinay_nativeandroidappusingc_MainActivity_stringFromJNI
## Authors

- [@Vinaykumar](https://github.com/vinaykumar2197)

  