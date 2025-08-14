# test
driver.manage().window().maximize();
driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10000));

WebElement alertBox = driver.findElement(By.id("alertexamples"));
alertBox.click();
Alert alert = driver.switchTo().alert();
Thread.sleep(5000);
alert.accept();

confirmBox.click();
Thread.sleep(5000);
Alert confirmAlert = driver.switchTo().alert();
confirmAlert.accept();
// Page scroll down
JavascriptExecutor jse = (JavascriptExecutor) driver;
jse.executeScript("window.scrollBy(0, 250)");

promptBox.click();
Alert promptalert = driver.switchTo().alert();
Thread.sleep(5000);
promptalert.sendKeys("HELLO");
promptalert.accept();

WebElement getPositionButton = driver.findElement(By.id("j_idt88:j_idt94"));
Point xyPoint = getPositionButton.getLocation();
int xValue = xyPoint.getX();
int yValue = xyPoint.getY();
System.out.println("X value is: " + xValue + " Y value is: " + yValue);
WebElement colourButton = driver.findElement(By.id("j_idt88:j_idt96"));
String colour = colourButton.getCssValue("background");
System.out.println("Button colour is: " + colour);
WebElement sizeButton = driver.findElement(By.id("j_idt88:j_idt98"));
int height = sizeButton.getSize().getHeight();
int width = sizeButton.getSize().getWidth();
System.out.println("Button Height is: " + height + " Button Width is: " + width);


WebElement ajaxOption = driver.findElement(By.xpath("//*[@id='j_idt87:j_idt91']/span"));
boolean ajaxStatus = ajaxOption.isSelected();
System.out.println("Ajax CheckBox Status is: " + ajaxStatus);

WebElement From = driver.findElement(By.xpath("//*[@id='form:drag_content']"));
WebElement To = driver.findElement(By.xpath("//*[@id='form:drop_header']"));
Actions actions = new Actions(driver);
Thread.sleep(5000);
actions.dragAndDrop(From, To).build().perform();
System.out.println("Successfully Dropped");

WebElement dropDown1 = driver.findElement(By.xpath("//*[@id=\"j_idt87\"]/div/div[1]/div[1]/div/div/select"));
Select select = new Select(dropDown1);
select.selectByIndex(1);
select.selectByVisibleText("Cypress");
List<WebElement> listOfOptions = select.getOptions();
int size = listOfOptions.size();
System.out.println("Number of Elements: " + size);
dropDown1.sendKeys("Playwright");

WebElement dropdown = driver.findElement(By.xpath("//select[@name='country']"));
if (dropdown.isEnabled() && dropdown.isDisplayed()) {
System.out.println("Dropdown is enabled and visible");
} else {
System.out.println("Dropdown is not visible");
}
Select select = new Select(dropdown);
if (select.isMultiple()) {
System.out.println("Dropdown list accepts multiple choices");
} else {
System.out.println("Dropdown list does not accept multiple choices");
}
int listSize = select.getOptions().size();
System.out.println("List size: " + listSize);
select.selectByVisibleText("India");
String getText = select.getFirstSelectedOption().getText();
System.out.println("Option chosen: " + getText);

File fileLoc = new File("D:\\CODE\\Temp-TestFiles\\");
File[] totFile = fileLoc.listFiles();
for(File file:totFile) {
if(file.getName().equals("TestLeaf Logo.png"));
System.out.println("File Download Successfull");

WebElement radio1 = driver.findElement(By.xpath("//*[@id='app']/div[1]/div[2]/div[2]/div/div/div/div[2]/div[1]/form/div[3]/div[2]/div[2]/div/div[2]/div[2]/div[2]/div/label/span"));
boolean selectState = radio1.isSelected();
if (!selectState) {
radio1.click();
}
JavascriptExecutor jse = (JavascriptExecutor) driver;
jse.executeScript("window.scrollBy(0,250)");
Thread.sleep(5000);
JavascriptExecutor jsel = (JavascriptExecutor) driver;
jsel.executeScript("window.scrollBy(0,-250)");

WebElement firstButton = driver.findElement(By.xpath("//*[@id='j_idt88:new']/span"));
firstButton.click();
Set<String> handles = driver.getWindowHandles();
System.out.println("Window Handles: " + handles);
for (String newWindow : handles) {
if (!newWindow.equals(oldWindow)) {
driver.switchTo().window(newWindow);
break;
}
}
WebElement textBox = driver.findElement(By.xpath("//*[@id='email']"));
textBox.sendKeys("mcavit@gmail.com");

driver.switchTo().defaultContent();
List<WebElement> totalFrames = driver.findElements(By.tagName("iframe"));
int size = totalFrames.size();
System.out.println("Total no of Frames: " + size);
driver.switchTo().frame(0);
WebElement button1 = driver.findElement(By.id("Click"));
button1.click();
String text = button1.getText();
System.out.println(text);
driver.switchTo().defaultContent();
driver.switchTo().frame(2);
driver.switchTo().frame("frame2");
WebElement button2 = driver.findElement(By.xpath("//*[@id='Click']"));
button2.click();
String text1 = button2.getText();
System.out.println(text1);
driver.switchTo().defaultContent();
System.out.println("Switched to default!!");

String file = "D:\\CODE\\Temp-TestFiles\\infix+prefix.txt";
StringSelection selection = new StringSelection(file);
Toolkit.getDefaultToolkit().getSystemClipboard().setContents(selection, null);
Robot robot = new Robot();
robot.keyPress(KeyEvent.VK_CONTROL);
robot.keyPress(KeyEvent.VK_V);
robot.keyRelease(KeyEvent.VK_CONTROL);
robot.keyPress(KeyEvent.VK_ENTER);
robot.keyRelease(KeyEvent.VK_ENTER);
