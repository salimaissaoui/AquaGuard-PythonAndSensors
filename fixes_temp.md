  Fixes applied                                                                          #: 1
  File: .ino:224-228                                                                   
  Fix: Motor watchdog — auto-stops after 500ms with no DIR command
  Verified: Test 1: watchdog fired 0.46s after last cmd
  ────────────────────────────────────────
  #: 2
  File: .ino:152
  Fix: Serial.setTimeout(100) — prevents 1s stall on partial data
  Verified: Compiles and runs correctly
  ────────────────────────────────────────
  #: 3
  File: .ino:183-188
  Fix: Accelerometer no longer bricks the board if missing
  Verified: Board boots without ADXL345 connected
  ────────────────────────────────────────
  #: 4
  File: .ino:185
  Fix: Wire.setWireTimeout(3000, true) — I2C bus can't hang forever
  Verified: Board boots without ADXL345 connected
  ────────────────────────────────────────
  #: 5
  File: .ino:341-349
  Fix: Motor state logging (MOTOR:FWD/REV/STOP/WATCHDOG_STOP)
  Verified: Both tests show clean state transitions
  ────────────────────────────────────────
  #: 6
  File: LiveFeedWithGetAndSend.py:186
  Fix: post_reading() wrapped in asyncio.to_thread()
  Verified: Event loop no longer blocked
  ────────────────────────────────────────
  #: 7
  File: LiveFeedWithGetAndSend.py:221
  Fix: Token fetch wrapped in asyncio.to_thread()
  Verified: Event loop no longer blocked
  ────────────────────────────────────────
  #: 8
  File: LiveFeedWithGetAndSend.py:59
  Fix: reset_output_buffer() before serial write
  Verified: Test 2: stop arrived in 0.04s after 584 cmds at 60Hz
