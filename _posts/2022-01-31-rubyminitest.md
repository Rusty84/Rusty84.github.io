---
layout: post
title: Run Selenium Tests in Ruby - Minitest
categories: [Blog, Selenium, Ruby]
tags: [Blog, Selenium, Ruby]
fullview: false
comments: false
---
<h3>What is Minitest?</h3>
Minitest is a testing framework for Ruby that provides a complete suite of testing facilities. It is quick to run and supports TDD, BDD, mocking, and benchmarking.
<br>

Here is a script using Ruby, Selenium WebDriver and Minitest to assert that the 'page title' for the Restful Booker Platform is equal to "Restful-booker-platform demo".
<br>

```rb
require 'rubygems'
require "selenium-webdriver"
require 'minitest/autorun'

class Test < Minitest::Test

	def test_page_title

		#Chrome browser instantiation
		driver = Selenium::WebDriver.for :chrome

		# maximize the browser window.
		driver.manage.window.maximize

		#Loading the Restful Booker URL
		driver.navigate.to "https://automationintesting.online/#/admin"

		# create a wait with a timeout of 15
		wait = Selenium::WebDriver::Wait.new(timeout: 15)

		# dismiss dropdown
		button = wait.until {
		element = driver.find_element(:xpath, "//button[text()='Let me hack!']")
		element if element.displayed?
		}
		button.click()

		#Populate username
		input = wait.until {
		element = driver.find_element(:id, "username")
		element if element.displayed?
		}
		input.send_keys("admin")

		#Populate password
		input = wait.until {
		element = driver.find_element(:id, "password")
		element if element.displayed?
		}
		input.send_keys("password")

		# click login button
		button = wait.until {
		element = driver.find_element(:id, "doLogin")
		element if element.displayed?
		}
		button.click()

		# assert page title
		assert_equal(driver.title, "russmorley.net")

		driver.quit

	end

end
```
<br>
<h3>Result</h3> 
<br>
The test has failed. From the test output below. We can see that the actual page title is "Restful-booker-platform demo"

The assertion made was against "russmorley.net". The test correctly failed.
<br>
<br>
<img src="/assets/media/mini_one.png">
<br>
<br>
Let's update the assertion in our script to "Restful-booker-platform demo"
<br>
```rb
require 'rubygems'
require "selenium-webdriver"
require 'minitest/autorun'

class Test < Minitest::Test

	def test_page_title

		#Chrome browser instantiation
		driver = Selenium::WebDriver.for :chrome

		# maximize the browser window.
		driver.manage.window.maximize

		#Loading the Restful Booker URL
		driver.navigate.to "https://automationintesting.online/#/admin"

		# create a wait with a timeout of 15
		wait = Selenium::WebDriver::Wait.new(timeout: 15)

		# dismiss dropdown
		button = wait.until {
		element = driver.find_element(:xpath, "//button[text()='Let me hack!']")
		element if element.displayed?
		}
		button.click()

		#Populate username
		input = wait.until {
		element = driver.find_element(:id, "username")
		element if element.displayed?
		}
		input.send_keys("admin")

		#Populate password
		input = wait.until {
		element = driver.find_element(:id, "password")
		element if element.displayed?
		}
		input.send_keys("password")

		# click login button
		button = wait.until {
		element = driver.find_element(:id, "doLogin")
		element if element.displayed?
		}
		button.click()

		# assert page title
		assert_equal(driver.title, "Restful-booker-platform demo")

		driver.quit

	end

end
```
<br>
<h3>Result</h3> 
<br>
Success! The test has passed. From the test output below. We can see that the assertion has been made correctly without any failures.
<br>
<br>
<img src="/assets/media/mini_two.png">