v# playwright
Code for creation of case

import { test, expect } from '@playwright/test';
test.setTimeout(20*10000);
const {LoginPage} =require('../PageObjects/LoginFile')
test('Handle in @medium', async ({ page, baseURL}) => {

    const loginpage=new LoginPage(page)

    await page.goto(baseURL!);
  
    await page.fill('input[type="email"]', 'SogetiTestAutomation@sogetial.onmicrosoft.com');
    await page.click('input[type="submit"]');
  
  
    await page.waitForSelector('input[type="password"]');
    await page.fill('input[type="password"]', 'Xuwa5572!');
  
    
    await page.click('input[type="submit"]');
  
    await page.click('input[type="submit"]');

    let frame = page.frameLocator('#AppLandingPage');
    await frame.locator('a[title="Customer Service Hub"]').click();

    await page.click('li[title="Cases"]');

    await page.click('[title="New Case"]');

    //await page.click('//[@id='id-a72c7955-442b-4ea4-9499-b10cd18b4256-50-name4273edbd-ac1d-40d3-9fb2-095c621b552d-name.fieldControl-text-box-text']');

    await page.fill('//*[@id="id-915f6055-2e07-4276-ae08-2b96c8d02c57-4-title4273edbd-ac1d-40d3-9fb2-095c621b552d-title.fieldControl-text-box-text"]', 'broken keyboard');
    

    await page.fill('//*[@id="id-915f6055-2e07-4276-ae08-2b96c8d02c57-7-customerid270bd3db-d9af-4782-9025-509e298dec0a-customerid.fieldControl-LookupResultsDropdown_customerid_0_textInputBox_with_filter_new"]', "sha");
    
    
   await page.locator('[aria-label="Customer, Lookup"]').waitFor({state : 'visible'});

   await page.locator('[aria-label="Customer, Lookup"]').hover();

   await page.locator('[aria-label="Customer, Lookup"]').fill('sha');

   await page.locator('[aria-label="Customer Lookup results"] ul li').first().click();

   await page.click('[aria-label="Save & Close"]');

   //await page.locator('li').filter({ hasText: 'sha' }).getByLabel('sha').click();

   //await page.click('.pa-xz');
   //await page.click('//*[@id="incident|NoRelationship|Form|Mscrm.SaveAndClosePrimary13-button"]');

});
