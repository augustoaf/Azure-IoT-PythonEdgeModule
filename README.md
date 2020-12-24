Module App in Python using the SimulatedTemperatureSensor to process (retain based on a desired parameter) data before send to cloud

It has a listener to receive the input from the SimulatedTemperatureSensor and also another to receive Twin (Desired) Property changes.
Note: The routes "SimulatedTemperatureSensor to the custom module app" and from the custom module app to IoT Hub must be configured. The Twin Desired temperature Threshold must be set as well.

Name the Module as CustomPythonApp to deploy on Edge Runtime, then use the routes in the deployment manifest.

Troubleshooting:
1- When running Module in the Edge Runtime
 ssl.SSLCertVerificationError: [SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed: IP address mismatch, certificate is not valid for
This error happened when I have "ip address" as "edge hostname" in "/etc/iotedge/config.yaml" file.
Solution: change to the edge hostname (e.g., raspberrypi - must be all in lowercase, then on downstream devices, set the same and add on "hosts, is windows, the dns translation")


by Augusto