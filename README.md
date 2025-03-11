import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.Test;

public class SeleniumTest {
    WebDriver driver;

    @BeforeClass
    public void setUp() {
        // Set up the path for ChromeDriver
        System.setProperty("webdriver.chrome.driver", "path_to_chromedriver");

        // Initialize the driver
        driver = new ChromeDriver();
    }

    @Test
    public void testTitle() {
        // Navigate to a website
        driver.get("https://www.example.com");

        // Get the page title
        String title = driver.getTitle();

        // Assert that the title is as expected
        Assert.assertEquals(title, "Example Domain");
    }

    @AfterClass
    public void tearDown() {
        // Close the browser
        driver.quit();
    }
}
