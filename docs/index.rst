👋 Welcome to MLC LLM
===================================

`Discord <https://discord.gg/9Xpy2HGBuD>`_ | `Demo <https://mlc.ai/mlc-llm>`_ | `GitHub <https://github.com/mlc-ai/mlc-llm>`_

🚧 This document is currently undergoing heavy construction.

Machine Learning Compilation for LLM (MLC LLM) is a universal deployment solution that enables LLMs to run efficiently on consumer devices, leveraging native hardware acceleration like GPUs.

.. table:: MLC LLM: A universal deployment solution for large language models
   :widths: 200, 250, 250, 250, 250
   :align: center

   +-------------------+-------------------+-------------------+-------------------+---------------------+
   |                   |  AMD GPU          | NVIDIA GPU        | Apple M1/M2 GPU   | Intel GPU           |
   +===================+===================+===================+===================+=====================+
   |   Linux / Win     | ✅ Vulkan, ROCm   | ✅ Vulkan, CUDA   | ❌                | ✅ Vulkan           |
   +-------------------+-------------------+-------------------+-------------------+---------------------+
   |   macOS           | ✅ Metal          | ❌                | ✅ Metal          | ✅ Metal            |
   +-------------------+-------------------+-------------------+-------------------+---------------------+
   |   Web Browser     | ✅ WebGPU         | ✅ WebGPU         | ✅ WebGPU         | ✅ WebGPU           |
   +-------------------+-------------------+-------------------+-------------------+---------------------+
   |   iOS / iPadOS    | ✅ Metal on Apple M1/M2 GPU                                                     |
   +-------------------+-------------------+-------------------+-------------------+---------------------+
   |   Android         | ✅ OpenCL, Vulkan on Snapdragon, Mali GPU                                       |
   +-------------------+-------------------+-------------------+-------------------+---------------------+


Project Structure
-----------------

The project comprises three independent modules: model definition, model compilation, and runtimes.

.. image:: _static/img/project-structure.svg
   :width: 600
   :align: center
   :alt: Project Structure

.. ➀➁➂➃➄➅➆➇➈➉
.. ➊➋➌➍➎➏➐➑➒➓

**➀ Model definition in Python.** MLC offers a variety of pre-defined architectures, such as Llama (e.g., Vicuna, OpenLlama, Llama, Wizard), GPT-NeoX (e.g., RedPajama, Dolly), RNNs (e.g., RWKV), and GPT-J (e.g., MOSS). Model developers could solely define the model in pure Python, without having to touch code generation and runtime.

**➁ Model compilation in Python.** TVM Unity compiler are configured in pure python, and the compiled artifact can be exported as shared or static libraries. Performance experts can concentrate on compiler optimization to enhance the speed of LLMs on specific devices of interest.

**➂ Platform-native runtimes.** MLCChat are provided as lightweight runtimes tailored for each platform, including **C++** for command line, **Javascript** for web, **Swift** for iOS, and **Java** for Android. App developers only need to familiarize themselves with the platform-naive runtimes to integrate MLC-compiled LLM into their applications.

Docs by Usecases
----------------

**TODO** Verticals

.. tabs ::

   .. tab :: ➂ Run Compiled Models

      MLCChat is a lightweight runtime designed to demonstrate how to integrate MLC-compiled LLMs:

      - 🚧 CLI
      - 🚧 WebLLM
      - 🚧 iOS
      - 🚧 Android

      Moreover, to incorporate MLC-compiled models without using MLCChat:

      - 🚧 Use MLC-compiled models in a C++ project
      - 🚧 Use MLC-compiled models in a Javascript project
      - 🚧 Use MLC-compiled models in an iOS project
      - 🚧 Use MLC-compiled models in an Android project

      **Note.** TVM Unity compiler is not a dependency to running any MLC-compiled model.

   .. tab :: ➁ Compile Models

      TVM Unity is required to compile models. :ref:`Installation Guidelines <tvm-unity-install-prebuilt-package>`.

      - 🚧 MLC LLM Build walkthrough
      - 🚧 Compilation artifact specification
      - 🚧 Configure hardware targets
      - 🚧 Configure quantization formats

   .. tab :: ➀ Define Model Architectures

      TVM Unity is required to define models. :ref:`Installation Guidelines <tvm-unity-install-prebuilt-package>`.

      - 🚧 Define new model architectures: :doc:`tutorials/bring-your-own-models`.
      .. - 🚧 Contribute new models: :ref:`contribute-new-models`.

   .. tab :: MLC-Prebuilt LLMs

      - 🚧 Off-the-shelf prebuilt models: :ref:`off-the-shelf-models`

.. - Machine Learning Compilation Basics: `Machine Learning Compilation <https://mlc.ai/>`__


.. toctree::
   :maxdepth: 1
   :caption: All tutorials

   install/index.rst
   install/software-dependencies.rst
   tutorials/deploy-models.rst
   tutorials/compile-models.rst
   tutorials/bring-your-own-models.rst
   tutorials/customize.rst

.. toctree::
   :maxdepth: 1
   :caption: Contribute to MLC-LLM

   contribute/community.rst

.. toctree::
   :maxdepth: 1
   :caption: Model Prebuilts

   model-prebuilts.rst

.. toctree::
   :maxdepth: 1
   :caption: Misc

   misc/faq.rst
