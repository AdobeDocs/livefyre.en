---
description: Run stress tests against the Livefyre platform.
seo-description: Run stress tests against the Livefyre platform.
seo-title: Stress Test Policy
solution: Experience Manager
title: Stress Test Policy
uuid: f2d49b55-f4fc-485f-9aea-a17ce64813ee
exl-id: cb87b6ca-4107-46fc-9b1e-dc9399ec6d3a
---
# Stress Test Policy{#stress-test-policy}

Run stress tests against the Livefyre platform.

This document provides guidance on running stress tests against the Livefyre platform. Ad-hoc testing by customers without notification is strictly prohibited. For more on [prohibited and allowed activities](#c_stress_test_policy/section_mhs_bfz_vdb).

>[!NOTE]
>
>Stress tests are optional. You are not required or expected to perform a stress test. Adobe Livefyre conducts regular stress tests and validations as part of the release process. If you choose to run tests, this document outlines the requirements and constraints for conducting stress tests.

## Notification {#section_ihs_bfz_vdb}

You must notify your Livefyre Customer Success Specialist and Adobe Technical Consultant of your planned tests three or more weeks in advance of when you plan to start.

To notify Livefyre, submit the following information to your Livefyre Customer Success Specialist and Adobe Technical Consultant:

* Purpose and description of the test 
* The use case you are testing against
* List of any Livefyre APIs you plan to use in the test
* Date, time, and duration of test
* IP addresses from which you will initiate the tests

## Requirements {#section_khs_bfz_vdb}

You may perform tests only if they meet the following requirements:

* You must receive explicit, written approval from an Adobe Technical Consultant 3 weeks or more before you begin the test.
* **You may only perform tests on the UAT Network.** 
* You must test against realistic scenarios. For example, you may not assume that your property will service *millions* of post requests every day, because this is not a realistic scenario. If you need assistance determining whether your scenario is realistic or not, ask your Livefyre Customer Success Specialist or Adobe Technical Consultant.
* Tests should be conducted during business hours for the Pacific Standard Time zone \(UTC -7\).
* You may need to produce data and your reasoning for the test.

## Governance {#section_mhs_bfz_vdb}

Livefyre reserves the right to terminate a test at any time if you perform a test:

* On the Production Network.
* Without explicit, written approval from an Adobe Technical Consultant three weeks or more in advance.
* Against unreal scenarios.

Livefyre terminates tests by blocking access to APIs, disabling Livefyre Networks, and refusing a load test request if it does not meet the requirements.
