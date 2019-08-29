# Quickstart

[Source](https://sourcery.ai/blog/python-best-practices/)

* When starting a new Python project, it is tempting to just dive in and start coding. Spending a tiny amount of time to setup a project with the best tools will save immense time and lead to a happier coding experience.

  In an ideal world, dependencies would be identical for all developers, code would be perfectly formatted, common errors forbidden and everything would be covered by tests. Additionally, all of these would ensured at each commit.

  In this article I'll go through how to set up a project that does exactly that. You can either follow along with the steps or jump straight to generating a new project automatically by installing [pipx](https://sourcery.ai/blog/python-best-practices/#pipx) and [pipenv](https://sourcery.ai/blog/python-best-practices/#pipenv) then [generating a new project](https://sourcery.ai/blog/python-best-practices/#generate).

  Let's create a new project directory:

  ```bash
  mkdir best_practices
  cd best_practices
  ```

  **Python command line tools with pipx**

  [Pipx](https://pipxproject.github.io/pipx/) is a handy utility that allows quick installation of python command line tools. We'll be using it to install pipenv and cookiecutter.

  ```bash
  python3 -m pip install --user pipx
  python3 -m pipx ensurepath
  ```

  **Dependency management with pipenv**

  > [Pipenv](https://github.com/pypa/pipenv) automatically creates and manages a virtualenv for your projects, as well as adding/removing packages from your Pipfile as you install/uninstall packages. It also generates the ever-important Pipfile.lock, which is used to produce deterministic builds.

  Knowing that you and your teammates are using the same library versions is a huge confidence boost. Pipenv takes care of this and has gained massive traction in the last year or so.

  ```bash
  pipx install pipenv
  ```

  **Code formatting with black and isort**

  [Black](https://github.com/psf/black) formats our code:

  > Black is the uncompromising Python code formatter. By using it, you agree to cede control over minutiae of hand-formatting. In return, Black gives you speed, determinism, and freedom from pycodestyle nagging about formatting. You will save time and mental energy for more important matters.
  >
  > Blackened code looks the same regardless of the project you're reading. Formatting becomes transparent after a while and you can focus on the content instead.
  >
  > Black makes code review faster by producing the smallest diffs possible.

  while [isort](https://github.com/timothycrosley/isort) sorts our imports:

  > isort your python imports for you so you don't have to. isort is a Python utility / library to sort imports alphabetically, and automatically separated into sections.

  Let's install them using pipenv as development dependencies so they don't clutter a deployment:

  ```bash
  pipenv install black isort --dev
  ```

  Black and isort have incompatible default options so we'll override isort to follow black's lead. Create a `setup.cfg` file and add this config:

  ```python
  [isort]
  multi_line_output=3
  include_trailing_comma=True
  force_grid_wrap=0
  use_parentheses=True
  line_length=88
  ```

  We can run these tools with:

  ```bash
  pipenv run black
  pipenv run isort
  ```

  **Style enforcement with flake8**

  Flake8 ensures our code follows the standard python conventions as defined in PEP8. Install using pipenv:

  ```text
  pipenv install flake8 --dev
  ```

  Just like isort it needs a little configuration to work well with black. Add this config to `setup.cfg`:

  ```python
  [flake8]
  ignore = E203, E266, E501, W503
  max-line-length = 88
  max-complexity = 18
  select = B,C,E,F,W,T4
  ```

  Now we can run flake8 with `pipenv run flake8`.

  **Static types with mypy**

  > [Mypy](http://mypy-lang.org/) is an optional static type checker for Python that aims to combine the benefits of dynamic \(or "duck"\) typing and static typing. Mypy combines the expressive power and convenience of Python with a powerful type system and compile-time type checking. Mypy type checks standard Python programs; run them using any Python VM with basically no runtime overhead.

  Having types in Python takes a little getting used to but the benefits are substantial. From the website:

  * Static typing can make programs easier to understand and maintain
  * Static typing can help you find bugs earlier and with less testing and debugging
  * Static typing can help you find difficult-to-find bugs before your code goes into production

  ```bash
  pipenv install mypy --dev
  ```

  Mypy by default will recursively check all imports for type annotations which leads to errors when libraries do not include these annotations. We need to configure mypy to run only on our code and to ignore any errors for imports without type annotations. We are assuming that our code lives in the `best_practices` package for the following config. Add this to `setup.cfg`:

  ```python
  [mypy]
  files=best_practices,test
  ignore_missing_imports=true
  ```

  Now we can run mypy with:

  ```text
  pipenv run mypy
  ```

  Here's a useful [cheat sheet](https://mypy.readthedocs.io/en/latest/cheat_sheet_py3.html) for using it.

  **Testing with pytest and pytest-cov**

  Writing tests with [pytest](https://docs.pytest.org/en/latest/) is incredibly easy and removing any friction to writing tests means we will write more of them!

  ```text
  pipenv install pytest pytest-cov --dev
  ```

  Here's a simple example from the pytest website:

  ```python
  # content of test_sample.py
  def inc(x):
      return x + 1


  def test_answer():
      assert inc(3) == 5
  ```

  To execute it:

  ```bash
  $ pipenv run pytest
  =========================== test session starts ============================
  platform linux -- Python 3.x.y, pytest-5.x.y, py-1.x.y, pluggy-0.x.y
  cachedir: $PYTHON_PREFIX/.pytest_cache
  rootdir: $REGENDOC_TMPDIR
  collected 1 item

  test_sample.py F                                                     [100%]

  ================================= FAILURES =================================
  _______________________________ test_answer ________________________________

      def test_answer():
  >       assert inc(3) == 5
  E       assert 4 == 5
  E        +  where 4 = inc(3)

  test_sample.py:6: AssertionError
  ========================= 1 failed in 0.12 seconds =========================
  ```

  All our tests should go in the `test` directory so add this config to `setup.cfg`:

  ```python
  [tool:pytest]
  testpaths=test
  ```

  We also want to check how much of our code is covered by tests. Create a new file `.coveragerc` to only return coverage statistics for our application code, again we are assuming our application code lives in the `best_practices` module:

  ```python
  [run]
  source = best_practices

  [report]
  exclude_lines =
      # Have to re-enable the standard pragma
      pragma: no cover

      # Don't complain about missing debug-only code:
      def __repr__
      if self\.debug

      # Don't complain if tests don't hit defensive assertion code:
      raise AssertionError
      raise NotImplementedError

      # Don't complain if non-runnable code isn't run:
      if 0:
      if __name__ == .__main__.:
  ```

  We can now run our tests and report coverage with

  ```bash
  pipenv run pytest --cov --cov-fail-under=100
  ```

  This will fail if our test coverage of the application code is less than 100%.

  **Git hooks with pre-commit**

  Git hooks allow you to run scripts any time you want to commit or push. This lets us run all of our linting and tests automatically every time we commit/push. [pre‑commit](https://pre-commit.com/) allows easy configuration of these hooks:

  > Git hook scripts are useful for identifying simple issues before submission to code review. We run our hooks on every commit to automatically point out issues in code such as missing semicolons, trailing whitespace, and debug statements. By pointing these issues out before code review, this allows a code reviewer to focus on the architecture of a change while not wasting time with trivial style nitpicks.

  Here we configure all of the above tools to run on any changed python files on committing, and also to run pytest coverage only when pushing as it can be slow. Create a new file `.pre-commit-config.yaml`:

  ```python
  repos:
  - repo: local
    hooks:
    - id: isort
      name: isort
      stages: [commit]
      language: system
      entry: pipenv run isort
      types: [python]

    - id: black
      name: black
      stages: [commit]
      language: system
      entry: pipenv run black
      types: [python]

    - id: flake8
      name: flake8
      stages: [commit]
      language: system
      entry: pipenv run flake8
      types: [python]
      exclude: setup.py

    - id: mypy
      name: mypy
      stages: [commit]
      language: system
      entry: pipenv run mypy
      types: [python]
      pass_filenames: false

    - id: pytest
      name: pytest
      stages: [commit]
      language: system
      entry: pipenv run pytest
      types: [python]

    - id: pytest-cov
      name: pytest
      stages: [push]
      language: system
      entry: pipenv run pytest --cov --cov-fail-under=100
      types: [python]
      pass_filenames: false
  ```

  If you ever need to skip these hooks you can run `git commit --no-verify` or `git push --no-verify`

  **Generate a project using cookiecutter**

  Now we've seen what an ideal project contains, we can turn this into a [template](https://github.com/sourceryai/python-best-practices-cookiecutter) to generate a new project with a single command:

  ```text
  pipx run cookiecutter gh:sourceryai/python-best-practices-cookiecutter
  ```

  Fill in the project name and repo name and your project will be generated for you.

  To finish setting up, follow these steps:

  ```bash
  # Enter project directory
  cd <repo_name>

  # Initialise git repo
  git init

  # Install dependencies
  pipenv install --dev

  # Setup pre-commit and pre-push hooks
  pipenv run pre-commit install -t pre-commit
  pipenv run pre-commit install -t pre-push
  ```

  The template project contains a very simple Python file and test to try the tools out on. Once you're happy with the code you can then do your first `git commit` and all the hooks will be run.

  **Editor Integration**

  While it is great to know that the standard of code on our project will always be maintained at the highest level when committing code, it is somewhat frustrating to find out any issues after we think the code changes have all been done. It is much better to get the issues displayed in real-time.

  Spend some time to make sure these commands are run by your code editor when saving a file. Having instant feedback means you can quickly fixup any minor issues introduced while the code is fresh in the mind.

  Personally I use some excellent Vim plugins to accomplish this:

  * [ale](https://github.com/dense-analysis/ale) runs flake8 in real-time, and runs black, isort and mypy on file save
  * [vim-test](https://github.com/janko/vim-test) with [projectionist integration](https://github.com/janko/vim-test#projectionist-integration) runs pytest on file save

  **Sourcery**

  The next step is to have your editor automatically refactor your code for you as you work. This is why we built [Sourcery](https://sourcery.ai/), give it a go!



