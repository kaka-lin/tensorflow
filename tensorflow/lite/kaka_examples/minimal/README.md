# TensorFlow Lite C++ minimal example

This example shows how you can build a simple TensorFlow Lite application.

#### Step 1. Install CMake tool

It requires CMake 3.16 or higher. On Ubuntu, you can simply run the following
command.

Linux/Ubuntu:

```sh
$ sudo apt-get install cmake
```

macOS:

```sh
$ brew install cmake
```

Or you can follow
[the official cmake installation guide](https://cmake.org/install/)

#### Step 2. Clone TensorFlow repository

```sh
$ git clone https://github.com/tensorflow/tensorflow.git
$ cd tensorflow
```

#### Step 3-1. Build TensorFlow Lite with Bazel

Using `Bazel`

```sh
$ bazel build --define MEDIAPIPE_DISABLE_GPU=1 \
    tensorflow/lite/kaka_examples/minimal:minimal
```

Run the minimal example

```
$ ./bazel-bin/tensorflow/lite/kaka_examples/minimal/minimal <tflite model>
```

or 

```sh
$ bazel run --define MEDIAPIPE_DISABLE_GPU=1 \
    tensorflow/lite/examples/minimal:minimal <tflite model>
```

### Step 3-2.  Build TensorFlow Lite with CMake

##### 1. Create CMake build directory and run CMake tool

```sh
$ mkdir minimal_build
$ cd minimal_build
$ cmake ../tensorflow/lite/kaka_examples/minimal
```

##### 2. Build TensorFlow Lite

In the minimal_build directory,

```sh
$ cmake --build .
```

##### 3. Run minimal example

```sh
$ ./minimal <tflite model>
```