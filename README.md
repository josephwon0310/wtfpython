<p align="center"><img src="images/logo.png" alt=""></p>
<h1 align="center">What the f*ck Python! 🐍</h1>
<p align="center">놀라운 파이썬 코드 예제들과 생소한 기능들.</p>
<p align="center">이 문서는 현재 번역이 진행 중인 미완성 문서입니다.</p>

<p align="center">
<a href="https://github.com/satwikkansal/wtfpython">English</a>
| <a href="https://github.com/leisurelicht/wtfpython-cn">中文</a>
  | <a href="#">한글</a>
</p>

[![WTFPL 2.0][license-image]][license-url]

파이썬은 아름답게 디자인된 고급(high-level) 인터프리터 기반 언어로, 개발자의 편의를 생각한 기능들이 아주 많습니다. 다만 이런 파이썬의 생소한 기능들에 익숙하지 않은 사람들에게 "파이써닉"하게 쓰여진 코드가 어떤 일을 하는지 한 눈에 알아차리기란 쉽지 않습니다.

이 문서는 이러한 특유의 파이써닉한 코드들의 이해를 돕고, 파이썬이 주어진 코드를 어떻게 처리하는지 정확히 알고자는 목적으로 파이썬의 생소한 기능들 및 코드 예제를 정리한 문서입니다.

몇몇 예제는 WTF까지는 아닐지라도, 어느면에서는 파이썬의 모르고 있었던 부분에 대한 설명이되지 않을까 싶습니다. 이러한 예제들이 프로그래밍 언어가 어떻게 작동하는지에대해 이해를 돕고, 좋은 학습 방법이될거라고 생각합니다.

만약 본인이 파이썬 배경지식이 충분한 파이써니스타라면, 아래 예제들을 몇개나 한 번에 맞출수 있는지 도전해보세요. 이미 알고있는 예제들이 있다면 처음 그 파이썬스러움을 담은 문법을 접했을 그때 그 시절의 기억을 되살려줄수 있지않을까요? :sweat_smile:


PS: 이 문서를 이미 읽던중이었으면, 수정된 부분은 [여기](https://github.com/satwikkansal/wtfpython/releases/)서 확인하실수 있습니다.

# 목차

<!-- toc -->


- [메타 예제](#메타-예제)
- [사용 방법](#사용-방법)
- [👀 예제](#-예제)
  - [섹션: 머리가 아플 수도 있어요!](#섹션-머리가-아플-수도-있어요)
    - [▶ 알쏭달쏭 문자열](#-알쏭달쏭-문자열-)
    - [▶ 스플릿스플릿!](#-스플릿스플릿-)
    - [▶ 파이썬의 예외처리](#-파이썬의-예외처리)
    - [▶ Return return everywhere!](#-return-return-everywhere)
    - [▶ Deep down, we're all the same.](#-deep-down-were-all-the-same-)
    - [▶ For what?](#-for-what)
    - [▶ Evaluation time discrepancy](#-evaluation-time-discrepancy)
    - [▶ `is` is not what it is!](#-is-is-not-what-it-is)
    - [▶ A tic-tac-toe where X wins in the first attempt!](#-a-tic-tac-toe-where-x-wins-in-the-first-attempt)
    - [▶ The sticky output function](#-the-sticky-output-function)
    - [▶ `is not ...` is not `is (not ...)`](#-is-not--is-not-is-not-)
    - [▶ The surprising comma](#-the-surprising-comma)
    - [▶ Backslashes at the end of string](#-backslashes-at-the-end-of-string)
    - [▶ not knot!](#-not-knot)
    - [▶ Half triple-quoted strings](#-half-triple-quoted-strings)
    - [▶ Midnight time doesn't exist?](#-midnight-time-doesnt-exist)
    - [▶ What's wrong with booleans?](#-whats-wrong-with-booleans)
    - [▶ Class attributes and instance attributes](#-class-attributes-and-instance-attributes)
    - [▶ yielding None](#-yielding-none)
    - [▶ Mutating the immutable!](#-mutating-the-immutable)
    - [▶ The disappearing variable from outer scope](#-the-disappearing-variable-from-outer-scope)
    - [▶ When True is actually False](#-when-true-is-actually-false)
    - [▶ From filled to None in one instruction...](#-from-filled-to-none-in-one-instruction)
    - [▶ Subclass relationships](#-subclass-relationships-)
    - [▶ The mysterious key type conversion](#-the-mysterious-key-type-conversion-)
    - [▶ Let's see if you can guess this?](#-lets-see-if-you-can-guess-this)
  - [Section: Appearances are deceptive!](#section-appearances-are-deceptive)
    - [▶ Skipping lines?](#-skipping-lines)
    - [▶ Teleportation](#-teleportation-)
    - [▶ Well, something is fishy...](#-well-something-is-fishy)
  - [Section: Watch out for the landmines!](#section-watch-out-for-the-landmines)
    - [▶ Modifying a dictionary while iterating over it](#-modifying-a-dictionary-while-iterating-over-it)
    - [▶ Stubborn `del` operator](#-stubborn-del-operator-)
    - [▶ Deleting a list item while iterating](#-deleting-a-list-item-while-iterating)
    - [▶ Loop variables leaking out!](#-loop-variables-leaking-out)
    - [▶ Beware of default mutable arguments!](#-beware-of-default-mutable-arguments)
    - [▶ Catching the Exceptions](#-catching-the-exceptions)
    - [▶ Same operands, different story!](#-same-operands-different-story)
    - [▶ The out of scope variable](#-the-out-of-scope-variable)
    - [▶ Be careful with chained operations](#-be-careful-with-chained-operations)
    - [▶ Name resolution ignoring class scope](#-name-resolution-ignoring-class-scope)
    - [▶ Needle in a Haystack](#-needle-in-a-haystack)
  - [섹션: 파이썬의 숨겨진 보물들!](#섹션-파이썬의-숨겨진-보물들)
    - [▶ 파이썬과 함께 나는 방법?](#-파이썬과-함께-나는-방법)
    - [▶ 파이썬에 `goto`문이 있다고?](#-파이썬에-goto문이-있다고-)
    - [▶ Brace yourself! *](#-brace-yourself-)
    - [▶ Let's meet Friendly Language Uncle For Life *](#-lets-meet-friendly-language-uncle-for-life-)
    - [▶ Even Python understands that love is complicated *](#-even-python-understands-that-love-is-complicated-)
    - [▶ Yes, it exists!](#-yes-it-exists)
    - [▶ Inpinity *](#-inpinity-)
    - [▶ Mangling time! *](#-mangling-time-)
  - [Section: Miscellaneous](#section-miscellaneous)
    - [▶ `+=` is faster](#--is-faster)
    - [▶ Let's make a giant string!](#-lets-make-a-giant-string)
    - [▶ Explicit typecast of strings](#-explicit-typecast-of-strings)
    - [▶ Minor Ones](#-minor-ones)
- [Contributing](#contributing)
- [Acknowledgements](#acknowledgements)
- [🎓 License](#-license)
  * [Help](#help)
  * [Surprise your geeky pythonist friends?](#surprise-your-geeky-pythonist-friends)
  * [Need a pdf version?](#need-a-pdf-version)

<!-- tocstop -->

# 메타 예제

모든 예제는 아래와 같이 주어집니다:

> ### ▶ 엄청난 제목 *
> 제목 끝의 별표(\*)는 첫 버전에는 없던, 새로 추가된 예제입니다.
>
> ```py
> # 코드 예제를 위한 준비
> # 파이썬의 놀라움을 기대하세요...
> ```
>
> **결과 (유효한 파이썬 버전):**
> ```py
> >>> 어느 입력1
> 신기한 결과
> ```
> (Optional): `신기한 결과`에 대한 한줄 설명.
>
>
> #### 💡 설명:
>
> * 코드의 결과에 관한 간단한 설명 및 이에 대한 이유.
>   ```py
>   설명을 도울 예제
>   ```
>   **Output Output (Python version(s)):**
>   ```py
>   >>> 어느 입력2 # 이 입력은 파이썬스러움의 이해를 도울 예제이면 좋습니다.
>   신기하지만 이해 가능한 결과
>   ```

**Note:** 모든 예제는 파이썬 3.5.2 버전에서 테스트되었으며, 특정 버전이 주어진 예제가 아닌 이상 모든 파이썬 버전에서 동일하게 작동합니다.

# 사용 방법

이 문서는 순서대로 읽어내려가며, 각 예제 별로 다음 아래 리스트대로 시도해보기를 권장합니다:
- 각 예제 코드의 첫 셋팅 부분을 잘 읽어주세요. 만약 파이썬 배경지식이 충분한 개발자라면 어떤 결과가 나올지에 대한 대부분의 짐작이 갈겁니다.
- 결과 코드를 읽고,
  + 짐작한 결과와 맞는지 확인해보세요.
  + 주어진 예제 코드가 어째서 그러한 결과를 낳는지 정확한 이유를 아셨나요?.
    - 만약 아니라면 (걱정하지마세요), 숨 한번 크게 쉬시고, 설명을 읽어보세요 (그래도 어렵다면 주저하지마시고 [여기](https://github.com/satwikkansal/wtfPython)에 이슈를 작성해주시면 됩니다!).
    - 만약 이미 알던 사실이라면 기뻐하셔도 좋습니다! 다음 예제로 넘어가세요.

PS: WTFPython은 커맨드라인으로 읽을 수도 있습니다. Pypi 패키지와 npm패키지가 있으며 두 버전 모두 동일합니다.

npm 패키지 설치: [`wtfpython`](https://www.npmjs.com/package/wtfpython)
```sh
$ npm install -g wtfpython
```

파이썬 패키지 설치: [`wtfpython`](https://pypi.python.org/pypi/wtfpython)
```sh
$ pip install wtfpython -U
```

설치가 끝났다면, 터미널에 `wtfpython` 입력하면 이 문서를 열 수 있습니다.

---

# 👀 예제


## 섹션: 머리가 아플 수도 있어요!

### ▶ 알쏭달쏭 문자열
<!-- Example ID: 30f1d3fc-e267-4b30-84ef-4d9e7091ac1a --->
1\.
```py
>>> a = "some_string"
>>> id(a)
140420665652016
>>> id("some" + "_" + "string") # 두 출력의 아이디가 같은 것에 주목하세요.
140420665652016
```

2\.
```py
>>> a = "wtf"
>>> b = "wtf"
>>> a is b
True

>>> a = "wtf!"
>>> b = "wtf!"
>>> a is b
False
```

3\.

**(< 파이썬 3.7 )**

```py
>>> 'a' * 20 is 'aaaaaaaaaaaaaaaaaaaa'
True
>>> 'a' * 21 is 'aaaaaaaaaaaaaaaaaaaaa'
False
```

이해 되셨나요?

#### 💡 설명:
+ 이러한 결과는 CPython의 불변객체를 재활용하려는 최적화 방식때문인데(string interning이라고 함), 경우에따라 새로운 객체를 만들기보다는, 이미 만들어진 객체를 재활용하기에 나타나는 결과입니다.
+ 이러한 과정을 통해 다른 변수들이 사실 메모리 내에서는 같은 문자열을 가리키게 됩니다(즉, 메모리를 절약).
+ 주어진 예제에서는 문자열이 모두 암시적으로 최적화 과정을 겪었는데, 이는 구현 방식별로 결과가 다를 수 있습니다. 아래 주어진 사실에 기반해 문자열이 위의 최적화 과정을 겪을 것인지에 대해 짐작할 수 있습니다:
  * 길이가 0 혹은 1인 모든 문자열은 위의 최적화 과정을 겪습니다.
  * 모든 문자열은 컴파일 타임에 최적화됩니다.  (`'wtf'` 은 최적화 과정을 거치나 `''.join(['w', 't', 'f']` 은 거치지 않는다.)
  * ASCII로 이루어지지 않은 문자열, 숫자와 언더스코어는 이 과정을 겪지 않습니다. 위 예제에서 `'wtf!'`이 서로 다른 두 객체를 생성한 것은 바로 `!`때문 입니다. 이에 대한 Cpython의 세부적인 구현 사항은 [이 곳](https://github.com/python/cpython/blob/3.6/Objects/codeobject.c#L19)에서 확인하실 수 있습니다.
  <img src="images/string-intern/string_intern.png" alt="">
+ 상수 폴딩은 [핍홀 최적화](https://en.wikipedia.org/wiki/Peephole_optimization)를 위해 파이썬이 사용하는 기법이며, 예제에서 `'a'*20`는 컴파일시 `'aaaaaaaaaaaaaaaaaaaa'`로 치환됩니다(이는 런타임에서 클럭수를 줄이는데 도움). 그렇다면 왜 `'a'*21`은 상수 폴딩을 거치지 않았냐구요? 상수폴딩은 길이가 20 이하인 문자열에 한하여 거치는 과정이기 때문입니다. (이유가 궁금하다면 `'a'*10**10`로 생성된 `.pyc` 파일의 크기를 상상해보세요). 이에 대한 구현은 [이 곳](https://github.com/python/cpython/blob/3.6/Python/peephole.c#L288)에서 확인하실 수 있습니다.
+ 참고: 상수 폴딩은 파이썬 3.7을 기준으로 파이썬의 최적화 로직에서 제외되었으며 이후 버전의 파이썬은 추상 구문 트리를 사용합니다. 이에 대한 변경 내용이 궁금하다면 [이 곳](https://bugs.python.org/issue11549)에서 확인하실 수 있습니다.

---

### ▶ 스플릿스플릿!
<!-- Example ID: ec3168ba-a81a-4482-afb0-691f1cc8d65a --->
```py
>>> 'a'.split()
['a']

# 위랑 같은 결과죠?
>>> 'a'.split(' ')
['a']

# 근데 길이를 보면..
>>> len(''.split())
0

# 서로 다르네요?
>>> len(''.split(' '))
1
```

#### 💡 설명:
- 얼핏보면 파이썬 `split` 함수의 기본 값이 `' '`(스페이스)처럼 보이지만, 공식 [문서](https://docs.python.org/2.7/library/stdtypes.html#str.split)를 확인해보면...
    > 만약 separator 값이 주어지지 않았거나, `None` 값을 주었을시에 이 함수는 다른 알고리즘을 사용합니다, 연속된 공백문자는 한개의 separator로 간주, 문자열의 앞 뒤로 있는 여백 역시 무시됩니다. 즉, 빈 문자열 혹은 여백으로 이루어진 문자열은 `[]`를 리턴합니다.

    > 만약 separator 값이 주어졌을 경우, 서로 연속된 delimeter는 하나로 간주되지 않으며 사이사이마다 빈 문자열을 추가합니다(예: `'1,,2'.split(',')`는 `['1', '', '2']`를 리턴합니다. 가운데 추가된 빈 문자열인 `''`를 주목하세요.). 빈 문자열과  `None`이 아닌 separator값을 주었을 경우 `['']`를 반환합니다.
- 두 경우에 따라 문자열 앞 뒤의 여백처리가 다른 점이 보이시나요?
    ```py
    >>> ' a '.split(' ')
    ['', 'a', '']
    >>> ' a '.split()
    ['a']
    >>> ''.split(' ')
    ['']
    ```

---



### ▶ Time for some hash brownies!
<!-- Example ID: eb17db53-49fd-4b61-85d6-345c5ca213ff --->
1\.
```py
some_dict = {}
some_dict[5.5] = "Ruby"
some_dict[5.0] = "JavaScript"
some_dict[5] = "Python"
```

**결과:**
```py
>>> some_dict[5.5]
"Ruby"
>>> some_dict[5.0]
"Python"
>>> some_dict[5] # "Python" destroyed the existence of "JavaScript"?
"Python"

>>> complex_five = 5 + 0j
>>> type(complex_five)
complex
>>> some_dict[complex_five]
"Python"
```

So, why is Python all over the place?


#### 💡 설명

* Python dictionaries check for equality and compare the hash value to determine if two keys are the same.
* Immutable objects with same value always have the same hash in Python.
  ```py
  >>> 5 == 5.0 == 5 + 0j
  True
  >>> hash(5) == hash(5.0) == hash(5 + 0j)
  True
  ```
  **Note:** Objects with different values may also have same hash (known as hash collision).
* When the statement `some_dict[5] = "Python"` is executed, the existing value "JavaScript" is overwritten with "Python" because Python recognizes `5` and `5.0` as the same keys of the dictionary `some_dict`.
* This StackOverflow [answer](https://stackoverflow.com/a/32211042/4354153) explains beautifully the rationale behind it.

---

### ▶ The disorder within order
<!-- Example ID: 91bff1f8-541d-455a-9de4-6cd8ff00ea66 --->
```py
from collections import OrderedDict

dictionary = dict()
dictionary[1] = 'a'; dictionary[2] = 'b';

ordered_dict = OrderedDict()
ordered_dict[1] = 'a'; ordered_dict[2] = 'b';

another_ordered_dict = OrderedDict()
another_ordered_dict[2] = 'b'; another_ordered_dict[1] = 'a';

class DictWithHash(dict):
    """
    A dict that also implements __hash__ magic.
    """
    __hash__ = lambda self: 0

class OrderedDictWithHash(OrderedDict):
    """
    A dict that also implements __hash__ magic.
    """
    __hash__ = lambda self: 0
```

**Output**
```py
>>> dictionary == ordered_dict # If a == b
True
>>> dictionary == another_ordered_dict # and b == c
True
>>> ordered_dict == another_ordered_dict # the why isn't c == a ??
False

# We all know that a set consists of only unique elements,
# let's try making a set of these dictionaries and see what happens...

>>> len({dictionary, ordered_dict, another_ordered_dict})
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'dict'

# Makes sense since dict don't have __hash__ implemented, let's use
# our wrapper classes.
>>> dictionary = DictWithHash()
>>> dictionary[1] = 'a'; dictionary[2] = 'b';
>>> ordered_dict = OrderedDictWithHash()
>>> ordered_dict[1] = 'a'; ordered_dict[2] = 'b';
>>> another_ordered_dict = OrderedDictWithHash()
>>> another_ordered_dict[2] = 'b'; another_ordered_dict[1] = 'a';
>>> len({dictionary, ordered_dict, another_ordered_dict})
1
>>> len({ordered_dict, another_ordered_dict, dictionary}) # changing the order
2
```

What is going on here?

#### 💡 설명:

- The reason why intransitive equality didn't hold among `dictionary`, `ordered_dict` and `another_ordered_dict` is because of the way `__eq__` method is implemented in `OrderedDict` class. From the [docs](https://docs.python.org/3/library/collections.html#ordereddict-objects)
    > Equality tests between OrderedDict objects are order-sensitive and are implemented as `list(od1.items())==list(od2.items())`. Equality tests between `OrderedDict` objects and other Mapping objects are order-insensitive like regular dictionaries.
- The reason for this equality is behavior  is that it allows `OrderedDict` objects to be directly substituted anywhere a regular dictionary is used.
- Okay, so why did changing the order affect the lenght of the generated `set` object? The answer is the lack of intransitive equality only. Since sets are "unordered" collections of unique elements, the order in which elements are inserted shouldn't matter. But in this case, it does matter. Let's break it down a bit,
    ```py
    >>> some_set = set()
    >>> some_set.add(dictionary) # these are the mapping objects from the snippets above
    >>> ordered_dict in some_set
    True
    >>> some_set.add(ordered_dict)
    >>> len(some_set)
    1
    >>> another_ordered_dict in some_set
    True
    >>> some_set.add(another_ordered_dict)
    >>> len(some_set)
    1

    >>> another_set = set()
    >>> another_set.add(ordered_dict)
    >>> another_ordered_dict in another_set
    False
    >>> another_set.add(another_ordered_dict)
    >>> len(another_set)
    2
    >>> dictionary in another_set
    True
    >>> another_set.add(another_ordered_dict)
    >>> len(another_set)
    2
    ```
    So the inconsistency is due to `another_ordered_dict in another_set` being False because `ordered_dict` was already present in `another_set` and as observed before, `ordered_dict == another_ordered_dict` is `False`.


---

### ▶ 파이썬의 예외처리
<!-- Example ID: b4349443-e89f-4d25-a109-82616be9d41a --->
```py
def some_func():
    try:
        return 'from_try'
    finally:
        return 'from_finally'

def another_func():
    for _ in range(3):
        try:
            continue
        finally:
            print("Finally!")

def one_more_func(): # 아마 맞추기 어려울겁니다!
    try:
        for i in range(3):
            try:
                1 / i
            except ZeroDivisionError:
                # raise 후, 루프 밖에서 예외처리
                raise ZeroDivisionError("A trivial divide by zero error")
            finally:
                print("Iteration", i)
                break
    except ZeroDivisionError as e:
        print("Zero division error ocurred", e)
```

**결과:**

```py
>>> some_func()
'from_finally'

>>> another_func()
Finally!
Finally!
Finally!

>>> 1 / 0
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: division by zero

>>> one_more_func()
Iteration 0

```

#### 💡 설명:

- `return`, `break` 혹은 `continue` 가 파이썬의 `try`...`finally` 안에서 실행될 경우, `try` 블럭 안의 코드가 실행된 후 `finally` 블럭 역시 항상 실행됩니다.
- 함수의 리턴값은 항상 마지막에 실행된 `return` 문이 리턴하는 값인데, `finally` 문은 항상 호출되는 코드 블럭이기에 항상 `finally` 문에 속한 `return` 이 항상 마지막에 실행됩니다.
- 세번째 예제의 경우 좀 의아할 수 있습니다. 조심해야 할 점은, 만약 `finally` 블럭 안에서 `return` 혹은 `break` 문이 사용될 경우, 기존에 저장되있던 예외처리는 버려집니다.

---

### ▶ Deep down, we're all the same
<!-- Example ID: 8f99a35f-1736-43e2-920d-3b78ec35da9b --->
```py
class WTF:
  pass
```

**Output:**
```py
>>> WTF() == WTF() # two different instances can't be equal
False
>>> WTF() is WTF() # identities are also different
False
>>> hash(WTF()) == hash(WTF()) # hashes _should_ be different as well
True
>>> id(WTF()) == id(WTF())
True
```

#### 💡 설명:

* When `id` was called, Python created a `WTF` class object and passed it to the `id` function. The `id` function takes its `id` (its memory location), and throws away the object. The object is destroyed.
* When we do this twice in succession, Python allocates the same memory location to this second object as well. Since (in CPython) `id` uses the memory location as the object id, the id of the two objects is the same.
* So, object's id is unique only for the lifetime of the object. After the object is destroyed, or before it is created, something else can have the same id.
* But why did the `is` operator evaluated to `False`? Let's see with this snippet.
  ```py
  class WTF(object):
    def __init__(self): print("I")
    def __del__(self): print("D")
  ```

  **Output:**
  ```py
  >>> WTF() is WTF()
  I
  I
  D
  D
  False
  >>> id(WTF()) == id(WTF())
  I
  D
  I
  D
  True
  ```
  As you may observe, the order in which the objects are destroyed is what made all the difference here.

---

### ▶ For what?
<!-- Example ID: 64a9dccf-5083-4bc9-98aa-8aeecde4f210 --->
```py
some_string = "wtf"
some_dict = {}
for i, some_dict[i] in enumerate(some_string):
    pass
```

**Output:**
```py
>>> some_dict # An indexed dict is created.
{0: 'w', 1: 't', 2: 'f'}
```

####  💡 설명:

* A `for` statement is defined in the [Python grammar](https://docs.python.org/3/reference/grammar.html) as:
  ```
  for_stmt: 'for' exprlist 'in' testlist ':' suite ['else' ':' suite]
  ```
  Where `exprlist` is the assignment target. This means that the equivalent of `{exprlist} = {next_value}` is **executed for each item** in the iterable.
  An interesting example that illustrates this:
  ```py
  for i in range(4):
      print(i)
      i = 10
  ```

  **Output:**
  ```
  0
  1
  2
  3
  ```

  Did you expect the loop to run just once?

  **💡 설명:**

  - The assignment statement `i = 10` never affects the iterations of the loop because of the way for loops work in Python. Before the beginning of every iteration, the next item provided by the iterator (`range(4)` this case) is unpacked and assigned the target list variables (`i` in this case).

* The `enumerate(some_string)` function yields a new value `i` (A counter going up) and a character from the `some_string` in each iteration. It then sets the (just assigned) `i` key of the dictionary `some_dict` to that character. The unrolling of the loop can be simplified as:
  ```py
  >>> i, some_dict[i] = (0, 'w')
  >>> i, some_dict[i] = (1, 't')
  >>> i, some_dict[i] = (2, 'f')
  >>> some_dict
  ```

---

### ▶ Evaluation time discrepancy
<!-- Example ID: 6aa11a4b-4cf1-467a-b43a-810731517e98 --->
1\.
```py
array = [1, 8, 15]
g = (x for x in array if array.count(x) > 0)
array = [2, 8, 22]
```

**Output:**
```py
>>> print(list(g))
[8]
```

2\.

```py
array_1 = [1,2,3,4]
g1 = (x for x in array_1)
array_1 = [1,2,3,4,5]

array_2 = [1,2,3,4]
g2 = (x for x in array_2)
array_2[:] = [1,2,3,4,5]
```

**Output:**
```py
>>> print(list(g1))
[1,2,3,4]

>>> print(list(g2))
[1,2,3,4,5]
```

3\.

```py
array_3 = [1, 2, 3]
array_4 = [10, 20, 30]
g = (i + j for i in array_3 for j in array_4)

array_3 = [4, 5, 6]
array_4 = [400, 500, 600]
```

**Output:**
```py
>>> print(list(g))
[401, 501, 601, 402, 502, 602, 403, 503, 603]
```

#### 💡 설명

- In a [generator](https://wiki.python.org/moin/Generators) expression, the `in` clause is evaluated at declaration time, but the conditional clause is evaluated at runtime.
- So before runtime, `array` is re-assigned to the list `[2, 8, 22]`, and since out of `1`, `8` and `15`, only the count of `8` is greater than `0`, the generator only yields `8`.
- The differences in the output of `g1` and `g2` in the second part is due the way variables `array_1` and `array_2` are re-assigned values.
- In the first case, `array_1` is binded to the new object `[1,2,3,4,5]` and since the `in` clause is evaluated at the declaration time it still refers to the old object `[1,2,3,4]` (which is not destroyed).
- In the second case, the slice assignment to `array_2` updates the same old object `[1,2,3,4]` to `[1,2,3,4,5]`. Hence both the `g2` and `array_2` still have reference to the same object (which has now been updated to `[1,2,3,4,5]`).
- Okay, going by the logic discussed so far, shouldn't be the value of `list(g)` in the third snippet be `[11, 21, 31, 12, 22, 32, 13, 23, 33]`? (because `array_3` and `array_4` are going to behave just like `array_1`). The reason why (only) `array_4` values got updated is explained in [PEP-289](https://www.python.org/dev/peps/pep-0289/#the-details)

    > Only the outermost for-expression is evaluated immediately, the other expressions are deferred until the generator is run.

---

### ▶ Messing around with `is` operator
<!-- Example ID: 230fa2ac-ab36-4ad1-b675-5f5a1c1a6217 --->
The following is a very famous example present all over the internet.

1\.
```py
>>> a = 256
>>> b = 256
>>> a is b
True

>>> a = 257
>>> b = 257
>>> a is b
False
```

2\.

```py
>>> a = []
>>> b = []
>>> a is b
False

>>> a = tuple()
>>> b = tuple()
>>> a is b
True
```

3\.
**Output (< Python 3.7)**
```
>>> a, b = 257, 257
True

>>> a = 257; b = 257
>>> a is b
True
```

**Output (Python 3.7)**
```
>>> a, b = 257, 257
False

>>> a = 257; b = 257
>>> a is b
True
```

#### 💡 설명:

**The difference between `is` and `==`**

* `is` operator checks if both the operands refer to the same object (i.e., it checks if the identity of the operands matches or not).
* `==` operator compares the values of both the operands and checks if they are the same.
* So `is` is for reference equality and `==` is for value equality. An example to clear things up,
  ```py
  >>> class A: pass
  >>> A() is A() # These are two empty objects at two different memory locations.
  False
  ```

**`256` is an existing object but `257` isn't**

When you start up python the numbers from `-5` to `256` will be allocated. These numbers are used a lot, so it makes sense just to have them ready.

Quoting from https://docs.python.org/3/c-api/long.html
> The current implementation keeps an array of integer objects for all integers between -5 and 256, when you create an int in that range you just get back a reference to the existing object. So it should be possible to change the value of 1. I suspect the behavior of Python, in this case, is undefined. :-)

```py
>>> id(256)
10922528
>>> a = 256
>>> b = 256
>>> id(a)
10922528
>>> id(b)
10922528
>>> id(257)
140084850247312
>>> x = 257
>>> y = 257
>>> id(x)
140084850247440
>>> id(y)
140084850247344
```

Here the interpreter isn't smart enough while executing `y = 257` to recognize that we've already created an integer of the value `257,` and so it goes on to create another object in the memory.

Similar optimization applies to other **immutable** objects like empty tuples as well. Since lists are mutable, that's why `[] is []` will return `False` and `() is ()` will return `True`. This explains our second snippet. Let's move on to the third one,

**Both `a` and `b` refer to the same object when initialized with same value in the same line.**

**Output (< Python 3.7)**
```py
>>> a, b = 257, 257
>>> id(a)
140640774013296
>>> id(b)
140640774013296
>>> a = 257
>>> b = 257
>>> id(a)
140640774013392
>>> id(b)
140640774013488
```

* When a and b are set to `257` in the same line, the Python interpreter creates a new object, then references the second variable at the same time. If you do it on separate lines, it doesn't "know" that there's already `257` as an object.
* It's a compiler optimization and specifically applies to the interactive environment. When you enter two lines in a live interpreter, they're compiled separately, therefore optimized separately. If you were to try this example in a `.py` file, you would not see the same behavior, because the file is compiled all at once.
* Why didn't this work for Python 3.7? The abstract reason is because such compiler optimizations are implementation specific (i.e. may change with version, OS, etc). I'm still figuring out what exact implementation change cause the issue, you can check out this [issue](https://github.com/satwikkansal/wtfpython/issues/100) for updates.

---

### ▶ A tic-tac-toe where X wins in the first attempt!
<!-- Example ID: 69329249-bdcb-424f-bd09-cca2e6705a7a --->
```py
# Let's initialize a row
row = [""]*3 #row i['', '', '']
# Let's make a board
board = [row]*3
```

**Output:**
```py
>>> board
[['', '', ''], ['', '', ''], ['', '', '']]
>>> board[0]
['', '', '']
>>> board[0][0]
''
>>> board[0][0] = "X"
>>> board
[['X', '', ''], ['X', '', ''], ['X', '', '']]
```

We didn't assign 3 "X"s or did we?

#### 💡 설명:

When we initialize `row` variable, this visualization explains what happens in the memory

![image](images/tic-tac-toe/after_row_initialized.png)

And when the `board` is initialized by multiplying the `row`, this is what happens inside the memory (each of the elements `board[0]`, `board[1]` and `board[2]` is a reference to the same list referred by `row`)

![image](images/tic-tac-toe/after_board_initialized.png)

We can avoid this scenario here by not using `row` variable to generate `board`. (Asked in [this](https://github.com/satwikkansal/wtfpython/issues/68) issue).

```py
>>> board = [['']*3 for _ in range(3)]
>>> board[0][0] = "X"
>>> board
[['X', '', ''], ['', '', ''], ['', '', '']]
```

---

### ▶ The sticky output function
<!-- Example ID: 4dc42f77-94cb-4eb5-a120-8203d3ed7604 --->
```py
funcs = []
results = []
for x in range(7):
    def some_func():
        return x
    funcs.append(some_func)
    results.append(some_func())  # note the function call here

funcs_results = [func() for func in funcs]
```

**Output:**
```py
>>> results
[0, 1, 2, 3, 4, 5, 6]
>>> funcs_results
[6, 6, 6, 6, 6, 6, 6]
```
Even when the values of `x` were different in every iteration prior to appending `some_func` to `funcs`, all the functions return 6.

//OR

```py
>>> powers_of_x = [lambda x: x**i for i in range(10)]
>>> [f(2) for f in powers_of_x]
[512, 512, 512, 512, 512, 512, 512, 512, 512, 512]
```

#### 💡 설명

- When defining a function inside a loop that uses the loop variable in its body, the loop function's closure is bound to the variable, not its value. So all of the functions use the latest value assigned to the variable for computation.

- To get the desired behavior you can pass in the loop variable as a named variable to the function. **Why this works?** Because this will define the variable again within the function's scope.

    ```py
    funcs = []
    for x in range(7):
        def some_func(x=x):
            return x
        funcs.append(some_func)
    ```

    **Output:**
    ```py
    >>> funcs_results = [func() for func in funcs]
    >>> funcs_results
    [0, 1, 2, 3, 4, 5, 6]
    ```

---

### ▶ The chicken-egg problem
<!-- Example ID: 60730dc2-0d79-4416-8568-2a63323b3ce8 --->
1\.
```py
>>> isinstance(3, int)
True
>>> isinstance(type, object)
True
>>> isinstance(object, type)
True
```

2\. So which is the ultimate, base class? And wait, there's more to the confusion

```py
>>> class A: pass
>>> isinstance(A, A)
False
>>> isinstance(type, type)
True
>>> isinstance(object, object)
True
```

3\.

```py
>>> issubclass(int, object)
True
>>> issubclass(type, object)
True
>>> issubclass(object, type)
False
```


#### 💡 설명

- `type` is a [metaclass](https://realpython.com/python-metaclasses/) in Python.
- **Everything** is an `object` in Python, which includes classes as well as their objects (instances).
- class `type` is the metaclass of class `object`, and every class (including `type`) has inherited directly or indirectly from `object`.
- There is no real base class among `object` and `type`. The confusion in the above snippets is arising because we're thinking these relationships (`issubclass` and `isinstance`) in terms of Python classes. The relationship between `object` and `type` can't be reproduced in pure python. To be more precise the following relationships can't be reproduced in pure Python,
    + class A is instance of class B, and class B is an instance of class A.
    + class A is an instance of itself.
- These relationships between `object` and `type` (both being instances of eachother as well as themselves) exist in Python because of "cheating" at implementation level.

---

### ▶ `is not ...` is not `is (not ...)`
<!-- Example ID: b26fb1ed-0c7d-4b9c-8c6d-94a58a055c0d --->
```py
>>> 'something' is not None
True
>>> 'something' is (not None)
False
```

#### 💡 설명

- `is not` is a single binary operator, and has behavior different than using `is` and `not` separated.
- `is not` evaluates to `False` if the variables on either side of the operator point to the same object and `True` otherwise.

---

### ▶ The surprising comma
<!-- Example ID: 31a819c8-ed73-4dcc-84eb-91bedbb51e58 --->
**Output:**
```py
>>> def f(x, y,):
...     print(x, y)
...
>>> def g(x=4, y=5,):
...     print(x, y)
...
>>> def h(x, **kwargs,):
  File "<stdin>", line 1
    def h(x, **kwargs,):
                     ^
SyntaxError: invalid syntax
>>> def h(*args,):
  File "<stdin>", line 1
    def h(*args,):
                ^
SyntaxError: invalid syntax
```

#### 💡 설명:

- Trailing comma is not always legal in formal parameters list of a Python function.
-  In Python, the argument list is defined partially with leading commas and partially with trailing commas. This conflict causes situations where a comma is trapped in the middle, and no rule accepts it.
-  **Note:** The trailing comma problem is [fixed in Python 3.6](https://bugs.python.org/issue9232). The remarks in [this](https://bugs.python.org/issue9232#msg248399) post discuss in brief different usages of trailing commas in Python.

---

### ▶ Strings and the backslashes
<!-- Example ID: 6ae622c3-6d99-4041-9b33-507bd1a4407b --->
**Output:**
```py
>>> print("\"")
"

>>> print(r"\"")
\"

>>> print(r"\")
File "<stdin>", line 1
    print(r"\")
              ^
SyntaxError: EOL while scanning string literal

>>> r'\'' == "\\'"
True
```

#### 💡 설명

- In a normal python string, the backslash is used to escape characters that may have special meaning (like single-quote, double-quote and the backslash itself).
    ```py
    >>> 'wt\"f'
    'wt"f'
    ```
- In a raw string literal (as indicated by the prefix `r`),  the backslashes pass themselves as is along with the behavior of escaping the following character.
    ```py
    >>> r'wt\"f' == 'wt\\"f'
    True
    >>> print(repr(r'wt\"f')
    'wt\\"f'

    >>> print("\n")

    >>> print(r"\\n")
    '\\\\n'
    ```
- This means when a parser encounters a backslash in a raw string, it expects another character following it. And in our case (`print(r"\")`), the backslash escaped the trailing quote, leaving the parser without a terminating quote (hence the `SyntaxError`). That's why backslashes don't work at the end of a raw string.

---

### ▶ not knot!
<!-- Example ID: 7034deb1-7443-417d-94ee-29a800524de8 --->
```py
x = True
y = False
```

**Output:**
```py
>>> not x == y
True
>>> x == not y
  File "<input>", line 1
    x == not y
           ^
SyntaxError: invalid syntax
```

#### 💡 설명:

* Operator precedence affects how an expression is evaluated, and `==` operator has higher precedence than `not` operator in Python.
* So `not x == y` is equivalent to `not (x == y)` which is equivalent to `not (True == False)` finally evaluating to `True`.
* But `x == not y` raises a `SyntaxError` because it can be thought of being equivalent to `(x == not) y` and not `x == (not y)` which you might have expected at first sight.
* The parser expected the `not` token to be a part of the `not in` operator (because both `==` and `not in` operators have the same precedence), but after not being able to find an `in` token following the `not` token, it raises a `SyntaxError`.

---

### ▶ Half triple-quoted strings
<!-- Example ID: c55da3e2-1034-43b9-abeb-a7a970a2ad9e --->
**Output:**
```py
>>> print('wtfpython''')
wtfpython
>>> print("wtfpython""")
wtfpython
>>> # The following statements raise `SyntaxError`
>>> # print('''wtfpython')
>>> # print("""wtfpython")
```

#### 💡 설명:
+ Python supports implicit [string literal concatenation](https://docs.python.org/2/reference/lexical_analysis.html#string-literal-concatenation), Example,
  ```
  >>> print("wtf" "python")
  wtfpython
  >>> print("wtf" "") # or "wtf"""
  wtf
  ```
+ `'''` and `"""` are also string delimiters in Python which causes a SyntaxError because the Python interpreter was expecting a terminating triple quote as delimiter while scanning the currently encountered triple quoted string literal.

---

### ▶ Midnight time doesn't exist?
<!-- Example ID: 1bce8294-5619-4d70-8ce3-fe0bade690d1 --->
```py
from datetime import datetime

midnight = datetime(2018, 1, 1, 0, 0)
midnight_time = midnight.time()

noon = datetime(2018, 1, 1, 12, 0)
noon_time = noon.time()

if midnight_time:
    print("Time at midnight is", midnight_time)

if noon_time:
    print("Time at noon is", noon_time)
```

**Output:**
```sh
('Time at noon is', datetime.time(12, 0))
```
The midnight time is not printed.

#### 💡 설명:

Before Python 3.5, the boolean value for `datetime.time` object was considered to be `False` if it represented midnight in UTC. It is error-prone when using the `if obj:` syntax to check if the `obj` is null or some equivalent of "empty."

---

### ▶ What's wrong with booleans?
<!-- Example ID: 0bba5fa7-9e6d-4cd2-8b94-952d061af5dd --->
1\.
```py
# A simple example to count the number of booleans and
# integers in an iterable of mixed data types.
mixed_list = [False, 1.0, "some_string", 3, True, [], False]
integers_found_so_far = 0
booleans_found_so_far = 0

for item in mixed_list:
    if isinstance(item, int):
        integers_found_so_far += 1
    elif isinstance(item, bool):
        booleans_found_so_far += 1
```

**Output:**
```py
>>> integers_found_so_far
4
>>> booleans_found_so_far
0
```


2\.
```py
>>> some_bool = True
>>> "wtf" * some_bool
'wtf'
>>> some_bool = False
>>> "wtf" * some_bool
''
```

#### 💡 설명:

* `bool` is a subclass of `int` in Python
    ```py
    >>> issubclass(bool, int)
    True
    >>> issubclass(int, bool)
    False
    ```
* And thus, `True` and `False` are instances of `int`
  ```py
  >>> isinstance(True, int)
  True
  >>> isinstance(False, int)
  True
  ```

* The integer value of `True` is `1` and that of `False` is `0`.
  ```py
  >>> int(True)
  1
  >>> int(False)
  0
  ```

* See this StackOverflow [answer](https://stackoverflow.com/a/8169049/4354153) for the rationale behind it.

---

### ▶ Class attributes and instance attributes
<!-- Example ID: 6f332208-33bd-482d-8106-42863b739ed9 --->
1\.
```py
class A:
    x = 1

class B(A):
    pass

class C(A):
    pass
```

**Output:**
```py
>>> A.x, B.x, C.x
(1, 1, 1)
>>> B.x = 2
>>> A.x, B.x, C.x
(1, 2, 1)
>>> A.x = 3
>>> A.x, B.x, C.x
(3, 2, 3)
>>> a = A()
>>> a.x, A.x
(3, 3)
>>> a.x += 1
>>> a.x, A.x
(4, 3)
```

2\.
```py
class SomeClass:
    some_var = 15
    some_list = [5]
    another_list = [5]
    def __init__(self, x):
        self.some_var = x + 1
        self.some_list = self.some_list + [x]
        self.another_list += [x]
```

**Output:**

```py
>>> some_obj = SomeClass(420)
>>> some_obj.some_list
[5, 420]
>>> some_obj.another_list
[5, 420]
>>> another_obj = SomeClass(111)
>>> another_obj.some_list
[5, 111]
>>> another_obj.another_list
[5, 420, 111]
>>> another_obj.another_list is SomeClass.another_list
True
>>> another_obj.another_list is some_obj.another_list
True
```

#### 💡 설명:

* Class variables and variables in class instances are internally handled as dictionaries of a class object. If a variable name is not found in the dictionary of the current class, the parent classes are searched for it.
* The `+=` operator modifies the mutable object in-place without creating a new object. So changing the attribute of one instance affects the other instances and the class attribute as well.

---

### ▶ yielding None
<!-- Example ID: 5a40c241-2c30-40d0-8ba9-cf7e097b3b53 --->
```py
some_iterable = ('a', 'b')

def some_func(val):
    return "something"
```

**Output:**
```py
>>> [x for x in some_iterable]
['a', 'b']
>>> [(yield x) for x in some_iterable]
<generator object <listcomp> at 0x7f70b0a4ad58>
>>> list([(yield x) for x in some_iterable])
['a', 'b']
>>> list((yield x) for x in some_iterable)
['a', None, 'b', None]
>>> list(some_func((yield x)) for x in some_iterable)
['a', 'something', 'b', 'something']
```

#### 💡 설명:
- Source and explanation can be found here: https://stackoverflow.com/questions/32139885/yield-in-list-comprehensions-and-generator-expressions
- Related bug report: http://bugs.python.org/issue10544

---

### ▶ Mutating the immutable!
<!-- Example ID: 15a9e782-1695-43ea-817a-a9208f6bb33d --->
```py
some_tuple = ("A", "tuple", "with", "values")
another_tuple = ([1, 2], [3, 4], [5, 6])
```

**Output:**
```py
>>> some_tuple[2] = "change this"
TypeError: 'tuple' object does not support item assignment
>>> another_tuple[2].append(1000) #This throws no error
>>> another_tuple
([1, 2], [3, 4], [5, 6, 1000])
>>> another_tuple[2] += [99, 999]
TypeError: 'tuple' object does not support item assignment
>>> another_tuple
([1, 2], [3, 4], [5, 6, 1000, 99, 999])
```

But I thought tuples were immutable...

#### 💡 설명:

* Quoting from https://docs.python.org/2/reference/datamodel.html

    > Immutable sequences
        An object of an immutable sequence type cannot change once it is created. (If the object contains references to other objects, these other objects may be mutable and may be modified; however, the collection of objects directly referenced by an immutable object cannot change.)

* `+=` operator changes the list in-place. The item assignment doesn't work, but when the exception occurs, the item has already been changed in place.

---

### ▶ The disappearing variable from outer scope
<!-- Example ID: 7f1e71b6-cb3e-44fb-aa47-87ef1b7decc8 --->
```py
e = 7
try:
    raise Exception()
except Exception as e:
    pass
```

**Output (Python 2.x):**
```py
>>> print(e)
# prints nothing
```

**Output (Python 3.x):**
```py
>>> print(e)
NameError: name 'e' is not defined
```

#### 💡 설명:

* Source: https://docs.python.org/3/reference/compound_stmts.html#except

  When an exception has been assigned using `as` target, it is cleared at the end of the except clause. This is as if

  ```py
  except E as N:
      foo
  ```

  was translated into

  ```py
  except E as N:
      try:
          foo
      finally:
          del N
  ```

  This means the exception must be assigned to a different name to be able to refer to it after the except clause. Exceptions are cleared because, with the traceback attached to them, they form a reference cycle with the stack frame, keeping all locals in that frame alive until the next garbage collection occurs.

* The clauses are not scoped in Python. Everything in the example is present in the same scope, and the variable `e` got removed due to the execution of the `except` clause. The same is not the case with functions which have their separate inner-scopes. The example below illustrates this:

     ```py
     def f(x):
         del(x)
         print(x)

     x = 5
     y = [5, 4, 3]
     ```

     **Output:**
     ```py
     >>>f(x)
     UnboundLocalError: local variable 'x' referenced before assignment
     >>>f(y)
     UnboundLocalError: local variable 'x' referenced before assignment
     >>> x
     5
     >>> y
     [5, 4, 3]
     ```

* In Python 2.x the variable name `e` gets assigned to `Exception()` instance, so when you try to print, it prints nothing.

    **Output (Python 2.x):**
    ```py
    >>> e
    Exception()
    >>> print e
    # Nothing is printed!
    ```

---

### ▶ When True is actually False
<!-- Example ID: c8317047-48ae-4306-af5a-04c6d8b7c2b9 --->
```py
True = False
if True == False:
    print("I've lost faith in truth!")
```

**Output:**
```
I've lost faith in truth!
```

#### 💡 설명:

- Initially, Python used to have no `bool` type (people used 0 for false and non-zero value like 1 for true). Then they added `True`, `False`, and a `bool` type, but, for backward compatibility, they couldn't make `True` and `False` constants- they just were built-in variables.
- Python 3 was backward-incompatible, so it was now finally possible to fix that, and so this example won't work with Python 3.x!

---

### ▶ Lossy zip of iterators
<!-- Example ID: c28ed154-e59f-4070-8eb6-8967a4acac6d --->
```py
>>> numbers = list(range(7))
>>> numbers
[0, 1, 2, 3, 4, 5, 6]
>>> first_three, remaining = numbers[:3], numbers[3:]
>>> first_three, remaining
([0, 1, 2], [3, 4, 5, 6])
>>> numbers_iter = iter(numbers)
>>> list(zip(numbers_iter, first_three))
[(0, 0), (1, 1), (2, 2)]
# so far so good, let's zip the remaining
>>> list(zip(numbers_iter, remaining))
[(4, 3), (5, 4), (6, 5)]
```
Where did element `3` go from the `numbers` list?

#### 💡 설명:

- From Python [docs](https://docs.python.org/3.3/library/functions.html#zip), here's an approximate implementation of zip function,
    ```py
    def zip(*iterables):
        sentinel = object()
        iterators = [iter(it) for it in iterables]
        while iterators:
            result = []
            for it in iterators:
                elem = next(it, sentinel)
                if elem is sentinel:
                    return
                result.append(elem)
            yield tuple(result)
    ```
- So the function takes in arbitrary number of itreable objects, adds each of their items to the `result` list by calling the `next` function on them, and stops whenever any of the iterable is exhausted.
- The caveat here is when any iterable is exhausted, the existing elements in the `result` list are discarded. That's what happened with `3` in the `numbers_iter`.
- The correct way to do the above using `zip` would be,
    ```py
    >>> numbers = list(range(7))
    >>> numbers_iter = iter(numbers)
    >>> list(zip(first_three, numbers_iter))
    [(0, 0), (1, 1), (2, 2)]
    >>> list(zip(remaining, numbers_iter))
    [(3, 3), (4, 4), (5, 5), (6, 6)]
    ```
    The first argument of zip should be the one with fewest elements.

---

### ▶ From filled to None in one instruction...
<!-- Example ID: 9a0d5335-efe5-4eae-af44-584d15233066 --->
```py
some_list = [1, 2, 3]
some_dict = {
  "key_1": 1,
  "key_2": 2,
  "key_3": 3
}

some_list = some_list.append(4)
some_dict = some_dict.update({"key_4": 4})
```

**Output:**
```py
>>> print(some_list)
None
>>> print(some_dict)
None
```

#### 💡 설명

Most methods that modify the items of sequence/mapping objects like `list.append`, `dict.update`, `list.sort`, etc. modify the objects in-place and return `None`. The rationale behind this is to improve performance by avoiding making a copy of the object if the operation can be done in-place (Referred from [here](http://docs.python.org/2/faq/design.html#why-doesn-t-list-sort-return-the-sorted-list))

---

### ▶ Subclass relationships
<!-- Example ID: 9f6d8cf0-e1b5-42d0-84a0-4cfab25a0bc0 --->
**Output:**
```py
>>> from collections import Hashable
>>> issubclass(list, object)
True
>>> issubclass(object, Hashable)
True
>>> issubclass(list, Hashable)
False
```

The Subclass relationships were expected to be transitive, right? (i.e., if `A` is a subclass of `B`, and `B` is a subclass of `C`, the `A` _should_ a subclass of `C`)

#### 💡 설명:

* Subclass relationships are not necessarily transitive in Python. Anyone is allowed to define their own, arbitrary `__subclasscheck__` in a metaclass.
* When `issubclass(cls, Hashable)` is called, it simply looks for non-Falsey "`__hash__`" method in `cls` or anything it inherits from.
* Since `object` is hashable, but `list` is non-hashable, it breaks the transitivity relation.
* More detailed explanation can be found [here](https://www.naftaliharris.com/blog/python-subclass-intransitivity/).

---

### ▶ The mysterious key type conversion
<!-- Example ID: 00f42dd0-b9ef-408d-9e39-1bc209ce3f36 --->
```py
class SomeClass(str):
    pass

some_dict = {'s':42}
```

**Output:**
```py
>>> type(list(some_dict.keys())[0])
str
>>> s = SomeClass('s')
>>> some_dict[s] = 40
>>> some_dict # expected: Two different keys-value pairs
{'s': 40}
>>> type(list(some_dict.keys())[0])
str
```

#### 💡 설명:

* Both the object `s` and the string `"s"` hash to the same value because `SomeClass` inherits the `__hash__` method of `str` class.
* `SomeClass("s") == "s"` evaluates to `True` because `SomeClass` also inherits `__eq__` method from `str` class.
* Since both the objects hash to the same value and are equal, they are represented by the same key in the dictionary.
* For the desired behavior, we can redefine the `__eq__` method in `SomeClass`
  ```py
  class SomeClass(str):
    def __eq__(self, other):
        return (
            type(self) is SomeClass
            and type(other) is SomeClass
            and super().__eq__(other)
        )

    # When we define a custom __eq__, Python stops automatically inheriting the
    # __hash__ method, so we need to define it as well
    __hash__ = str.__hash__

  some_dict = {'s':42}
  ```

  **Output:**
  ```py
  >>> s = SomeClass('s')
  >>> some_dict[s] = 40
  >>> some_dict
  {'s': 40, 's': 42}
  >>> keys = list(some_dict.keys())
  >>> type(keys[0]), type(keys[1])
  (__main__.SomeClass, str)
  ```

---

### ▶ Let's see if you can guess this?
<!-- Example ID: 81aa9fbe-bd63-4283-b56d-6fdd14c9105e --->
```py
a, b = a[b] = {}, 5
```

**Output:**
```py
>>> a
{5: ({...}, 5)}
```

#### 💡 설명:

* According to [Python language reference](https://docs.python.org/2/reference/simple_stmts.html#assignment-statements), assignment statements have the form
  ```
  (target_list "=")+ (expression_list | yield_expression)
  ```
  and

> An assignment statement evaluates the expression list (remember that this can be a single expression or a comma-separated list, the latter yielding a tuple) and assigns the single resulting object to each of the target lists, from left to right.

* The `+` in `(target_list "=")+` means there can be **one or more** target lists. In this case, target lists are `a, b` and `a[b]` (note the expression list is exactly one, which in our case is `{}, 5`).

* After the expression list is evaluated, it's value is unpacked to the target lists from **left to right**. So, in our case, first the `{}, 5` tuple is unpacked to `a, b` and we now have `a = {}` and `b = 5`.

* `a` is now assigned to `{}` which is a mutable object.

* The second target list is `a[b]` (you may expect this to throw an error because both `a` and `b` have not been defined in the statements before. But remember, we just assigned `a` to `{}` and `b` to `5`).

* Now, we are setting the key `5` in the dictionary to the tuple `({}, 5)` creating a circular reference (the `{...}` in the output refers to the same object that `a` is already referencing). Another simpler example of circular reference could be
  ```py
  >>> some_list = some_list[0] = [0]
  >>> some_list
  [[...]]
  >>> some_list[0]
  [[...]]
  >>> some_list is some_list[0]
  True
  >>> some_list[0][0][0][0][0][0] == some_list
  True
  ```
  Similar is the case in our example (`a[b][0]` is the same object as `a`)

* So to sum it up, you can break the example down to
  ```py
  a, b = {}, 5
  a[b] = a, b
  ```
  And the circular reference can be justified by the fact that `a[b][0]` is the same object as `a`
  ```py
  >>> a[b][0] is a
  True
  ```

---

---

## Section: Appearances are deceptive!

### ▶ Skipping lines?
<!-- Example ID: d50bbde1-fb9d-4735-9633-3444b9d2f417 --->
**Output:**
```py
>>> value = 11
>>> valuе = 32
>>> value
11
```

Wut?

**Note:** The easiest way to reproduce this is to simply copy the statements from the above snippet and paste them into your file/shell.

#### 💡 설명

Some non-Western characters look identical to letters in the English alphabet but are considered distinct by the interpreter.

```py
>>> ord('е') # cyrillic 'e' (Ye)
1077
>>> ord('e') # latin 'e', as used in English and typed using standard keyboard
101
>>> 'е' == 'e'
False

>>> value = 42 # latin e
>>> valuе = 23 # cyrillic 'e', Python 2.x interpreter would raise a `SyntaxError` here
>>> value
42
```

The built-in `ord()` function returns a character's Unicode [code point](https://en.wikipedia.org/wiki/Code_point), and different code positions of Cyrillic 'e' and Latin 'e' justify the behavior of the above example.

---

### ▶ Teleportation
<!-- Example ID: edafe923-0c20-4315-b6e1-0c31abfc38f5 --->
```py
import numpy as np

def energy_send(x):
    # Initializing a numpy array
    np.array([float(x)])

def energy_receive():
    # Return an empty numpy array
    return np.empty((), dtype=np.float).tolist()
```

**Output:**
```py
>>> energy_send(123.456)
>>> energy_receive()
123.456
```

Where's the Nobel Prize?

#### 💡 설명:

* Notice that the numpy array created in the `energy_send` function is not returned, so that memory space is free to reallocate.
* `numpy.empty()` returns the next free memory slot without reinitializing it. This memory spot just happens to be the same one that was just freed (usually, but not always).

---

### ▶ Well, something is fishy...
<!-- Example ID: cb6a37c5-74f7-44ca-b58c-3b902419b362 --->
```py
def square(x):
    """
    A simple function to calculate the square of a number by addition.
    """
    sum_so_far = 0
    for counter in range(x):
        sum_so_far = sum_so_far + x
  return sum_so_far
```

**Output (Python 2.x):**

```py
>>> square(10)
10
```

Shouldn't that be 100?

**Note:** If you're not able to reproduce this, try running the file [mixed_tabs_and_spaces.py](/mixed_tabs_and_spaces.py) via the shell.

#### 💡 설명

* **Don't mix tabs and spaces!** The character just preceding return is a "tab",  and the code is indented by multiple of "4 spaces" elsewhere in the example.
* This is how Python handles tabs:

  > First, tabs are replaced (from left to right) by one to eight spaces such that the total number of characters up to and including the replacement is a multiple of eight <...>
* So the "tab" at the last line of `square` function is replaced with eight spaces, and it gets into the loop.
* Python 3 is kind enough to throw an error for such cases automatically.

    **Output (Python 3.x):**
    ```py
    TabError: inconsistent use of tabs and spaces in indentation
    ```

---

---

## Section: Watch out for the landmines!


### ▶ Modifying a dictionary while iterating over it
<!-- Example ID: b4e5cdfb-c3a8-4112-bd38-e2356d801c41 --->
```py
x = {0: None}

for i in x:
    del x[i]
    x[i+1] = None
    print(i)
```

**Output (Python 2.7- Python 3.5):**

```
0
1
2
3
4
5
6
7
```

Yes, it runs for exactly **eight** times and stops.

#### 💡 설명:

* Iteration over a dictionary that you edit at the same time is not supported.
* It runs eight times because that's the point at which the dictionary resizes to hold more keys (we have eight deletion entries, so a resize is needed). This is actually an implementation detail.
* How deleted keys are handled and when the resize occurs might be different for different Python implementations.
* So for Python versions other than Python 2.7 - Python 3.5 the count might be different from 8 (but whatever the count is, it's going to be the same every time you run it). You can find some discussion around this [here](https://github.com/satwikkansal/wtfpython/issues/53) or in [this](https://stackoverflow.com/questions/44763802/bug-in-python-dict) StackOverflow thread.

---

### ▶ Stubborn `del` operation
<!-- Example ID: 777ed4fd-3a2d-466f-95e7-c4058e61d78e --->
```py
class SomeClass:
    def __del__(self):
        print("Deleted!")
```

**Output:**
1\.
```py
>>> x = SomeClass()
>>> y = x
>>> del x # this should print "Deleted!"
>>> del y
Deleted!
```

Phew, deleted at last. You might have guessed what saved from `__del__` being called in our first attempt to delete `x`. Let's add more twist to the example.

2\.
```py
>>> x = SomeClass()
>>> y = x
>>> del x
>>> y # check if y exists
<__main__.SomeClass instance at 0x7f98a1a67fc8>
>>> del y # Like previously, this should print "Deleted!"
>>> globals() # oh, it didn't. Let's check all our global variables and confirm
Deleted!
{'__builtins__': <module '__builtin__' (built-in)>, 'SomeClass': <class __main__.SomeClass at 0x7f98a1a5f668>, '__package__': None, '__name__': '__main__', '__doc__': None}
```

Okay, now it's deleted :confused:

#### 💡 설명:
+ `del x` doesn’t directly call `x.__del__()`.
+ Whenever `del x` is encountered, Python decrements the reference count for `x` by one, and `x.__del__()` when x’s reference count reaches zero.
+ In the second output snippet, `y.__del__()` was not called because the previous statement (`>>> y`) in the interactive interpreter created another reference to the same object, thus preventing the reference count to reach zero when `del y` was encountered.
+ Calling `globals` caused the existing reference to be destroyed and hence we can see "Deleted!" being printed (finally!).

---

### ▶ Deleting a list item while iterating
<!-- Example ID: 4cc52d4e-d42b-4e09-b25f-fbf5699b7d4e --->
```py
list_1 = [1, 2, 3, 4]
list_2 = [1, 2, 3, 4]
list_3 = [1, 2, 3, 4]
list_4 = [1, 2, 3, 4]

for idx, item in enumerate(list_1):
    del item

for idx, item in enumerate(list_2):
    list_2.remove(item)

for idx, item in enumerate(list_3[:]):
    list_3.remove(item)

for idx, item in enumerate(list_4):
    list_4.pop(idx)
```

**Output:**
```py
>>> list_1
[1, 2, 3, 4]
>>> list_2
[2, 4]
>>> list_3
[]
>>> list_4
[2, 4]
```

Can you guess why the output is `[2, 4]`?

#### 💡 설명:

* It's never a good idea to change the object you're iterating over. The correct way to do so is to iterate over a copy of the object instead, and `list_3[:]` does just that.

     ```py
     >>> some_list = [1, 2, 3, 4]
     >>> id(some_list)
     139798789457608
     >>> id(some_list[:]) # Notice that python creates new object for sliced list.
     139798779601192
     ```

**Difference between `del`, `remove`, and `pop`:**
* `del var_name` just removes the binding of the `var_name` from the local or global namespace (That's why the `list_1` is unaffected).
* `remove` removes the first matching value, not a specific index, raises `ValueError` if the value is not found.
* `pop` removes the element at a specific index and returns it, raises `IndexError` if an invalid index is specified.

**Why the output is `[2, 4]`?**
- The list iteration is done index by index, and when we remove `1` from `list_2` or `list_4`, the contents of the lists are now `[2, 3, 4]`. The remaining elements are shifted down, i.e., `2` is at index 0, and `3` is at index 1. Since the next iteration is going to look at index 1 (which is the `3`), the `2` gets skipped entirely. A similar thing will happen with every alternate element in the list sequence.

* Refer to this StackOverflow [thread](https://stackoverflow.com/questions/45946228/what-happens-when-you-try-to-delete-a-list-element-while-iterating-over-it) explaining the example
* See also this nice StackOverflow [thread](https://stackoverflow.com/questions/45877614/how-to-change-all-the-dictionary-keys-in-a-for-loop-with-d-items) for a similar example related to dictionaries in Python.

---

### ▶ Loop variables leaking out!
<!-- Example ID: ccec7bf6-7679-4963-907a-1cd8587be9ea --->
1\.
```py
for x in range(7):
    if x == 6:
        print(x, ': for x inside loop')
print(x, ': x in global')
```

**Output:**
```py
6 : for x inside loop
6 : x in global
```

But `x` was never defined outside the scope of for loop...

2\.
```py
# This time let's initialize x first
x = -1
for x in range(7):
    if x == 6:
        print(x, ': for x inside loop')
print(x, ': x in global')
```

**Output:**
```py
6 : for x inside loop
6 : x in global
```

3\.

**Output (Python 2.x):**
```
>>> x = 1
>>> print([x for x in range(5)])
[0, 1, 2, 3, 4]
>>> print(x, ': x in global')
(4, ': x in global')
```

**Output (Python 3.x):**
```
>>> x = 1
>>> print([x for x in range(5)])
[0, 1, 2, 3, 4]
>>> print(x, ': x in global')
1 : x in global
```

#### 💡 설명:

- In Python, for-loops use the scope they exist in and leave their defined loop-variable behind. This also applies if we explicitly defined the for-loop variable in the global namespace before. In this case, it will rebind the existing variable.

- The differences in the output of Python 2.x and Python 3.x interpreters for list comprehension example can be explained by following change documented in [What’s New In Python 3.0](https://docs.python.org/3/whatsnew/3.0.html) documentation:

    > "List comprehensions no longer support the syntactic form `[... for var in item1, item2, ...]`. Use `[... for var in (item1, item2, ...)]` instead. Also, note that list comprehensions have different semantics: they are closer to syntactic sugar for a generator expression inside a `list()` constructor, and in particular the loop control variables are no longer leaked into the surrounding scope."

---

### ▶ Beware of default mutable arguments!
<!-- Example ID: 7d42dade-e20d-4a7b-9ed7-16fb58505fe9 --->
```py
def some_func(default_arg=[]):
    default_arg.append("some_string")
    return default_arg
```

**Output:**
```py
>>> some_func()
['some_string']
>>> some_func()
['some_string', 'some_string']
>>> some_func([])
['some_string']
>>> some_func()
['some_string', 'some_string', 'some_string']
```

#### 💡 설명:

- The default mutable arguments of functions in Python aren't really initialized every time you call the function. Instead, the recently assigned value to them is used as the default value. When we explicitly passed `[]` to `some_func` as the argument, the default value of the `default_arg` variable was not used, so the function returned as expected.

    ```py
    def some_func(default_arg=[]):
        default_arg.append("some_string")
        return default_arg
    ```

    **Output:**
    ```py
    >>> some_func.__defaults__ #This will show the default argument values for the function
    ([],)
    >>> some_func()
    >>> some_func.__defaults__
    (['some_string'],)
    >>> some_func()
    >>> some_func.__defaults__
    (['some_string', 'some_string'],)
    >>> some_func([])
    >>> some_func.__defaults__
    (['some_string', 'some_string'],)
    ```

- A common practice to avoid bugs due to mutable arguments is to assign `None` as the default value and later check if any value is passed to the function corresponding to that argument. Example:

    ```py
    def some_func(default_arg=None):
        if not default_arg:
            default_arg = []
        default_arg.append("some_string")
        return default_arg
    ```

---

### ▶ Catching the Exceptions
<!-- Example ID: b5ca5e6a-47b9-4f69-9375-cda0f8c6755d --->
```py
some_list = [1, 2, 3]
try:
    # This should raise an ``IndexError``
    print(some_list[4])
except IndexError, ValueError:
    print("Caught!")

try:
    # This should raise a ``ValueError``
    some_list.remove(4)
except IndexError, ValueError:
    print("Caught again!")
```

**Output (Python 2.x):**
```py
Caught!

ValueError: list.remove(x): x not in list
```

**Output (Python 3.x):**
```py
  File "<input>", line 3
    except IndexError, ValueError:
                     ^
SyntaxError: invalid syntax
```

#### 💡 설명

* To add multiple Exceptions to the except clause, you need to pass them as parenthesized tuple as the first argument. The second argument is an optional name, which when supplied will bind the Exception instance that has been raised. Example,
  ```py
  some_list = [1, 2, 3]
  try:
     # This should raise a ``ValueError``
     some_list.remove(4)
  except (IndexError, ValueError), e:
     print("Caught again!")
     print(e)
  ```
  **Output (Python 2.x):**
  ```
  Caught again!
  list.remove(x): x not in list
  ```
  **Output (Python 3.x):**
  ```py
    File "<input>", line 4
      except (IndexError, ValueError), e:
                                       ^
  IndentationError: unindent does not match any outer indentation level
  ```

* Separating the exception from the variable with a comma is deprecated and does not work in Python 3; the correct way is to use `as`. Example,
  ```py
  some_list = [1, 2, 3]
  try:
      some_list.remove(4)

  except (IndexError, ValueError) as e:
      print("Caught again!")
      print(e)
  ```
  **Output:**
  ```
  Caught again!
  list.remove(x): x not in list
  ```

---

### ▶ Same operands, different story!
<!-- Example ID: ca052cdf-dd2d-4105-b936-65c28adc18a0 --->
1\.
```py
a = [1, 2, 3, 4]
b = a
a = a + [5, 6, 7, 8]
```

**Output:**
```py
>>> a
[1, 2, 3, 4, 5, 6, 7, 8]
>>> b
[1, 2, 3, 4]
```

2\.
```py
a = [1, 2, 3, 4]
b = a
a += [5, 6, 7, 8]
```

**Output:**
```py
>>> a
[1, 2, 3, 4, 5, 6, 7, 8]
>>> b
[1, 2, 3, 4, 5, 6, 7, 8]
```

#### 💡 설명:

*  `a += b` doesn't always behave the same way as `a = a + b`.  Classes *may* implement the *`op=`* operators differently, and lists do this.

* The expression `a = a + [5,6,7,8]` generates a new list and sets `a`'s reference to that new list, leaving `b` unchanged.

* The expression `a += [5,6,7,8]` is actually mapped to an "extend" function that operates on the list such that `a` and `b` still point to the same list that has been modified in-place.

---

### ▶ The out of scope variable
<!-- Example ID: 75c03015-7be9-4289-9e22-4f5fdda056f7 --->
```py
a = 1
def some_func():
    return a

def another_func():
    a += 1
    return a
```

**Output:**
```py
>>> some_func()
1
>>> another_func()
UnboundLocalError: local variable 'a' referenced before assignment
```

#### 💡 설명:
* When you make an assignment to a variable in scope, it becomes local to that scope. So `a` becomes local to the scope of `another_func`,  but it has not been initialized previously in the same scope which throws an error.
* Read [this](http://sebastianraschka.com/Articles/2014_python_scope_and_namespaces.html) short but an awesome guide to learn more about how namespaces and scope resolution works in Python.
* To modify the outer scope variable `a` in `another_func`, use `global` keyword.
  ```py
  def another_func()
      global a
      a += 1
      return a
  ```

  **Output:**
  ```py
  >>> another_func()
  2
  ```

---

### ▶ Be careful with chained operations
<!-- Example ID: 07974979-9c86-4720-80bd-467aa19470d9 --->
```py
>>> (False == False) in [False] # makes sense
False
>>> False == (False in [False]) # makes sense
False
>>> False == False in [False] # now what?
True

>>> True is False == False
False
>>> False is False is False
True

>>> 1 > 0 < 1
True
>>> (1 > 0) < 1
False
>>> 1 > (0 < 1)
False
```

#### 💡 설명:

As per https://docs.python.org/2/reference/expressions.html#not-in

> Formally, if a, b, c, ..., y, z are expressions and op1, op2, ..., opN are comparison operators, then a op1 b op2 c ... y opN z is equivalent to a op1 b and b op2 c and ... y opN z, except that each expression is evaluated at most once.

While such behavior might seem silly to you in the above examples, it's fantastic with stuff like `a == b == c` and `0 <= x <= 100`.

* `False is False is False` is equivalent to `(False is False) and (False is False)`
* `True is False == False` is equivalent to `True is False and False == False` and since the first part of the statement (`True is False`) evaluates to `False`, the overall expression evaluates to `False`.
* `1 > 0 < 1` is equivalent to `1 > 0 and 0 < 1` which evaluates to `True`.
* The expression `(1 > 0) < 1` is equivalent to `True < 1` and
  ```py
  >>> int(True)
  1
  >>> True + 1 #not relevant for this example, but just for fun
  2
  ```
  So, `1 < 1` evaluates to `False`

---

### ▶ Name resolution ignoring class scope
<!-- Example ID: 03f73d96-151c-4929-b0a8-f74430788324 --->
1\.
```py
x = 5
class SomeClass:
    x = 17
    y = (x for i in range(10))
```

**Output:**
```py
>>> list(SomeClass.y)[0]
5
```

2\.
```py
x = 5
class SomeClass:
    x = 17
    y = [x for i in range(10)]
```

**Output (Python 2.x):**
```py
>>> SomeClass.y[0]
17
```

**Output (Python 3.x):**
```py
>>> SomeClass.y[0]
5
```

#### 💡 설명
- Scopes nested inside class definition ignore names bound at the class level.
- A generator expression has its own scope.
- Starting from Python 3.X, list comprehensions also have their own scope.


---

### ▶ Needles in a Haystack
<!-- Example ID: 52a199b1-989a-4b28-8910-dff562cebba9 --->
1\.
```py
x, y = (0, 1) if True else None, None
```

**Output:**
```
>>> x, y  # expected (0, 1)
((0, 1), None)
```

Almost every Python programmer has faced a similar situation.

2\.
```py
t = ('one', 'two')
for i in t:
    print(i)

t = ('one')
for i in t:
    print(i)

t = ()
print(t)
```

**Output:**
```py
one
two
o
n
e
tuple()
```

3\.

```
ten_words_list = [
    "some",
    "very",
    "big",
    "list",
    "that"
    "consists",
    "of",
    "exactly",
    "ten",
    "words"
]
```

**Output**

```py
>>> len(ten_words_list)
9
```

4\. Not asserting strongly enough

```py
a = "python"
b = "javascript"
```
**Output:**
```py
# An assert statement with an assertion failure message.
>>> assert(a == b, "Both languages are different")
# No AssertionError is raised
```

#### 💡 설명:
* For 1, the correct statement for expected behavior is `x, y = (0, 1) if True else (None, None)`.
* For 2, the correct statement for expected behavior is `t = ('one',)` or `t = 'one',` (missing comma) otherwise the interpreter considers `t` to be a `str` and iterates over it character by character.
* `()` is a special token and denotes empty `tuple`.
* In 3, as you might have already figured out, there's a missing comma after 5th element (`"that"`) in the list. So by implicit string literal concatenation,
    ```py
    >>> ten_words_list
    ['some', 'very', 'big', 'list', 'thatconsists', 'of', 'exactly', 'ten', 'words']
    ```
* No `AssertionError` was raised in 4th snippet because instead of asserting the individual expression `a == b`, we're asserting entire tuple. The following snippet will clear things up,
    ```py
    >>> a = "python"
    >>> b = "javascript"
    >>> assert a == b
    Traceback (most recent call last):
        File "<stdin>", line 1, in <module>
    AssertionError

    >>> assert (a == b, "Values are not equal")
    <stdin>:1: SyntaxWarning: assertion is always true, perhaps remove parentheses?

    >>> assert a == b, "Values are not equal"
    Traceback (most recent call last):
        File "<stdin>", line 1, in <module>
    AssertionError: Values aren not equal
    ```

---

### ▶ Wild imports
<!-- Example ID: 83deb561-bd55-4461-bb5e-77dd7f411e1c --->
```py
# File: module.py

def some_weird_name_func_():
    print("works!")

def _another_weird_name_func():
    print("works!")

```

**Output**

```py
>>> from module import *
>>> some_weird_name_func_()
"works!"
>>> _another_weird_name_func()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name '_another_weird_name_func' is not defined
```

#### 💡 설명:

- It if often adivsable to not use wildcard imports. The first obvious reason for this is In wildcard imports, the names with leading underscore are be imported. This may lead to errors in runtime.
- Had we used `from ... import a, b, c` syntax, the above `NameError` won't have occurred.
    ```py
    >>> from module import some_weird_name_func_, _another_weird_name_func
    >>> _another_weird_name_func()
    works!
    ```
- If you really want to use wildcard imports, then you'd have to define the list `__all__` in your module that will contain a list of public objects that'll be available when we do wildcard imports.
```py
__all__ = ['_another_weird_name_func']

def some_weird_name_func_():
    print("works!")

def _another_weird_name_func():
    print("works!")
```
**Output**

```py
>>> _another_weird_name_func()
"works!"
>>> some_weird_name_func_()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'some_weird_name_func_' is not defined
```

---


## 섹션: 파이썬의 숨겨진 보물들!

아래 섹션은 처음 접하는 사람들에게는 생소할 수도 있는 파이썬의 기능들을 소개합니다.

### ▶ 파이썬과 함께 나는 방법? *
<!-- Example ID: a92f3645-1899-4d50-9721-0031be4aec3f --->
방법이 궁금하세요? 아래 예제를 확인하세요!

```py
import antigravity
```

**결과:**
쉿..! 일급 기밀이에요.

#### 💡 설명:
+ `antigravity` 모듈은 파이썬이 가진 몇 안되는 이스터에그중 하나입니다.
+ `import antigravity`는 파이썬에 관한 [XKCD](http://xkcd.com/353/)만화가 담긴 웹페이지를 엽니다(XKCD는 미국의 유명한 이공계열 만화).
+ 이게 전부가 아닙니다! **이 이스터에그 안에는 사실 이스터에그가 하나 더 있습니다**. 이 [코드](https://github.com/python/cpython/blob/master/Lib/antigravity.py#L7-L17)를 확인해보면, [XKCD의 지오해싱 알고리즘](https://xkcd.com/426/)이 구현되어 있습니다(!).
+ [지오해싱](https://en.wikipedia.org/wiki/Geohashing)? 지오해싱은 xkcd 만화에서 처음 소개된 놀이로 더 잘 알려진 [지오캐싱](https://ko.wikipedia.org/wiki/%EC%A7%80%EC%98%A4%EC%BA%90%EC%8B%B1)과는 다릅니다.

---

### ▶ 파이썬에 `goto`문이 있다고?
<!-- Example ID: 2aff961e-7fa5-4986-a18a-9e5894bd89fe --->
```py
from goto import goto, label
for i in range(9):
    for j in range(9):
        for k in range(9):
            print("I'm trapped, please rescue!")
            if k == 2:
                goto .breakout # breaking out from a deeply nested loop
label .breakout
print("Freedom!")
```

**결과 (파이썬 2.3):**
```py
I'm trapped, please rescue!
I'm trapped, please rescue!
Freedom!
```

#### 💡 설명:
- 파이썬의 `goto`문은 2004년 4월 1일 만우절 기념으로 [발표](https://mail.python.org/pipermail/python-announce-list/2004-April/002982.html)되었습니다.
- 이후 발표된 최근 버전들은 이 모듈이 없습니다.
- 사용할 수 있다고해서 사용하지는 말아주세요! 파이썬에 왜 `goto`문이 없는가에 대한 이유가 궁금하시면 이 [링크](https://docs.python.org/3/faq/design.html#why-is-there-no-goto)를 확인해주세요.

---

### ▶ Brace yourself!
<!-- Example ID: 5c0c75f2-ddd9-4da3-ba49-c4be7ec39acf --->
If you are one of the people who doesn't like using whitespace in Python to denote scopes, you can use the C-style {} by importing,

```py
from __future__ import braces
```

**Output:**
```py
  File "some_file.py", line 1
    from __future__ import braces
SyntaxError: not a chance
```

Braces? No way! If you think that's disappointing, use Java. Okay, another surprising thing, can you find where's the `SyntaxError` raised in `__future__` module [code](https://github.com/python/cpython/blob/master/Lib/__future__.py)?

#### 💡 설명:
+ The `__future__` module is normally used to provide features from future versions of Python. The "future" in this specific context is however ironic.
+ This is an easter egg concerned with the community's feelings on this issue.
+ The code is actually present [here](https://github.com/python/cpython/blob/025eb98dc0c1dc27404df6c544fc2944e0fa9f3a/Python/future.c#L49) in `future.c` file.
+ When the CPython compiler encounters a [future statement](https://docs.python.org/3.3/reference/simple_stmts.html#future-statements), it first runs the appropriate code in `future.c` before treating it as a normal import statement.

---

### ▶ Let's meet Friendly Language Uncle For Life
<!-- Example ID: 6427fae6-e959-462d-85da-ce4c94ce41be --->
**Output (Python 3.x)**
```py
>>> from __future__ import barry_as_FLUFL
>>> "Ruby" != "Python" # there's no doubt about it
  File "some_file.py", line 1
    "Ruby" != "Python"
              ^
SyntaxError: invalid syntax

>>> "Ruby" <> "Python"
True
```

There we go.

#### 💡 설명:
- This is relevant to [PEP-401](https://www.python.org/dev/peps/pep-0401/) released on April 1, 2009 (now you know, what it means).
- Quoting from the PEP-401

  > Recognized that the != inequality operator in Python 3.0 was a horrible, finger pain inducing mistake, the FLUFL reinstates the <> diamond operator as the sole spelling.
- There were more things that Uncle Barry had to share in the PEP; you can read them [here](https://www.python.org/dev/peps/pep-0401/).
- It works well on interactive environment, but it will raise a `SyntaxError` when you run via python file (see this [issue](https://github.com/satwikkansal/wtfpython/issues/94)). However, you can wrap the statement inside an `eval` or `compile` to get it working,
    ```py
    from __future__ import barry_as_FLUFL
    print(eval('"Ruby" <> "Python"'))
    ```

---

### ▶ Even Python understands that love is complicated
<!-- Example ID: b93cad9e-d341-45d1-999c-fcdce65bed25 --->
```py
import this
```

Wait, what's **this**? `this` is love :heart:

**Output:**
```
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

It's the Zen of Python!

```py
>>> love = this
>>> this is love
True
>>> love is True
False
>>> love is False
False
>>> love is not True or False
True
>>> love is not True or False; love is love  # Love is complicated
True
```

#### 💡 설명:

* `this` module in Python is an easter egg for The Zen Of Python ([PEP 20](https://www.python.org/dev/peps/pep-0020)).
* And if you think that's already interesting enough, check out the implementation of [this.py](https://hg.python.org/cpython/file/c3896275c0f6/Lib/this.py). Interestingly, the code for the Zen violates itself (and that's probably the only place where this happens).
* Regarding the statement `love is not True or False; love is love`, ironic but it's self-explanatory.

---

### ▶ Yes, it exists!
<!-- Example ID: 4286db3d-1ea7-47c9-8fb6-a9a04cac6e49 --->
**The `else` clause for loops.** One typical example might be:

```py
  def does_exists_num(l, to_find):
      for num in l:
          if num == to_find:
              print("Exists!")
              break
      else:
          print("Does not exist")
```

**Output:**
```py
>>> some_list = [1, 2, 3, 4, 5]
>>> does_exists_num(some_list, 4)
Exists!
>>> does_exists_num(some_list, -1)
Does not exist
```

**The `else` clause in exception handling.** An example,

```py
try:
    pass
except:
    print("Exception occurred!!!")
else:
    print("Try block executed successfully...")
```

**Output:**
```py
Try block executed successfully...
```

#### 💡 설명:
- The `else` clause after a loop is executed only when there's no explicit `break` after all the iterations.
- `else` clause after try block is also called "completion clause" as reaching the `else` clause in a `try` statement means that the try block actually completed successfully.

---
### ▶ Ellipsis
<!-- Example ID: 969b7100-ab3d-4a7d-ad7d-a6be16181b2b --->
```py
def some_func():
    Ellipsis
```

**Output**
```py
>>> some_func()
# No output, No Error

>>> SomeRandomString
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'SomeRandomString' is not defined

>>> Ellipsis
Ellipsis
```

#### 💡 설명
- In Python, `Ellipsis` is a globally available builtin object which is equivalent to `...`.
    ```py
    >>> ...
    Ellipsis
    ```
- Eliipsis can be used for several purposes,
    + As a placeholder for code that hasn't been written yet (just like `pass` statement)
    + In slicing syntax to represent the full slices in remaining direction
    ```py
    >>> import numpy as np
    >>> three_dimensional_array = np.arange(8).reshape(2, 2, 2)
    array([
        [
            [0, 1],
            [2, 3]
        ],

        [
            [4, 5],
            [6, 7]
        ]
    ])
    ```
    So our `three_dimensional_array` is an array of array of arrays. Let's say we want to print the second element (index `1`) of all the innermost arrays, we can use Ellipsis to bypass all the preceding dimensions
    ```py
    >>> three_dimensional_array[:,:,1]
    array([[1, 3],
       [5, 7]])
    >>> three_dimensional_array[..., 1] # using Ellipsis.
    array([[1, 3],
       [5, 7]])
    ```
    Note: this will work for any number of dimensions. You can even select slice in first and last dimension and ignore the middle ones this way (`n_dimensional_array[firs_dim_slice, ..., last_dim_slice]`)
    + In [type hinting](https://docs.python.org/3/library/typing.html) to indicate only a part of the type (like `(Callable[..., int]` or `Tuple[str, ...]`))
    + You may also use Ellipsis as a default function argument (in the cases when you want to differentiate between the "no argument passed" and "None value passed" scenarios).

---

### ▶ Inpinity
<!-- Example ID: ff473ea8-a3b1-4876-a6f0-4378aff790c1 --->
The spelling is intended. Please, don't submit a patch for this.

**Output (Python 3.x):**
```py
>>> infinity = float('infinity')
>>> hash(infinity)
314159
>>> hash(float('-inf'))
-314159
```

#### 💡 설명:
- Hash of infinity is 10⁵ x π.
- Interestingly, the hash of `float('-inf')` is "-10⁵ x π" in Python 3, whereas "-10⁵ x e" in Python 2.

---

### ▶ Let's mangle
<!-- Example ID: 37146d2d-9e67-43a9-8729-3c17934b910c --->
1\.
```py
class Yo(object):
    def __init__(self):
        self.__honey = True
        self.bro = True
```

**Output:**
```py
>>> Yo().bro
True
>>> Yo().__honey
AttributeError: 'Yo' object has no attribute '__honey'
>>> Yo()._Yo__honey
True
```

2\.
```py
class Yo(object):
    def __init__(self):
        # Let's try something symmetrical this time
        self.__honey__ = True
        self.bro = True
```

**Output:**
```py
>>> Yo().bro
True

>>> Yo()._Yo__honey__
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Yo' object has no attribute '_Yo__honey__'
```

Why did `Yo()._Yo__honey` work?

2\.

```py
_A__variable = "Some value"

class A(object):
    def some_func(self):
        return __variable # not initiatlized anywhere yet
```

**Output:**
```py
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'A' object has no attribute '__variable'

>>> >>> A().some_func()
'Some value'
```

3\.

```py

```


#### 💡 설명:

* [Name Mangling](https://en.wikipedia.org/wiki/Name_mangling) is used to avoid naming collisions between different namespaces.
* In Python, the interpreter modifies (mangles) the class member names starting with `__` (double underscore a.k.a "dunder") and not ending with more than one trailing underscore by adding `_NameOfTheClass` in front.
* So, to access `__honey` attribute in first snippet, we had to append `_Yo` to the front which would prevent conflicts with the same name attribute defined in any other class.
* But then why didn't it work in the second snippet? Because name mangling excludes the names ending with double underscores.
* The third snippet was also a consequence of name mangling. The name `__variable` in the statement `return __variable` was mangled to `_A__variable` which also happens to be the name of the variable we declared in outer scope.

---





---

## Section: Miscellaneous


### ▶ `+=` is faster
<!-- Example ID: bfd19c60-a807-4a26-9598-4912b86ddb36 --->
```py
# using "+", three strings:
>>> timeit.timeit("s1 = s1 + s2 + s3", setup="s1 = ' ' * 100000; s2 = ' ' * 100000; s3 = ' ' * 100000", number=100)
0.25748300552368164
# using "+=", three strings:
>>> timeit.timeit("s1 += s2 + s3", setup="s1 = ' ' * 100000; s2 = ' ' * 100000; s3 = ' ' * 100000", number=100)
0.012188911437988281
```

#### 💡 설명:
+ `+=` is faster than `+` for concatenating more than two strings because the first string (example, `s1` for `s1 += s2 + s3`) is not destroyed while calculating the complete string.

---

### ▶ Let's make a giant string!
<!-- Example ID: c7a07424-63fe-4504-9842-8f3d334f28fc --->
```py
def add_string_with_plus(iters):
    s = ""
    for i in range(iters):
        s += "xyz"
    assert len(s) == 3*iters

def add_bytes_with_plus(iters):
    s = b""
    for i in range(iters):
        s += b"xyz"
    assert len(s) == 3*iters

def add_string_with_format(iters):
    fs = "{}"*iters
    s = fs.format(*(["xyz"]*iters))
    assert len(s) == 3*iters

def add_string_with_join(iters):
    l = []
    for i in range(iters):
        l.append("xyz")
    s = "".join(l)
    assert len(s) == 3*iters

def convert_list_to_string(l, iters):
    s = "".join(l)
    assert len(s) == 3*iters
```

**Output:**

```py
# Executed in ipython shell using %timeit for better readablity of results.
# You can also use the timeit module in normal python shell/scriptm=, example usage below
# timeit.timeit('add_string_with_plus(10000)', number=1000, globals=globals())

>>> NUM_ITERS = 1000
>>> %timeit -n1000 add_string_with_plus(NUM_ITERS)
124 µs ± 4.73 µs per loop (mean ± std. dev. of 7 runs, 100 loops each)
>>> %timeit -n1000 add_bytes_with_plus(NUM_ITERS)
211 µs ± 10.5 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> %timeit -n1000 add_string_with_format(NUM_ITERS)
61 µs ± 2.18 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> %timeit -n1000 add_string_with_join(NUM_ITERS)
117 µs ± 3.21 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> l = ["xyz"]*NUM_ITERS
>>> %timeit -n1000 convert_list_to_string(l, NUM_ITERS)
10.1 µs ± 1.06 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
```

Let's increase the number of iterations by a factor of 10.

```py
>>> NUM_ITERS = 10000
>>> %timeit -n1000 add_string_with_plus(NUM_ITERS) # Linear increase in execution time
1.26 ms ± 76.8 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> %timeit -n1000 add_bytes_with_plus(NUM_ITERS) # Quadratic increase
6.82 ms ± 134 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> %timeit -n1000 add_string_with_format(NUM_ITERS) # Linear increase
645 µs ± 24.5 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> %timeit -n1000 add_string_with_join(NUM_ITERS) # Linear increase
1.17 ms ± 7.25 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> l = ["xyz"]*NUM_ITERS
>>> %timeit -n1000 convert_list_to_string(l, NUM_ITERS) # Linear increase
86.3 µs ± 2 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
```

#### 💡 설명
- You can read more about [timeit](https://docs.python.org/3/library/timeit.html) or [%timeit](https://ipython.org/ipython-doc/dev/interactive/magics.html#magic-timeit) on these links. They are used to measure the execution time of code pieces.
- Don't use `+` for generating long strings — In Python, `str` is immutable, so the left and right strings have to be copied into the new string for every pair of concatenations. If you concatenate four strings of length 10, you'll be copying (10+10) + ((10+10)+10) + (((10+10)+10)+10) = 90 characters instead of just 40 characters. Things get quadratically worse as the number and size of the string increases (justified with the execution times of `add_bytes_with_plus` function)
- Therefore, it's advised to use `.format.` or `%` syntax (however, they are slightly slower than `+` for very short strings).
- Or better, if already you've contents available in the form of an iterable object, then use `''.join(iterable_object)` which is much faster.
- `add_string_with_plus` didn't show a quadratic increase in execution time unlike `add_bytes_with_plus` because of the `+=` optimizations discussed in the previous example. Had the statement been `s = s + "x" + "y" + "z"` instead of `s += "xyz"`, the increase would have been quadratic.
  ```py
  def add_string_with_plus(iters):
      s = ""
      for i in range(iters):
          s = s + "x" + "y" + "z"
      assert len(s) == 3*iters

  >>> %timeit -n100 add_string_with_plus(1000)
  388 µs ± 22.4 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
  >>> %timeit -n100 add_string_with_plus(10000) # Quadratic increase in execution time
  9 ms ± 298 µs per loop (mean ± std. dev. of 7 runs, 100 loops each)
  ```
- So many ways to format and create a giant string are somewhat in contrast to the [Zen of Python](https://www.python.org/dev/peps/pep-0020/), according to which,
    > There should be one-- and preferably only one --obvious way to do it.

---

### ▶ Explicit typecast of strings
<!-- Example ID: 59bee91a-36e0-47a4-8c7d-aa89bf1d3976 --->
```py
a = float('inf')
b = float('nan')
c = float('-iNf')  #These strings are case-insensitive
d = float('nan')
```

**Output:**
```py
>>> a
inf
>>> b
nan
>>> c
-inf
>>> float('some_other_string')
ValueError: could not convert string to float: some_other_string
>>> a == -c #inf==inf
True
>>> None == None # None==None
True
>>> b == d #but nan!=nan
False
>>> 50/a
0.0
>>> a/a
nan
>>> 23 + b
nan
```

#### 💡 설명:

`'inf'` and `'nan'` are special strings (case-insensitive), which when explicitly typecasted to `float` type, are used to represent mathematical "infinity" and "not a number" respectively.

---

### ▶ Minor Ones
<!-- Example ID: f885cb82-f1e4-4daa-9ff3-972b14cb1324 --->
* `join()` is a string operation instead of list operation. (sort of counter-intuitive at first usage)

  **💡 설명:**
  If `join()` is a method on a string then it can operate on any iterable (list, tuple, iterators). If it were a method on a list, it'd have to be implemented separately by every type. Also, it doesn't make much sense to put a string-specific method on a generic `list` object API.

* Few weird looking but semantically correct statements:
  + `[] = ()` is a semantically correct statement (unpacking an empty `tuple` into an empty `list`)
  + `'a'[0][0][0][0][0]` is also a semantically correct statement as strings are [sequences](https://docs.python.org/3/glossary.html#term-sequence)(iterables supporting element access using integer indices) in Python.
  + `3 --0-- 5 == 8` and `--5 == 5` are both semantically correct statements and evaluate to `True`.

* Given that `a` is a number, `++a` and `--a` are both valid Python statements but don't behave the same way as compared with similar statements in languages like C, C++ or Java.
  ```py
  >>> a = 5
  >>> a
  5
  >>> ++a
  5
  >>> --a
  5
  ```

  **💡 설명:**
  + There is no `++` operator in Python grammar. It is actually two `+` operators.
  + `++a` parses as `+(+a)` which translates to `a`. Similarly, the output of the statement `--a` can be justified.
  + This StackOverflow [thread](https://stackoverflow.com/questions/3654830/why-are-there-no-and-operators-in-python) discusses the rationale behind the absence of increment and decrement operators in Python.

* Python uses 2 bytes for local variable storage in functions. In theory, this means that only 65536 variables can be defined in a function. However, python has a handy solution built in that can be used to store more than 2^16 variable names. The following code demonstrates what happens in the stack when more than 65536 local variables are defined (Warning: This code prints around 2^18 lines of text, so be prepared!):
     ```py
     import dis
     exec("""
     def f():
         """ + """
         """.join(["X"+str(x)+"=" + str(x) for x in range(65539)]))

     f()

     print(dis.dis(f))
     ```

* Multiple Python threads won't run your *Python code* concurrently (yes you heard it right!). It may seem intuitive to spawn several threads and let them execute your Python code concurrently, but, because of the [Global Interpreter Lock](https://wiki.python.org/moin/GlobalInterpreterLock) in Python, all you're doing is making your threads execute on the same core turn by turn. Python threads are good for IO-bound tasks, but to achieve actual parallelization in Python for CPU-bound tasks, you might want to use the Python [multiprocessing](https://docs.python.org/2/library/multiprocessing.html) module.

* List slicing with out of the bounds indices throws no errors
  ```py
  >>> some_list = [1, 2, 3, 4, 5]
  >>> some_list[111:]
  []
  ```

* `int('١٢٣٤٥٦٧٨٩')` returns `123456789` in Python 3. In Python, Decimal characters include digit characters, and all characters that can be used to form decimal-radix numbers, e.g. U+0660, ARABIC-INDIC DIGIT ZERO. Here's an [interesting story](http://chris.improbable.org/2014/8/25/adventures-in-unicode-digits/) related to this behavior of Python.

* `'abc'.count('') == 4`. Here's an approximate implementation of `count` method, which would make the things more clear
  ```py
  def count(s, sub):
      result = 0
      for i in range(len(s) + 1 - len(sub)):
          result += (s[i:i + len(sub)] == sub)
      return result
  ```
  The behavior is due to the matching of empty substring(`''`) with slices of length 0 in the original string.

---

# Contributing

All patches are Welcome! Please see [CONTRIBUTING.md](/CONTRIBUTING.md) for further details.

For discussions, you can either create a new [issue](https://github.com/satwikkansal/wtfpython/issues/new) or ping on the Gitter [channel](https://gitter.im/wtfpython/Lobby)

# Acknowledgements

The idea and design for this collection were initially inspired by Denys Dovhan's awesome project [wtfjs](https://github.com/denysdovhan/wtfjs). The overwhelming support by the community gave it the shape it is in right now.

#### Some nice Links!
* https://www.youtube.com/watch?v=sH4XF6pKKmk
* https://www.reddit.com/r/Python/comments/3cu6ej/what_are_some_wtf_things_about_python
* https://sopython.com/wiki/Common_Gotchas_In_Python
* https://stackoverflow.com/questions/530530/python-2-x-gotchas-and-landmines
* https://stackoverflow.com/questions/1011431/common-pitfalls-in-python
* https://www.python.org/doc/humor/
* https://www.codementor.io/satwikkansal/python-practices-for-efficient-code-performance-memory-and-usability-aze6oiq65

# 🎓 License

[![CC 4.0][license-image]][license-url]

&copy; [Satwik Kansal](https://satwikkansal.xyz)

[license-url]: http://www.wtfpl.net
[license-image]: https://img.shields.io/badge/License-WTFPL%202.0-lightgrey.svg?style=flat-square

## Help

If you have any wtfs, ideas or suggestions, please share.

## Surprise your geeky pythonist friends?

You can use these quick links to recommend wtfpython to your friends,

[Twitter](https://twitter.com/intent/tweet?url=https://github.com/satwikkansal/wtfpython&hastags=python,wtfpython)
 | [Linkedin](https://www.linkedin.com/shareArticle?url=https://github.com/satwikkansal&title=What%20the%20f*ck%20Python!&summary=An%20interesting%20collection%20of%20subtle%20and%20tricky%20Python%20snippets.)

## Need a pdf version?

I've received a few requests for the pdf version of wtfpython. You can add your details [here](https://satwikkansal.xyz/wtfpython-pdf/) to get the pdf as soon as it is finished.
