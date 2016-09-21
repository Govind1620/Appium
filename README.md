package com.sahara;

import java.net.MalformedURLException;
import java.net.URL;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.Capabilities;
import org.openqa.selenium.SearchContext;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.remote.DesiredCapabilities;
import org.openqa.selenium.remote.RemoteWebDriver;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;

import io.appium.java_client.android.AndroidDriver;

public class Task {

	//public static void main(String[] args) throws MalformedURLException {
			
		@BeforeTest
		public void setUp() throws MalformedURLException {
WebDriver driver;

				
	DesiredCapabilities capabilities=new DesiredCapabilities();
	capabilities.setCapability("BROWSER_NAME", "Android");
    capabilities.setCapability("VERSION", "5.0");
    capabilities.setCapability("DeviceName", "0123456789ABCDEF");
    capabilities.setCapability("platfromName", "Android");
    
    capabilities.setCapability("appPackage", "com.nikiapp");
    
    capabilities.setCapability("appActivity", "com.nikiapp.task");
    
    driver = new RemoteWebDriver(new URL("http://127.0.0.1:4723/wd/hub"), capabilities);
    driver.manage().timeouts().implicitlyWait(15, TimeUnit.SECONDS);
   
    
		}
		

		@Test
		public void hiMessage(){
			By driver;
			driver.findElements((SearchContext) By.xpath("//android.widget.TextView")).get(1).click();
				driver.findElements((SearchContext) By.xpath("//android.widget.EditText")).get(0).sendKeys("Hi"); // This is for group chat
				driver.findElements((SearchContext) By.xpath("//android.widget.ImageView")).get(0).click();
				driver.findElements((SearchContext) By.xpath("//android.widget.RelativeLayout")).get(1).click();
				driver.findElements((SearchContext) By.xpath("//android.widget.EditText")).get(0).sendKeys("Hi");  // This is for individual chat
				driver.findElements((SearchContext) By.xpath("//android.widget.ImageView")).get(1).click();
				
				
				
				
		}
