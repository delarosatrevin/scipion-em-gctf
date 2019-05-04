# Gctf plugin

This plugin provide wrappers around [Gctf](https://www.mrc-lmb.cam.ac.uk/kzhang/) program.

![build status](http://scipion-test.cnb.csic.es:9980/badges/gctf_devel.svg "Build status")

## Installation

You will need to use [2.0](https://github.com/I2PC/scipion/releases/tag/v2.0) version of Scipion to be able to run these protocols. To install the plugin, you have two options:

   a) Stable version
   ```
   scipion installp -p scipion-em-gctf
   ```
   b) Developer's version
   * download repository 
   ```
    git clone https://github.com/scipion-em/scipion-em-gctf.git
   ```
   * install 
   ```
    scipion installp -p path_to_scipion-em-gctf --devel
   ```

Gctf binaries will be installed automatically with the plugin, but you can also link an existing installation. 
Default installation path assumed is `software/em/gctf-1.06`, if you want to change it, set *GCTF_HOME* in `scipion.conf` file to the folder where the Gctf is installed. Depending on your CUDA version and GPU card compute capability you might want to change the default binary from `Gctf-v1.06_sm_20_cu8.0_x86_64` to a different one by explicitly setting *GCTF* variable. If you need to use CUDA different from the one used during Scipion installation (defined by CUDA_LIB), you can add *GCTF_CUDA_LIB* variable to the config file. Various binaries can be downloaded from the official Gctf website. 

To check the installation, simply run one of the following Scipion tests: 

```
   scipion test gctf.tests.test_protocols_gctf.TestGctfRefine
   scipion test gctf.tests.test_protocols_gctf.TestGctf
```

## Supported versions

1.06 and 1.18.

1.18 is a special version designed for VPP data, it does not support local/movie CTF refinement or validation options. 

## Protocols

* ctf estimation
* ctf refinement

## References

1. Zhang K. (2016). Gctf: Real-time CTF determination and correction. JSB, 193: 1-12.
