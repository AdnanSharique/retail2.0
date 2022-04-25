1. Define the variables;
   
   ```powershell
   $appservicename="aidevproductsearchdev01"
   $rgname = "rg-apptest"
   $location = "eastus"
   $build_path = "/home/sanjay/march302022/ddibproductsearch/build"
   $app_service_plan="Sanjaypant_asp_2513"
   $default_path = (Get-Location).path
   ```
   
   2. Replace urls for config-prod.js in public folder
      
      ```js
      product_search_function_name = ""
      bot_url = ""
      ```
   
   3. Inside build directory, run the following command:
   
   ```powershell
   Set-Location -Path $build_path;
   az webapp up -n $appservicename -g $rgname -l $location -p $app_service_plan --html;
   Set-Location -Path $default_path;
   ```


