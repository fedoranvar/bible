*Rules for developers only*
# Fix tiny issues
* Fix tiny issues right after you find it, e.g.
  * wrong developer name or any other detail in \_\_openerp\_\_.py
  * variable that has to be renamed for any reason
  * etc.
* If you don't fix in time, you could forget to do it at all. It means that your supervisor has to spend his time to find your tiny issues and wait for updates. If your supervisor doesn't notice such issue, you will release non-perfect product.

# Make specification first
* Make [specification](https://odoo-development.readthedocs.io/en/latest/dev/docs/index.html) before you start actual development
  * It helps you to review requirements again before you start.
  * It helps your supervisor to check, that you understand requirements correctly

# Always use specification templates
This rule helps keep module specification correct and complete
* Don't use specification from old modules, use templates instead
  * Templates may be changed, while files in old modules may keep old variant
  * Templates have placeholders with instruction (like ``{put description here}``) which you have to read before writing specification
    * Non updated (forgotten) placeholders are catched by travis

# No code duplicates
Consider to make a method if you have similar code at least in two places

* Such code is easy to fix / update (you do in a one place instead of 2+)
* It doesn't matter how much lines is needed for new refactored code. It's ok to do it even when after refactoring it takes few more lines than in original approach

# Use right names
Method, variables names:
* shall not confuse. It must do / contain exactly what how it's named