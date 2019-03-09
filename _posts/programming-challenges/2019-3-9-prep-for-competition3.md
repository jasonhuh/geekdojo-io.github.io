---
layout: post
title: Programming Challenges - Week 3 - Prep for Competition
---

### Create GitHub page using Jekyell

1. Go to [jekyll-now](https://github.com/barryclark/jekyll-now), and follow the *Quick Start* step by step.
2. Once your site is up and running, let's create a new post by following the above guide.

### Unit Testing

Python has a built-in `UnitTest` module, but it's cumbersome to use. Let's use `assert` function instead. Using `assert` function is quite simple. Here is an example:

```py
def add(a, b):
    return a + b

def simple_test():
    assert(add(2, 5)) == 7

if __name__ == '__main__':
    simple_test()
```

The benefit of using `assert` function is that, you can automate the unit testing. Instead of typing input manually, you can run the code, and testing is done for you.

### Programming Competition

Some competitions requires to read input from a file and write output to a file.

{% gist b9d3e8c7316c88696ececa817b708ae5 %}
