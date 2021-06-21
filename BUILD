python_requirements(
  module_mapping={
    "setuptools": ["pkg_resources"],
  },
)

resources(
    name="pyest_ini",
    sources=["pytest.ini"],
)

python_distribution(
    name="tavern_wheel",
    dependencies=[
      "//tavern",
      "//tavern/_plugins",
      "//tavern/_plugins/mqtt",
      "//tavern/_plugins/rest",
      "//tavern/request",
      "//tavern/response",
      "//tavern/schemas",
      "//tavern/schemas:schema_yaml",
      "//tavern/testutils",
      "//tavern/testutils/pytesthook",
      "//tavern/util",
    ],
    provides=setup_py(
        name="tavern",
        author="Michael Boulton",
        description = "Simple testing of RESTful APIs",
        version = "1.11.1",
        long_description = "file: README.rst",
        url = "https://taverntesting.github.io/",
        include_package_data = True,
        license = "MIT",
        license_file = "LICENSE",
        entry_points={
            "pytest11": "tavern = tavern.testutils.pytesthook",
            "tavern_http": "requests = tavern._plugins.rest.tavernhook:TavernRestPlugin",
            "tavern_mqtt": "paho-mqtt = tavern._plugins.mqtt.tavernhook",
        },
        keywords=["testing", "pytest"],
        classifiers=[
                "Development Status :: 5 - Production/Stable",
                "Intended Audience :: Developers",
                "Framework :: Pytest",
                "Programming Language :: Python :: 3",
                "Programming Language :: Python :: 3.6",
                "Programming Language :: Python :: 3.7",
                "Programming Language :: Python :: 3.8",
                "Topic :: Utilities",
                "Topic :: Software Development :: Testing",
                "License :: OSI Approved :: MIT License",
        ],

    ).with_binaries({
      "tavern-ci": "//tavern:tavern-ci",
    }),
    setup_py_commands=["bdist_wheel"]
)
