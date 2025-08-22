# miniwdl-colima

This [container backend](https://miniwdl.readthedocs.io/en/latest/runner_backends.html) plugin for [miniwdl](https://github.com/chanzuckerberg/miniwdl) runs WDL task containers by simply shelling out to `docker run` &mdash; a toy version of miniwdl's default docker integration suitable for use with colima on macOS.

Forked from [miniwdl-ext/miniwdl-backend-example](https://github.com/miniwdl-ext/miniwdl-backend-example).

To run the example, `cd` into a clone of this repo and:

```bash
pip3 install .
export MINIWDL__SCHEDULER__CONTAINER_BACKEND=miniwdl_colima
miniwdl run_self_test
```

Installing the Python package registers a specific [entry point](https://packaging.python.org/en/latest/specifications/entry-points/) which miniwdl discovers upon starting (details in [setup.py](https://github.com/miniwdl-ext/miniwdl-backend-example/blob/main/setup.py)). Then we activate it by setting the environment variable `MINIWDL__SCHEDULER__CONTAINER_BACKEND` to the registered backend name `example_docker_run`. (Equivalently, we could set `[scheduler] container_backend = example_docker_run` in a [miniwdl configuration file](https://miniwdl.readthedocs.io/en/latest/runner_reference.html#configuration).)