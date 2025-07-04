# {{ package_name }}

A [QIIME 2](https://qiime2.org) plugin [developed](https://develop.qiime2.org) by {{ author_name }} ({{ author_email }}). 🔌

## Installation instructions

**The following instructions are intended to be a starting point** and should be replaced when `{{ package_name }}` is ready to share with others.
They will enable you to install the most recent *development* version of `{{ package_name }}`.
Remember that *release* versions should be used for all "real" work (i.e., where you're not testing or prototyping) - if there aren't instructions for installing a release version of this plugin, it is probably not yet intended for use in practice.

### Install Prerequisites

[Miniconda](https://conda.io/miniconda.html) provides the `conda` environment and package manager, and is currently the only supported way to install QIIME 2.
Follow the instructions for downloading and installing Miniconda.

After installing Miniconda and opening a new terminal, make sure you're running the latest version of `conda`:

```bash
conda update conda
```

###  Install development version of `{{ package_name }}`

Next, you need to get into the top-level `{{ package_name }}` directory.
If you already have this (e.g., because you just created the plugin), this may be as simple as running `cd {{ package_name }}`.
If not, you'll need the `{{ package_name }}` directory on your computer.
How you do that will differ based on how the package is shared, and ideally the developer will update these instructions to be more specific (remember, these instructions are intended to be a starting point).
For example, if it's maintained in a GitHub repository, you can achieve this by [cloning the repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository).
Once you have the directory on your computer, change (`cd`) into it.

If you're in a conda environment, deactivate it by running `conda deactivate`.


Then, follow the install instructions below, based on your machine's architecture:

<details>
<summary><strong>🍏&nbsp;Apple Silicon (ARM)</strong></summary>
<p>&nbsp;</p>

Start by creating a new conda environment:

```shell
CONDA_SUBDIR=osx-64 conda env create -n {{ package_name }}-dev --file ./environment-files/{{ package_name }}-qiime2-{{ target_distro }}-dev.yml
```

After this completes, activate the new environment you created by running:

```shell
conda activate {{ package_name }}-dev
```

Once this new environment has been activated, update your conda config to set the subdir to osx-64:

```shell
conda config --env --set subdir osx-64
```

Finally, run:

```shell
make install
```
</details>

<details>
<summary><strong>🛠&nbsp;All other architectures (Apple Intel, Linux, WSL)</strong></summary>
<p>&nbsp;</p>

Start by creating a new conda environment:

```shell
conda env create -n {{ package_name }}-dev --file ./environment-files/{{ package_name }}-qiime2-{{ target_distro }}-dev.yml
```

After this completes, activate the new environment you created by running:

```shell
conda activate {{ package_name }}-dev
```

Finally, run:

```shell
make install
```
</details>

## Testing and using the most recent development version of `{{ package_name }}`

After completing the install steps above, confirm that everything is working as expected by running:

```shell
make test
```

You should get a report that tests were run, and you should see that all tests passed and none failed.
It's usually ok if some warnings are reported.

If all of the tests pass, you're ready to use the plugin.
Start by making QIIME 2's command line interface aware of `{{ package_name }}` by running:

```shell
qiime dev refresh-cache
```

You should then see the plugin in the list of available plugins if you run:

```shell
qiime info
```

You should be able to review the help text by running:

```shell
qiime {{ plugin_name }} --help
```

Have fun! 😎

## About

The `{{ package_name }}` Python package was [created from a template](https://develop.qiime2.org/en/latest/plugins/tutorials/create-from-template.html).
To learn more about `{{ package_name }}`, refer to the [project website]({{ project_url }}).
To learn how to use QIIME 2, refer to the [QIIME 2 User Documentation](https://docs.qiime2.org).
To learn QIIME 2 plugin development, refer to [*Developing with QIIME 2*](https://develop.qiime2.org).

`{{ package_name }}` is a QIIME 2 community plugin, meaning that it is not necessarily developed and maintained by the developers of QIIME 2.
Please be aware that because community plugins are developed by the QIIME 2 developer community, and not necessarily the QIIME 2 developers themselves, some may not be actively maintained or compatible with current release versions of the QIIME 2 distributions.
More information on development and support for community plugins can be found [here](https://library.qiime2.org).
If you need help with a community plugin, first refer to the [project website]({{ project_url }}).
If that page doesn't provide information on how to get help, or you need additional help, head to the [Community Plugins category](https://forum.qiime2.org/c/community-contributions/community-plugins/14) on the QIIME 2 Forum where the QIIME 2 developers will do their best to help you.
