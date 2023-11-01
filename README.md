# Raspberry Pi Pico SDK Examples

## Getting started

See [Getting Started with the Raspberry Pi Pico](https://rptl.io/pico-get-started) and the README in the [pico-sdk](https://github.com/raspberrypi/pico-sdk) for information
on getting up and running.

### First  Examples

App|Description | Link to prebuilt UF2
---|---|---
[hello_serial](hello_world/serial) | The obligatory Hello World program for Pico (Output over serial version) |
[hello_usb](hello_world/usb) | The obligatory Hello World program for Pico (Output over USB version) | https://rptl.io/pico-hello-usb
[blink](blink) | Blink an LED on and off. | https://rptl.io/pico-blink

### Flash

App|Description
---|---
[cache_perfctr](flash/cache_perfctr) | Read and clear the cache performance counters. Show how they are affected by different types of flash reads.
[nuke](flash/nuke) | Obliterate the contents of flash. An example of a NO_FLASH binary (UF2 loaded directly into SRAM and runs in-place there). A useful utility to drag and drop onto your Pico if the need arises.
[program](flash/program) | Erase a flash sector, program one flash page, and read back the data.
[xip_stream](flash/xip_stream) | Stream data using the XIP stream hardware, which allows data to be DMA'd in the background whilst executing code from flash.
[ssi_dma](flash/ssi_dma) | DMA directly from the flash interface (continuous SCK clocking) for maximum bulk read performance.

### Pico Board

App|Description
---|---
[blinky](picoboard/blinky) | Blink "hello, world" in Morse code on Pico's LED
[button](picoboard/button) | Use Pico's BOOTSEL button as a regular button input, by temporarily suspending flash access.

### Pico W Networking

These examples are for the Pico W, and are only available for `PICO_BOARD=pico_w`

App|Description
---|---
[picow_access_point](pico_w/wifi/access_point) | Starts a WiFi access point, and fields DHCP requests.
[picow_blink](pico_w/wifi/blink) | Blinks the on-board LED (which is connected via the WiFi chip).
[picow_iperf_server](pico_w/wifi/iperf) | Runs an "iperf" server for WiFi speed testing.
[picow_ntp_client](pico_w/wifi/ntp_client) | Connects to an NTP server to fetch and display the current time.
[picow_tcp_client](pico_w/wifi/tcp_client) | A simple TCP client. You can run [python_test_tcp_server.py](pico_w/wifi/python_test_tcp/python_test_tcp_server.py) for it to connect to.
[picow_tcp_server](pico_w/wifi/tcp_server) | A simple TCP server. You can use [python_test_tcp_client.py](pico_w//wifi/python_test_tcp/python_test_tcp_client.py) to connect to it.
[picow_tls_client](pico_w/wifi/tls_client) | Demonstrates how to make a HTTPS request using TLS.
[picow_tls_verify](pico_w/wifi/tls_client) | Demonstrates how to make a HTTPS request using TLS with certificate verification.
[picow_wifi_scan](pico_w/wifi/wifi_scan) | Scans for WiFi networks and prints the results.
[picow_udp_beacon](pico_w/wifi/udp_beacon) | A simple UDP transmitter.

### Pico W Bluetooth

These examples are for the Pico W, and are only available for `PICO_BOARD=pico_w`.
They are examples from the Blue Kitchen Bluetooth stack, see [here](https://bluekitchen-gmbh.com/btstack/#examples/examples/index.html) for a full description.

By default, the Bluetooth examples are only built in one "mode" only (*background*, *poll*, or *freertos*), with the 
default being *background*. This can be changed by passing `-DBTSTACK_EXAMPLE_TYPE=poll` etc. to `CMake`, or all 
examples can be built (which may be slow) by passing `-DBTSTACK_EXAMPLE_TYPE=all`
Freertos versions can only be built if `FREERTOS_KERNEL_PATH` is defined.

App|Description
---|---
[picow_bt_example_a2dp_sink_demo](https://github.com/bluekitchen/btstack/tree/master/example/a2dp_sink_demo.c) | A2DP Sink - Receive Audio Stream and Control Playback.
[picow_bt_example_a2dp_source_demo](https://github.com/bluekitchen/btstack/tree/master/example/a2dp_source_demo.c) | A2DP Source - Stream Audio and Control Volume.
[picow_bt_example_ancs_client_demo](https://github.com/bluekitchen/btstack/tree/master/example/ancs_client_demo.c) | LE ANCS Client - Apple Notification Service.
[picow_bt_example_att_delayed_response](https://github.com/bluekitchen/btstack/tree/master/example/att_delayed_response.c) | LE Peripheral - Delayed Response.
[picow_bt_example_audio_duplex](https://github.com/bluekitchen/btstack/tree/master/example/audio_duplex.c) | Audio Driver - Forward Audio from Source to Sink.
[picow_bt_example_avrcp_browsing_client](https://github.com/bluekitchen/btstack/tree/master/example/avrcp_browsing_client.c) | AVRCP Browsing - Browse Media Players and Media Information.
[picow_bt_example_dut_mode_classic](https://github.com/bluekitchen/btstack/tree/master/example/dut_mode_classic.c) | Testing - Enable Device Under Test (DUT.c) Mode for Classic.
[picow_bt_example_gap_dedicated_bonding](https://github.com/bluekitchen/btstack/tree/master/example/gap_dedicated_bonding.c) | GAP bonding
[picow_bt_example_gap_inquiry](https://github.com/bluekitchen/btstack/tree/master/example/gap_inquiry.c) | GAP Classic Inquiry.
[picow_bt_example_gap_le_advertisements](https://github.com/bluekitchen/btstack/tree/master/example/gap_le_advertisements.c) | GAP LE Advertisements Scanner.
[picow_bt_example_gap_link_keys](https://github.com/bluekitchen/btstack/tree/master/example/gap_link_keys.c) | GAP Link Key Management (Classic.c).
[picow_bt_example_gatt_battery_query](https://github.com/bluekitchen/btstack/tree/master/example/gatt_battery_query.c) | GATT Battery Service Client.
[picow_bt_example_gatt_browser](https://github.com/bluekitchen/btstack/tree/master/example/gatt_browser.c) | GATT Client - Discover Primary Services.
[picow_bt_example_gatt_counter](https://github.com/bluekitchen/btstack/tree/master/example/gatt_counter.c) | GATT Server - Heartbeat Counter over GATT.
[picow_bt_example_gatt_device_information_query](https://github.com/bluekitchen/btstack/tree/master/example/gatt_device_information_query.c) | GATT Device Information Service Client.
[picow_bt_example_gatt_heart_rate_client](https://github.com/bluekitchen/btstack/tree/master/example/gatt_heart_rate_client.c) | GATT Heart Rate Sensor Client.
[picow_bt_example_gatt_streamer_server](https://github.com/bluekitchen/btstack/tree/master/example/gatt_streamer_server.c) | Performance - Stream Data over GATT (Server.c).
[picow_bt_example_hfp_ag_demo](https://github.com/bluekitchen/btstack/tree/master/example/hfp_ag_demo.c) | HFP AG - Audio Gateway.
[picow_bt_example_hfp_hf_demo](https://github.com/bluekitchen/btstack/tree/master/example/hfp_hf_demo.c) | HFP HF - Hands-Free.
[picow_bt_example_hid_host_demo](https://github.com/bluekitchen/btstack/tree/master/example/hid_host_demo.c) | HID Host Classic.
[picow_bt_example_hid_keyboard_demo](https://github.com/bluekitchen/btstack/tree/master/example/hid_keyboard_demo.c) | HID Keyboard Classic.
[picow_bt_example_hid_mouse_demo](https://github.com/bluekitchen/btstack/tree/master/example/hid_mouse_demo.c) | HID Mouse Classic.
[picow_bt_example_hog_boot_host_demo](https://github.com/bluekitchen/btstack/tree/master/example/hog_boot_host_demo.c) | HID Boot Host LE.
[picow_bt_example_hog_host_demo](https://github.com/bluekitchen/btstack/tree/master/example/hog_host_demo.c) | HID Host LE.
[picow_bt_example_hog_keyboard_demo](https://github.com/bluekitchen/btstack/tree/master/example/hog_keyboard_demo.c) | HID Keyboard LE.
[picow_bt_example_hog_mouse_demo](https://github.com/bluekitchen/btstack/tree/master/example/hog_mouse_demo.c) | HID Mouse LE.
[picow_bt_example_hsp_ag_demo](https://github.com/bluekitchen/btstack/tree/master/example/hsp_ag_demo.c) | HSP AG - Audio Gateway.
[picow_bt_example_hsp_hs_demo](https://github.com/bluekitchen/btstack/tree/master/example/hsp_hs_demo.c) | HSP HS - Headset.
[picow_bt_example_le_credit_based_flow_control_mode_client](https://github.com/bluekitchen/btstack/tree/master/example/le_credit_based_flow_control_mode_client.c) | LE Credit-Based Flow-Control Mode Client - Send Data over L2CAP.
[picow_bt_example_le_credit_based_flow_control_mode_server](https://github.com/bluekitchen/btstack/tree/master/example/le_credit_based_flow_control_mode_server.c) | LE Credit-Based Flow-Control Mode Server - Receive data over L2CAP.
[picow_bt_example_led_counter](https://github.com/bluekitchen/btstack/tree/master/example/led_counter.c) | Hello World - Blinking a LED without Bluetooth.
[picow_bt_example_le_mitm](https://github.com/bluekitchen/btstack/tree/master/example/le_mitm.c) | LE Man-in-the-Middle Tool.
[picow_bt_example_le_streamer_client](https://github.com/bluekitchen/btstack/tree/master/example/le_streamer_client.c) | Performance - Stream Data over GATT (Client.c).
[picow_bt_example_mod_player](https://github.com/bluekitchen/btstack/tree/master/example/mod_player.c) | Audio Driver - Play 80's MOD Song.
[picow_bt_example_nordic_spp_le_counter](https://github.com/bluekitchen/btstack/tree/master/example/nordic_spp_le_counter.c) | LE Nordic SPP-like Heartbeat Server.
[picow_bt_example_nordic_spp_le_streamer](https://github.com/bluekitchen/btstack/tree/master/example/nordic_spp_le_streamer.c) | LE Nordic SPP-like Streamer Server.
[picow_bt_example_sdp_general_query](https://github.com/bluekitchen/btstack/tree/master/example/sdp_general_query.c) | SDP Client - Query Remote SDP Records.
[picow_bt_example_sdp_rfcomm_query](https://github.com/bluekitchen/btstack/tree/master/example/sdp_rfcomm_query.c) | SDP Client - Query RFCOMM SDP record.
[picow_bt_example_sine_player](https://github.com/bluekitchen/btstack/tree/master/example/sine_player.c) | Audio Driver - Play Sine.
[picow_bt_example_sm_pairing_central](https://github.com/bluekitchen/btstack/tree/master/example/sm_pairing_central.c) | LE Central - Test Pairing Methods.
[picow_bt_example_sm_pairing_peripheral](https://github.com/bluekitchen/btstack/tree/master/example/sm_pairing_peripheral.c) | LE Peripheral - Test Pairing Methods.
[picow_bt_example_spp_and_gatt_counter](https://github.com/bluekitchen/btstack/tree/master/example/spp_and_gatt_counter.c) | Dual Mode - SPP and LE Counter.
[picow_bt_example_spp_and_gatt_streamer](https://github.com/bluekitchen/btstack/tree/master/example/spp_and_gatt_streamer.c) | Dual Mode - SPP and LE streamer.
[picow_bt_example_spp_counter](https://github.com/bluekitchen/btstack/tree/master/example/spp_counter.c) | SPP Server - Heartbeat Counter over RFCOMM.
[picow_bt_example_spp_flowcontrol](https://github.com/bluekitchen/btstack/tree/master/example/spp_flowcontrol.c) | SPP Server - RFCOMM Flow Control.
[picow_bt_example_spp_streamer_client](https://github.com/bluekitchen/btstack/tree/master/example/spp_streamer_client.c) | Performance - Stream Data over SPP (Client.c).
[picow_bt_example_spp_streamer](https://github.com/bluekitchen/btstack/tree/master/example/spp_streamer.c) | Performance - Stream Data over SPP (Server.c).
[picow_bt_example_ublox_spp_le_counter](https://github.com/bluekitchen/btstack/blob/master/example/ublox_spp_le_counter.c) | LE u-blox SPP-like Heartbeat Server.

Some Standalone Bluetooth examples (without all the common example build infrastructure) are also available:

App|Description
---|---
[picow_ble_temp_sensor](pico_w/bt/standalone) | Reads from the on board temperature sensor and sends notifications via BLE
[picow_ble_temp_sensor_with_wifi](pico_w/bt/standalone) | Same as above but also connects to Wi-Fi and starts an "iperf" server
[picow_ble_temp_reader](pico_w/bt/standalone) | Connects to one of the above "sensors" and reads the temperature
