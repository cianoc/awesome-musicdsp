# Awesome Music DSP [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
A curated list of my favourite music DSP and audio plug-in frameworks, focusing on the C++ programming language. 

I like implementations that allow you to be creative quickly. The less code for the end user (e.g plug-in developer) the better!

Whilst there is some crossover here (for instance JUCE includes DSP functionality), hopefully the grouping make sense...

Oli Larkin

## Frameworks
- [JUCE](https://github.com/WeAreROLI/JUCE) - JUCE is an undeniably awesome C++ application framework with audio roots. It boasts a vast amount of functionality for the development of music software, including support for almost all plug-in formats and platforms. JUCE is used widely in the music technology industry and it has excellent documentation, code standards, functionality and support. The JUCE team at Roli organise the [Audio Developer's Conference (ADC)](https://juce.com/adc) which is the most awesome conference around if you like audio programming. What's more all the videos from the three ADCs so far are available [on youtube](https://www.youtube.com/channel/UCaF6fKdDrSmPDmiZcl9KLnQ/videos).
- [WDL](https://github.com/justinfrankel/WDL) - WDL is Cockos' library of reusable C++ code, that is used to power the DAW Reaper, amongst other things. Whilst not traditionally a framework, there is so much good stuff in here, it is highly recommended - although there is next to no documentation, so it's not for the faint of heart. For more info about the various parts of WDL (which can be used independently), check [the Cockos site](https://www.cockos.com/wdl/)
- [WDL-OL/iPlug](https://github.com/olilarkin/wdl-ol) - Not to blow my own physically modelled trumpet, so to speak, but iPlug (originally created by Cockos) is an awesome plug-in framework. I have been maintaining a fork of it since ~2011, which is probably the most widely used and maintained of all of the forks out there. iPlug's syntax is super simple, for example, creating a parameter or a control in the UI is only a single line of C++ code.
- [VSTGUI](https://github.com/steinbergmedia/vstgui) - VSTGUI is Steinberg's cross-platform UI toolkit for audio plug-ins. It is released under a BSD licence, and although it's not my weapon of choice, it's an impressive piece of work and many plug-in developers use it for their products.

## DSP Libraries

- [Gamma](https://github.com/LancePutnam/Gamma) - Gamma is a very awesome C++ DSP framework by Lance Putnam - a developer whose name I've known since the synthedit days. The beauty of Gamma is the conciseness of the implementation of certain techniques. The STFT is a bit of a pain to code, involving overlapping FFT windows etc. How about [this](https://github.com/LancePutnam/Gamma/blob/master/examples/spectral/STFT.cpp) for a concise end user implementation. 
- [FAUST](https://github.com/grame-cncm/faust) - FAUST is a powerful domain specific programming language (DSL) for audio DSP with many options for quickly compiling to different “architectures” including audio plug-ins. FAUST is not interpreted like programming languages such as Puredata/Max/Supercollider, it is fully compiled - so the FAUST compiler is really a transpiler. This functionality is highly suited to rapid prototyping but can also produce robust and performant binaries. Whilst the rapid prototyping possibilities of FAUST are appealing to me, what I like most about it is the extensive library of high quality DSP routines. Coupled with a concise and expressive syntax, FAUST is a powerful tool and definitely worth learning, to use in conjunction with C++.
- [HIIR](http://ldesoras.free.fr/prod.html) - HIIR is a seriously cool oversampling library by Laurent de Soras. Oversampling is something we often need in audio DSP, and this library handles it elegantly - providing a variety of classes for low latency IIR half band filtering (including SIMD optimizations). The original code (which was first released in 2005), is a little bit hard to get your head round, but fear not [here is](https://github.com/olilarkin/wdl-ol/tree/iplugquake/IPlug/Extras/HIIR) an updated version with [an example](https://github.com/olilarkin/wdl-ol/blob/iplugquake/IPlug/Extras/Oversampler.h) of how to use it inside an iPlug 2 plug-in.
- [HOALibrary](https://github.com/CICM/HoaLibrary-Light) - As someone who works a lot with spatial audio, it's fantastic that the CICM have released this flexible DSP library for high order ambisonics (HOA) - a spatial audio platform that is becoming more and more relevant thanks to VR.

## Books/Authors
This is a small selection of books that have been helpful to me. There are many others that look absolutely great but I have not used them in anger (yet).

- [Will Pirkle](http://www.willpirkle.com/) - Will Pirkle has written two books that will be invaluable the aspiring audio plug-in developer - "Designing Audio Effect Plug-Ins in C++" and "Designing Software Synthesizer Plug-Ins in C++". For more info [see here](http://www.willpirkle.com/about/books/])
- [Dodge and Jerse - Computer Music: Synthesis, Composition and Performance, 2nd Edition](https://books.google.co.uk/books/about/Computer_Music.html?id=eY_BQgAACAAJ&redir_esc=y) - This is my absolute favourite book to recommend to students studying computer music/audio synthesis. I find the book does not date like some other computer music texts. I find the MUSIC-N style diagrams charming and the techniques are discussed very well.
- [Udo Zölzer (Ed) - DAFX: Digital Audio Effects](https://books.google.co.uk/books/about/DAFX.html?id=DX-mRhkJL74C&source=kp_cover&redir_esc=y) - This is an invaluable book on audio DSP, written by a variety of domain experts, and including Matlab code examples.

## Tools
Slightly veering off topic, these are the software tools that I find useful in my audio programming. 

- [Cockos Reaper](http://reaper.fm) - In my opinion Reaper is "the programmer's DAW". Whilst it might not be as immediate as some other DAWs, for anyone who wants to try anything experimental in terms of music technology, Reaper is a great place to do it. This is most obvious to me in the area of spatial audio. Reaper supports up to 64 channels per bus/track - that means you can do 7th order ambisonics in Reaper (since a long time ago). Protools and Nuendo have recently announced 3rd order Ambisonics support (16 channel buses).  7 > 3 go figure. Reaper includes its own scriptable assembly language "JS" (which stands for JesuSonic NOT JavaScript). This can really come in handy for quick custom plug-ins. It also has great metering and visualisation utility plug-ins written with JS. Reaper has its own API so you can make plug-ins that integrate very closely with the DAW at a level that VST etc can't provide.
- [Mathworks Matlab](https://www.mathworks.com/products/matlab.html) - Matlab is a great piece of software, even if open source alternatives such as Octave and Python + ... are equally capable. The audio systems toolbox allows you to build VST plug-ins directly from Matlab. Although it's buried deep in the application, you'll find that Matlab audio systems toolbox uses both WDL-OL and JUCE to provide its plug-in functionality.
- [Cycling '74 Max](https://cycling74.com/) - Max is a great environment to use for prototyping audio plug-ins. There are just so many options for integrating different technologies, I highly recommend it - even if nowadays most of the max patches I make only include a few objects!

## Places
Here are a few links to the various corners of the internet and real-world where you might like to hang out if you like this kind of geeky stuff...

- [musicdsp mailing list](http://sites.music.columbia.edu/cmc/music-dsp/) - The music DSP mailing list is pretty quiet these days, but it still worth signing up, despite the web 0-1 front page. Every now and again a music DSP legend posts something interesting. 
- [KvR Audio DSP and Plug-in Development Forum](https://www.kvraudio.com/forum/viewforum.php?f=33) - This is probably the most active forum for audio DSP that is not aligned with a particular plug-in framework. There are some very smart people, some mavericks and some plain weirdos who hang out here.
- [JUCE Forums](https://forum.juce.com/) - This is a collection of forums centred around the variety of things that JUCE does. Since there is such a huge amount of people using JUCE to make audio software, there is a lot of good info here.
- [Cockos Forums](https://forum.cockos.com) - Another collection of forums centred around Cockos' tools including one for WDL/iPlug and one for Reaper JS.
- [The audio developer conference (ADC)](https://juce.com/adc) - Whilst the other places mentioned here are all virtual, this is a real conference where you can go and meet real people face-to-face who do audio programming - highly recommended! Having been to a lot of more academic conferences, I can say this one is well worth the cost of entry!

___

Oli Larkin 2018  
www.olilarkin.co.uk

## License

[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
