1. Create the Azure Function
   
   ```powershell
   az functionapp create --resource-group rg-dmdemoAIDev --consumption-plan-location eastus --runtime node --runtime-version 16 --functions-version 4 --name funcappdreamdemodev001 --storage-account staidreamdemodev001`
   ```

2. Deploy the code.

```powershell
az functionapp deployment source config-zip -g $resourcegroupname -n $functionappname --src api.zip
```

3. Fix the settings for the app
   
   ```powershell
   az functionapp config appsettings set --SearchApiKey $SearchApiKey --SearchFacets "category1, category2, category3" --SearchIndexName "fabrikam-fashion" --SearchServiceName $SearchServiceName
   
   ```


