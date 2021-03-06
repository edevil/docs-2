
# Google Suite SAML

Steps to create a Google Suite SAML application to use with Fyde Enterprise Console

- The steps were retrieved from this tutorial `https://support.google.com/a/answer/6087519?hl=en`

## Configure SAML

1. Got to SAML Apps `https://admin.google.com/AdminHome?fral=1#AppsList:serviceType=SAML_APPS`

1. Create a new application by selecting the `yellow plus sign` and then `SETUP MY OWN APP`

    ![New Application](imgs/google_saml_new_application.png)

1. Get the custom application SAML configuration:

    - Please take note of the `SSO URL` and the `Entity ID`

    - Click `Download` to get the `Certificate`

    - Select `Next` to continue

    ![SAML Provider](imgs/google_saml_provider.png)

1. Configure custom application

    - Insert the desired `Name` (suggestion: Fyde Enterprise Console)

    - [Optional] Insert description to identify the application if needed

    - [Optional] Use this [image](../../fyde_logo.png) to configure the logo for the application

    - Select `Next` to continue

    ![SAML Configuration](imgs/google_saml_configuration.png)

1. In this menu we are going to use the values obtained from step 2 in [Fyde Enterprise Console](fyde_console_saml.md):

    - Please fill in:

        - `ACS URL` (Assertion Consumer Service URL)

        - `Entity ID`

        - Leave the remaining fields to defaults (as shown)

    - Select `Next` to continue

    ![SAML Details](imgs/google_saml_details.png)

1. Select `Finish` to complete the configuration

1. Select `EDIT SERVICE` to configure permissions

    ![SAML Application Properties](imgs/google_saml_application_properties.png)

1. Select `EDIT SERVICE` to configure permissions

    - We recomend setting `ON for everyone`, otherwise manually configure individual Organizational Units (OUs) allowed to use the application

    ![SAML Enable](imgs/google_saml_enable.png)

1. Use the values obtained to continue the step 3 configuration in [Fyde Enterprise Console](fyde_console_saml.md):

    - `Entity ID`

    - `SSO URL`

    - `Certificate`
