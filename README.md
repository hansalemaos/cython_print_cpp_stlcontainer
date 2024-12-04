# Print any nested C++ STL container in Cython/Python

![](https://github.com/hansalemaos/cython_print_cpp_stlcontainer/blob/main/example_output.png?raw=true)


### Download the C++ header file here:

https://github.com/hansalemaos/stl_pretty_print/blob/main/prettyprint.hpp

```py 

# some examples of the data types you can print 
from libcpp.vector cimport vector
from libcpp.string cimport string 
from libcpp.set cimport multiset,set,pair 
from libcpp.map cimport map,multimap
from libcpp.unordered_map cimport unordered_map,unordered_multimap
from libcpp.deque cimport deque
from libcpp.queue cimport queue,priority_queue
from libcpp.unordered_set cimport unordered_set, unordered_multiset
from libcpp.forward_list cimport forward_list

# use this code to include the STL printer 
# https://github.com/hansalemaos/stl_pretty_print/blob/main/prettyprint.hpp
cdef extern from "prettyprint.hpp" namespace "prettyprinter"  nogil :
    string print_black[T](T, string, string)
    string print_red[T](T, string, string)
    string print_green[T](T, string, string)
    string print_yellow[T](T, string, string)
    string print_blue[T](T, string, string)
    string print_purple[T](T, string, string)
    string print_cyan[T](T, string, string)
    string print_white[T](T, string, string)
    string print_black[T](T, string)
    string print_red[T](T, string)
    string print_green[T](T, string)
    string print_yellow[T](T, string)
    string print_blue[T](T, string)
    string print_purple[T](T, string)
    string print_cyan[T](T, string)
    string print_white[T](T, string)
    string print_black[T](T)
    string print_red[T](T)
    string print_green[T](T)
    string print_yellow[T](T)
    string print_blue[T](T)
    string print_purple[T](T)
    string print_cyan[T](T)
    string print_white[T](T)

# how to use it 
cdef:
    vector[int] hallo = [1,2,3,4,5]
    unordered_map[int,int] hallo2={3:4,2:3,1:12}
    string tete=print_red(hallo)
    string tete2=print_red(hallo2)
    string tete3=print_yellow(hallo,<string>b"debug_prefix")
    string tete4=print_cyan(hallo2,<string>b"debug_prefix",<string>b"debug_suffix")
```
