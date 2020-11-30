[Test-Driven Development](https://en.wikipedia.org/wiki/Test-driven_development) (TDD) is a test-first approach in software development  aka ["утром документация, днем тесты, вечером стулья"](https://www.youtube.com/results?search_query=%D1%83%D1%82%D1%80%D0%BE%D0%BC+%D0%B4%D0%B5%D0%BD%D1%8C%D0%B3%D0%B8+%D0%B2%D0%B5%D1%87%D0%B5%D1%80%D0%BE%D0%BC+%D1%81%D1%82%D1%83%D0%BB%D1%8C%D1%8F). 

To apply TDD on *odoo development* you have to be sure that you make **only** following **types of updates** .

# Preparation

* You make a **skeleton** of the module, which is basically placeholders for the code, but not the code itself.
* You write a **documentation** of a new feature/module.

# Tests

* You make a **test**.

# Passing tests

* You fix a **failure in the tests** or CI checks. You can make only minimal updates that fix the failures.

# Exceptional development without tests

* You make updates that can be checked **by human only**, e.g. design updates (CSS, pictures, etc).
* You make **basic backend UI** (views, menus, etc.).
* You add demo data for simplify reviewing
* Access Settings (``ir.rule``, ``ir.model.access``, etc.)

# Refactoring

* You **refactor** covered code.
