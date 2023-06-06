# rating-api

Container exposes port 3000.
Required configuration via environment variables:

- MONGODB_URI:  `<set to mongoDB endpoint>`. The database is called `webratings` so the format would look like `mongodb://[endpoint]:27017/webratings`

Upon startup, the application checks if it can connect to the database. If the database is empty, it populates it with data.

# Contributing



This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.




Download image terraform: quay.io/nmartins/terraform_ee 
name: Terraform EE
Pull: Only pull the image.
