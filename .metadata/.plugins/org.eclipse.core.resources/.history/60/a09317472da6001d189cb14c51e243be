package pages;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.time.Duration;
import java.util.Properties;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.WebDriverWait;



public abstract class AbstractPage {
	
	Properties prop;
	WebDriver driver ;
	WebDriverWait wait;
	
	
	
	public AbstractPage(WebDriver driver) {
		this.driver =driver;
        }

		public abstract String getTitle();
		public abstract WebElement getElementforPage ( By locator);
		public abstract void waitforElementPresent ( By locator);
		public abstract void waitForPageTitle (String title);
		
		public <Tpage extends BasePage> Tpage getInstancePage(Class<Tpage> pageClass) {
			// in get instance method we are passsing a pageClass which has reference of Tpage. Here, this get instance
			//method will return a Tpage which is extended to basepage. now create Base page class
			//this will help to get instance of any class that wee give to it.
			// page.getInstance(Loginpage.class).doLogin()// here, we are calling get instance from page class and using it with passing login page class and calling doLoginmethod()...
			//thi way we do not need to create isntace of the Login page.
			try {
				return pageClass.getDeclaredConstructor(WebDriver.class).newInstance(this.driver);
			} catch(Exception e) {
				e.printStackTrace();
				return null;
			}
			
		
		}

}
