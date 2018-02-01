
py_library(
    name = "improv_rnn",
    srcs = ["__init__.py"],
    srcs_version = "PY2AND3",
    visibility = ["//magenta/tools/pip:__subpackages__"],
    deps = [
        ":improv_rnn_model",
    ],
)

py_library(
    name = "improv_rnn_config_flags",
    srcs = ["improv_rnn_config_flags.py"],
    srcs_version = "PY2AND3",
    visibility = [
        # internal model:improv_rnn
    ],
    deps = [
        ":improv_rnn_model",
        # tensorflow dep
    ],
)

py_library(
    name = "improv_rnn_model",
    srcs = ["improv_rnn_model.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//magenta",
        "//magenta/models/shared:events_rnn_model",
    ],
)

py_library(
    name = "improv_rnn_sequence_generator",
    srcs = ["improv_rnn_sequence_generator.py"],
    srcs_version = "PY2AND3",
    visibility = ["//magenta/interfaces:generator_interfaces"],
    deps = [
        ":improv_rnn_model",
        "//magenta",
    ],
)

py_binary(
    name = "improv_rnn_create_dataset",
    srcs = ["improv_rnn_create_dataset.py"],
    srcs_version = "PY2AND3",
    visibility = [
        # internal model:improv_rnn
        "//magenta/tools/pip:__subpackages__",
    ],
    deps = [
        ":improv_rnn_config_flags",
        "//magenta",
        # tensorflow dep
    ],
)

py_test(
    name = "improv_rnn_create_dataset_test",
    srcs = ["improv_rnn_create_dataset_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":improv_rnn_create_dataset",
        ":improv_rnn_model",
        "//magenta",
        # tensorflow dep
    ],
)

py_binary(
    name = "improv_rnn_train",
    srcs = ["improv_rnn_train.py"],
    srcs_version = "PY2AND3",
    visibility = [
        "//magenta/tools/pip:__subpackages__",
    ],
    deps = [
        ":improv_rnn_config_flags",
        "//magenta/models/shared:events_rnn_graph",
        "//magenta/models/shared:events_rnn_train",
        # tensorflow dep
    ],
)

py_binary(
    name = "improv_rnn_generate",
    srcs = ["improv_rnn_generate.py"],
    srcs_version = "PY2AND3",
    visibility = [
        "//magenta/tools/pip:__subpackages__",
    ],
    deps = [
        ":improv_rnn_config_flags",
        ":improv_rnn_model",
        ":improv_rnn_sequence_generator",
        "//magenta",
        # tensorflow dep
    ],
)