Improving Location Performance
==================================

ODK Collect uses Android's `Fused Location Provider <https://developers.google.com/location-context/fused-location-provider>`_ to get a device's geolocation. This means data from multiple sensors including GPS, WiFi and Bluetooth are combined to quickly compute accurate geolocation readings. When Collect is accessing your device's geolocation, you will see a location (:fa:`map-marker`) icon in the upper right corner of your screen. Learn more about geolocation-based questions in :ref:`the question types section <location-widgets>`.


.. warning::
  Some versions of ODK Collect prior to v1.28.0 use raw location sensors because of an Android bug. If you are having trouble getting a geolocation reading, first make sure you are using the latest version of ODK Collect.

Devices
--------

Different devices can have dramatically different quality sensors. If you are having trouble getting a geolocation reading from a specific device, it is likely either because the device model does not have high-quality sensors or because the specific device has a faulty sensor. If you can, try going to the same geolocation with a different device to compare performance. Sensor quality has dramatically improved over the years so in general, newer devices will get higher-accuracy readings more quickly.

Android Location Settings
--------------------------

Different Android versions provide different settings for controlling how geolocation is captured. See how to configure Android location `in the Android documentation <https://support.google.com/accounts/answer/3467281>`_. In general, the more different sensors are available to Android, the better its geolocation estimation will be so make sure they are all enabled.

Helping the GPS Sensor
------------------------

GPS works by receiving signals from specific satellites so to help your device get a geolocation reading, get as clear of a view of the sky as possible. GPS does not work inside of buildings and will be affected by obstacles like dense forest canopy or tall buildings. It is typically the main technology used to identify a device's geolocation anywhere other than in urban areas where multiple WiFi access points and cell towers can be accessed at the same time. 

It can take a while to get satellite lock when first attempting to get a geolocation. You can use a :ref:`background location question <metadata-start-geopoint>` at the beginning of your form definition to "warm" the GPS before data collectors to answer a :ref:`location question <location-widgets>`. You can also use an external app such as `GPS Status & Toolbox <https://play.google.com/store/apps/details?id=com.eclipsim.gpsstatus2>`_ for this purpose. Additionally, this application can help you troubleshoot GPS issues. See `its documentation <https://mobiwia.com/gpsstatus/>`_ for more details.