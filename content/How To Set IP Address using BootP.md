**1) Connect your PC to the same Ethernet Network as your SLC-5/05.**

2) Launch the BootP-DHCP Tool installed with RSLinx Classic:

3) If this is the first time you’ve launched the tool, there are a few initial steps:

– First, accept the license agreement:

– Then select the Ethernet connection you’ll be using to connect to your SLC-5/05:

– Then, if prompted, allow the tool to communicate to your networks:

[![](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-0c.png?resize=544%2C404&ssl=1)](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-0c.png?ssl=1)

**– Then click on “OK” in the “Network Setup Error” window, and at a minimum enter in your network mask in the “Network Settings” window:**

[![](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-0d.png?resize=300%2C167&ssl=1)](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-0d.png?ssl=1)[![](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-1b.png?resize=326%2C311&ssl=1)](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-1b.png?ssl=1)

**4) Once the tool is up and running, you should see your SLC-5/05’s MAC Address in the Top “Discovery History” list. If it does not show up, try cycling power to your SLC-5/05:**

[![](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-3b.png?resize=659%2C454&ssl=1)](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-3b.png?ssl=1)**NOTE: You’ll find your SLC-5/05’s MAC Address on the bottom of the left side of the controller, as can be seen in our SLC-500 controller image gallery** [**HERE**](https://theautomationblog.com/the-slc-500-controller-image-gallery/)**.**

**5) Once you’re SLC-5/05 shows up in the “Discovery History” list, double click on it (or select it, and then click on the “Add Relation” button) to bring up the “New Entry” window. There, fill in the IP Address you wish to give your SLC-5/05, and then click on OK:**

[![](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-4b.png?resize=655%2C447&ssl=1)](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-4b.png?ssl=1)**6) Once the above is done, your SLC-5/05 should show up in the “Entered Relations” list as shown below:**

[![](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-5b.png?resize=661%2C452&ssl=1)](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-5b.png?ssl=1)**NOTE: At this point we have only assigned the SLC-5/05 a temporary IP Address as it is still set for BOOTP. If we were to cycle power to the SLC-5/05 it would likely lose it’s IP Address and request another. For that reason we must continue on and disable BOOTP, which for some devices can be done right in this Tool as shown in the next step.**

**7) The last step is to disable BOOTP in the SLC-5/05 so it will maintain the address we just gave it. To do this, select the SLC-5/05 in the “Entered Relations” list and then click on “Disable BOOTP/DHCP:”**

[![](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-5b.png?resize=661%2C452&ssl=1)](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/10/TheAutomationBlog-SLC505-BOOTP-5b.png?ssl=1)**8) If you do not get the below message saying BOOTP was disabled successfully (this image is from a previous version,) it likely did not work. If that is the case, you’ll need to go online with the controller and disable BOOTP, as shown in this article** [**HERE**](https://theautomationblog.com/the-slc-5-05-how-to-set-the-ethernet-ip-address-using-rslogix-500/)**.**

![](https://i0.wp.com/theautomationblog.com/wp-content/uploads/2018/09/TheAutomationBlog-SLC505-BOOTP-8.png?resize=670%2C120&ssl=1)