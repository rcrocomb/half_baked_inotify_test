# half_baked_inotify_test
Working inotify-using code that does do a while lot (watches '.')

    This one works more than another 'inotify' test I have, but it's not great.
    
    You have to be *in* the directory of interest since it only looks at '.'.  I
    guess I just never got around to handling commandline_options::filenames.
    Ah well.
    
    Output looks something like (if I do a 'touch' once the program is running):
<pre>    
    $ ~/.../main
    main: Signal handler installed.
    main: inotify_init... OK
    main: inotify_add_watch for '.' as 1 (0x000001) ... OK
    main: 1554357971.678 Reading...
    main: Got 32 bytes
    main: wd:     1 (0x000001)
    main: mask:   00000020
    main:   IN_OPEN
    main: cookie: 00000000
    main: len:    16
    main: name: 'fXXXXXH.jpg' length 11
    main: ----------------------------------------------------------------------
    main: 1554357977.409 Reading...
    main: Got 64 bytes
    main: wd:     1 (0x000001)
    main: mask:   00000004
    main:   IN_ATTRIB
    main: cookie: 00000000
    main: len:    16
    main: name: 'fXXXXXH.jpg' length 11
    main: ----------------------------------------------------------------------
    main: wd:     1 (0x000001)
    main: mask:   00000008
    main:   IN_CLOSE_WRITE
    main: cookie: 00000000
    main: len:    16
    main: name: 'fXXXXXH.jpg' length 11
    main: ----------------------------------------------------------------------
    main: 1554357977.409 Reading...
    ^CCaught signal 2: SIGINT -- no error detected
    SIGINT received: synchronous shutdown.
    main: Got -1 bytes
    main: Negative bytes read... quittin' time?
    main: inotify_rm_watch() succeeded
    main: close() succeeded for the inotify_fd
    main: Everything closed down okay
</pre>
