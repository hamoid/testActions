A quick test of caching apt packages in GitHub actions for faster completion of actions.

Here I tested running `xvfb-run glxinfo -B`. In worst case it has taken over 2 minutes in the past. Using caching makes it happen in a second.

I also tested having two separate actions that need the same package to see if it's cached for both. It seems to be the case.

The log shows

```
Found 13 files in the cache.
- cache_key.md5
- install.log
- libdecor-0-0=0.2.2-1build2.tar
- libdecor-0-plugin-1-gtk=0.2.2-1build2.tar
- libegl-mesa0=25.0.7-0ubuntu0.24.04.1.tar
- libegl1=1.7.0-1build1.tar
- libgles2=1.7.0-1build1.tar
- libxcb-xkb1=1.15-1ubuntu2.tar
- libxkbcommon-x11-0=1.6.0-1build1.tar
- manifest_all.log
- manifest_main.log
- mesa-utils-bin=9.0.0-2.tar
- mesa-utils=9.0.0-2.tar

Reading from main requested packages manifest...
- mesa-utils=9.0.0-2
done

Restoring 9 packages from cache...
- libdecor-0-0=0.2.2-1build2.tar restoring...
  done
- libdecor-0-plugin-1-gtk=0.2.2-1build2.tar restoring...
  done
- libegl-mesa0=25.0.7-0ubuntu0.24.04.1.tar restoring...
  done
- libegl1=1.7.0-1build1.tar restoring...
  done
- libgles2=1.7.0-1build1.tar restoring...
  done
- libxcb-xkb1=1.15-1ubuntu2.tar restoring...
  done
- libxkbcommon-x11-0=1.6.0-1build1.tar restoring...
  done
- mesa-utils-bin=9.0.0-2.tar restoring...
  done
- mesa-utils=9.0.0-2.tar restoring...
  done
done
```
