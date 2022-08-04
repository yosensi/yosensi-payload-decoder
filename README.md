# Yosensi Payload Decoder

JavaScript code that allows to decode measurement data, sent from Yosensi nodes, into a form readable for the user's applications. It is compatible with the TTN v3 payload formatter and ChirpStack payload codec, including the proper functions and naming of variables. All you need to do is provide encoded data.

## Examples of usage

#### 1. Requirements

We assume that you have at least one Yosensi node added in the ChirpStack or/and TTN console in your application and a LoRaWAN gateway through which data can be transmitted. You can also observe the data transmission between the Yosensi node and the server in the ChirpStack or/and TTN console.

#### 2. Adding a new TTN v3 payload formatter

After entering your application, expand the `Payload formatters` tab from application menu and then select `Uplink`. Next, from the `Formatter Type` list, select `Custom Javascript formatter` and paste Yosensi Payload Decoder code into `Formatter code`. Finally, press the `Save changes` button.

To observe the decoded data go to the `Live data` tab from application menu and open the `Event detail` window by clicking on the `Forward uplink data message` text.

![TTN uplink message details](/img/ttn-uplink-message-details.png)

To decode a single message, copy the bytes of the selected payload and go to the `End devices` tab from application menu. After selecting a specific device, open the `Payload formatters` tab in the device menu, paste the copied bytes into the `Byte payload` field and click the `Test decoder` button. The decoded data will appear in the `Decoded test payload` field.

![TTN payload test](/img/ttn-payload-test.png)

#### 3. Adding a new ChirpStack payload codec

After selecting your organization from the main menu, go to the `Device profiles` tab of the organization. Select or create a new profile and go to the `Codec` tab selected from the profiles menu. From the `Payload codec` drop-down list, select `Custom JavaScript codec functions`. Then paste the Yosensi Payload Ddecoder code into the decoding field. Then click the `UPDATE DEVICE-PROFILE` button.

To observe the decoded data go to the `Applications` tab from the main menu and select the device added with the previously created profile with Yosensi Payload Decoder codec. Go to the `DEVICE DATA` tab from the device menu and expand the entry of one of the `up` packets transmitted from the device.

![ChirpStack uplink message details](/img/chirpstack-uplink-message-details.png)

#### 4. Local testing of payload decoder

Alternatively, if you don't have a LoRaWAN infrastructure, or don't currently have a Yosensi device you plan to add to your system there is an option to test the Yosensi Payload Decoder locally. The script code contains sample payloads from various Yosensi devices. To decode one of the sample payloads, or your own payload from a Yosensi node, put it as an argument to the ```testPayloadV2Decoder()``` function. Below is an example of usage the test function for YO PurePro 3.0:

![TTN payload test](/img/yo-pure-pro-decoded-payload.png)

## License

![BSD 3 Clause](/img/bsd-3-clause.svg)