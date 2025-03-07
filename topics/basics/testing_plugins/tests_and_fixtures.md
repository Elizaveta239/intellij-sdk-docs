[//]: # (title: Tests and Fixtures)

<!-- Copyright 2000-2021 JetBrains s.r.o. and other contributors. Use of this source code is governed by the Apache 2.0 license that can be found in the LICENSE file. -->

The IntelliJ Platform testing infrastructure is not tied to any specific test framework. In fact, the IntelliJ IDEA Team uses [JUnit](https://junit.org), [TestNG](https://testng.org), and [Cucumber](https://cucumber.io/) for testing different parts of the project. However, most of the tests are written using JUnit 3.

When writing your tests, you have the choice between using a standard base class to perform the test set up for you and using a fixture class, which lets you perform the setup manually and does not tie you to a specific test framework.

With the former approach, you can use classes such as [`BasePlatformTestCase`](upsource:///platform/testFramework/src/com/intellij/testFramework/fixtures/BasePlatformTestCase.java) ([`LightPlatformCodeInsightFixtureTestCase`](upsource:///platform/testFramework/src/com/intellij/testFramework/fixtures/LightPlatformCodeInsightFixtureTestCase.java) before 2019.2).

With the latter approach, you use the [`IdeaTestFixtureFactory`](upsource:///platform/testFramework/src/com/intellij/testFramework/fixtures/IdeaTestFixtureFactory.java) class to create instances of fixtures for the test environment. You need to call the fixture creation and setup methods from the test setup method used by your test framework.