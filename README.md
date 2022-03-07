# ES6 low way
An embedded assembly language for JavaScript low way.

(Draft)

## Processing instruction (PI) session

```xml
<?xml version="1.1" lang="UTF-8" standalone="yes"?>
<!-- The standalone="yes" is for a test. -->
<!--?? <?xml version="1.1" lang="UTF-8" standalone="no"?> ??-->

<?low-way "version=6.0" lang="asm"
  % Syntatic sugar test
  Move a to [an-address|reg-n].
  Move reg-n [b|an-address].
  Push a to a-stack.
  Pop a from a-stack.
  Shift a to a-quene.
  Unshift a from a-queue.
  Pick the-value of a-name from a-hash-table.

  Add a and b.       % result is stored in a
  Substract a by b.  % "
  Multiply a by b.
  Divide a by b.
  Factorial a.

  Branch-eq.   % ==
  Branch-neq.  % !=
  Branch-ge.   % >=
  Branch-gt.   % >
  Branch-lt.   % <
  Branch-le.   % <=

  Return.


  % I wanted to put the notion of the rational number in, but
  % I don't know how to do it yet.
?>
```

## Test
We don't test the types yet because I am very interested in rat.
Could you help me? I ask it now.

### Unit Test
We test in jsPerf for the benchmark.

An idea for the defination of an operator or a function by `asm(str)` is
as follows.

```js
const add = (a, b) => {
  let c = asm(`
    Move a to reg-63    % or reg-31
    Add reg-63 and b
  `, {a, b})
  return c
}
// i.e.,
const add = (a, b) => {
  return asm(`
    Move a to reg-63    % or reg-31
    Add reg-63 and b
  `, {a, b})
}
````

And an idea to test it in functional programming in which `asm(str)` is
a closure.

```js
/* Ref, arr.reduce(
          callback[accumulator, currentValue, currentIndex, array],
          initialValue
        )
*/
const reduce = (callback, initialValue = 0) => {
  return asm(`
    Move base to reg-63.
    % Something
  `, {callback, initialValue})
}
```
I don't know. Is is possible for you to test it now?
To the best of my knowledge for now.
Can you do it? Some of you? Yes, please lead us.


## License
It is licensed under the MIT License.
A short and simple permissive license with conditions only requiring
preservation of copyright and license notices. Licensed works,
modifications, and larger works may be distributed under different
terms and without source code.
Reference https://github.com/GodotExplorer/ECMAScript/blob/master/LICENSE

