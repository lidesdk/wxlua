wx
==

.. code-block::

 author   : Julian Smart, Robert Roebling
 version  : 2.8.12
 license  : MIT/X11
 website  : http://www.opensource.org/licenses/wxwindows.php

wxLua is a lua scripting language wrapper around the wxWidgets cross-platform GUI library.

.. code-block::

  architectures:     x86
  platforms:         windows

Supports
--------

This incudes the ability to create complex user
interface dialogs, image manipulation, file manipulation, sockets, displaying
HTML, and printing to name a few.


Usage
-----

.. code-block:: lua

  -- Load the wxLua module, does nothing if running from wxLua, wxLuaFreeze, or wxLuaEdit
  package.cpath = package.cpath..";./?.dll;./?.so;../lib/?.so;../lib/vc_dll/?.dll;../lib/bcc_dll/?.dll;../lib/mingw_dll/?.dll;"
  require("wx")

  frame = nil

  function main()

      -- create the frame window
      frame = wx.wxFrame( wx.NULL, wx.wxID_ANY, "wxLua Very Minimal Demo",
                          wx.wxDefaultPosition, wx.wxSize(450, 450),
                          wx.wxDEFAULT_FRAME_STYLE )

      -- show the frame window
      frame:Show(true)
  end

  main()

  -- Call wx.wxGetApp():MainLoop() last to start the wxWidgets event loop,
  -- otherwise the wxLua program will exit immediately.
  -- Does nothing if running from wxLua, wxLuaFreeze, or wxLuaEdit since the
  -- MainLoop is already running or will be started by the C++ program.
  wx.wxGetApp():MainLoop()