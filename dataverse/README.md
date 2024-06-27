# How do I run Microsoft Dataverse samples?

1. Download or clone the sample repo so that you have a local copy.
1. (Optional) Edit the `dataverse/App.config` file to define a connection string that points to your Dataverse instance.
1. Open the sample solution in Visual Studio and press F5 to run the sample.
    - If you've specified a connection string in `dataverse/App.config`, any sample you run uses that connection information.
    - If you haven't specified a connection string in `dataverse/App.config`, a dialog ([XRM tooling common login control](https://learn.microsoft.com/powerapps/developer/common-data-service/xrm-tooling/use-xrm-tooling-common-login-control-client-applications)) opens each time you run the sample. You must enter information about which Dataverse instance you want to connect to and which credentials you want to use.

    This dialog caches previous connections so that you can choose a previously used connection. See the [Known issue](#known-issue) and its workaround for this scenario.

The samples in this repo that require a connection to a Dataverse instance to run includes a linked reference to the `dataverse/App.config` file.

## Known issue

With the recent changes to .NET Framework, an exception is thrown when a sample tries to open the XRM tooling common login control dialog. As a workaround, do one of the following:

- Specify a connection string in `dataverse/App.config` to run the samples.
- Enable **HTTP Activation** on your computer where you are running the samples, and then run the sample without specifying a connection string in `dataverse/App.config`.

  :::image type="content" source="media/http-activation.png" alt-text="Screenshot that shows the TurnWindows features on or off popup. You can check or uncheck the features you want to enable or disable. The feature HTTP Activation is checked and found in the WCF Services folder of .NET Framework 4.8 Advanced Services. ":::

This issue will be resolved in a future update when we distribute the updated assemblies through our [NuGet package](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.WpfControls/).
