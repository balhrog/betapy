# Organisation du code et normes de codages #

**Proposition**: utiliser le _[guide de style pour le code python (PEP8)](http://www.python.org/dev/peps/pep-0008/)_ pour permettre la clarté du code.

<br>

<h2>Traduction en français</h2>

voici une <a href='http://www.biologeek.com/bonnes-pratiques%2Cconferences%2Cdjango%2Cpython%2Ctraduction/bonnes-pratiques-et-astuces-python/'>petite traduction française du style guide pour le code python</a>.<br>
<br>
<br>

<h2>Aide-mémoire pour l'organisation du code</h2>
source: <a href='http://wwd.ca/blog/2009/07/09/pep-8-cheatsheet/'>PEP-8 cheatsheet</a>

<pre><code>#! /usr/bin/env python<br>
# -*- coding: utf-8 -*-<br>
"""This module's docstring summary line.<br>
<br>
This is a multi-line docstring. Paragraphs are separated with blank lines. <br>
Lines conform to 79-column limit. <br>
<br>
Module and packages names should be short, lower_case_with_underscores.<br>
<br>
See http://www.python.org/dev/peps/pep-0008/ for more PEP-8 details and<br>
http://wwd.ca/blog/2009/07/09/pep-8-cheatsheet/ for an up-to-date version<br>
of this cheatsheet.<br>
"""<br>
import os<br>
import sys<br>
<br>
import some_third_party_lib<br>
import some_other_third_party_lib<br>
<br>
import your_local_stuff<br>
import more_local_stuff<br>
import dont_import_two, modules_in_one_line     # IMPORTANT!<br>
<br>
_a_global_var = 2   # so it won't get imported by 'from foo import *'<br>
_b_global_var = 3<br>
<br>
A_CONSTANT = 'ugh.'<br>
<br>
# 2 empty lines between top-level funcs + classes<br>
def some_function():<br>
    pass<br>
<br>
<br>
class FooBar(object):<br>
    """Write docstrings for ALL public classes, funcs and methods.<br>
    <br>
    Class and exception names are CapWords.<br>
    """<br>
    <br>
    a = 2<br>
    b = 4<br>
    _internal_variable = 3<br>
    class_ = 'foo'      # trailing underscore to avoid conflict with builtin<br>
<br>
    # this will trigger name mangling to further discourage use from outside<br>
    # this is also very useful if you intend your class to be subclassed, and<br>
    # the children might also use the same var name for something else; e.g. <br>
    # for simple variables like 'a' above. Name mangling will ensure that <br>
    # *your* a and the children's a will not collide.<br>
    __internal_var = 4  <br>
<br>
    # NEVER use double leading and trailing underscores for your own names<br>
    __nooooooodontdoit__ = 0<br>
<br>
    # don't call anything:<br>
    l = 1<br>
    O = 2<br>
    I = 3<br>
<br>
    # some examples of how to wrap code to conform to 79-columns limit:<br>
    def __init__(self, width, height,<br>
                 color='black', emphasis=None, highlight=0):<br>
        if width == 0 and height == 0 and \<br>
           color == 'red' and emphasis == 'strong' or \<br>
           highlight &gt; 100:<br>
            raise ValueError("sorry, you lose")<br>
        if width == 0 and height == 0 and (color == 'red' or<br>
                                           emphasis is None):<br>
            raise ValueError("I don't think so -- values are %s, %s" %<br>
                             (width, height))<br>
        Blob.__init__(self, width, height,<br>
                      color, emphasis, highlight)<br>
        <br>
        # empty lines within method to enhance readability; no set rule<br>
        short_foo_dict = {'loooooooooooooooooooong_element_name': 'cat',<br>
                          'other_element': 'dog'}<br>
                            <br>
        long_foo_dict_with_many_elements = {<br>
            'foo': 'cat',<br>
            'bar': 'dog'<br>
        }<br>
<br>
    # 1 empty line between in-class def'ns<br>
    def foo_method(self, x, y=None):<br>
        """Method and function names are lower_case_with_underscores.<br>
        <br>
        Always use self as first arg.<br>
        """<br>
        if x == 4:          # x is blue &lt;== USEFUL 1-liner comment<br>
            x, y = y, x     # inverse x and y &lt;== USELESS COMMENT<br>
        dict['key'] = dict[index] = {x: 2, 'cat': 'not a dog'}<br>
        c = (a + b) * (a - b)<br>
<br>
    @classmethod<br>
    def bar(cls):<br>
        """Use cls!"""<br>
        pass<br>
<br>
<br>
# a 79-char ruler:<br>
#234567891123456789212345678931234567894123456789512345678961234567897123456789<br>
<br>
</code></pre>