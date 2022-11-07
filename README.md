
# Simple DirectMedia Layer (SDL) Version 2.0

https://www.libsdl.org/

Simple DirectMedia Layer is a cross-platform development library designed
to provide low level access to audio, keyboard, mouse, joystick, and graphics
hardware via OpenGL and Direct3D. It is used by video playback software,
emulators, and popular games including Valve's award winning catalog
and many Humble Bundle games.

More extensive documentation is available in the docs directory, starting
with README.md

Enjoy!

Sam Lantinga (slouken@libsdl.org)



Here are some changes made to the rockchip platform to fit the rockchip platform:

Compile： 

```
cmake -S /your/source/SDL -DSDL_STATIC=OFF -DSDL_LIBC=ON -DSDL_GCC_ATOMICS=ON -DSDL_ALTIVEC=OFF -DSDL_OSS=OFF -DSDL_ALSA=ON -DSDL_ALSA_SHARED=ON -DSDL_JACK=OFF -DSDL_JACK_SHARED=OFF -DSDL_ESD=OFF -DSDL_ESD_SHARED=OFF -DSDL_ARTS=OFF -DSDL_ARTS_SHARED=OFF -DSDL_NAS=OFF -DSDL_NAS_SHARED=OFF -DSDL_LIBSAMPLERATE=OFF -DSDL_LIBSAMPLERATE_SHARED=OFF -DSDL_SNDIO=OFF -DSDL_DISKAUDIO=OFF -DSDL_DUMMYAUDIO=OFF -DSDL_DUMMYVIDEO=OFF -DSDL_WAYLAND=OFF -DSDL_WAYLAND_QT_TOUCH=ON -DSDL_WAYLAND_SHARED=OFF -DSDL_COCOA=OFF -DSDL_DIRECTFB=OFF -DSDL_VIVANTE=OFF -DSDL_DIRECTFB_SHARED=OFF -DSDL_FUSIONSOUND=OFF -DSDL_FUSIONSOUND_SHARED=OFF -DSDL_PTHREADS=ON -DSDL_PTHREADS_SEM=ON -DSDL_DIRECTX=OFF -DSDL_CLOCK_GETTIME=OFF -DSDL_RPATH=OFF -DSDL_RENDER_D3D=OFF -DSDL_X11=OFF -DSDL_OPENGLES=ON -DSDL_OPENGL=OFF -DSDL_VULKAN=OFF -DSDL_PULSEAUDIO=ON -DSDL_HIDAPI_JOYSTICK=OFF -DSDL_KMSDRM=ON -DSDL_TEST=ON -DSDL_TESTS=ON && make -j8
```

For user-space Gpus driven mali on arm platform, both gbm and opengles are implemented in libmali.so.1.9.0, so the code changes the default location of the gles library to call libmali.so.1.9.0. You'll also need to do that. libmali.so.1.9.0 to enable gpu hardware acceleration, You can view:

```
vi src/video/SDL_egl.c +97
```



Here are some debugging methods：

```
SDL_LogSetAllPriority(SDL_LOG_PRIORITY_VERBOSE);
```

You can add the above to the code and you'll get more information。

Enjoy!

huangzihan

