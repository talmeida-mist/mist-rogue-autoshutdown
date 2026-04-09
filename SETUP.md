# Setup Instructions for Mist Rogue Autoshutdown

## Obtaining Mist API Credentials
1. Log in to your Mist dashboard.
2. Navigate to **Settings** > **API**.
3. Generate a new API token if you don't have one already.
4. Copy your API token for later use.

## Finding Organization ID
1. In the Mist dashboard, go to **Organizations**.
2. Select your organization.
3. The Organization ID will be displayed in the URL or in the settings of the organization.

## Configuring Mist Webhook Integration
1. Go to **Settings** > **Webhooks** in the Mist dashboard.
2. Add a new webhook and enter the URL where your webhook listener is located.
3. Choose the appropriate events you want to trigger the webhook.

## Setting up n8n HTTP Header Auth Credential for Mist API Token
1. Open your n8n instance and go to **Credentials**.
2. Create a new HTTP Header Auth credential.
3. In the **API Key** field, paste your Mist API token obtained earlier.
4. Save your credentials.

## Configuring SMTP Email Credentials
1. In your application, navigate to the SMTP email settings section.
2. Input your SMTP server details, including host, port, username, and password.
3. Ensure that you allow access for less secure applications if required by your email provider.

## Editing the Config Node with API Host and ORG-ID
1. Open the configuration node in your codebase.
2. Locate the variables for `API_HOST` and `ORG_ID`.
3. Assign the Mist API base URL to `API_HOST` and your Organization ID to `ORG_ID`.

## Testing the Webhook
1. Set up your webhook listener to log incoming requests.
2. Trigger an event from the Mist dashboard to see if your webhook is invoked correctly.
3. Check the logs and ensure the expected data is received.

## Environment Variables Reference
- `MIST_API_TOKEN`: Your Mist API token.
- `MIST_ORG_ID`: Your Mist Organization ID.
- `SMTP_HOST`: SMTP server host.
- `SMTP_PORT`: SMTP server port.
- `SMTP_USERNAME`: SMTP username.
- `SMTP_PASSWORD`: SMTP password.

Ensure that all environment variables are correctly set in your application before running.

---