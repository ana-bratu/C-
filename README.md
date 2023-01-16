# C++

Some things to keep in mind when coding


## DRY: Don’t Repeat Yourself
• ”Every piece of knowledge must have a single, unambiguous,
authoritative representation within a system”.

- In most cases it is preferable to use fully-qualified names:

```C++
- int main() {
std::cout << cin << std::endl;
}
```

- if you really want to use unqualified names (= shorthands):
```C++
using std::cout; using std::endl;
int main() {
cout << cin << endl;
}
```

### Data members should be at least protected
- The user may only interact with the class through its public
interface
- If necessary, this interface may include accessors and
mutators (getters and setters) to allow controlled read, resp.
write access to data members

There is always one and only one destructor
- It is called automatically at the object’s ”death”



- The newline character (\n) is called an escape sequence, and it forces the cursor to change its position to the beginning of the next line on the screen. This results in a new line.

| Escape Sequence|	Description                     |               
| -------------- |:--------------------------------:|
| \t	           |Creates a horizontal tab	        |
| \\\             |Inserts a backslash character (\)	|
| \\"             |	Inserts a double quote character|


- Normally, we use // for short comments, and /* */ for longer.

### Note that the * sign does two different things in our code:

- When used in declaration (string* ptr), it creates a pointer variable.
- When not used in declaration, it act as a dereference operator.

#### It is considered good practice to declare your class attributes as private (as often as you can). This will reduce the possibility of yourself (or others) to mess up the code. This is also the main ingredient of the Encapsulation concept, which you will learn more about in the next chapter.

- Note: By default, all members of a class are private if you don't specify an access specifier:

```C++
// Better: declare p2 and initialize it
int* p2 = std::null_ptr; // p points to nothing
```

#### Note : Operators & and * are reciprocal: (&*a) == (*&a) == a


#### In C++: new and delete (operators)
- For each new : « where’s the corresponding
delete ? »


```C++
// Pointers and objects being pointed-to:
const char* string = "hello";
// string[0] = 'H'; // error: non-modifiable object
string = nullptr; // OK, the pointer is not const
char* const string = new char[5];
string[0] = 'H’; // OK, the object is not const
// string = nullptr; // error: non-modifiable pointer

```

#### The --staged option refers to the destination of the restore operation (where things will be changed,
written to). Here, the source will be the ’latest commit’ unless we specify otherwise.
In brief, git restore --staged hello will replace the staged version of file hello with the ’latest commit’
version of this file.

```C++

$ git diff # working copy w.r.t index
diff --git a/hello b/hello
index bd6cb7c..d219b78 100644
--- a/hello
+++ b/hello
@@ -1,2 +1,3 @@
Hello World
Bonjour
+Buen dia
$ git diff HEAD # working copy w.r.t latest commit
diff --git a/hello b/hello
index d7407a1..d219b78 100644
--- a/hello
+++ b/hello
@@ -1 +1,3 @@
Hello World
+Bonjour
+Buen dia
$ git diff --staged # index w.r.t latest commit
diff --git a/hello b/hello
index d7407a1..bd6cb7c 100644
--- a/hello
+++ b/hello
@@ -1 +1,2 @@
Hello World
+Bonjour !
```
